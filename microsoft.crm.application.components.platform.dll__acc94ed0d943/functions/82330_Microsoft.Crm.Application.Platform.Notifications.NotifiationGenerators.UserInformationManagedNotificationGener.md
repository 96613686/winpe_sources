# Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.UserInformationManagedNotificationGenerator::AddNotificationIfNecessary

- ea: `0x82330`
- end: `0x82474`
- name: `Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.UserInformationManagedNotificationGenerator::AddNotificationIfNecessary`
- size: `324`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x11760`
- `0x16b80`
- `0x16b90`
- `0x30260`
- `0x3a980`
- `0x44960`
- `0x45120`
- `0x45de0`
- `0x5bab0`
- `0x5bac0`
- `0x5be20`
- `0x6a2d0`
- `0x82330`
- `0x8bb40`

## string_xrefs

- `0x82352`: `issyncwithdirectory`
- `0x82362`: `issyncwithdirectory`
- `0x8237b`: `Office365.Admin.Portal.Link`
- `0x823d6`: `<a href="{0}" class="default-link" target="userManagement">{1}</a>`
- `0x8244a`: `Web.biz.users.edit_user_osdp_deleted`

## pseudocode

```c

```

## disassembly

```asm
0x82330  call     bool Microsoft.Crm.Application.Utility.Util::IsOsdpOrganization()
0x82335  brfalse  loc_82473
0x8233a  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationId()
0x8233f  ldarg.1
0x82340  call     bool Microsoft.Crm.Application.Platform.Utility.GraphUserHelperWrapper::IsUserHardDeletedBasedOnSystemUserId(valuetype [mscorlib]System.Guid orgId, class Microsoft.Crm.Application.Platform.Entity systemUser)
0x82345  stloc.0
0x82346  ldloc.0
0x82347  brtrue   loc_82442
0x8234c  ldarg.1
0x8234d  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.Crm.Application.Platform.EntityBase::get_Properties()
0x82352  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x82357  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::ContainsKey(var<u1>)
0x8235c  brfalse  loc_82442
0x82361  ldarg.1
0x82362  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x82367  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8236c  unbox.any [mscorlib]System.Boolean
0x82371  brfalse  loc_82442
0x82376  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8237b  ldstr    aOffice365Admin// "Office365.Admin.Portal.Link"
0x82380  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x82385  stloc.1
0x82386  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8238b  ldstr    aWebBizUsersEdi_0// "Web.biz.users.edit_user_osdp.aspx"
0x82390  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x82395  stloc.2
0x82396  ldarg.1
0x82397  callvirt instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x8239c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x823a1  ldarg.1
0x823a2  callvirt instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x823a7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x823ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x823b1  call     class Microsoft.Crm.Application.ClientOrganizationContext Microsoft.Crm.Application.ClientOrganizationContext::get_Instance()
0x823b6  ldarg.1
0x823b7  callvirt instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x823bc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x823c1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx Microsoft.Crm.Application.ClientOrganizationContext::Get(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x823c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserId()
0x823cb  call     string Microsoft.Crm.Application.Utility.Util::RetrieveOffice365UserManagementUrl(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId)
0x823d0  stloc.3
0x823d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x823d6  ldstr    aAHref0ClassDef// "<a href=\"{0}\" class=\"default-link\" "...
0x823db  ldc.i4.2
0x823dc  newarr   [mscorlib]System.Object
0x823e1  dup
0x823e2  ldc.i4.0
0x823e3  ldloc.3
0x823e4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x823e9  stelem.ref
0x823ea  dup
0x823eb  ldc.i4.1
0x823ec  ldloc.1
0x823ed  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x823f2  stelem.ref
0x823f3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x823f8  stloc.s  4
0x823fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x823ff  ldloc.2
0x82400  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x82405  ldc.i4.1
0x82406  newarr   [mscorlib]System.Object
0x8240b  dup
0x8240c  ldc.i4.0
0x8240d  ldloc.s  4
0x8240f  stelem.ref
0x82410  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x82415  stloc.s  5
0x82417  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x8241c  ldloc.2
0x8241d  ldc.i4.1
0x8241e  newarr   [mscorlib]System.Object
0x82423  dup
0x82424  ldc.i4.0
0x82425  ldloc.1
0x82426  stelem.ref
0x82427  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8242c  stloc.s  6
0x8242e  ldc.i4.3
0x8242f  ldloc.s  5
0x82431  ldloc.s  6
0x82433  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateHtmlNotification(int32, string, string)
0x82438  stloc.s  7
0x8243a  ldarg.2
0x8243b  ldloc.s  7
0x8243d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x82442  ldloc.0
0x82443  brfalse.s loc_82473
0x82445  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8244a  ldstr    aWebBizUsersEdi_1// "Web.biz.users.edit_user_osdp_deleted"
0x8244f  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x82454  stloc.s  8
0x82456  ldloc.s  8
0x82458  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x8245d  stloc.s  9
0x8245f  ldc.i4.3
0x82460  ldloc.s  9
0x82462  ldloc.s  8
0x82464  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateHtmlNotification(int32, string, string)
0x82469  stloc.s  0xA
0x8246b  ldarg.2
0x8246c  ldloc.s  0xA
0x8246e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x82473  ret
```
