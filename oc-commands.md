## ```oc``` OpenShift command line client

https://github.com/openshift/origin/tags : Release auswählen -> ```Downloads```: e.g. "openshift-origin-client-tools-v3.6.1-008f2d5-linux-64bit.tar.gz"

```oc --help``` shows an overview of the available commands

```oc <command> -h``` shows a short descripton and usage examples ```oc new-project -h```

- Client settings are located in the  ```.kube``` folder in the home directory

- Multiple Login shells of the same Linux User "share" the same connection (e.g. changing the default project in one shell will effect the other shells as well).

#### Options (available for all commands)
* ```--token=```                  Use a secret token instead of username/password
* ```-n``` or ```--namespace=```  Use the given namespace (project) for the command instead of the active project
    * unless indicated with above settings commands will execute in the scope of the active project

#### Basic Commands:
*  ```login```           Log in to a server
*  ```logout```          End the current server session
*  ```whoami```          Return information about the current session
    * ```-t``` Display the Token (this is as good as your Username/Password Login)
*  ```new-project```     Request a new project
    * usually project and purpose (e.g. stage)
    * must be unique in cluster
*  ```new-app```         Create a new application
    * selects template and source
    * creates stuff like routes too
    * https://blog.openshift.com/getting-started-with-wildfly/
*  ```status```          Show an overview of the current project
*  ```project```         Switch to another project
    * this effects all shells which share the config
*  ```projects```        Display existing projects

#### Build and Deploy Commands:
*  ```deploy```          View, start, cancel, or retry a deployment
*  ```rollout```         Start a new rollout, view its status or history, rollback to a previous revision of your app
*  ```start-build```     Start a new build
     * docker build
     * s2i build (source | binary)
*  ```tag```             Tag existing images into image streams

#### Application Management Commands:
*  ```get```             Display one or many resources
*  ```export```          Export resources so they can be used elsewhere
     * ```-o json```     output format json (defaults to yaml otherwise)
*  ```describe```        Show details of a specific resource or group of resources
*  ```edit```            Edit a resource on the server
*  ```create```          Create a resource by filename or stdin
*  ```delete```          Delete one or more resources
*  ```secrets```         Manage secrets

#### Troubleshooting and Debugging Commands:
*  ```rsh```             Start a shell session in a pod
    * available commands may differ between containers (as they are part of the image)
*  ```logs```            Print the logs for a resource
    * ```-f```           follow (like tail -f)
    * ```-c <containername>```     select a specific container inside pod (if more than one)
*  ```rsync```           Copy files between local filesystem and a pod
*  ```cp```              Copy files and directories to and from containers.
*  ```port-forward```    Forward one or more local ports to a pod
    * Eclipse Debugger (Java Remote Application)
    * Connect to a database inside the platform using a local tool (e.g. SQLDeveloper or Squirrel)
*  ```debug```           Launch a new instance of a pod for debugging

### ```jq``` JSON command line tool for JSON processing
*   syntax highlighting
*   query language
*   supports transformation
*   https://stedolan.github.io/jq/
