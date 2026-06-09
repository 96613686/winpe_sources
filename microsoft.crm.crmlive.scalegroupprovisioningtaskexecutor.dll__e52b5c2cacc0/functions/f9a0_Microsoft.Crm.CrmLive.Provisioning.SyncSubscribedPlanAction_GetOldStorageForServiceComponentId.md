# Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::GetOldStorageForServiceComponentId

- ea: `0xf9a0`
- end: `0xfa43`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::GetOldStorageForServiceComponentId`
- size: `163`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xf950`
- `0xf970`
- `0xf990`

## callees

- `0xf9a0`

## string_xrefs

- `0xf9ad`: `ServiceComponentId`
- `0xf9f9`: `GetOldStorageForServiceComponentId`
- `0xf9fe`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\SyncSubscribedPlanAction.cs`

## pseudocode

```c

```

## disassembly

```asm
0xf9a0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xf9a5  stloc.0
0xf9a6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xf9ab  stloc.1
0xf9ac  ldloc.1
0xf9ad  ldstr    aServicecompone_0// "ServiceComponentId"
0xf9b2  ldarg.1
0xf9b3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xf9b8  ldloc.1
0xf9b9  ldstr    aOrganizationid_0// "OrganizationId"
0xf9be  ldarg.0
0xf9bf  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xf9c4  box      [mscorlib]System.Guid
0xf9c9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xf9ce  ldloc.0
0xf9cf  ldstr    aOrganizationre_1// "OrganizationResources"
0xf9d4  ldc.i4.2
0xf9d5  newarr   [mscorlib]System.String
0xf9da  dup
0xf9db  ldc.i4.0
0xf9dc  ldstr    aId// "Id"
0xf9e1  stelem.ref
0xf9e2  dup
0xf9e3  ldc.i4.1
0xf9e4  ldstr    aCount// "Count"
0xf9e9  stelem.ref
0xf9ea  ldc.i4.1
0xf9eb  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xf9f0  dup
0xf9f1  ldc.i4.0
0xf9f2  ldloc.1
0xf9f3  stelem.ref
0xf9f4  ldc.i4   0xF3
0xf9f9  ldstr    aGetoldstoragef// "GetOldStorageForServiceComponentId"
0xf9fe  ldstr    aDDbsShDccm2110_20// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xfa03  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xfa08  stloc.2
0xfa09  ldloc.2
0xfa0a  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0xfa0f  brtrue.s loc_FA32
0xfa11  ldloc.2
0xfa12  call     T0x2B000032
0xfa17  stloc.3
0xfa18  ldloca.s 3
0xfa1a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0xfa1f  ldstr    aCount// "Count"
0xfa24  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xfa29  unbox.any [mscorlib]System.Int32
0xfa2e  stloc.s  4
0xfa30  leave.s  loc_FA40
0xfa32  leave.s  loc_FA3E
0xfa34  ldloc.0
0xfa35  brfalse.s loc_FA3D
0xfa37  ldloc.0
0xfa38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfa3d  endfinally
0xfa3e  ldc.i4.0
0xfa3f  ret
0xfa40  ldloc.s  4
0xfa42  ret
```
