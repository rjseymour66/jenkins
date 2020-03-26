# Master/Slave Mode

As the role Jenkins plays in an organization expands, Jenkins emplys a distributed build solution to help offload some of the work and to position Jenkins as a scalable, cross-platfrom solution.

**Master** - base installation of Jenkins. Performs basic operations and serves as the UI.
**Slave node** - does the work assigned by the master. A device connected to a master with a TCP connection, configured to act as an automation executor on behalf of the master. Any device that can run the Java Runtime Environment (JRE)

This model allows the master to remain responsive to users while offloading automation execution to any connected slaves. Work is offloaded to slaves only when specified, and the master continues to own tasks that are designated soley to the master, such as less resource-intensive work.

**Master specific tasks**
- SCM polling (SVN, GIT, Perforce, ...)
- Job scheduling
- LDAP authentication (Lightweight Directory Access Protocol)
- Build output, reporting, and notifications
- Job history and build logs
- Executing jobs/tasks tied to the master

## Jenkins > Nodes > New Node screen

| Field name    | Example      | Description   |
|:--------------|:-------------|---------------|
| Name          | My Test Slave node    | Name for the slave node |
| Description   | Executes on behalf of our master as an additional worker | Attaches a longer description to the node  |
| # executors   | 5 | Defines how many parallel jobs can run at one time on the node | 
| Remote root directory | C:\Jenkins\   | Deines where the slave node, its workspace, and files live on the remote system |
| Labels | Windows Build    | Label or group that the slave belongs to. Can have multiple slaves in a lable to load balance |
| Usage | Utilize this slave node as much as possible  | Controls how Jenkins utilizes this node |
| Launch method | Launch slave agents via Java Web Start    | The installation and connection method used to manage the slave node |
| Availability  | Keep this slave node online as much as possible | Describes when to enable or disable this slave node (on a schedule, on demand, or always on) |
