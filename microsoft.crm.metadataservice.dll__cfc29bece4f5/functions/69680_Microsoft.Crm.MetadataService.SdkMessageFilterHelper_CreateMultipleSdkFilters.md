# Microsoft.Crm.MetadataService.SdkMessageFilterHelper::CreateMultipleSdkFilters

- ea: `0x69680`
- end: `0x69738`
- name: `Microsoft.Crm.MetadataService.SdkMessageFilterHelper::CreateMultipleSdkFilters`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x69510`
- `0x69680`
- `0x69740`

## string_xrefs

- `0x696a0`: `Create`
- `0x696d3`: `Update`
- `0x696e4`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x69680  newobj   instance void Microsoft.Crm.MetadataService.SdkMessageFilterHelper::.ctor()
0x69685  stloc.0
0x69686  ldarg.0
0x69687  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0x6968c  stloc.1
0x6968d  br       loc_69720
0x69692  ldloc.1
0x69693  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0x69698  stloc.2
0x69699  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x6969e  stloc.3
0x6969f  ldloc.3
0x696a0  ldstr    aCreate// "Create"
0x696a5  ldloc.2
0x696a6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AvailableForCreate()
0x696ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x696b0  ldloc.3
0x696b1  ldstr    aRetrieve// "Retrieve"
0x696b6  ldloc.2
0x696b7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AvailableForRetrieve()
0x696bc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x696c1  ldloc.3
0x696c2  ldstr    aRetrievemultip// "RetrieveMultiple"
0x696c7  ldloc.2
0x696c8  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AvailableForRetrieveMultiple()
0x696cd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x696d2  ldloc.3
0x696d3  ldstr    aUpdate// "Update"
0x696d8  ldloc.2
0x696d9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AvailableForUpdate()
0x696de  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x696e3  ldloc.3
0x696e4  ldstr    aDelete// "Delete"
0x696e9  ldloc.2
0x696ea  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AvailableForDelete()
0x696ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x696f4  ldloc.0
0x696f5  ldloc.2
0x696f6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBPFEntity()
0x696fb  ldloc.2
0x696fc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsReplicated()
0x69701  ldloc.2
0x69702  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x69707  ldloc.2
0x69708  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x6970d  ldloc.2
0x6970e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_DataProviderId()
0x69713  ldloc.2
0x69714  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_OwnershipTypeMask()
0x69719  ldarg.1
0x6971a  ldloc.3
0x6971b  callvirt instance void Microsoft.Crm.MetadataService.SdkMessageFilterHelper::CreateSdkFiltersForCustomEntity(bool isBPFEntity, bool isReplicated, int32 objectTypeCode, bool isCustomActivity, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId, int32 ownershipTypeMask, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> sdkFilterRestrictionLevels)
0x69720  ldloc.1
0x69721  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x69726  brtrue   loc_69692
0x6972b  leave.s  loc_69737
0x6972d  ldloc.1
0x6972e  brfalse.s loc_69736
0x69730  ldloc.1
0x69731  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69736  endfinally
0x69737  ret
```
