# Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::ConfigurePage

- ea: `0x32da0`
- end: `0x33264`
- name: `Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::ConfigurePage`
- size: `1220`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## string_xrefs

- `0x32da7`: `Privileges.Alt.Tag.Format`
- `0x32dbd`: `Privileges.Misc.Alt.Tag.Format`
- `0x32dd3`: `Web.Biz.Roles.edit_role.aspx_create`
- `0x32de9`: `Web.Biz.Roles.edit_role.aspx_read`
- `0x32dff`: `Web.Biz.Roles.edit_role.aspx_write`
- `0x32e15`: `Web.Biz.Roles.edit_role.aspx_delete`
- `0x32ed3`: `LOCID_NO_CREATEUSER_PRIV_TITLE`
- `0x32ede`: `ALERT_INSUFFICIENT_CREATEUSERSETTINGS_PRIV_TITLE`
- `0x32ef4`: `LOCID_NO_CREATEUSER_PRIV_OK`
- `0x32eff`: `ALERT_INSUFFICIENT_CREATEUSERSETTINGS_PRIV_OK`
- `0x32f15`: `LOCID_NO_CREATEUSER_PRIV_CANCEL`
- `0x32f20`: `ALERT_INSUFFICIENT_CREATEUSERSETTINGS_PRIV_CANCEL`
- `0x33009`: `LOCID_PRIVTYPE_CREATE`
- `0x33020`: `LOCID_PRIVTYPE_READ`
- `0x33037`: `LOCID_PRIVTYPE_WRITE`
- `0x3304e`: `LOCID_PRIVTYPE_DELETE`
- `0x330c1`: `_iPrivilegeLevelNone`
- `0x330d3`: `_iPrivilegeLevelBasic`
- `0x330e5`: `_iPrivilegeLevelLocal`
- `0x330f7`: `_iPrivilegeLevelDeep`
- `0x33109`: `_iPrivilegeLevelGlobal`
- `0x3311b`: `_sPrivilegeLevelNone`
- `0x33135`: `_sPrivilegeLevelBasic`
- `0x3314f`: `_sPrivilegeLevelLocal`
- `0x33169`: `_sPrivilegeLevelDeep`
- `0x33183`: `_sPrivilegeLevelGlobal`
- `0x3319d`: `_sPrivilegeColNone`
- `0x331af`: `_sPrivilegeColCreate`
- `0x331c1`: `_sPrivilegeColRead`
- `0x331d3`: `_sPrivilegeColWrite`
- `0x331e5`: `_sPrivilegeColDelete`
- `0x331f7`: `_sPrivilegeColAppend`
- `0x33209`: `_sPrivilegeColAppendTo`
- `0x3321b`: `_sPrivilegeColAssign`
- `0x3322d`: `_sPrivilegeColShare`

## pseudocode

```c

```

## disassembly

