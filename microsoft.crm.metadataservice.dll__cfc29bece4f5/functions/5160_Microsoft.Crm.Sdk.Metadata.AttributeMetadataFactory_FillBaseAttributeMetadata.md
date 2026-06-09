# Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::FillBaseAttributeMetadata

- ea: `0x5160`
- end: `0x560e`
- name: `Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::FillBaseAttributeMetadata`
- size: `1198`
- prototype: ``
- caller_count: `18`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3e40`
- `0x3f20`
- `0x40b0`
- `0x4120`
- `0x41b0`
- `0x4340`
- `0x4460`
- `0x4500`
- `0x48d0`
- `0x4b00`
- `0x4be0`
- `0x4c60`
- `0x4cd0`
- `0x4d40`
- `0x4e30`
- `0x4ec0`
- `0x5010`
- `0x5120`

## callees

- `0x5160`
- `0x5610`
- `0x58e0`
- `0x5950`
- `0xb660`
- `0xc120`

## string_xrefs

- `0x52b7`: `linkedattributeid`
- `0x52c5`: `linkedattributeid`
- `0x532f`: `canbesecuredforcreate`
- `0x533d`: `canbesecuredforcreate`
- `0x5357`: `canbesecuredforread`
- `0x5365`: `canbesecuredforread`
- `0x537f`: `canbesecuredforupdate`
- `0x538d`: `canbesecuredforupdate`
- `0x54cf`: `validforcreateapi`
- `0x54dd`: `validforcreateapi`
- `0x54f7`: `validforupdateapi`
- `0x5505`: `validforupdateapi`
- `0x551f`: `validforreadapi`
- `0x552d`: `validforreadapi`

## pseudocode

```c

