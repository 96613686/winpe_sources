# Microsoft.Crm.Application.Controls.AppHtmlBarControl::RenderEmailActivityControls

- ea: `0x883f0`
- end: `0x884bb`
- name: `Microsoft.Crm.Application.Controls.AppHtmlBarControl::RenderEmailActivityControls`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x88240`

## callees

- `0x881d0`
- `0x883f0`
- `0x885d0`
- `0x88610`

## string_xrefs

- `0x88447`: `ApplyTemplate();`
- `0x88452`: `HtmlBar_Title_InsertTemplate`
- `0x8845c`: `cmd_InsertEmailTemplate_16`
- `0x88461`: `idinserttemplate`

## pseudocode

```c

```

## disassembly

```asm
0x883f0  ldc.i4   0x7DA
0x883f5  ldc.i4.1
0x883f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x883fb  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x88400  brtrue.s loc_88414
0x88402  ldc.i4.s 0x7F
0x88404  ldc.i4.1
0x88405  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8840a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8840f  brfalse  loc_884BA
0x88414  ldarg.0
0x88415  ldarg.1
0x88416  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter)
0x8841b  ldarg.0
0x8841c  ldc.i4.0
0x8841d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::set_AllowSpacer(bool)
0x88422  ldc.i4   0x7DA
0x88427  ldc.i4.1
0x88428  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8842d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x88432  brfalse.s loc_88472
0x88434  ldarg.0
0x88435  ldfld    valuetype Microsoft.Crm.Application.Controls.HtmlBarHeaderType Microsoft.Crm.Application.Controls.AppHtmlBarControl::_headerType
0x8843a  ldc.i4.2
0x8843b  bne.un.s loc_88472
0x8843d  ldarg.0
0x8843e  call     instance bool Microsoft.Crm.Application.Controls.AppHtmlBarControl::get_DisableTemplate()
0x88443  brtrue.s loc_88472
0x88445  ldarg.0
0x88446  ldarg.1
0x88447  ldstr    aApplytemplate// "ApplyTemplate();"
0x8844c  ldarg.0
0x8844d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppHtmlBarControl::_rm
0x88452  ldstr    aHtmlbarTitleIn// "HtmlBar_Title_InsertTemplate"
0x88457  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8845c  ldstr    aCmdInsertemail// "cmd_InsertEmailTemplate_16"
0x88461  ldstr    aIdinserttempla// "idinserttemplate"
0x88466  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::AddTextButton(class [mscorlib]System.IO.TextWriter, string, string, string, string)
0x8846b  ldarg.0
0x8846c  ldc.i4.1
0x8846d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::set_AllowSpacer(bool)
0x88472  ldarg.0
0x88473  ldarg.1
0x88474  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter)
0x88479  ldarg.0
0x8847a  ldarg.1
0x8847b  call     instance void Microsoft.Crm.Application.Controls.AppHtmlBarControl::AddInsertKBArticleButton(class [mscorlib]System.IO.TextWriter writer)
0x88480  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x88485  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x8848a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EmailSignature()
0x8848f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x88494  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x88499  brfalse.s loc_884BA
0x8849b  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadEmailSignature()
0x884a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x884a5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x884aa  brfalse.s loc_884BA
0x884ac  ldarg.0
0x884ad  ldarg.1
0x884ae  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter)
0x884b3  ldarg.0
0x884b4  ldarg.1
0x884b5  call     instance void Microsoft.Crm.Application.Controls.AppHtmlBarControl::AddInsertEmailSignatureButton(class [mscorlib]System.IO.TextWriter writer)
0x884ba  ret
```
