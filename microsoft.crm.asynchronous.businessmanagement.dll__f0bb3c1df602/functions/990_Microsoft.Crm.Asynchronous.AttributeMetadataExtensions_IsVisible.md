# Microsoft.Crm.Asynchronous.AttributeMetadataExtensions::IsVisible

- ea: `0x990`
- end: `0xa97`
- name: `Microsoft.Crm.Asynchronous.AttributeMetadataExtensions::IsVisible`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1dd0`

## callees

- `0x990`

## pseudocode

```c

```

## disassembly

```asm
0x990  ldarg.0
0x991  brfalse.s loc_9A3
0x993  ldarg.0
0x994  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x999  brfalse.s loc_9A3
0x99b  ldarg.0
0x99c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x9a1  brtrue.s loc_9A5
0x9a3  ldc.i4.0
0x9a4  ret
0x9a5  ldarg.0
0x9a6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsLogical()
0x9ab  stloc.0
0x9ac  ldc.i4.1
0x9ad  stloc.1
0x9ae  ldloca.s 0
0x9b0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x9b5  ldloc.1
0x9b6  beq.s    loc_9BB
0x9b8  ldc.i4.0
0x9b9  br.s     loc_9C2
0x9bb  ldloca.s 0
0x9bd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x9c2  brfalse.s loc_9EA
0x9c4  ldsfld   class [mscorlib]System.Collections.Generic.ICollection`1<string> Microsoft.Crm.Asynchronous.AttributeMetadataExtensions::VisibleAddressAttributes
0x9c9  ldarg.0
0x9ca  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x9cf  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x9d4  brtrue.s loc_9EA
0x9d6  ldarg.0
0x9d7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_AttributeTypeName()
0x9dc  ldsfld   class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName::ImageType
0x9e1  call     bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName::op_Inequality(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName)
0x9e6  brfalse.s loc_9EA
0x9e8  ldc.i4.0
0x9e9  ret
0x9ea  ldarg.0
0x9eb  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x9f0  ldstr    aOwner// "owner"
0x9f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fa  brfalse.s loc_A19
0x9fc  ldarg.0
0x9fd  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsPrimaryId()
0xa02  stloc.0
0xa03  ldc.i4.1
0xa04  stloc.1
0xa05  ldloca.s 0
0xa07  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0xa0c  ldloc.1
0xa0d  beq.s    loc_A11
0xa0f  ldc.i4.0
0xa10  ret
0xa11  ldloca.s 0
0xa13  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa18  ret
0xa19  ldarg.0
0xa1a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0xa1f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa24  brtrue.s loc_A3A
0xa26  ldarg.0
0xa27  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_AttributeTypeName()
0xa2c  ldsfld   class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName::ImageType
0xa31  call     bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName::op_Inequality(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName)
0xa36  brfalse.s loc_A3A
0xa38  ldc.i4.0
0xa39  ret
0xa3a  ldarg.0
0xa3b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsValidForRead()
0xa40  stloc.0
0xa41  ldc.i4.1
0xa42  stloc.1
0xa43  ldloca.s 0
0xa45  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0xa4a  ldloc.1
0xa4b  beq.s    loc_A50
0xa4d  ldc.i4.1
0xa4e  br.s     loc_A5A
0xa50  ldloca.s 0
0xa52  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa57  ldc.i4.0
0xa58  ceq
0xa5a  brfalse.s loc_A5E
0xa5c  ldc.i4.0
0xa5d  ret
0xa5e  ldarg.0
0xa5f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_DeprecatedVersion()
0xa64  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa69  brtrue.s loc_A6D
0xa6b  ldc.i4.0
0xa6c  ret
0xa6d  ldarg.0
0xa6e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0xa73  ldstr    aMessageiddupch// "messageiddupcheck"
0xa78  ldc.i4.5
0xa79  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xa7e  brfalse.s loc_A95
0xa80  ldarg.0
0xa81  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0xa86  ldstr    aEmail// "email"
0xa8b  ldc.i4.5
0xa8c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xa91  brfalse.s loc_A95
0xa93  ldc.i4.0
0xa94  ret
0xa95  ldc.i4.1
0xa96  ret
```
