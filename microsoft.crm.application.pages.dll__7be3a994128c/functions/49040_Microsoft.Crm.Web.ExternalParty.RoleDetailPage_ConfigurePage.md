# Microsoft.Crm.Web.ExternalParty.RoleDetailPage::ConfigurePage

- ea: `0x49040`
- end: `0x49352`
- name: `Microsoft.Crm.Web.ExternalParty.RoleDetailPage::ConfigurePage`
- size: `786`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## string_xrefs

- `0x49073`: `Web.Biz.Roles.edit_role.aspx_create`
- `0x49089`: `Web.Biz.Roles.edit_role.aspx_read`
- `0x4909f`: `Web.Biz.Roles.edit_role.aspx_write`
- `0x49105`: `LOCID_NO_CREATEUSER_PRIV_TITLE`
- `0x49110`: `ALERT_INSUFFICIENT_CREATEUSERSETTINGS_PRIV_TITLE`
- `0x49126`: `LOCID_NO_CREATEUSER_PRIV_OK`
- `0x49131`: `ALERT_INSUFFICIENT_CREATEUSERSETTINGS_PRIV_OK`
- `0x49147`: `LOCID_NO_CREATEUSER_PRIV_CANCEL`
- `0x49152`: `ALERT_INSUFFICIENT_CREATEUSERSETTINGS_PRIV_CANCEL`
- `0x4921a`: `LOCID_PRIVTYPE_CREATE`
- `0x49231`: `LOCID_PRIVTYPE_READ`
- `0x49248`: `LOCID_PRIVTYPE_WRITE`
- `0x4925f`: `_iPrivilegeLevelNone`
- `0x49271`: `_iPrivilegeLevelBasic`
- `0x49283`: `_iPrivilegeLevelLocal`
- `0x49295`: `_iPrivilegeLevelGlobal`
- `0x492a7`: `_sPrivilegeLevelNone`
- `0x492c1`: `_sPrivilegeLevelBasic`
- `0x492db`: `_sPrivilegeLevelLocal`
- `0x492f5`: `_sPrivilegeLevelGlobal`
- `0x4930f`: `_sPrivilegeColNone`
- `0x49321`: `_sPrivilegeColCreate`
- `0x49333`: `_sPrivilegeColRead`
- `0x49345`: `_sPrivilegeColWrite`
- `0x49047`: `Privileges.ExternalParty.Alt.Tag.Format`
- `0x4905d`: `Privileges.ExternalParty.Misc.Alt.Tag.Format`

## pseudocode

```c

```

## disassembly

