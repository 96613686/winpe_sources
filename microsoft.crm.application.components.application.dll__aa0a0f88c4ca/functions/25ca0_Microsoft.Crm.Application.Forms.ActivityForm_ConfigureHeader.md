# Microsoft.Crm.Application.Forms.ActivityForm::ConfigureHeader

- ea: `0x25ca0`
- end: `0x25da9`
- name: `Microsoft.Crm.Application.Forms.ActivityForm::ConfigureHeader`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x25ca0`
- `0x264c0`
- `0x2ae50`
- `0x2fa00`
- `0x82fe0`
- `0x869b0`

## string_xrefs

- `0x25cb4`: `scheduledstart`
- `0x25cc4`: `scheduledend`
- `0x25ce9`: `skipInitialXMLValue`

## pseudocode

```c

```

## disassembly

```asm
0x25ca0  ldarg.0
0x25ca1  call     instance void Microsoft.Crm.Application.Forms.CrudForm::ConfigureHeader()
0x25ca6  ldarg.0
0x25ca7  call     instance class Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Controls.AppControl::get_CurrentAppHeader()
0x25cac  ldc.i4.s 0x10
0x25cae  callvirt instance void Microsoft.Crm.Application.Controls.AppHeader::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType type)
0x25cb3  ldarg.0
0x25cb4  ldstr    aScheduledstart// "scheduledstart"
0x25cb9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string name)
0x25cbe  brfalse  loc_25DA8
0x25cc3  ldarg.0
0x25cc4  ldstr    aScheduledend// "scheduledend"
0x25cc9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string name)
0x25cce  brfalse  loc_25DA8
0x25cd3  ldarg.0
0x25cd4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x25cd9  ldstr    aStaticControls_2// "/_static/_controls/startendduration/sta"...
0x25cde  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x25ce3  ldarg.0
0x25ce4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x25ce9  ldstr    aSkipinitialxml// "skipInitialXMLValue"
0x25cee  ldc.i4.1
0x25cef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x25cf4  ldarg.0
0x25cf5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x25cfa  ldstr    aInitdates// "initDates"
0x25cff  ldstr    aInitdates_0// "initDates();"
0x25d04  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x25d09  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x25d0e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25d13  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x25d18  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25d1d  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x25d22  callvirt instance class [mscorlib]System.TimeZone [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZone()
0x25d27  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x25d2c  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToLocalTime(valuetype [mscorlib]System.DateTime)
0x25d31  stloc.1
0x25d32  ldloca.s 1
0x25d34  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x25d39  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x25d3e  stloc.1
0x25d3f  ldloca.s 1
0x25d41  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x25d46  sub
0x25d47  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int64)
0x25d4c  stloc.2
0x25d4d  ldloca.s 2
0x25d4f  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x25d54  stloc.0
0x25d55  ldarg.0
0x25d56  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x25d5b  ldstr    aOrgTimezoneOff// "ORG_TIMEZONE_OFFSET_STRING"
0x25d60  ldloca.s 0
0x25d62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25d67  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x25d6c  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x25d71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x25d76  ldarg.0
0x25d77  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x25d7c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x25d81  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x25d86  stloc.3
0x25d87  ldloc.3
0x25d88  ldc.i4   0x1069
0x25d8d  beq.s    loc_25DA8
0x25d8f  ldloc.3
0x25d90  ldc.i4   0x1076
0x25d95  beq.s    loc_25DA8
0x25d97  ldarg.0
0x25d98  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x25d9d  ldstr    aIsSchedulableA// "IS_SCHEDULABLE_ACTIVITY"
0x25da2  ldc.i4.0
0x25da3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x25da8  ret
```