```asm
0x32da0  ldarg.0
0x32da1  ldarg.0
0x32da2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32da7  ldstr    aPrivilegesAltT// "Privileges.Alt.Tag.Format"
0x32dac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32db1  stfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_altTagFormat
0x32db6  ldarg.0
0x32db7  ldarg.0
0x32db8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32dbd  ldstr    aPrivilegesMisc// "Privileges.Misc.Alt.Tag.Format"
0x32dc2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32dc7  stfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_altTagFormatMisc
0x32dcc  ldarg.0
0x32dcd  ldarg.0
0x32dce  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32dd3  ldstr    aWebBizRolesEdi// "Web.Biz.Roles.edit_role.aspx_create"
0x32dd8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32ddd  stfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeCreate
0x32de2  ldarg.0
0x32de3  ldarg.0
0x32de4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32de9  ldstr    aWebBizRolesEdi_0// "Web.Biz.Roles.edit_role.aspx_read"
0x32dee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32df3  stfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeRead
0x32df8  ldarg.0
0x32df9  ldarg.0
0x32dfa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32dff  ldstr    aWebBizRolesEdi_1// "Web.Biz.Roles.edit_role.aspx_write"
0x32e04  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32e09  stfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeWrite
0x32e0e  ldarg.0
0x32e0f  ldarg.0
0x32e10  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32e15  ldstr    aWebBizRolesEdi_2// "Web.Biz.Roles.edit_role.aspx_delete"
0x32e1a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32e1f  stfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeDelete
0x32e24  ldarg.0
0x32e25  ldarg.0
0x32e26  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32e2b  ldstr    aWebBizRolesEdi_3// "Web.Biz.Roles.edit_role.aspx_append"
0x32e30  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32e35  stfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeAppend
0x32e3a  ldarg.0
0x32e3b  ldarg.0
0x32e3c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32e41  ldstr    aWebBizRolesEdi_4// "Web.Biz.Roles.edit_role.aspx_appendto"
0x32e46  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32e4b  stfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeAppendTo
0x32e50  ldarg.0
0x32e51  ldarg.0
0x32e52  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32e57  ldstr    aWebBizRolesEdi_5// "Web.Biz.Roles.edit_role.aspx_assign"
0x32e5c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32e61  stfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeAssign
0x32e66  ldarg.0
0x32e67  ldarg.0
0x32e68  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32e6d  ldstr    aWebBizRolesEdi_6// "Web.Biz.Roles.edit_role.aspx_share"
0x32e72  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32e77  stfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeShare
0x32e7c  ldarg.0
0x32e7d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32e82  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0x32e87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x32e8c  ldarg.0
0x32e8d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32e92  ldstr    aStaticBizRoles// "/_static/biz/roles/controls/roles.js"
0x32e97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x32e9c  ldarg.0
0x32e9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32ea2  ldstr    aStaticBizRoles_0// "/_static/biz/roles/scripts/actions.js"
0x32ea7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x32eac  ldarg.0
0x32ead  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32eb2  ldstr    aLocidToggleRow// "LOCID_TOGGLE_ROW_PRIV"
0x32eb7  ldarg.0
0x32eb8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32ebd  ldstr    aWebBizRolesEdi_7// "Web.Biz.Roles.edit_role.aspx_rowTip"
0x32ec2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32ec7  ldc.i4.0
0x32ec8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x32ecd  ldarg.0
0x32ece  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32ed3  ldstr    aLocidNoCreateu// "LOCID_NO_CREATEUSER_PRIV_TITLE"
0x32ed8  ldarg.0
0x32ed9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32ede  ldstr    aAlertInsuffici// "ALERT_INSUFFICIENT_CREATEUSERSETTINGS_P"...
0x32ee3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32ee8  ldc.i4.0
0x32ee9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x32eee  ldarg.0
0x32eef  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32ef4  ldstr    aLocidNoCreateu_0// "LOCID_NO_CREATEUSER_PRIV_OK"
0x32ef9  ldarg.0
0x32efa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32eff  ldstr    aAlertInsuffici_0// "ALERT_INSUFFICIENT_CREATEUSERSETTINGS_P"...
0x32f04  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32f09  ldc.i4.0
0x32f0a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x32f0f  ldarg.0
0x32f10  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32f15  ldstr    aLocidNoCreateu_1// "LOCID_NO_CREATEUSER_PRIV_CANCEL"
0x32f1a  ldarg.0
0x32f1b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32f20  ldstr    aAlertInsuffici_1// "ALERT_INSUFFICIENT_CREATEUSERSETTINGS_P"...
0x32f25  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32f2a  ldc.i4.0
0x32f2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x32f30  ldarg.0
0x32f31  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32f36  ldstr    aLocidBizRoleNo// "LOCID_BIZ_ROLE_NONE"
0x32f3b  ldarg.0
0x32f3c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32f41  ldstr    aWebBizRolesEdi_8// "Web.Biz.Roles.edit_role.aspx_none"
0x32f46  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32f4b  ldc.i4.0
0x32f4c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x32f51  ldarg.0
0x32f52  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32f57  ldstr    aLocidBizRoleBa// "LOCID_BIZ_ROLE_BASIC"
0x32f5c  ldarg.0
0x32f5d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32f62  ldstr    aWebBizRolesEdi_9// "Web.Biz.Roles.edit_role.aspx_basic"
0x32f67  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32f6c  ldc.i4.0
0x32f6d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x32f72  ldarg.0
0x32f73  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32f78  ldstr    aLocidBizRoleLo// "LOCID_BIZ_ROLE_LOCAL"
0x32f7d  ldarg.0
0x32f7e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32f83  ldstr    aWebBizRolesEdi_10// "Web.Biz.Roles.edit_role.aspx_local"
0x32f88  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32f8d  ldc.i4.0
0x32f8e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x32f93  ldarg.0
0x32f94  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32f99  ldstr    aLocidBizRoleDe// "LOCID_BIZ_ROLE_DEEP"
0x32f9e  ldarg.0
0x32f9f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32fa4  ldstr    aWebBizRolesEdi_11// "Web.Biz.Roles.edit_role.aspx_deep"
0x32fa9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32fae  ldc.i4.0
0x32faf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x32fb4  ldarg.0
0x32fb5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32fba  ldstr    aLocidBizRoleGl// "LOCID_BIZ_ROLE_GLOBAL"
0x32fbf  ldarg.0
0x32fc0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32fc5  ldstr    aWebBizRolesEdi_12// "Web.Biz.Roles.edit_role.aspx_global"
0x32fca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32fcf  ldc.i4.0
0x32fd0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x32fd5  ldarg.0
0x32fd6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32fdb  ldstr    aLocidFormatAlt// "LOCID_FORMAT_ALTTAG"
0x32fe0  ldarg.0
0x32fe1  ldfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_altTagFormat
0x32fe6  ldc.i4.0
0x32fe7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x32fec  ldarg.0
0x32fed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32ff2  ldstr    aLocidFormatAlt_0// "LOCID_FORMAT_ALTTAGMISC"
0x32ff7  ldarg.0
0x32ff8  ldfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_altTagFormatMisc
0x32ffd  ldc.i4.0
0x32ffe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x33003  ldarg.0
0x33004  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x33009  ldstr    aLocidPrivtypeC// "LOCID_PRIVTYPE_CREATE"
0x3300e  ldarg.0
0x3300f  ldfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeCreate
0x33014  ldc.i4.0
0x33015  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3301a  ldarg.0
0x3301b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x33020  ldstr    aLocidPrivtypeR// "LOCID_PRIVTYPE_READ"
0x33025  ldarg.0
0x33026  ldfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeRead
0x3302b  ldc.i4.0
0x3302c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x33031  ldarg.0
0x33032  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x33037  ldstr    aLocidPrivtypeW// "LOCID_PRIVTYPE_WRITE"
0x3303c  ldarg.0
0x3303d  ldfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeWrite
0x33042  ldc.i4.0
0x33043  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x33048  ldarg.0
0x33049  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3304e  ldstr    aLocidPrivtypeD// "LOCID_PRIVTYPE_DELETE"
0x33053  ldarg.0
0x33054  ldfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeDelete
0x33059  ldc.i4.0
0x3305a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3305f  ldarg.0
0x33060  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x33065  ldstr    aLocidPrivtypeA// "LOCID_PRIVTYPE_APPEND"
0x3306a  ldarg.0
0x3306b  ldfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeAppend
0x33070  ldc.i4.0
0x33071  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x33076  ldarg.0
0x33077  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3307c  ldstr    aLocidPrivtypeA_0// "LOCID_PRIVTYPE_APPENDTO"
0x33081  ldarg.0
0x33082  ldfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeAppendTo
0x33087  ldc.i4.0
0x33088  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3308d  ldarg.0
0x3308e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x33093  ldstr    aLocidPrivtypeA_1// "LOCID_PRIVTYPE_ASSIGN"
0x33098  ldarg.0
0x33099  ldfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeAssign
0x3309e  ldc.i4.0
0x3309f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x330a4  ldarg.0
0x330a5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x330aa  ldstr    aLocidPrivtypeS// "LOCID_PRIVTYPE_SHARE"
0x330af  ldarg.0
0x330b0  ldfld    string Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_privTypeShare
0x330b5  ldc.i4.0
0x330b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x330bb  ldarg.0
0x330bc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x330c1  ldstr    aIprivilegeleve// "_iPrivilegeLevelNone"
0x330c6  ldc.i4.0
0x330c7  conv.i8
0x330c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x330cd  ldarg.0
0x330ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x330d3  ldstr    aIprivilegeleve_0// "_iPrivilegeLevelBasic"
0x330d8  ldc.i4.1
0x330d9  conv.i8
0x330da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x330df  ldarg.0
0x330e0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x330e5  ldstr    aIprivilegeleve_1// "_iPrivilegeLevelLocal"
0x330ea  ldc.i4.2
0x330eb  conv.i8
0x330ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x330f1  ldarg.0
0x330f2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x330f7  ldstr    aIprivilegeleve_2// "_iPrivilegeLevelDeep"
0x330fc  ldc.i4.4
0x330fd  conv.i8
0x330fe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x33103  ldarg.0
0x33104  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x33109  ldstr    aIprivilegeleve_3// "_iPrivilegeLevelGlobal"
0x3310e  ldc.i4.8
0x3310f  conv.i8
0x33110  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x33115  ldarg.0
0x33116  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3311b  ldstr    aSprivilegeleve// "_sPrivilegeLevelNone"
0x33120  ldstr    aX_0// "X"
0x33125  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x3312a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x3312f  ldarg.0
0x33130  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x33135  ldstr    aSprivilegeleve_0// "_sPrivilegeLevelBasic"
0x3313a  ldstr    aB// "B"
0x3313f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x33144  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x33149  ldarg.0
0x3314a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3314f  ldstr    aSprivilegeleve_1// "_sPrivilegeLevelLocal"
0x33154  ldstr    aL// "L"
0x33159  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x3315e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x33163  ldarg.0
0x33164  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x33169  ldstr    aSprivilegeleve_2// "_sPrivilegeLevelDeep"
0x3316e  ldstr    aD// "D"
0x33173  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x33178  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x3317d  ldarg.0
0x3317e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x33183  ldstr    aSprivilegeleve_3// "_sPrivilegeLevelGlobal"
0x33188  ldstr    aG// "G"
0x3318d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x33192  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x33197  ldarg.0
0x33198  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3319d  ldstr    aSprivilegecoln// "_sPrivilegeColNone"
0x331a2  ldc.i4.m1
0x331a3  conv.i8
0x331a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x331a9  ldarg.0
0x331aa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x331af  ldstr    aSprivilegecolc// "_sPrivilegeColCreate"
0x331b4  ldc.i4.0
0x331b5  conv.i8
0x331b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x331bb  ldarg.0
0x331bc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x331c1  ldstr    aSprivilegecolr// "_sPrivilegeColRead"
0x331c6  ldc.i4.1
0x331c7  conv.i8
  ... truncated ...
```
