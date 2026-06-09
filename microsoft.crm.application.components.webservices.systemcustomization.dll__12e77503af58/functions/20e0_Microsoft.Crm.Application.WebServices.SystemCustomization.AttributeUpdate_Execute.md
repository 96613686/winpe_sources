# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeUpdate::Execute

- ea: `0x20e0`
- end: `0x2214`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeUpdate::Execute`
- size: `308`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xaf20`
- `0xafd0`

## callees

- `0x1a0`
- `0x290`
- `0x330`
- `0x430`
- `0x1ed0`
- `0x20e0`
- `0x2220`

## string_xrefs

- `0x21c8`: `linkedattributecreaterequired`

## pseudocode

```c

```

## disassembly

```asm
0x20e0  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteAttribute()
0x20e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20ea  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20ef  brtrue.s loc_2102
0x20f1  ldc.i4   0x80040277
0x20f6  ldc.i4.0
0x20f7  newarr   [mscorlib]System.Object
0x20fc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2101  throw
0x2102  ldarg.1
0x2103  ldstr    aAttributeid// "attributeid"
0x2108  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x210d  stloc.0
0x210e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x2113  ldloc.0
0x2114  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetAttribute(valuetype [mscorlib]System.Guid)
0x2119  stloc.1
0x211a  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::.ctor()
0x211f  stloc.2
0x2120  ldarg.1
0x2121  ldloc.1
0x2122  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetAttributeInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x2127  stloc.3
0x2128  ldloc.1
0x2129  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x212e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x2133  ldstr    aStatus// "status"
0x2138  call     bool [mscorlib]System.String::op_Equality(string, string)
0x213d  brfalse.s loc_21B3
0x213f  ldloc.1
0x2140  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x2145  ldstr    aStatecode// "statecode"
0x214a  ldc.i4.1
0x214b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x2150  stloc.s  4
0x2152  ldc.i4.2
0x2153  newarr   [mscorlib]System.Guid
0x2158  dup
0x2159  ldc.i4.0
0x215a  ldloc.0
0x215b  stelem   [mscorlib]System.Guid
0x2160  dup
0x2161  ldc.i4.1
0x2162  ldloc.s  4
0x2164  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x2169  stelem   [mscorlib]System.Guid
0x216e  stloc.s  5
0x2170  ldc.i4.2
0x2171  newarr   [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo
0x2176  dup
0x2177  ldc.i4.0
0x2178  ldloc.3
0x2179  stelem.ref
0x217a  dup
0x217b  ldc.i4.1
0x217c  ldarg.1
0x217d  ldstr    aType// "type"
0x2182  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x2187  ldloc.s  4
0x2189  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeUpdate::GetStateInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x218e  stelem.ref
0x218f  stloc.s  6
0x2191  ldloc.2
0x2192  ldloc.s  5
0x2194  ldloc.s  6
0x2196  ldc.i4.1
0x2197  ldarg.0
0x2198  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x219d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21a2  brtrue.s loc_21A7
0x21a4  ldarg.0
0x21a5  br.s     loc_21AC
0x21a7  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x21ac  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::UpdateMultiple(valuetype [mscorlib]System.Guid[], class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo[], bool, valuetype [mscorlib]System.Guid)
0x21b1  br.s     loc_2209
0x21b3  ldloc.3
0x21b4  isinst   [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.LookupAttributeInfo
0x21b9  stloc.s  7
0x21bb  ldloc.s  7
0x21bd  brfalse.s loc_21C7
0x21bf  ldloc.s  7
0x21c1  ldnull
0x21c2  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.LookupAttributeInfo::set_LookupValues(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeLookupValueByTypeDictionary)
0x21c7  ldarg.1
0x21c8  ldstr    aLinkedattribut// "linkedattributecreaterequired"
0x21cd  ldc.i4.0
0x21ce  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x21d3  brfalse.s loc_21EB
0x21d5  ldarg.0
0x21d6  ldarg.1
0x21d7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::CreateLinkedAttribute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x21dc  stloc.s  8
0x21de  ldloc.3
0x21df  ldloc.s  8
0x21e1  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x21e6  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_LinkedAttributeId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x21eb  ldloc.2
0x21ec  ldloc.0
0x21ed  ldloc.3
0x21ee  ldc.i4.1
0x21ef  ldarg.0
0x21f0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21f5  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21fa  brtrue.s loc_21FF
0x21fc  ldarg.0
0x21fd  br.s     loc_2204
0x21ff  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x2204  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::Update(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo, bool, valuetype [mscorlib]System.Guid)
0x2209  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x220e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2213  ret
```
