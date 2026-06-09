# Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::Update

- ea: `0x12550`
- end: `0x125a2`
- name: `Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::Update`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x12060`
- `0x12230`
- `0x12550`

## string_xrefs

- `0x12585`: `Update`
- `0x12551`: `serviceComponentSku`
- `0x12574`: `ServiceComponentSku`
- `0x1258a`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceComponentSkuService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x12550  ldarg.1
0x12551  ldstr    aServicecompone_3// "serviceComponentSku"
0x12556  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1255b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x12560  stloc.0
0x12561  ldarg.1
0x12562  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.ServiceComponentSku::ToPropertyBag()
0x12567  stloc.1
0x12568  ldloc.1
0x12569  ldstr    aName// "Name"
0x1256e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Remove(string)
0x12573  ldloc.0
0x12574  ldstr    aServicecompone_4// "ServiceComponentSku"
0x12579  ldarg.1
0x1257a  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceComponentSku::get_Description()
0x1257f  ldloc.1
0x12580  ldc.i4   0xDB
0x12585  ldstr    aUpdate// "Update"
0x1258a  ldstr    aDA1SSrcCrmlive_24// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x1258f  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x12594  pop
0x12595  leave.s  loc_125A1
0x12597  ldloc.0
0x12598  brfalse.s loc_125A0
0x1259a  ldloc.0
0x1259b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x125a0  endfinally
0x125a1  ret
```
