# Microsoft.Crm.Web.MainPage::UpdateTimeZone

- ea: `0x26f90`
- end: `0x2708e`
- name: `Microsoft.Crm.Web.MainPage::UpdateTimeZone`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x26b50`

## callees

- `0x26f90`

## string_xrefs

- `0x26f9b`: `updatetimezone`
- `0x26fe1`: `updatetimezone`
- `0x27038`: `UPDATE_TIMEZONE`
- `0x2706e`: `UPDATE_TIMEZONE`
- `0x27081`: `UPDATE_TIMEZONE`

## pseudocode

```c

```

## disassembly

```asm
0x26f90  ldarg.0
0x26f91  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x26f96  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x26f9b  ldstr    aUpdatetimezone// "updatetimezone"
0x26fa0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x26fa5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x26faa  brtrue   loc_27045
0x26faf  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x26fb4  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x26fb9  ldc.i4.2
0x26fba  bne.un   loc_27045
0x26fbf  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x26fc4  ldarg.0
0x26fc5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x26fca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x26fcf  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x26fd4  brtrue.s loc_27045
0x26fd6  ldarg.0
0x26fd7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x26fdc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x26fe1  ldstr    aUpdatetimezone// "updatetimezone"
0x26fe6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x26feb  call     bool [mscorlib]System.Boolean::Parse(string)
0x26ff0  brfalse.s loc_27045
0x26ff2  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetLatestInvitationExpirationDate()
0x26ff7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x26ffc  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x27001  brtrue.s loc_27032
0x27003  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetLatestInvitationExpirationDate()
0x27008  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x2700d  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x27012  brfalse.s loc_27045
0x27014  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x27019  ldarg.0
0x2701a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x2701f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x27024  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x27029  brtrue.s loc_27045
0x2702b  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.SecurityUtility::IsCurrentUserLiveBillingAdmin()
0x27030  brfalse.s loc_27045
0x27032  ldarg.0
0x27033  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x27038  ldstr    aUpdateTimezone// "UPDATE_TIMEZONE"
0x2703d  ldc.i4.1
0x2703e  conv.i8
0x2703f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x27044  ret
0x27045  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x2704a  ldarg.0
0x2704b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x27050  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x27055  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x2705a  brfalse.s loc_2707B
0x2705c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x27061  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_InviteStatusCode()
0x27066  brtrue.s loc_2707B
0x27068  ldarg.0
0x27069  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2706e  ldstr    aUpdateTimezone// "UPDATE_TIMEZONE"
0x27073  ldc.i4.1
0x27074  conv.i8
0x27075  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x2707a  ret
0x2707b  ldarg.0
0x2707c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x27081  ldstr    aUpdateTimezone// "UPDATE_TIMEZONE"
0x27086  ldc.i4.0
0x27087  conv.i8
0x27088  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x2708d  ret
```
