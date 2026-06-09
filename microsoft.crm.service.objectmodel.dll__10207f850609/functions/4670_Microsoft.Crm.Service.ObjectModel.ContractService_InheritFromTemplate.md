# Microsoft.Crm.Service.ObjectModel.ContractService::InheritFromTemplate

- ea: `0x4670`
- end: `0x46db`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::InheritFromTemplate`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4670`

## string_xrefs

- `0x46b8`: `contractservicelevelcode`

## pseudocode

```c

```

## disassembly

```asm
0x4670  ldarg.1
0x4671  ldarg.2
0x4672  ldstr    aAllotmenttypec// "allotmenttypecode"
0x4677  call     void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.OMUtil::InheritFromTemplate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, string)
0x467c  ldarg.1
0x467d  ldstr    aAllotmenttypec// "allotmenttypecode"
0x4682  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x4687  unbox.any [mscorlib]System.Int32
0x468c  stloc.0
0x468d  ldloc.0
0x468e  ldc.i4.1
0x468f  beq.s    loc_46AA
0x4691  ldloc.0
0x4692  ldc.i4.3
0x4693  beq.s    loc_46AA
0x4695  ldloc.0
0x4696  ldc.i4.2
0x4697  beq.s    loc_46AA
0x4699  ldc.i4   0x80043205
0x469e  ldc.i4.0
0x469f  newarr   [mscorlib]System.Object
0x46a4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x46a9  throw
0x46aa  ldarg.1
0x46ab  ldarg.2
0x46ac  ldstr    aUsediscountasp// "usediscountaspercentage"
0x46b1  call     void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.OMUtil::InheritFromTemplate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, string)
0x46b6  ldarg.1
0x46b7  ldarg.2
0x46b8  ldstr    aContractservic// "contractservicelevelcode"
0x46bd  call     void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.OMUtil::InheritFromTemplate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, string)
0x46c2  ldarg.1
0x46c3  ldarg.2
0x46c4  ldstr    aBillingfrequen// "billingfrequencycode"
0x46c9  call     void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.OMUtil::InheritFromTemplate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, string)
0x46ce  ldarg.1
0x46cf  ldarg.2
0x46d0  ldstr    aEffectivitycal// "effectivitycalendar"
0x46d5  call     void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.OMUtil::InheritFromTemplate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, string)
0x46da  ret
```
