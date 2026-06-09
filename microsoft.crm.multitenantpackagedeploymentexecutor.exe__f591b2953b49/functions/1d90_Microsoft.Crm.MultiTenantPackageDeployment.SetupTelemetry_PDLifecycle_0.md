# Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::PDLifecycle_0

- ea: `0x1d90`
- end: `0x1ddf`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::PDLifecycle_0`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x870`

## callees

- `0x1d90`

## pseudocode

```c

```

## disassembly

```asm
0x1d90  ldnull
0x1d91  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d96  ldc.i4.s 0x14
0x1d98  ldc.i4   0x3E7
0x1d9d  ldstr    aNotAnErrorPdli_0// "NOT AN ERROR PDLifecycle: {0}, cmdline:"...
0x1da2  ldc.i4.6
0x1da3  newarr   [mscorlib]System.Object
0x1da8  dup
0x1da9  ldc.i4.0
0x1daa  ldsfld   string Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::applicationVersion
0x1daf  stelem.ref
0x1db0  dup
0x1db1  ldc.i4.1
0x1db2  ldarg.0
0x1db3  stelem.ref
0x1db4  dup
0x1db5  ldc.i4.2
0x1db6  ldarg.1
0x1db7  stelem.ref
0x1db8  dup
0x1db9  ldc.i4.3
0x1dba  ldarg.2
0x1dbb  stelem.ref
0x1dbc  dup
0x1dbd  ldc.i4.4
0x1dbe  ldsfld   class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string> Microsoft.Crm.MultiTenantPackageDeployment.PdJobController::jobManager
0x1dc3  dup
0x1dc4  brtrue.s loc_1DCA
0x1dc6  pop
0x1dc7  ldc.i4.0
0x1dc8  br.s     loc_1DCF
0x1dca  call     instance int32 class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string>::get_ActiveJobCount()
0x1dcf  box      [mscorlib]System.Int32
0x1dd4  stelem.ref
0x1dd5  dup
0x1dd6  ldc.i4.5
0x1dd7  ldarg.3
0x1dd8  stelem.ref
0x1dd9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x1dde  ret
```