```

## disassembly

```asm
0x5160  ldarg.1
0x5161  ldarg.2
0x5162  ldstr    aAttributeid// "attributeid"
0x5167  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x516c  unbox.any [mscorlib]System.Guid
0x5171  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x5176  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::set_MetadataId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x517b  ldarg.1
0x517c  ldarg.0
0x517d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_AttributeType(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode>)
0x5182  ldarg.2
0x5183  ldstr    aName// "name"
0x5188  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x518d  brtrue.s loc_51A5
0x518f  ldarg.1
0x5190  ldarg.2
0x5191  ldstr    aPhysicalname// "physicalname"
0x5196  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x519b  castclass [mscorlib]System.String
0x51a0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_SchemaName(string)
0x51a5  ldarg.2
0x51a6  ldstr    aLogicalname// "logicalname"
0x51ab  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x51b0  brtrue.s loc_51C8
0x51b2  ldarg.1
0x51b3  ldarg.2
0x51b4  ldstr    aLogicalname// "logicalname"
0x51b9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x51be  castclass [mscorlib]System.String
0x51c3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_LogicalName(string)
0x51c8  ldarg.1
0x51c9  ldarg.2
0x51ca  ldstr    aExternalname// "externalname"
0x51cf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x51d4  castclass [mscorlib]System.String
0x51d9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_ExternalName(string)
0x51de  ldarg.2
0x51df  ldstr    aAttributetypei// "attributetypeid"
0x51e4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x51e9  brtrue.s loc_5222
0x51eb  ldarg.2
0x51ec  ldstr    aAttributetypei// "attributetypeid"
0x51f1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x51f6  unbox.any [mscorlib]System.Guid
0x51fb  stloc.0
0x51fc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x5201  ldloc.0
0x5202  box      [mscorlib]System.Guid
0x5207  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x520c  stloc.1
0x520d  ldarg.1
0x520e  ldloc.1
0x520f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x5214  ldc.i4.s 0xD
0x5216  ceq
0x5218  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x521d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsPrimaryId(valuetype [mscorlib]System.Nullable`1<bool>)
0x5222  ldarg.1
0x5223  ldarg.s  4
0x5225  ldarg.1
0x5226  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x522b  stloc.2
0x522c  ldloca.s 2
0x522e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x5233  ldstr    aDescription// "Description"
0x5238  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label Microsoft.Crm.Sdk.Metadata.MetadataLoader::LoadLocalizedNames(valuetype [mscorlib]System.Guid objectId, string objectColumnName)
0x523d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_Description(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label)
0x5242  ldarg.1
0x5243  ldarg.s  4
0x5245  ldarg.1
0x5246  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x524b  stloc.2
0x524c  ldloca.s 2
0x524e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x5253  ldstr    aDisplayname// "DisplayName"
0x5258  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label Microsoft.Crm.Sdk.Metadata.MetadataLoader::LoadLocalizedNames(valuetype [mscorlib]System.Guid objectId, string objectColumnName)
0x525d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_DisplayName(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label)
0x5262  ldarg.2
0x5263  ldstr    aAttributeof// "attributeof"
0x5268  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x526d  brtrue.s loc_528C
0x526f  ldarg.1
0x5270  ldarg.s  4
0x5272  ldarg.2
0x5273  ldstr    aAttributeof// "attributeof"
0x5278  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x527d  unbox.any [mscorlib]System.Guid
0x5282  callvirt instance string Microsoft.Crm.Sdk.Metadata.MetadataLoader::GetAttributeName(valuetype [mscorlib]System.Guid attributeId)
0x5287  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_AttributeOf(string)
0x528c  ldarg.2
0x528d  ldstr    aAggregateof// "aggregateof"
0x5292  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5297  brtrue.s loc_52B6
0x5299  ldarg.1
0x529a  ldarg.s  4
0x529c  ldarg.2
0x529d  ldstr    aAggregateof// "aggregateof"
0x52a2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x52a7  unbox.any [mscorlib]System.Guid
0x52ac  callvirt instance string Microsoft.Crm.Sdk.Metadata.MetadataLoader::GetAttributeName(valuetype [mscorlib]System.Guid attributeId)
0x52b1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_AggregateOf(string)
0x52b6  ldarg.2
0x52b7  ldstr    aLinkedattribut// "linkedattributeid"
0x52bc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x52c1  brtrue.s loc_52DE
0x52c3  ldarg.1
0x52c4  ldarg.2
0x52c5  ldstr    aLinkedattribut// "linkedattributeid"
0x52ca  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x52cf  unbox.any [mscorlib]System.Guid
0x52d4  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x52d9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_LinkedAttributeId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x52de  ldarg.2
0x52df  ldstr    aIsmanaged// "ismanaged"
0x52e4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x52e9  brtrue.s loc_5306
0x52eb  ldarg.1
0x52ec  ldarg.2
0x52ed  ldstr    aIsmanaged// "ismanaged"
0x52f2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x52f7  unbox.any [mscorlib]System.Boolean
0x52fc  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5301  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsManaged(valuetype [mscorlib]System.Nullable`1<bool>)
0x5306  ldarg.2
0x5307  ldstr    aIssecured// "issecured"
0x530c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5311  brtrue.s loc_532E
0x5313  ldarg.1
0x5314  ldarg.2
0x5315  ldstr    aIssecured// "issecured"
0x531a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x531f  unbox.any [mscorlib]System.Boolean
0x5324  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5329  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsSecured(valuetype [mscorlib]System.Nullable`1<bool>)
0x532e  ldarg.2
0x532f  ldstr    aCanbesecuredfo// "canbesecuredforcreate"
0x5334  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5339  brtrue.s loc_5356
0x533b  ldarg.1
0x533c  ldarg.2
0x533d  ldstr    aCanbesecuredfo// "canbesecuredforcreate"
0x5342  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5347  unbox.any [mscorlib]System.Boolean
0x534c  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5351  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_CanBeSecuredForCreate(valuetype [mscorlib]System.Nullable`1<bool>)
0x5356  ldarg.2
0x5357  ldstr    aCanbesecuredfo_0// "canbesecuredforread"
0x535c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5361  brtrue.s loc_537E
0x5363  ldarg.1
0x5364  ldarg.2
0x5365  ldstr    aCanbesecuredfo_0// "canbesecuredforread"
0x536a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x536f  unbox.any [mscorlib]System.Boolean
0x5374  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5379  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_CanBeSecuredForRead(valuetype [mscorlib]System.Nullable`1<bool>)
0x537e  ldarg.2
0x537f  ldstr    aCanbesecuredfo_1// "canbesecuredforupdate"
0x5384  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5389  brtrue.s loc_53A6
0x538b  ldarg.1
0x538c  ldarg.2
0x538d  ldstr    aCanbesecuredfo_1// "canbesecuredforupdate"
0x5392  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5397  unbox.any [mscorlib]System.Boolean
0x539c  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x53a1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_CanBeSecuredForUpdate(valuetype [mscorlib]System.Nullable`1<bool>)
0x53a6  ldarg.2
0x53a7  ldstr    aIssearchable// "issearchable"
0x53ac  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x53b1  brtrue.s loc_53CE
0x53b3  ldarg.1
0x53b4  ldarg.2
0x53b5  ldstr    aIssearchable// "issearchable"
0x53ba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x53bf  unbox.any [mscorlib]System.Boolean
0x53c4  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x53c9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsSearchable(valuetype [mscorlib]System.Nullable`1<bool>)
0x53ce  ldarg.2
0x53cf  ldstr    aIsfilterable// "isfilterable"
0x53d4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x53d9  brtrue.s loc_53F6
0x53db  ldarg.1
0x53dc  ldarg.2
0x53dd  ldstr    aIsfilterable// "isfilterable"
0x53e2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x53e7  unbox.any [mscorlib]System.Boolean
0x53ec  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x53f1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsFilterable(valuetype [mscorlib]System.Nullable`1<bool>)
0x53f6  ldarg.2
0x53f7  ldstr    aIsretrievable// "isretrievable"
0x53fc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5401  brtrue.s loc_541E
0x5403  ldarg.1
0x5404  ldarg.2
0x5405  ldstr    aIsretrievable// "isretrievable"
0x540a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x540f  unbox.any [mscorlib]System.Boolean
0x5414  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5419  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsRetrievable(valuetype [mscorlib]System.Nullable`1<bool>)
0x541e  ldarg.2
0x541f  ldstr    aColumnnumber_0// "columnnumber"
0x5424  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5429  brtrue.s loc_5446
0x542b  ldarg.1
0x542c  ldarg.2
0x542d  ldstr    aColumnnumber_0// "columnnumber"
0x5432  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5437  unbox.any [mscorlib]System.Int32
0x543c  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x5441  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_ColumnNumber(valuetype [mscorlib]System.Nullable`1<int32>)
0x5446  ldarg.1
0x5447  ldarg.3
0x5448  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_EntityLogicalName(string)
0x544d  ldarg.2
0x544e  ldstr    aDisplaymask// "displaymask"
0x5453  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5458  brtrue.s loc_54A6
0x545a  ldarg.1
0x545b  ldarg.2
0x545c  ldstr    aDisplaymask// "displaymask"
0x5461  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5466  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DisplayMasks
0x546b  call     void Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::FillFromDisplayMask(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata attributeMetadata, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DisplayMasks mask)
0x5470  ldarg.1
0x5471  ldarg.2
0x5472  ldstr    aDisplaymask// "displaymask"
0x5477  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x547c  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DisplayMasks
0x5481  call     valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DisplayMasks Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::GetDisplayMask(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DisplayMasks mask)
0x5486  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_DisplayMask(int32)
0x548b  ldarg.1
0x548c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsValidForAdvancedFind()
0x5491  ldarg.2
0x5492  ldstr    aCanmodifysearc// "canmodifysearchsettings"
0x5497  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x549c  unbox.any [mscorlib]System.Boolean
0x54a1  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::set_CanBeChanged(bool)
0x54a6  ldarg.2
0x54a7  ldstr    aIscustomfield// "iscustomfield"
0x54ac  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x54b1  brtrue.s loc_54CE
0x54b3  ldarg.1
0x54b4  ldarg.2
0x54b5  ldstr    aIscustomfield// "iscustomfield"
0x54ba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54bf  unbox.any [mscorlib]System.Boolean
0x54c4  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x54c9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsCustomAttribute(valuetype [mscorlib]System.Nullable`1<bool>)
0x54ce  ldarg.2
0x54cf  ldstr    aValidforcreate// "validforcreateapi"
0x54d4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x54d9  brtrue.s loc_54F6
0x54db  ldarg.1
0x54dc  ldarg.2
0x54dd  ldstr    aValidforcreate// "validforcreateapi"
0x54e2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54e7  unbox.any [mscorlib]System.Boolean
0x54ec  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x54f1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsValidForCreate(valuetype [mscorlib]System.Nullable`1<bool>)
0x54f6  ldarg.2
0x54f7  ldstr    aValidforupdate// "validforupdateapi"
0x54fc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5501  brtrue.s loc_551E
0x5503  ldarg.1
0x5504  ldarg.2
0x5505  ldstr    aValidforupdate// "validforupdateapi"
0x550a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x550f  unbox.any [mscorlib]System.Boolean
0x5514  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5519  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsValidForUpdate(valuetype [mscorlib]System.Nullable`1<bool>)
0x551e  ldarg.2
0x551f  ldstr    aValidforreadap// "validforreadapi"
0x5524  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5529  brtrue.s loc_5546
0x552b  ldarg.1
0x552c  ldarg.2
0x552d  ldstr    aValidforreadap// "validforreadapi"
0x5532  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5537  unbox.any [mscorlib]System.Boolean
0x553c  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5541  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsValidForRead(valuetype [mscorlib]System.Nullable`1<bool>)
0x5546  ldarg.2
0x5547  ldstr    aIslogical// "islogical"
0x554c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5551  brtrue.s loc_556E
0x5553  ldarg.1
0x5554  ldarg.2
0x5555  ldstr    aIslogical// "islogical"
0x555a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x555f  unbox.any [mscorlib]System.Boolean
0x5564  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5569  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_IsLogical(valuetype [mscorlib]System.Nullable`1<bool>)
0x556e  ldarg.2
0x556f  ldstr    aDeprecatedvers// "deprecatedversion"
0x5574  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5579  brtrue.s loc_5591
0x557b  ldarg.1
0x557c  ldarg.2
0x557d  ldstr    aDeprecatedvers// "deprecatedversion"
  ... truncated ...
```
