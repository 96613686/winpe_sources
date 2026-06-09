# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityKeyCreate::GetEntityKeyInfo

- ea: `0x31b0`
- end: `0x32c6`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityKeyCreate::GetEntityKeyInfo`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x3140`

## callees

- `0x190`
- `0x220`
- `0x330`
- `0x31b0`

## pseudocode

```c

```

## disassembly

```asm
0x31b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x31b5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x31ba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x31bf  stloc.0
0x31c0  ldloc.0
0x31c1  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x31c6  stloc.1
0x31c7  ldloc.1
0x31c8  ldarg.0
0x31c9  ldstr    aEntityid// "entityid"
0x31ce  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x31d3  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo::set_EntityId(valuetype [mscorlib]System.Guid)
0x31d8  ldarg.0
0x31d9  ldstr    aDisplayname// "displayname"
0x31de  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x31e3  brfalse.s loc_320B
0x31e5  ldloc.1
0x31e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_DisplayName()
0x31eb  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x31f0  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x31f5  ldarg.0
0x31f6  ldstr    aDisplayname// "displayname"
0x31fb  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x3200  ldloc.0
0x3201  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3206  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x320b  ldarg.0
0x320c  ldstr    aName// "name"
0x3211  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x3216  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetSchemaName(string)
0x321b  stloc.2
0x321c  ldloc.1
0x321d  ldloc.2
0x321e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo::set_Name(string)
0x3223  ldloc.1
0x3224  ldloc.2
0x3225  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo::set_LogicalName(string)
0x322a  ldarg.0
0x322b  ldstr    aEntitykeyattri// "entitykeyattributes"
0x3230  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x3235  ldc.i4.1
0x3236  newarr   [mscorlib]System.Char
0x323b  dup
0x323c  ldc.i4.0
0x323d  ldc.i4.s 0x3B
0x323f  stelem.i2
0x3240  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x3245  stloc.3
0x3246  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x324b  stloc.s  4
0x324d  ldnull
0x324e  stloc.s  5
0x3250  ldloc.1
0x3251  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_EntityId()
0x3256  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x325b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3260  brfalse.s loc_3271
0x3262  ldloc.s  4
0x3264  ldloc.1
0x3265  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_EntityId()
0x326a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x326f  stloc.s  5
0x3271  ldloc.s  5
0x3273  brfalse.s loc_32C4
0x3275  ldloc.1
0x3276  ldloc.3
0x3277  ldlen
0x3278  conv.i4
0x3279  newarr   [mscorlib]System.Guid
0x327e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo::set_KeyAttributeIds(valuetype [mscorlib]System.Guid[])
0x3283  ldc.i4.0
0x3284  stloc.s  6
0x3286  br.s     loc_32BD
0x3288  ldloc.3
0x3289  ldloc.s  6
0x328b  ldelem.ref
0x328c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3291  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x3296  stloc.s  7
0x3298  ldloc.s  5
0x329a  ldloc.s  7
0x329c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(int32)
0x32a1  stloc.s  8
0x32a3  ldloc.1
0x32a4  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_KeyAttributeIds()
0x32a9  ldloc.s  6
0x32ab  ldloc.s  8
0x32ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x32b2  stelem   [mscorlib]System.Guid
0x32b7  ldloc.s  6
0x32b9  ldc.i4.1
0x32ba  add
0x32bb  stloc.s  6
0x32bd  ldloc.s  6
0x32bf  ldloc.3
0x32c0  ldlen
0x32c1  conv.i4
0x32c2  blt.s    loc_3288
0x32c4  ldloc.1
0x32c5  ret
```
