# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetDefaultViewForGrid

- ea: `0x1e840`
- end: `0x1e8ed`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetDefaultViewForGrid`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1d330`

## callees

- `0x17760`
- `0x1c890`
- `0x1c8a0`
- `0x1c970`
- `0x1cb30`
- `0x1e840`

## pseudocode

```c

```

## disassembly

```asm
0x1e840  ldarg.0
0x1e841  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ViewId()
0x1e846  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e84b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e850  brfalse.s loc_1E8C4
0x1e852  ldarg.0
0x1e853  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0x1e858  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e85d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetEntityMetadata(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e862  stloc.0
0x1e863  ldloc.0
0x1e864  brtrue.s loc_1E867
0x1e866  ret
0x1e867  ldloc.0
0x1e868  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x1e86d  brfalse.s loc_1E8C4
0x1e86f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache::Instance()
0x1e874  ldloc.0
0x1e875  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x1e87a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x1e87f  ldc.i4.2
0x1e880  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e885  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.QueryIdData [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache::TryLookupEntry(int32, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e88a  stloc.1
0x1e88b  ldloc.1
0x1e88c  brtrue.s loc_1E8AA
0x1e88e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache::Instance()
0x1e893  ldloc.0
0x1e894  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x1e899  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x1e89e  ldc.i4.0
0x1e89f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e8a4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.QueryIdData [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache::TryLookupEntry(int32, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e8a9  stloc.1
0x1e8aa  ldloc.1
0x1e8ab  brfalse.s loc_1E8C4
0x1e8ad  ldarg.0
0x1e8ae  ldloc.1
0x1e8af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.QueryIdData::get_QueryId()
0x1e8b4  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ViewId(valuetype [mscorlib]System.Guid value)
0x1e8b9  ldarg.0
0x1e8ba  ldc.i4   0x40F
0x1e8bf  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType value)
0x1e8c4  ldarg.0
0x1e8c5  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ViewId()
0x1e8ca  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e8cf  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e8d4  brfalse.s loc_1E8EC
0x1e8d6  ldarg.0
0x1e8d7  ldstr    aViewid_0// "viewid"
0x1e8dc  ldarg.0
0x1e8dd  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ViewId()
0x1e8e2  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1e8e7  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControl::AddExpando(string name, string value)
0x1e8ec  ret
```
