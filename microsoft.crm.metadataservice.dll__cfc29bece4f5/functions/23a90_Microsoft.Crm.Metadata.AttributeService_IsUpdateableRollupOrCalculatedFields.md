# Microsoft.Crm.Metadata.AttributeService::IsUpdateableRollupOrCalculatedFields

- ea: `0x23a90`
- end: `0x23ae1`
- name: `Microsoft.Crm.Metadata.AttributeService::IsUpdateableRollupOrCalculatedFields`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x23970`

## callees

- `0x23a90`

## string_xrefs

- `0x23aa0`: `overwritetime`
- `0x23ac2`: `overwritetime`

## pseudocode

```c

```

## disassembly

```asm
0x23a90  ldarg.0
0x23a91  ldstr    aAttributeid// "attributeid"
0x23a96  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x23a9b  brfalse.s loc_23A9F
0x23a9d  ldc.i4.0
0x23a9e  ret
0x23a9f  ldarg.0
0x23aa0  ldstr    aOverwritetime// "overwritetime"
0x23aa5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x23aaa  brfalse.s loc_23AAE
0x23aac  ldc.i4.0
0x23aad  ret
0x23aae  ldarg.0
0x23aaf  ldarg.1
0x23ab0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::GetTopSolutionId(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23ab5  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x23aba  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x23abf  brfalse.s loc_23ADF
0x23ac1  ldarg.0
0x23ac2  ldstr    aOverwritetime// "overwritetime"
0x23ac7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x23acc  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x23ad1  box      [mscorlib]System.DateTime
0x23ad6  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x23adb  brfalse.s loc_23ADF
0x23add  ldc.i4.1
0x23ade  ret
0x23adf  ldc.i4.0
0x23ae0  ret
```
