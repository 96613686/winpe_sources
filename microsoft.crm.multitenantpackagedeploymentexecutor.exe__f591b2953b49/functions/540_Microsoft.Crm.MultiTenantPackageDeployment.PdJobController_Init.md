# Microsoft.Crm.MultiTenantPackageDeployment.PdJobController::Init

- ea: `0x540`
- end: `0x562`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PdJobController::Init`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x650`

## pseudocode

```c

```

## disassembly

```asm
0x540  ldnull
0x541  ldftn    void Microsoft.Crm.MultiTenantPackageDeployment.PdExecutor::Process(class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs input, class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<string> output, valuetype [mscorlib]System.Threading.CancellationToken ct)
0x547  newobj   instance void class [mscorlib]System.Action`3<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<string>, valuetype [mscorlib]System.Threading.CancellationToken>::.ctor(object, native int)
0x54c  newobj   instance void class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string>::.ctor(class [mscorlib]System.Action`3<var<u1>, !!T0, class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>>>)
0x551  stsfld   class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string> Microsoft.Crm.MultiTenantPackageDeployment.PdJobController::jobManager
0x556  ldsfld   class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string> Microsoft.Crm.MultiTenantPackageDeployment.PdJobController::jobManager
0x55b  ldarg.0
0x55c  call     void [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.JobManagerExtensions::ConnectIdleTimer(class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.Model.IJobManager, class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper)
0x561  ret
```
