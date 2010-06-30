## example usage i.e. 'documenation'

### Specifying servers on the command line with "--server"

    run "uptime; df -h; echo" on each of three servers set on the command line with the '--server' option:

    stu@sente ~/scratch $ runremote --cmd "uptime; df -h; echo" --server remy --server ffc --server twg
     15:48:45 up 245 days, 17:38,  1 user,  load average: 0.12, 0.11, 0.04
    Filesystem            Size  Used Avail Use% Mounted on
    tmpfs                  12G     0   12G   0% /lib/init/rw
    tmpfs                  12G     0   12G   0% /dev/shm
    simfs                 1.1T  781G  317G  72% /

     15:49:35 up 256 days, 27 min,  0 users,  load average: 0.11, 0.11, 0.04
    Filesystem            Size  Used Avail Use% Mounted on
    tmpfs                  12G     0   12G   0% /lib/init/rw
    tmpfs                  12G     0   12G   0% /dev/shm
    simfs                 1.6T  1.1T  468G  71% /

     15:48:45 up 171 days, 19:13,  1 user,  load average: 0.28, 0.29, 0.12
    Filesystem            Size  Used Avail Use% Mounted on
    tmpfs                  12G     0   12G   0% /lib/init/rw
    tmpfs                  12G     0   12G   0% /dev/shm
    simfs                 1.1T  879G  220G  81% /


### Example 2

    ./runremote --cmd "df -hl" --list data/tdlinx.txt --thread --bg --header | ansi2html.sh --bg=dark > df-report.html

    # the previous command will execute "df -hl" on each of the servers listed in
    # the data/tdlinx file.

    # the '--bg' flag will cause the commands to be executed in parallel, opposed
    # to waiting for server1 to finish before running the command on server2 the

    # '--header' flag adds a header row before printing the command's (buffered)
    # output, this is simply to partition the output so for easier reading.

    # ansi2html.sh creates a pretty html file from shell output - colors and all :)

    # http://www.sente.cc/misc/df-report.html