```asm
0x49040  ldarg.0
0x49041  ldarg.0
0x49042  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x49047  ldstr    aPrivilegesExte// "Privileges.ExternalParty.Alt.Tag.Format"
0x4904c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x49051  stfld    string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_altTagFormat
0x49056  ldarg.0
0x49057  ldarg.0
0x49058  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4905d  ldstr    aPrivilegesExte_0// "Privileges.ExternalParty.Misc.Alt.Tag.F"...
0x49062  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x49067  stfld    string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_altTagFormatMisc
0x4906c  ldarg.0
0x4906d  ldarg.0
0x4906e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x49073  ldstr    aWebBizRolesEdi// "Web.Biz.Roles.edit_role.aspx_create"
0x49078  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4907d  stfld    string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_privTypeCreate
0x49082  ldarg.0
0x49083  ldarg.0
0x49084  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x49089  ldstr    aWebBizRolesEdi_0// "Web.Biz.Roles.edit_role.aspx_read"
0x4908e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x49093  stfld    string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_privTypeRead
0x49098  ldarg.0
0x49099  ldarg.0
0x4909a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4909f  ldstr    aWebBizRolesEdi_1// "Web.Biz.Roles.edit_role.aspx_write"
0x490a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x490a9  stfld    string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_privTypeWrite
0x490ae  ldarg.0
0x490af  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x490b4  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0x490b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x490be  ldarg.0
0x490bf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x490c4  ldstr    aStaticBizRoles// "/_static/biz/roles/controls/roles.js"
0x490c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x490ce  ldarg.0
0x490cf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x490d4  ldstr    aStaticControls_11// "/_static/_controls/ExternalPartyRoles/a"...
0x490d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x490de  ldarg.0
0x490df  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x490e4  ldstr    aLocidToggleRow// "LOCID_TOGGLE_ROW_PRIV"
0x490e9  ldarg.0
0x490ea  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x490ef  ldstr    aWebBizRolesEdi_7// "Web.Biz.Roles.edit_role.aspx_rowTip"
0x490f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x490f9  ldc.i4.0
0x490fa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x490ff  ldarg.0
0x49100  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49105  ldstr    aLocidNoCreateu// "LOCID_NO_CREATEUSER_PRIV_TITLE"
0x4910a  ldarg.0
0x4910b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x49110  ldstr    aAlertInsuffici// "ALERT_INSUFFICIENT_CREATEUSERSETTINGS_P"...
0x49115  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4911a  ldc.i4.0
0x4911b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x49120  ldarg.0
0x49121  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49126  ldstr    aLocidNoCreateu_0// "LOCID_NO_CREATEUSER_PRIV_OK"
0x4912b  ldarg.0
0x4912c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x49131  ldstr    aAlertInsuffici_0// "ALERT_INSUFFICIENT_CREATEUSERSETTINGS_P"...
0x49136  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4913b  ldc.i4.0
0x4913c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x49141  ldarg.0
0x49142  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49147  ldstr    aLocidNoCreateu_1// "LOCID_NO_CREATEUSER_PRIV_CANCEL"
0x4914c  ldarg.0
0x4914d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x49152  ldstr    aAlertInsuffici_1// "ALERT_INSUFFICIENT_CREATEUSERSETTINGS_P"...
0x49157  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4915c  ldc.i4.0
0x4915d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x49162  ldarg.0
0x49163  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49168  ldstr    aLocidBizRoleNo// "LOCID_BIZ_ROLE_NONE"
0x4916d  ldarg.0
0x4916e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x49173  ldstr    aWebBizRolesEdi_20// "Web.Biz.Roles.edit_role.aspx_externalpa"...
0x49178  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4917d  ldc.i4.0
0x4917e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x49183  ldarg.0
0x49184  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49189  ldstr    aLocidBizRoleBa// "LOCID_BIZ_ROLE_BASIC"
0x4918e  ldarg.0
0x4918f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x49194  ldstr    aWebBizRolesEdi_21// "Web.Biz.Roles.edit_role.aspx_externalpa"...
0x49199  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4919e  ldc.i4.0
0x4919f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x491a4  ldarg.0
0x491a5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x491aa  ldstr    aLocidBizRoleLo// "LOCID_BIZ_ROLE_LOCAL"
0x491af  ldarg.0
0x491b0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x491b5  ldstr    aWebBizRolesEdi_22// "Web.Biz.Roles.edit_role.aspx_externalpa"...
0x491ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x491bf  ldc.i4.0
0x491c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x491c5  ldarg.0
0x491c6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x491cb  ldstr    aLocidBizRoleGl// "LOCID_BIZ_ROLE_GLOBAL"
0x491d0  ldarg.0
0x491d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x491d6  ldstr    aWebBizRolesEdi_23// "Web.Biz.Roles.edit_role.aspx_externalpa"...
0x491db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x491e0  ldc.i4.0
0x491e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x491e6  ldarg.0
0x491e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x491ec  ldstr    aLocidFormatAlt// "LOCID_FORMAT_ALTTAG"
0x491f1  ldarg.0
0x491f2  ldfld    string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_altTagFormat
0x491f7  ldc.i4.0
0x491f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x491fd  ldarg.0
0x491fe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49203  ldstr    aLocidFormatAlt_0// "LOCID_FORMAT_ALTTAGMISC"
0x49208  ldarg.0
0x49209  ldfld    string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_altTagFormatMisc
0x4920e  ldc.i4.0
0x4920f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x49214  ldarg.0
0x49215  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4921a  ldstr    aLocidPrivtypeC// "LOCID_PRIVTYPE_CREATE"
0x4921f  ldarg.0
0x49220  ldfld    string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_privTypeCreate
0x49225  ldc.i4.0
0x49226  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4922b  ldarg.0
0x4922c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49231  ldstr    aLocidPrivtypeR// "LOCID_PRIVTYPE_READ"
0x49236  ldarg.0
0x49237  ldfld    string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_privTypeRead
0x4923c  ldc.i4.0
0x4923d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x49242  ldarg.0
0x49243  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49248  ldstr    aLocidPrivtypeW// "LOCID_PRIVTYPE_WRITE"
0x4924d  ldarg.0
0x4924e  ldfld    string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_privTypeWrite
0x49253  ldc.i4.0
0x49254  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x49259  ldarg.0
0x4925a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4925f  ldstr    aIprivilegeleve// "_iPrivilegeLevelNone"
0x49264  ldc.i4.0
0x49265  conv.i8
0x49266  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x4926b  ldarg.0
0x4926c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49271  ldstr    aIprivilegeleve_0// "_iPrivilegeLevelBasic"
0x49276  ldc.i4.1
0x49277  conv.i8
0x49278  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x4927d  ldarg.0
0x4927e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49283  ldstr    aIprivilegeleve_1// "_iPrivilegeLevelLocal"
0x49288  ldc.i4.2
0x49289  conv.i8
0x4928a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x4928f  ldarg.0
0x49290  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49295  ldstr    aIprivilegeleve_3// "_iPrivilegeLevelGlobal"
0x4929a  ldc.i4.8
0x4929b  conv.i8
0x4929c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x492a1  ldarg.0
0x492a2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x492a7  ldstr    aSprivilegeleve// "_sPrivilegeLevelNone"
0x492ac  ldstr    aX_0// "X"
0x492b1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x492b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x492bb  ldarg.0
0x492bc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x492c1  ldstr    aSprivilegeleve_0// "_sPrivilegeLevelBasic"
0x492c6  ldstr    aB// "B"
0x492cb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x492d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x492d5  ldarg.0
0x492d6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x492db  ldstr    aSprivilegeleve_1// "_sPrivilegeLevelLocal"
0x492e0  ldstr    aL// "L"
0x492e5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x492ea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x492ef  ldarg.0
0x492f0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x492f5  ldstr    aSprivilegeleve_3// "_sPrivilegeLevelGlobal"
0x492fa  ldstr    aG// "G"
0x492ff  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x49304  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x49309  ldarg.0
0x4930a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4930f  ldstr    aSprivilegecoln// "_sPrivilegeColNone"
0x49314  ldc.i4.m1
0x49315  conv.i8
0x49316  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x4931b  ldarg.0
0x4931c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49321  ldstr    aSprivilegecolc// "_sPrivilegeColCreate"
0x49326  ldc.i4.0
0x49327  conv.i8
0x49328  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x4932d  ldarg.0
0x4932e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49333  ldstr    aSprivilegecolr// "_sPrivilegeColRead"
0x49338  ldc.i4.1
0x49339  conv.i8
0x4933a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x4933f  ldarg.0
0x49340  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x49345  ldstr    aSprivilegecolw// "_sPrivilegeColWrite"
0x4934a  ldc.i4.2
0x4934b  conv.i8
0x4934c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x49351  ret
```
