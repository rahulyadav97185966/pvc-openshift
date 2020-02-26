# pvc-openshift

1) git clone https://github.com/rahulyadav97185966/pvc-openshift OR create PV , PVC AND POD definition
2) for PVC you need nfs following commands are usefull :-
  3)yum install nfs-kernel-server
  4)mkdir /mydata
  5)chown nfsnobody:nfsnobody /mydata
  6)chmod 777 /mydata/
  7)vi /etc/exports : In this paste below code
        :- /mydata *(rw,sync,no_root_squash)
  8)exportfs -r
  9)mkdir /sagar
  10)systemctl restart nfs-utils
  11)systemctl restart nfs-server
  12)ip a | less
  13)mount -t nfs 172.17.0.82:/mydata /sagar
  14)df -h
  15)umount /sagar
  16)Now Create PV, PVC and POD
  17)vi pv.yml  : Copy the code given in pv.yml change only ip and directory name
  18)oc create -f pv.yml
  19)vi pvc.yml
  20)oc create -f pvc.yml
  21)oc get pvc
  22)oc get pv : check a pvc is bounded or not
  23)vi pod-sql.yml
  24)oc create -f pod-sql.yml
  25)oc get pods -w
  26) oc get pods
  27)oc exec -it wordpress-mysql-75bdb7f786-4jclm bash
  
  
  
      Codebunk Link : https://codebunk.com/b/2831100067550/
