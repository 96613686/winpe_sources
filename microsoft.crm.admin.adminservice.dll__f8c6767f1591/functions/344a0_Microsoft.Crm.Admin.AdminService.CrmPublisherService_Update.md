# Microsoft.Crm.Admin.AdminService.CrmPublisherService::Update

- ea: `0x344a0`
- end: `0x3459d`
- name: `Microsoft.Crm.Admin.AdminService.CrmPublisherService::Update`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18790`
- `0x344a0`
- `0x347f0`

## string_xrefs

- `0x34532`: `Update`
- `0x3451c`: `PluginPublishers`
- `0x34537`: `D:\a\1\s\src\CrmLive\Admin\Publisher\CrmPublisherService.cs`
- `0x344ec`: `Update Publisher, Id=({0})`
- `0x34549`: `Update Publisher, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x344a0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x344a5  stloc.0
0x344a6  ldarg.1
0x344a7  ldstr    aPublisherdata// "publisherData"
0x344ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x344b1  ldarg.1
0x344b2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x344b7  ldstr    aId// "Id"
0x344bc  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x344c1  brtrue.s loc_344D3
0x344c3  ldstr    aPublisherdataI// "publisherData.Id"
0x344c8  ldstr    aPublisherIdent// "Publisher identifier must be set"
0x344cd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string, string)
0x344d2  throw
0x344d3  ldarg.1
0x344d4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.PublisherData::get_Id()
0x344d9  stloc.0
0x344da  ldloc.0
0x344db  ldstr    aPublisherid// "publisherId"
0x344e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x344e5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x344ea  ldc.i4.s 0x14
0x344ec  ldstr    aUpdatePublishe// "Update Publisher, Id=({0})"
0x344f1  ldc.i4.1
0x344f2  newarr   [mscorlib]System.Object
0x344f7  dup
0x344f8  ldc.i4.0
0x344f9  ldloc.0
0x344fa  box      [mscorlib]System.Guid
0x344ff  stelem.ref
0x34500  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x34505  ldarg.1
0x34506  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x3450b  ldstr    aId// "Id"
0x34510  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Remove(string)
0x34515  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x3451a  stloc.1
0x3451b  ldloc.1
0x3451c  ldstr    aPluginpublishe// "PluginPublishers"
0x34521  ldloc.0
0x34522  box      [mscorlib]System.Guid
0x34527  ldarg.1
0x34528  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x3452d  ldc.i4   0x11D
0x34532  ldstr    aUpdate// "Update"
0x34537  ldstr    aDA1SSrcCrmlive_60// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Publi"...
0x3453c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x34541  pop
0x34542  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x34547  ldc.i4.s 0x14
0x34549  ldstr    aUpdatePublishe// "Update Publisher, Id=({0})"
0x3454e  ldc.i4.1
0x3454f  newarr   [mscorlib]System.Object
0x34554  dup
0x34555  ldc.i4.0
0x34556  ldloc.0
0x34557  box      [mscorlib]System.Guid
0x3455c  stelem.ref
0x3455d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x34562  leave.s  loc_3456E
0x34564  ldloc.1
0x34565  brfalse.s loc_3456D
0x34567  ldloc.1
0x34568  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3456d  endfinally
0x3456e  leave.s  loc_3459C
0x34570  stloc.2
0x34571  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x34576  ldc.i4.s 0x14
0x34578  ldstr    aExceptionUpdat_3// "Exception updating Publisher, Id=({0} :"...
0x3457d  ldc.i4.2
0x3457e  newarr   [mscorlib]System.Object
0x34583  dup
0x34584  ldc.i4.0
0x34585  ldloc.0
0x34586  box      [mscorlib]System.Guid
0x3458b  stelem.ref
0x3458c  dup
0x3458d  ldc.i4.1
0x3458e  ldloc.2
0x3458f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x34594  stelem.ref
0x34595  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3459a  rethrow
0x3459c  ret
```
