# Microsoft.Crm.Metadata.ActivityEntityService::MarkAttributesValidForUpdate

- ea: `0x28720`
- end: `0x28809`
- name: `Microsoft.Crm.Metadata.ActivityEntityService::MarkAttributesValidForUpdate`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x284e0`

## callees

- `0x28720`
- `0x45150`

## string_xrefs

- `0x287a9`: `validforupdateapi`
- `0x287e6`: `validforupdateapi`
- `0x287f8`: `validforupdateapi`

## pseudocode

```c

```

## disassembly

```asm
0x28720  ldarg.1
0x28721  brfalse.s loc_28726
0x28723  ldarg.2
0x28724  brtrue.s loc_28727
0x28726  ret
0x28727  ldarg.1
0x28728  callvirt instance bool Microsoft.Crm.Metadata.IEntityInfo::get_IsCustomActivity()
0x2872d  ldarg.3
0x2872e  or
0x2872f  brfalse  loc_28808
0x28734  ldarg.2
0x28735  ldstr    aLogicalname// "logicalname"
0x2873a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2873f  castclass [mscorlib]System.String
0x28744  stloc.0
0x28745  ldloc.0
0x28746  ldstr    aStatecode_1// "statecode"
0x2874b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28750  brtrue.s loc_2877D
0x28752  ldloc.0
0x28753  ldstr    aStatuscode// "statuscode"
0x28758  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2875d  brtrue.s loc_287BA
0x2875f  ldloc.0
0x28760  ldstr    aOwnerid// "ownerid"
0x28765  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2876a  brtrue   loc_287F7
0x2876f  ldloc.0
0x28770  ldstr    aOwneridtype_0// "owneridtype"
0x28775  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2877a  brtrue.s loc_287F7
0x2877c  ret
0x2877d  ldarg.2
0x2877e  ldstr    aAttributetypei// "attributetypeid"
0x28783  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x28788  unbox.any [mscorlib]System.Guid
0x2878d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x28792  ldstr    aState// "state"
0x28797  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x2879c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x287a1  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x287a6  brfalse.s loc_28808
0x287a8  ldarg.2
0x287a9  ldstr    aValidforupdate// "validforupdateapi"
0x287ae  ldc.i4.1
0x287af  box      [mscorlib]System.Boolean
0x287b4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x287b9  ret
0x287ba  ldarg.2
0x287bb  ldstr    aAttributetypei// "attributetypeid"
0x287c0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x287c5  unbox.any [mscorlib]System.Guid
0x287ca  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x287cf  ldstr    aStatus// "status"
0x287d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x287d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x287de  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x287e3  brfalse.s loc_28808
0x287e5  ldarg.2
0x287e6  ldstr    aValidforupdate// "validforupdateapi"
0x287eb  ldc.i4.1
0x287ec  box      [mscorlib]System.Boolean
0x287f1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x287f6  ret
0x287f7  ldarg.2
0x287f8  ldstr    aValidforupdate// "validforupdateapi"
0x287fd  ldc.i4.1
0x287fe  box      [mscorlib]System.Boolean
0x28803  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x28808  ret
```
