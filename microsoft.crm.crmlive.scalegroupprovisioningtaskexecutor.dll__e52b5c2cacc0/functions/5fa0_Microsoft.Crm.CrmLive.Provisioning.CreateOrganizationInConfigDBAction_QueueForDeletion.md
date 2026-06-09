# Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::QueueForDeletion

- ea: `0x5fa0`
- end: `0x6067`
- name: `Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::QueueForDeletion`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5ef0`

## callees

- `0x5fa0`

## string_xrefs

- `0x5ff9`: `DeleteOrganization`
- `0x6005`: `CreatedOn`
- `0x6042`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\CreateOrganizationInConfigDbAction.cs`

## pseudocode

```c

```

## disassembly

```asm
0x5fa0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x5fa5  stloc.0
0x5fa6  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmDatacenterService::.ctor()
0x5fab  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.DatacenterData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmDatacenterService::RetrieveMultiple()
0x5fb0  stloc.1
0x5fb1  ldc.i4.0
0x5fb2  stloc.2
0x5fb3  br       loc_6051
0x5fb8  ldloc.1
0x5fb9  ldloc.2
0x5fba  ldelem.ref
0x5fbb  stloc.3
0x5fbc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x5fc1  stloc.s  4
0x5fc3  ldloc.s  4
0x5fc5  ldstr    aId// "Id"
0x5fca  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x5fcf  box      [mscorlib]System.Guid
0x5fd4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5fd9  ldloc.s  4
0x5fdb  ldstr    aData// "Data"
0x5fe0  ldarga.s 0
0x5fe2  constrained. [mscorlib]System.Guid
0x5fe8  callvirt instance string [mscorlib]System.Object::ToString()
0x5fed  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5ff2  ldloc.s  4
0x5ff4  ldstr    aOperationtype// "OperationType"
0x5ff9  ldstr    aDeleteorganiza// "DeleteOrganization"
0x5ffe  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6003  ldloc.s  4
0x6005  ldstr    aCreatedon// "CreatedOn"
0x600a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x600f  box      [mscorlib]System.DateTime
0x6014  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6019  ldloc.s  4
0x601b  ldstr    aDatacenterid// "DataCenterId"
0x6020  ldloc.3
0x6021  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.DatacenterData::get_Id()
0x6026  box      [mscorlib]System.Guid
0x602b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6030  ldloc.0
0x6031  ldstr    aGeoqueue// "GeoQueue"
0x6036  ldloc.s  4
0x6038  ldc.i4   0xD3
0x603d  ldstr    aQueuefordeleti// "QueueForDeletion"
0x6042  ldstr    aDDbsShDccm2110_4// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x6047  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x604c  pop
0x604d  ldloc.2
0x604e  ldc.i4.1
0x604f  add
0x6050  stloc.2
0x6051  ldloc.2
0x6052  ldloc.1
0x6053  ldlen
0x6054  conv.i4
0x6055  blt      loc_5FB8
0x605a  leave.s  loc_6066
0x605c  ldloc.0
0x605d  brfalse.s loc_6065
0x605f  ldloc.0
0x6060  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6065  endfinally
0x6066  ret
```
