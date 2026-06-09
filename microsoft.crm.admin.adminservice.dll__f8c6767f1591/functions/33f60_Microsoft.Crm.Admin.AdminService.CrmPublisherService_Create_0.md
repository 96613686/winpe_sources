# Microsoft.Crm.Admin.AdminService.CrmPublisherService::Create_0

- ea: `0x33f60`
- end: `0x340a7`
- name: `Microsoft.Crm.Admin.AdminService.CrmPublisherService::Create_0`
- size: `327`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x33f50`
- `0x340b0`
- `0x340d0`

## callees

- `0x18790`
- `0x33f60`
- `0x347d0`
- `0x347f0`
- `0x34810`
- `0x34850`
- `0x34890`
- `0x348d0`

## string_xrefs

- `0x34030`: `Create`
- `0x33f72`: `Creating Publisher, PublicKeyToken=({0}), FQN=({1})`
- `0x33fde`: `Invalid PluginTrustLevel: `
- `0x34023`: `PluginPublishers`
- `0x34035`: `D:\a\1\s\src\CrmLive\Admin\Publisher\CrmPublisherService.cs`
- `0x34053`: `Created Publisher, Id=({0})`
- `0x3407f`: `Exception creating Publisher, PublicKeyToken=({0} :{1} :{2})`

## pseudocode

```c

```

## disassembly

```asm
0x33f60  ldarg.1
0x33f61  ldstr    aId_0// "id"
0x33f66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x33f6b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x33f70  ldc.i4.s 0x14
0x33f72  ldstr    aCreatingPublis// "Creating Publisher, PublicKeyToken=({0}"...
0x33f77  ldc.i4.2
0x33f78  newarr   [mscorlib]System.Object
0x33f7d  dup
0x33f7e  ldc.i4.0
0x33f7f  ldarg.2
0x33f80  stelem.ref
0x33f81  dup
0x33f82  ldc.i4.1
0x33f83  ldarg.s  4
0x33f85  stelem.ref
0x33f86  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x33f8b  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x33f90  stloc.2
0x33f91  ldloca.s 2
0x33f93  constrained. [mscorlib]System.Guid
0x33f99  callvirt instance string [mscorlib]System.Object::ToString()
0x33f9e  ldc.i4.0
0x33f9f  ldc.i4.s 0x20
0x33fa1  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x33fa6  stloc.0
0x33fa7  ldc.i4.1
0x33fa8  ldarg.3
0x33fa9  bne.un.s loc_33FBC
0x33fab  ldarg.s  4
0x33fad  ldstr    aFullyqualified// "fullyQualifiedName"
0x33fb2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x33fb7  ldloc.0
0x33fb8  starg.s  2
0x33fba  br.s     loc_33FF9
0x33fbc  ldc.i4.2
0x33fbd  ldarg.3
0x33fbe  bne.un.s loc_33FDE
0x33fc0  ldarg.2
0x33fc1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33fc6  brtrue.s loc_33FCD
0x33fc8  ldloc.0
0x33fc9  starg.s  4
0x33fcb  br.s     loc_33FF9
0x33fcd  ldarg.s  4
0x33fcf  ldstr    aFullyqualified// "fullyQualifiedName"
0x33fd4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x33fd9  ldloc.0
0x33fda  starg.s  2
0x33fdc  br.s     loc_33FF9
0x33fde  ldstr    aInvalidPlugint// "Invalid PluginTrustLevel: "
0x33fe3  ldarg.3
0x33fe4  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.PluginTrustLevel
0x33fe9  call     string [mscorlib]System.String::Concat(object, object)
0x33fee  ldc.i4   0x80040216
0x33ff3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x33ff8  throw
0x33ff9  newobj   instance void Microsoft.Crm.Admin.AdminService.PublisherData::.ctor()
0x33ffe  stloc.1
0x33fff  ldloc.1
0x34000  ldarg.1
0x34001  callvirt instance void Microsoft.Crm.Admin.AdminService.PublisherData::set_Id(valuetype [mscorlib]System.Guid value)
0x34006  ldloc.1
0x34007  ldarg.2
0x34008  callvirt instance void Microsoft.Crm.Admin.AdminService.PublisherData::set_PublicKeyToken(string value)
0x3400d  ldloc.1
0x3400e  ldarg.3
0x3400f  callvirt instance void Microsoft.Crm.Admin.AdminService.PublisherData::set_TrustLevel(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.PluginTrustLevel value)
0x34014  ldloc.1
0x34015  ldarg.s  4
0x34017  callvirt instance void Microsoft.Crm.Admin.AdminService.PublisherData::set_FullyQualifiedName(string value)
0x3401c  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x34021  stloc.3
0x34022  ldloc.3
0x34023  ldstr    aPluginpublishe// "PluginPublishers"
0x34028  ldloc.1
0x34029  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x3402e  ldc.i4.s 0x58
0x34030  ldstr    aCreate// "Create"
0x34035  ldstr    aDA1SSrcCrmlive_60// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Publi"...
0x3403a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x3403f  pop
0x34040  leave.s  loc_3404C
0x34042  ldloc.3
0x34043  brfalse.s loc_3404B
0x34045  ldloc.3
0x34046  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3404b  endfinally
0x3404c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x34051  ldc.i4.s 0x14
0x34053  ldstr    aCreatedPublish// "Created Publisher, Id=({0})"
0x34058  ldc.i4.1
0x34059  newarr   [mscorlib]System.Object
0x3405e  dup
0x3405f  ldc.i4.0
0x34060  ldloc.1
0x34061  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.PublisherData::get_Id()
0x34066  box      [mscorlib]System.Guid
0x3406b  stelem.ref
0x3406c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x34071  ldloc.1
0x34072  stloc.s  4
0x34074  leave.s  loc_340A4
0x34076  stloc.s  5
0x34078  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3407d  ldc.i4.s 0x14
0x3407f  ldstr    aExceptionCreat_9// "Exception creating Publisher, PublicKey"...
0x34084  ldc.i4.3
0x34085  newarr   [mscorlib]System.Object
0x3408a  dup
0x3408b  ldc.i4.0
0x3408c  ldarg.2
0x3408d  stelem.ref
0x3408e  dup
0x3408f  ldc.i4.1
0x34090  ldarg.s  4
0x34092  stelem.ref
0x34093  dup
0x34094  ldc.i4.2
0x34095  ldloc.s  5
0x34097  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3409c  stelem.ref
0x3409d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x340a2  rethrow
0x340a4  ldloc.s  4
0x340a6  ret
```
