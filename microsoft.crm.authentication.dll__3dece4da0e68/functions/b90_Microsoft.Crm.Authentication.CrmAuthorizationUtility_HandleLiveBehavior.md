# Microsoft.Crm.Authentication.CrmAuthorizationUtility::HandleLiveBehavior

- ea: `0xb90`
- end: `0xc6b`
- name: `Microsoft.Crm.Authentication.CrmAuthorizationUtility::HandleLiveBehavior`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x15130`

## callees

- `0xb90`

## string_xrefs

- `0xbee`: `D:\a\1\s\src\Platform\Authentication\Legacy\Common\CrmAuthorizationUtility.cs`
- `0xc0f`: `D:\a\1\s\src\Platform\Authentication\Legacy\Common\CrmAuthorizationUtility.cs`

## pseudocode

```c

```

## disassembly

```asm
0xb90  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xb95  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xb9a  ldc.i4.2
0xb9b  bne.un   loc_C6A
0xba0  ldarg.0
0xba1  ldc.i4.s 0x16
0xba3  ldstr    aCrmauthorizati// "CrmAuthorizationUtility checking if Sig"...
0xba8  ldc.i4.0
0xba9  newarr   [mscorlib]System.Object
0xbae  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xbb3  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0xbb8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0xbbd  stloc.0
0xbbe  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0xbc3  ldarg.0
0xbc4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0xbc9  stloc.1
0xbca  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0xbcf  ldloc.1
0xbd0  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupState [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupState(valuetype [mscorlib]System.Guid)
0xbd5  ldc.i4.1
0xbd6  beq.s    loc_BE1
0xbd8  ldarg.0
0xbd9  ldc.i4.0
0xbda  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::RedirectToNotificationUrl(valuetype [mscorlib]System.Guid, bool)
0xbdf  br.s     loc_C49
0xbe1  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xbe6  ldarg.0
0xbe7  ldc.i4.s 0x32
0xbe9  ldstr    aHandlelivebeha// "HandleLiveBehavior"
0xbee  ldstr    aDA1SSrcPlatfor// "D:\\a\\1\\s\\src\\Platform\\Authenticat"...
0xbf3  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationState(valuetype [mscorlib]System.Guid, int32, string, string)
0xbf8  stloc.2
0xbf9  ldloc.2
0xbfa  brfalse.s loc_C02
0xbfc  ldloc.2
0xbfd  ldc.i4.1
0xbfe  beq.s    loc_C49
0xc00  br.s     loc_C42
0xc02  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xc07  ldarg.0
0xc08  ldc.i4.s 0x36
0xc0a  ldstr    aHandlelivebeha// "HandleLiveBehavior"
0xc0f  ldstr    aDA1SSrcPlatfor// "D:\\a\\1\\s\\src\\Platform\\Authenticat"...
0xc14  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganization(valuetype [mscorlib]System.Guid, int32, string, string)
0xc19  stloc.3
0xc1a  ldloc.3
0xc1b  ldstr    aSuspended// "Suspended"
0xc20  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xc25  brfalse.s loc_C39
0xc27  ldloc.3
0xc28  ldstr    aSuspended// "Suspended"
0xc2d  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xc32  unbox.any [mscorlib]System.Boolean
0xc37  brtrue.s loc_C49
0xc39  ldarg.0
0xc3a  ldc.i4.1
0xc3b  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::RedirectToNotificationUrl(valuetype [mscorlib]System.Guid, bool)
0xc40  br.s     loc_C49
0xc42  ldarg.0
0xc43  ldc.i4.1
0xc44  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::RedirectToNotificationUrl(valuetype [mscorlib]System.Guid, bool)
0xc49  ldc.i4.1
0xc4a  ldc.i4.0
0xc4b  ldc.i4.1
0xc4c  ldc.i4.1
0xc4d  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::RedirectIfFeatureIsDisabled(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.LiveFeatureType, bool, bool, bool)
0xc52  ldloca.s 1
0xc54  ldloc.0
0xc55  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xc5a  brtrue.s loc_C6A
0xc5c  ldstr    aOrganizationSc// "Organization.Scalegroup.Mismatch"
0xc61  ldc.i4.0
0xc62  ldc.i4.1
0xc63  ldc.i4.1
0xc64  ldc.i4.1
0xc65  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::RedirectToFeatureNotificationUrl(string, bool, bool, bool, bool)
0xc6a  ret
```
