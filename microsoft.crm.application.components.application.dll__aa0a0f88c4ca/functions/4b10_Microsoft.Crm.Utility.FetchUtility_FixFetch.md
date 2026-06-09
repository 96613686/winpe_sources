# Microsoft.Crm.Utility.FetchUtility::FixFetch

- ea: `0x4b10`
- end: `0x5103`
- name: `Microsoft.Crm.Utility.FetchUtility::FixFetch`
- size: `1523`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x4b10`
- `0x5110`
- `0x5170`
- `0x51f0`
- `0xf1060`
- `0xf1070`

## string_xrefs

- `0x4bb1`: `LINK-ENTITY`
- `0x4c2c`: `Message_ErrorOpeningSavedQuery_NoEntity`
- `0x4c91`: `AdvFind_NoReadPrivilegeToEntity`
- `0x4f15`: `Message_ErrorOpeningSavedQuery_EntityAccess`

## pseudocode

```c

```

## disassembly

```asm
0x4b10  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4b15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x4b1a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4b1f  stloc.0
0x4b20  ldarg.2
0x4b21  ldnull
0x4b22  stind.ref
0x4b23  ldarg.0
0x4b24  brfalse.s loc_4B2E
0x4b26  ldarg.0
0x4b27  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b2c  brtrue.s loc_4B30
0x4b2e  ldnull
0x4b2f  ret
0x4b30  ldc.i4.s 0x64
0x4b32  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x4b37  stloc.1
0x4b38  ldnull
0x4b39  stloc.2
0x4b3a  ldc.i4.s 0xA
0x4b3c  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0x4b41  stloc.3
0x4b42  ldc.i4.s 0xA
0x4b44  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0x4b49  stloc.s  4
0x4b4b  ldsfld   string [mscorlib]System.String::Empty
0x4b50  stloc.s  6
0x4b52  ldc.i4.0
0x4b53  stloc.s  0xA
0x4b55  ldc.i4.s 0xA
0x4b57  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32)
0x4b5c  stloc.s  0xB
0x4b5e  ldnull
0x4b5f  stloc.s  0xC
0x4b61  ldarg.0
0x4b62  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x4b67  stloc.s  0xD
0x4b69  ldloc.s  0xD
0x4b6b  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x4b70  stloc.s  0xE
0x4b72  br       loc_4ED3
0x4b77  ldloc.s  0xE
0x4b79  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x4b7e  stloc.s  0xF
0x4b80  ldloc.s  0xF
0x4b82  ldc.i4.1
0x4b83  beq.s    loc_4B93
0x4b85  ldloc.s  0xF
0x4b87  ldc.i4.s 0xF
0x4b89  beq      loc_4EBC
0x4b8e  br       loc_4ED3
0x4b93  ldloc.s  0xE
0x4b95  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x4b9a  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4b9f  stloc.s  5
0x4ba1  ldloc.s  5
0x4ba3  ldstr    aEntity_0// "ENTITY"
0x4ba8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4bad  brtrue.s loc_4BE4
0x4baf  ldloc.s  5
0x4bb1  ldstr    aLinkEntity// "LINK-ENTITY"
0x4bb6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4bbb  brtrue.s loc_4BE4
0x4bbd  ldloc.s  5
0x4bbf  ldstr    aCondition_0// "CONDITION"
0x4bc4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4bc9  brtrue   loc_4D6E
0x4bce  ldloc.s  5
0x4bd0  ldstr    aValue_1// "VALUE"
0x4bd5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4bda  brtrue   loc_4E8C
0x4bdf  br       loc_4ED3
0x4be4  nop
0x4be5  ldloc.s  0xE
0x4be7  ldstr    aName// "name"
0x4bec  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x4bf1  stloc.s  6
0x4bf3  ldstr    aEntity// "entity"
0x4bf8  ldloc.s  5
0x4bfa  ldc.i4.5
0x4bfb  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4c00  brtrue.s loc_4C06
0x4c02  ldarg.2
0x4c03  ldloc.s  6
0x4c05  stind.ref
0x4c06  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4c0b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x4c10  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4c15  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4c1a  ldloc.s  6
0x4c1c  ldc.i4.1
0x4c1d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x4c22  stloc.2
0x4c23  leave.s  loc_4C51
0x4c25  pop
0x4c26  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c2b  ldarg.1
0x4c2c  ldstr    aMessageErrorop// "Message_ErrorOpeningSavedQuery_NoEntity"
0x4c31  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4c36  ldc.i4.1
0x4c37  newarr   [mscorlib]System.Object
0x4c3c  dup
0x4c3d  ldc.i4.0
0x4c3e  ldloc.s  6
0x4c40  stelem.ref
0x4c41  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c46  ldc.i4   0x80631104
0x4c4b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4c50  throw
0x4c51  ldloc.2
0x4c52  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsIntersect()
0x4c57  brtrue   loc_4CDC
0x4c5c  ldloc.2
0x4c5d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x4c62  call     bool Microsoft.Crm.Utility.FetchUtility::CheckReadPrivilege(int32 objectType)
0x4c67  brtrue.s loc_4CDC
0x4c69  ldloc.3
0x4c6a  ldloc.2
0x4c6b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x4c70  box      [mscorlib]System.Int32
0x4c75  callvirt instance int32 [mscorlib]System.Collections.ArrayList::IndexOf(object)
0x4c7a  ldc.i4.0
0x4c7b  bge.s    loc_4CDC
0x4c7d  ldloc.1
0x4c7e  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x4c83  ldc.i4.0
0x4c84  ble.s    loc_4C8F
0x4c86  ldloc.1
0x4c87  ldc.i4.s 0xA
0x4c89  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x4c8e  pop
0x4c8f  ldloc.1
0x4c90  ldarg.1
0x4c91  ldstr    aAdvfindNoreadp// "AdvFind_NoReadPrivilegeToEntity"
0x4c96  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4c9b  ldc.i4.1
0x4c9c  newarr   [mscorlib]System.Object
0x4ca1  dup
0x4ca2  ldc.i4.0
0x4ca3  ldloc.2
0x4ca4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x4ca9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x4cae  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x4cb3  ldloc.0
0x4cb4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4cb9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x4cbe  stelem.ref
0x4cbf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x4cc4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4cc9  pop
0x4cca  ldloc.3
0x4ccb  ldloc.2
0x4ccc  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x4cd1  box      [mscorlib]System.Int32
0x4cd6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4cdb  pop
0x4cdc  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x4ce1  brtrue   loc_4ED3
0x4ce6  ldloc.2
0x4ce7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsReplicated()
0x4cec  brtrue   loc_4ED3
0x4cf1  ldloc.s  4
0x4cf3  ldloc.2
0x4cf4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x4cf9  box      [mscorlib]System.Int32
0x4cfe  callvirt instance int32 [mscorlib]System.Collections.ArrayList::IndexOf(object)
0x4d03  ldc.i4.0
0x4d04  bge      loc_4ED3
0x4d09  ldloc.1
0x4d0a  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x4d0f  ldc.i4.0
0x4d10  ble.s    loc_4D1B
0x4d12  ldloc.1
0x4d13  ldc.i4.s 0xA
0x4d15  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x4d1a  pop
0x4d1b  ldloc.1
0x4d1c  ldarg.1
0x4d1d  ldstr    aAdvfindEntityn// "AdvFind_EntityNotAvailableWhileOffline"
0x4d22  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4d27  ldc.i4.1
0x4d28  newarr   [mscorlib]System.Object
0x4d2d  dup
0x4d2e  ldc.i4.0
0x4d2f  ldloc.2
0x4d30  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x4d35  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x4d3a  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x4d3f  ldloc.0
0x4d40  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4d45  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x4d4a  stelem.ref
0x4d4b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x4d50  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d55  pop
0x4d56  ldloc.s  4
0x4d58  ldloc.2
0x4d59  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x4d5e  box      [mscorlib]System.Int32
0x4d63  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4d68  pop
0x4d69  br       loc_4ED3
0x4d6e  ldloc.s  0xA
0x4d70  ldc.i4.0
0x4d71  ceq
0x4d73  ldstr    aErrorInProcess// "Error in processing lookup conditions. "...
0x4d78  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4d7d  ldloc.s  0xE
0x4d7f  ldstr    aAttribute// "attribute"
0x4d84  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x4d89  stloc.s  7
0x4d8b  ldloc.2
0x4d8c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x4d91  ldloc.s  7
0x4d93  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x4d98  stloc.s  0xC
0x4d9a  ldloc.s  0xC
0x4d9c  brfalse  loc_4ED3
0x4da1  ldloc.s  0xC
0x4da3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x4da8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x4dad  stloc.s  0x10
0x4daf  ldloc.s  0x10
0x4db1  ldstr    aPrimarykey// "primarykey"
0x4db6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4dbb  brtrue.s loc_4E06
0x4dbd  ldloc.s  0x10
0x4dbf  ldstr    aCustomer// "customer"
0x4dc4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4dc9  brtrue.s loc_4E06
0x4dcb  ldloc.s  0x10
0x4dcd  ldstr    aLookup// "lookup"
0x4dd2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4dd7  brtrue.s loc_4E06
0x4dd9  ldloc.s  0x10
0x4ddb  ldstr    aOwner// "owner"
0x4de0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4de5  brtrue.s loc_4E06
0x4de7  ldloc.s  0x10
0x4de9  ldstr    aUniqueidentifi// "uniqueidentifier"
0x4dee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4df3  brtrue.s loc_4E06
0x4df5  ldloc.s  0x10
0x4df7  ldstr    aPartylist// "partylist"
0x4dfc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4e01  brfalse  loc_4ED3
0x4e06  ldloc.s  0xE
0x4e08  ldstr    aOperator// "operator"
0x4e0d  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x4e12  stloc.s  8
0x4e14  ldloc.s  8
0x4e16  brfalse  loc_4ED3
0x4e1b  ldloc.s  8
0x4e1d  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4e22  stloc.s  0x10
0x4e24  ldloc.s  0x10
0x4e26  ldstr    aEq// "EQ"
0x4e2b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4e30  brtrue.s loc_4E5E
0x4e32  ldloc.s  0x10
0x4e34  ldstr    aNe// "NE"
0x4e39  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4e3e  brtrue.s loc_4E5E
0x4e40  ldloc.s  0x10
0x4e42  ldstr    aIn_0// "IN"
0x4e47  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4e4c  brtrue.s loc_4E87
0x4e4e  ldloc.s  0x10
0x4e50  ldstr    aNotIn// "NOT-IN"
0x4e55  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4e5a  brtrue.s loc_4E87
0x4e5c  br.s     loc_4ED3
0x4e5e  ldloc.s  0xE
0x4e60  ldstr    aUiname// "uiname"
0x4e65  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x4e6a  stloc.s  9
0x4e6c  ldloc.s  9
0x4e6e  brtrue.s loc_4ED3
0x4e70  ldloc.s  0xE
0x4e72  ldstr    aValue// "value"
0x4e77  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x4e7c  ldloc.s  0xC
0x4e7e  ldloc.s  0xB
0x4e80  call     void Microsoft.Crm.Utility.FetchUtility::AddLookupOTCsForId(string id, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attrMeta, class [mscorlib]System.Collections.Hashtable lookupIdsMissingNames)
0x4e85  br.s     loc_4ED3
0x4e87  ldc.i4.1
0x4e88  stloc.s  0xA
0x4e8a  br.s     loc_4ED3
0x4e8c  ldloc.s  0xA
0x4e8e  brfalse.s loc_4ED3
0x4e90  ldloc.s  0xE
0x4e92  ldstr    aUiname// "uiname"
0x4e97  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x4e9c  stloc.s  9
0x4e9e  ldloc.s  9
0x4ea0  brtrue.s loc_4ED3
0x4ea2  ldloc.s  0xE
0x4ea4  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x4ea9  pop
0x4eaa  ldloc.s  0xE
  ... truncated ...
```
