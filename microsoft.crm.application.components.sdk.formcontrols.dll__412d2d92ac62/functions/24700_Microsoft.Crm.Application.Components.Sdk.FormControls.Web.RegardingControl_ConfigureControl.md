# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RegardingControl::ConfigureControl

- ea: `0x24700`
- end: `0x247ed`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RegardingControl::ConfigureControl`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x182d0`
- `0x1f8b0`
- `0x1f930`
- `0x1f940`
- `0x1fc00`
- `0x1fe30`
- `0x24700`

## pseudocode

```c

```

## disassembly

```asm
0x24700  ldarg.0
0x24701  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x24706  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2470b  call     int32[] [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Utility.ActivityHelper::BuildAllowedObjectTypeCodeList(int32[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24710  stloc.0
0x24711  ldarg.0
0x24712  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x24717  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x2471c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x24721  brtrue.s loc_2473A
0x24723  ldarg.0
0x24724  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x24729  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x2472e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x24733  ldc.i4   0x1068
0x24738  bne.un.s loc_247AC
0x2473a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x2473f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24744  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x24749  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2474e  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x24753  ldstr    aSetregardinglo// "SetRegardingLookupDefaultEntityType"
0x24758  ldsfld   string [mscorlib]System.String::Empty
0x2475d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x24762  castclass [mscorlib]System.String
0x24767  stloc.1
0x24768  ldloc.1
0x24769  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2476e  brtrue.s loc_247AC
0x24770  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24775  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2477a  ldloc.1
0x2477b  ldc.i4.1
0x2477c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x24781  stloc.2
0x24782  ldloc.2
0x24783  brfalse.s loc_247AC
0x24785  ldc.i4.0
0x24786  stloc.3
0x24787  br.s     loc_247A6
0x24789  ldloc.0
0x2478a  ldloc.3
0x2478b  ldelem.i4
0x2478c  ldloc.2
0x2478d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x24792  bne.un.s loc_247A2
0x24794  ldarg.0
0x24795  ldloc.2
0x24796  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x2479b  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultType(int32 value)
0x247a0  br.s     loc_247AC
0x247a2  ldloc.3
0x247a3  ldc.i4.1
0x247a4  add
0x247a5  stloc.3
0x247a6  ldloc.3
0x247a7  ldloc.0
0x247a8  ldlen
0x247a9  conv.i4
0x247aa  blt.s    loc_24789
0x247ac  ldarg.0
0x247ad  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::ConfigureControl()
0x247b2  ldarg.0
0x247b3  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupStyle()
0x247b8  ldstr    aSingle// "single"
0x247bd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x247c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x247c7  ldstr    aRegardingContr// "Regarding control with id = {0} has inc"...
0x247cc  ldc.i4.1
0x247cd  newarr   [mscorlib]System.Object
0x247d2  dup
0x247d3  ldc.i4.0
0x247d4  ldarg.0
0x247d5  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x247da  stelem.ref
0x247db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x247e0  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x247e5  ldarg.0
0x247e6  ldloc.0
0x247e7  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[] value)
0x247ec  ret
```
