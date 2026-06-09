# Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::Call

- ea: `0x18310`
- end: `0x183ef`
- name: `Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::Call`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x64f0`

## callees

- `0x2c50`
- `0x2c80`
- `0x7100`
- `0x7110`
- `0x7140`
- `0x18310`
- `0x183f0`
- `0x18c00`
- `0x18c20`
- `0x18c30`

## string_xrefs

- `0x18364`: `MultiTenantPD_JobHostException on attempt {0}`
- `0x183b8`: `PD API Host failed to complete package deployment after retrying for {0} times. Arguments: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x18310  ldstr    aPdjobretrycoun// "PdJobRetryCount"
0x18315  ldc.i4.3
0x18316  box      [mscorlib]System.Int32
0x1831b  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x18320  unbox.any [mscorlib]System.Int32
0x18325  stloc.0
0x18326  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs::.ctor()
0x1832b  dup
0x1832c  ldarg.2
0x1832d  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs::set_Arguments(string[] value)
0x18332  dup
0x18333  call     string [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::CaptureRoot()
0x18338  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs::set_RootContextJson(string value)
0x1833d  stloc.1
0x1833e  ldc.i4.0
0x1833f  stloc.3
0x18340  br.s     loc_183B4
0x18342  nop
0x18343  ldarg.0
0x18344  ldarg.1
0x18345  ldloc.1
0x18346  call     class Microsoft.Crm.Tools.Admin.PackageDeployerResult Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::CallOnce(valuetype [mscorlib]System.Guid orgId, string packageName, class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs pdeArgs)
0x1834b  stloc.s  4
0x1834d  leave.s  loc_18395
0x1834f  stloc.s  5
0x18351  ldarg.0
0x18352  ldarg.1
0x18353  ldloc.s  5
0x18355  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::PDFallback(valuetype [mscorlib]System.Guid organizationId, string packageName, class [mscorlib]System.Exception ex)
0x1835a  ldc.i4.0
0x1835b  ldc.i4.1
0x1835c  ldc.i4.2
0x1835d  newarr   [mscorlib]System.String
0x18362  dup
0x18363  ldc.i4.0
0x18364  ldstr    aMultitenantpdJ// "MultiTenantPD_JobHostException on attem"...
0x18369  ldloc.3
0x1836a  box      [mscorlib]System.Int32
0x1836f  call     string [mscorlib]System.String::Format(string, object)
0x18374  stelem.ref
0x18375  dup
0x18376  ldc.i4.1
0x18377  ldloc.s  5
0x18379  callvirt instance string [mscorlib]System.Object::ToString()
0x1837e  stelem.ref
0x1837f  newobj   instance void Microsoft.Crm.Tools.Admin.PackageDeployerResult::.ctor(bool isSuccess, bool isCriticalServerFailure, class [mscorlib]System.Collections.Generic.IList`1<string> pdInfoLog)
0x18384  dup
0x18385  ldloc.s  5
0x18387  callvirt instance string [mscorlib]System.Object::ToString()
0x1838c  callvirt instance void Microsoft.Crm.Tools.Admin.PackageDeployerResult::set_Error(string value)
0x18391  stloc.s  6
0x18393  leave.s  loc_183EC
0x18395  ldloc.s  4
0x18397  brfalse.s loc_1839C
0x18399  ldloc.s  4
0x1839b  ret
0x1839c  ldloc.3
0x1839d  ldc.i4.1
0x1839e  add
0x1839f  ldarg.0
0x183a0  ldarg.1
0x183a1  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::PDRetry(int32 attempt, valuetype [mscorlib]System.Guid orgId, string packageName)
0x183a6  ldc.i4   0xBB8
0x183ab  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x183b0  ldloc.3
0x183b1  ldc.i4.1
0x183b2  add
0x183b3  stloc.3
0x183b4  ldloc.3
0x183b5  ldloc.0
0x183b6  blt.s    loc_18342
0x183b8  ldstr    aPdApiHostFaile// "PD API Host failed to complete package "...
0x183bd  ldloc.0
0x183be  box      [mscorlib]System.Int32
0x183c3  ldstr    asc_20254// " "
0x183c8  ldarg.2
0x183c9  call     string [mscorlib]System.String::Join(string, string[])
0x183ce  call     string [mscorlib]System.String::Format(string, object, object)
0x183d3  stloc.2
0x183d4  ldc.i4.0
0x183d5  ldc.i4.1
0x183d6  newarr   [mscorlib]System.String
0x183db  dup
0x183dc  ldc.i4.0
0x183dd  ldloc.2
0x183de  stelem.ref
0x183df  newobj   instance void Microsoft.Crm.Tools.Admin.PackageDeployerResult::.ctor(bool isSuccess, class [mscorlib]System.Collections.Generic.IList`1<string> pdInfoLog)
0x183e4  dup
0x183e5  ldloc.2
0x183e6  callvirt instance void Microsoft.Crm.Tools.Admin.PackageDeployerResult::set_Error(string value)
0x183eb  ret
0x183ec  ldloc.s  6
0x183ee  ret
```
