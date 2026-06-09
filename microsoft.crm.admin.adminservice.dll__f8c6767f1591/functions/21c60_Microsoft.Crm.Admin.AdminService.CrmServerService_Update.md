# Microsoft.Crm.Admin.AdminService.CrmServerService::Update

- ea: `0x21c60`
- end: `0x21d1a`
- name: `Microsoft.Crm.Admin.AdminService.CrmServerService::Update`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18790`
- `0x21c60`
- `0x22090`
- `0x220b0`
- `0x22350`

## string_xrefs

- `0x21ccf`: `Update`
- `0x21cd4`: `D:\a\1\s\src\CrmLive\Admin\Server\CrmServerService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x21c60  ldarg.1
0x21c61  ldstr    aServerIdentifi// "Server identifier"
0x21c66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x21c6b  ldarg.2
0x21c6c  ldstr    aServerdata// "ServerData"
0x21c71  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x21c76  ldsfld   string [mscorlib]System.String::Empty
0x21c7b  stloc.0
0x21c7c  ldarg.2
0x21c7d  callvirt instance string Microsoft.Crm.Admin.AdminService.ServerData::get_Version()
0x21c82  ldloca.s 0
0x21c84  call     bool Microsoft.Crm.Admin.AdminService.ServerVersionFormat::TryCanonicalizeServerVersion(string serverVersion, [out] string& canonicalizedServerVersion)
0x21c89  brfalse.s loc_21C92
0x21c8b  ldarg.2
0x21c8c  ldloc.0
0x21c8d  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_Version(string value)
0x21c92  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x21c97  ldc.i4.s 0x14
0x21c99  ldstr    aUpdatingServer// "Updating Server property, Id=({0}))"
0x21c9e  ldc.i4.1
0x21c9f  newarr   [mscorlib]System.Object
0x21ca4  dup
0x21ca5  ldc.i4.0
0x21ca6  ldarg.1
0x21ca7  box      [mscorlib]System.Guid
0x21cac  stelem.ref
0x21cad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21cb2  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x21cb7  stloc.1
0x21cb8  ldloc.1
0x21cb9  ldstr    aServer_1// "Server"
0x21cbe  ldarg.1
0x21cbf  box      [mscorlib]System.Guid
0x21cc4  ldarg.2
0x21cc5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x21cca  ldc.i4   0x460
0x21ccf  ldstr    aUpdate// "Update"
0x21cd4  ldstr    aDA1SSrcCrmlive_43// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x21cd9  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x21cde  pop
0x21cdf  leave.s  loc_21CEB
0x21ce1  ldloc.1
0x21ce2  brfalse.s loc_21CEA
0x21ce4  ldloc.1
0x21ce5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21cea  endfinally
0x21ceb  leave.s  loc_21D19
0x21ced  stloc.2
0x21cee  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x21cf3  ldc.i4.s 0x14
0x21cf5  ldstr    aExceptionInUpd_2// "Exception in updating server Id=({0} : "...
0x21cfa  ldc.i4.2
0x21cfb  newarr   [mscorlib]System.Object
0x21d00  dup
0x21d01  ldc.i4.0
0x21d02  ldarg.1
0x21d03  box      [mscorlib]System.Guid
0x21d08  stelem.ref
0x21d09  dup
0x21d0a  ldc.i4.1
0x21d0b  ldloc.2
0x21d0c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x21d11  stelem.ref
0x21d12  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21d17  rethrow
0x21d19  ret
```
