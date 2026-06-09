# Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::CreateManagedPropertyAttributeMetadata

- ea: `0x4e30`
- end: `0x4eb6`
- name: `Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::CreateManagedPropertyAttributeMetadata`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3bd0`

## callees

- `0x4e30`
- `0x5160`

## string_xrefs

- `0x4e6a`: `managedpropertyparentcomponenttype`
- `0x4e78`: `managedpropertyparentcomponenttype`

## pseudocode

```c

```

## disassembly

```asm
0x4e30  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManagedPropertyAttributeMetadata::.ctor()
0x4e35  stloc.0
0x4e36  ldc.i4.s 0x13
0x4e38  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode>::.ctor(var<u1>)
0x4e3d  ldloc.0
0x4e3e  ldarg.0
0x4e3f  ldarg.1
0x4e40  ldarg.2
0x4e41  call     void Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::FillBaseAttributeMetadata(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode> type, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata attribute, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attributeEntity, string entityName, class Microsoft.Crm.Sdk.Metadata.MetadataLoader loader)
0x4e46  ldarg.0
0x4e47  ldstr    aManagedpropert// "managedpropertylogicalname"
0x4e4c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4e51  brtrue.s loc_4E69
0x4e53  ldloc.0
0x4e54  ldarg.0
0x4e55  ldstr    aManagedpropert// "managedpropertylogicalname"
0x4e5a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e5f  castclass [mscorlib]System.String
0x4e64  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManagedPropertyAttributeMetadata::set_ManagedPropertyLogicalName(string)
0x4e69  ldarg.0
0x4e6a  ldstr    aManagedpropert_0// "managedpropertyparentcomponenttype"
0x4e6f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4e74  brtrue.s loc_4E91
0x4e76  ldloc.0
0x4e77  ldarg.0
0x4e78  ldstr    aManagedpropert_0// "managedpropertyparentcomponenttype"
0x4e7d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e82  unbox.any [mscorlib]System.Int32
0x4e87  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x4e8c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManagedPropertyAttributeMetadata::set_ParentComponentType(valuetype [mscorlib]System.Nullable`1<int32>)
0x4e91  ldarg.0
0x4e92  ldstr    aManagedpropert_1// "managedpropertyparentattributename"
0x4e97  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4e9c  brtrue.s loc_4EB4
0x4e9e  ldloc.0
0x4e9f  ldarg.0
0x4ea0  ldstr    aManagedpropert_1// "managedpropertyparentattributename"
0x4ea5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4eaa  castclass [mscorlib]System.String
0x4eaf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManagedPropertyAttributeMetadata::set_ParentAttributeName(string)
0x4eb4  ldloc.0
0x4eb5  ret
```
