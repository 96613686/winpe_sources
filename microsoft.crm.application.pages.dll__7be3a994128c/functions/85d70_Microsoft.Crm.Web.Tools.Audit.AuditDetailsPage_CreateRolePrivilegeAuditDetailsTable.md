# Microsoft.Crm.Web.Tools.Audit.AuditDetailsPage::CreateRolePrivilegeAuditDetailsTable

- ea: `0x85d70`
- end: `0x85ed0`
- name: `Microsoft.Crm.Web.Tools.Audit.AuditDetailsPage::CreateRolePrivilegeAuditDetailsTable`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x85a20`

## callees

- `0x85d70`
- `0x85f90`
- `0x86050`
- `0x860f0`

## string_xrefs

- `0x85d76`: `Audit.DetailsPage.PrivilegeName`
- `0x85d87`: `Audit.DetailsPage.OldPrivilegeDepth`
- `0x85d98`: `Audit.DetailsPage.NewPrivilegeDepth`
- `0x85da9`: `Audit.DetailsPage.PrivilegeDepth`
- `0x85dea`: `Audit.DetailsPage.InfoBar.NoPrivilegesChanged`

## pseudocode

```c

```

## disassembly

```asm
0x85d70  ldarg.0
0x85d71  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x85d76  ldstr    aAuditDetailspa_7// "Audit.DetailsPage.PrivilegeName"
0x85d7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x85d80  stloc.0
0x85d81  ldarg.0
0x85d82  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x85d87  ldstr    aAuditDetailspa_8// "Audit.DetailsPage.OldPrivilegeDepth"
0x85d8c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x85d91  stloc.1
0x85d92  ldarg.0
0x85d93  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x85d98  ldstr    aAuditDetailspa_9// "Audit.DetailsPage.NewPrivilegeDepth"
0x85d9d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x85da2  stloc.2
0x85da3  ldarg.0
0x85da4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x85da9  ldstr    aAuditDetailspa_10// "Audit.DetailsPage.PrivilegeDepth"
0x85dae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x85db3  stloc.3
0x85db4  ldarg.0
0x85db5  ldloc.0
0x85db6  ldloc.1
0x85db7  ldloc.2
0x85db8  ldloc.3
0x85db9  call     instance void Microsoft.Crm.Web.Tools.Audit.AuditDetailsPage::AddHeaderRow(string fieldCol, string oldValueCol, string newValueCol, string valueCol)
0x85dbe  ldarg.1
0x85dbf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AuditDetail::get_AuditRecord()
0x85dc4  ldstr    aAttributemask// "attributemask"
0x85dc9  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x85dce  castclass [mscorlib]System.String
0x85dd3  stloc.s  4
0x85dd5  ldloc.s  4
0x85dd7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x85ddc  brfalse.s loc_85DFA
0x85dde  ldarg.0
0x85ddf  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.Audit.AuditDetailsPage::infoBar
0x85de4  ldarg.0
0x85de5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x85dea  ldstr    aAuditDetailspa_11// "Audit.DetailsPage.InfoBar.NoPrivilegesC"...
0x85def  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x85df4  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x85df9  ret
0x85dfa  ldarg.0
0x85dfb  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.Audit.AuditDetailsPage::infoBar
0x85e00  ldarg.0
0x85e01  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x85e06  ldstr    aAuditDetailspa_6// "Audit.DetailsPage.InfoBar.d"
0x85e0b  ldarg.0
0x85e0c  ldfld    int32 Microsoft.Crm.Web.Tools.Audit.AuditDetailsPage::_action
0x85e11  box      [mscorlib]System.Int32
0x85e16  call     string [mscorlib]System.String::Concat(object, object)
0x85e1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x85e20  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x85e25  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x85e2a  ldloc.s  4
0x85e2c  ldc.i4.1
0x85e2d  newarr   [mscorlib]System.Char
0x85e32  dup
0x85e33  ldc.i4.0
0x85e34  ldc.i4.s 0x2C
0x85e36  stelem.i2
0x85e37  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x85e3c  stloc.s  5
0x85e3e  ldloc.s  5
0x85e40  ldlen
0x85e41  conv.i4
0x85e42  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object[]>>::.ctor(int32)
0x85e47  stloc.s  6
0x85e49  ldc.i4.0
0x85e4a  stloc.s  7
0x85e4c  br.s     loc_85EBF
0x85e4e  ldloca.s 8
0x85e50  ldloc.s  5
0x85e52  ldloc.s  7
0x85e54  ldelem.ref
0x85e55  call     instance void [mscorlib]System.Guid::.ctor(string)
0x85e5a  ldloc.s  8
0x85e5c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuditAppHelper::GetPrivilegeDisplayName(valuetype [mscorlib]System.Guid)
0x85e61  stloc.s  9
0x85e63  ldarg.1
0x85e64  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege[] [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilegeAuditDetail::get_OldRolePrivileges()
0x85e69  ldloc.s  7
0x85e6b  ldelem.ref
0x85e6c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuditAppHelper::GetPrivilegeDepthDisplayString(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege)
0x85e71  stloc.s  0xA
0x85e73  ldsfld   string [mscorlib]System.String::Empty
0x85e78  stloc.s  0xB
0x85e7a  ldarg.1
0x85e7b  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege[] [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilegeAuditDetail::get_NewRolePrivileges()
0x85e80  ldloc.s  7
0x85e82  ldelem.ref
0x85e83  brtrue.s loc_85E99
0x85e85  ldarg.1
0x85e86  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilegeAuditDetail::get_InvalidNewPrivileges()
0x85e8b  ldloc.s  8
0x85e8d  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x85e92  brfalse.s loc_85E99
0x85e94  ldnull
0x85e95  stloc.s  0xB
0x85e97  br.s     loc_85EA9
0x85e99  ldarg.1
0x85e9a  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege[] [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilegeAuditDetail::get_NewRolePrivileges()
0x85e9f  ldloc.s  7
0x85ea1  ldelem.ref
0x85ea2  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuditAppHelper::GetPrivilegeDepthDisplayString(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege)
0x85ea7  stloc.s  0xB
0x85ea9  ldarg.0
0x85eaa  ldloc.s  6
0x85eac  ldloc.s  9
0x85eae  ldloc.s  9
0x85eb0  ldloc.s  0xA
0x85eb2  ldloc.s  0xB
0x85eb4  call     instance void Microsoft.Crm.Web.Tools.Audit.AuditDetailsPage::AddToSortedList(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object[]>> sortedList, string attributeLogicalName, string attributeDisplayName, object oldValue, object newValue)
0x85eb9  ldloc.s  7
0x85ebb  ldc.i4.1
0x85ebc  add
0x85ebd  stloc.s  7
0x85ebf  ldloc.s  7
0x85ec1  ldloc.s  5
0x85ec3  ldlen
0x85ec4  conv.i4
0x85ec5  blt.s    loc_85E4E
0x85ec7  ldarg.0
0x85ec8  ldloc.s  6
0x85eca  call     instance void Microsoft.Crm.Web.Tools.Audit.AuditDetailsPage::SortAndAddToTable(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object[]>> sortedList)
0x85ecf  ret
```
