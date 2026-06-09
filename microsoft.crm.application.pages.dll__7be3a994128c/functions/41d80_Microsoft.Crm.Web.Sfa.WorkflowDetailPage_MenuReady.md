# Microsoft.Crm.Web.Sfa.WorkflowDetailPage::MenuReady

- ea: `0x41d80`
- end: `0x423e0`
- name: `Microsoft.Crm.Web.Sfa.WorkflowDetailPage::MenuReady`
- size: `1632`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x41d80`
- `0x42a40`
- `0x42a70`
- `0x42a90`

## string_xrefs

- `0x41ee4`: `_deleteActionEnabled`
- `0x41f4f`: `_deleteActionEnabled`
- `0x41efb`: `MenuItem_Label_DeleteworkflowObject`
- `0x41f0d`: `onActionMenuClick('delete', '`

## pseudocode

```c

```

## disassembly

```asm
0x41d80  ldarg.2
0x41d81  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuId()
0x41d86  stloc.0
0x41d87  ldloc.0
0x41d88  ldc.i4.s 0x20
0x41d8a  bne.un   loc_423DF
0x41d8f  ldarg.0
0x41d90  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x41d95  ldstr    aType// "type"
0x41d9a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x41d9f  unbox.any [mscorlib]System.Int32
0x41da4  stloc.0
0x41da5  ldloca.s 0
0x41da7  ldstr    aD// "D"
0x41dac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x41db1  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x41db6  stloc.1
0x41db7  ldarg.0
0x41db8  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x41dbd  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x41dc2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x41dc7  brfalse  loc_42054
0x41dcc  ldarg.0
0x41dcd  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x41dd2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x41dd7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x41ddc  ldc.i4.1
0x41ddd  stloc.2
0x41dde  ldloca.s 2
0x41de0  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.WorkflowState
0x41de6  callvirt instance string [mscorlib]System.Object::ToString()
0x41deb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x41df0  brfalse  loc_41ECC
0x41df5  ldarg.2
0x41df6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x41dfb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x41e00  ldarg.2
0x41e01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x41e06  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x41e0b  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x41e10  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x41e15  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x41e1a  stloc.3
0x41e1b  ldloc.3
0x41e1c  ldarg.0
0x41e1d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x41e22  ldstr    aMenuLabelDeact// "Menu_Label_Deactivate"
0x41e27  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x41e2c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x41e31  ldloc.3
0x41e32  ldc.i4.7
0x41e33  newarr   [mscorlib]System.String
0x41e38  dup
0x41e39  ldc.i4.0
0x41e3a  ldstr    aChangeworkflow// "ChangeWorkflowState('deactivate', '"
0x41e3f  stelem.ref
0x41e40  dup
0x41e41  ldc.i4.1
0x41e42  ldc.i4   0x125F
0x41e47  stloc.0
0x41e48  ldloca.s 0
0x41e4a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x41e4f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x41e54  stelem.ref
0x41e55  dup
0x41e56  ldc.i4.2
0x41e57  ldstr    asc_142CA2// "', '"
0x41e5c  stelem.ref
0x41e5d  dup
0x41e5e  ldc.i4.3
0x41e5f  ldc.i4.5
0x41e60  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId
0x41e65  ldstr    aD// "D"
0x41e6a  call     instance string [mscorlib]System.Enum::ToString(string)
0x41e6f  stelem.ref
0x41e70  dup
0x41e71  ldc.i4.4
0x41e72  ldstr    asc_14E85C// "',"
0x41e77  stelem.ref
0x41e78  dup
0x41e79  ldc.i4.5
0x41e7a  ldloc.1
0x41e7b  stelem.ref
0x41e7c  dup
0x41e7d  ldc.i4.6
0x41e7e  ldstr    asc_14E862// ")"
0x41e83  stelem.ref
0x41e84  call     string [mscorlib]System.String::Concat(string[])
0x41e89  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x41e8e  ldloc.3
0x41e8f  ldstr    aImgsIco16Unpub// "/_imgs/ico/16_unpublish.gif"
0x41e94  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x41e99  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41e9e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x41ea3  ldloc.3
0x41ea4  ldarg.0
0x41ea5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x41eaa  ldstr    aMenuLabelDeact// "Menu_Label_Deactivate"
0x41eaf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x41eb4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x41eb9  ldloc.3
0x41eba  ldc.i4.1
0x41ebb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::set_FlipImageInRightToLeft(bool)
0x41ec0  ldloc.3
0x41ec1  ldc.i4.1
0x41ec2  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x41ec7  br       loc_42054
0x41ecc  ldarg.0
0x41ecd  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x41ed2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x41ed7  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_IsInstanceCustomizable()
0x41edc  brfalse.s loc_41F49
0x41ede  ldarg.0
0x41edf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x41ee4  ldstr    aDeleteactionen// "_deleteActionEnabled"
0x41ee9  ldc.i4.1
0x41eea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x41eef  ldarg.2
0x41ef0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x41ef5  ldarg.0
0x41ef6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x41efb  ldstr    aMenuitemLabelD_2// "MenuItem_Label_DeleteworkflowObject"
0x41f00  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x41f05  ldc.i4.5
0x41f06  newarr   [mscorlib]System.String
0x41f0b  dup
0x41f0c  ldc.i4.0
0x41f0d  ldstr    aOnactionmenucl_1// "onActionMenuClick('delete', '"
0x41f12  stelem.ref
0x41f13  dup
0x41f14  ldc.i4.1
0x41f15  ldc.i4   0x125F
0x41f1a  stloc.0
0x41f1b  ldloca.s 0
0x41f1d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x41f22  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x41f27  stelem.ref
0x41f28  dup
0x41f29  ldc.i4.2
0x41f2a  ldstr    asc_14E85C// "',"
0x41f2f  stelem.ref
0x41f30  dup
0x41f31  ldc.i4.3
0x41f32  ldloc.1
0x41f33  stelem.ref
0x41f34  dup
0x41f35  ldc.i4.4
0x41f36  ldstr    asc_12EE04// ");"
0x41f3b  stelem.ref
0x41f3c  call     string [mscorlib]System.String::Concat(string[])
0x41f41  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x41f46  pop
0x41f47  br.s     loc_41F5A
0x41f49  ldarg.0
0x41f4a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x41f4f  ldstr    aDeleteactionen// "_deleteActionEnabled"
0x41f54  ldc.i4.0
0x41f55  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x41f5a  ldarg.2
0x41f5b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x41f60  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x41f65  ldarg.2
0x41f66  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x41f6b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x41f70  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x41f75  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x41f7a  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x41f7f  stloc.s  4
0x41f81  ldloc.s  4
0x41f83  ldarg.0
0x41f84  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x41f89  ldstr    aMenuLabelActiv// "Menu_Label_Activate"
0x41f8e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x41f93  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x41f98  ldloc.s  4
0x41f9a  ldc.i4.7
0x41f9b  newarr   [mscorlib]System.String
0x41fa0  dup
0x41fa1  ldc.i4.0
0x41fa2  ldstr    aChangeworkflow_0// "ChangeWorkflowState('activate', '"
0x41fa7  stelem.ref
0x41fa8  dup
0x41fa9  ldc.i4.1
0x41faa  ldc.i4   0x125F
0x41faf  stloc.0
0x41fb0  ldloca.s 0
0x41fb2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x41fb7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x41fbc  stelem.ref
0x41fbd  dup
0x41fbe  ldc.i4.2
0x41fbf  ldstr    asc_142CA2// "', '"
0x41fc4  stelem.ref
0x41fc5  dup
0x41fc6  ldc.i4.3
0x41fc7  ldc.i4.6
0x41fc8  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId
0x41fcd  ldstr    aD// "D"
0x41fd2  call     instance string [mscorlib]System.Enum::ToString(string)
0x41fd7  stelem.ref
0x41fd8  dup
0x41fd9  ldc.i4.4
0x41fda  ldstr    asc_14E85C// "',"
0x41fdf  stelem.ref
0x41fe0  dup
0x41fe1  ldc.i4.5
0x41fe2  ldloc.1
0x41fe3  stelem.ref
0x41fe4  dup
0x41fe5  ldc.i4.6
0x41fe6  ldstr    asc_14E862// ")"
0x41feb  stelem.ref
0x41fec  call     string [mscorlib]System.String::Concat(string[])
0x41ff1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x41ff6  ldloc.s  4
0x41ff8  ldstr    aImgsIco16Publi// "/_imgs/ico/16_publish.gif"
0x41ffd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x42002  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42007  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x4200c  ldloc.s  4
0x4200e  ldarg.0
0x4200f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x42014  ldstr    aMenuLabelActiv// "Menu_Label_Activate"
0x42019  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4201e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x42023  ldloc.s  4
0x42025  ldc.i4.1
0x42026  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::set_FlipImageInRightToLeft(bool)
0x4202b  ldloc.s  4
0x4202d  ldc.i4.1
0x4202e  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x42033  ldarg.0
0x42034  call     instance bool Microsoft.Crm.Web.Sfa.WorkflowDetailPage::get_IsSyncWorkflow()
0x42039  brfalse.s loc_42054
0x4203b  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ActivateSynchronousWorkflow()
0x42040  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x42045  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4204a  brtrue.s loc_42054
0x4204c  ldloc.s  4
0x4204e  ldc.i4.0
0x4204f  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x42054  ldarg.0
0x42055  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x4205a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x4205f  ldc.i4.0
0x42060  stloc.2
0x42061  ldloca.s 2
0x42063  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.WorkflowState
0x42069  callvirt instance string [mscorlib]System.Object::ToString()
0x4206e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42073  brfalse  loc_42243
0x42078  ldarg.0
0x42079  call     instance bool Microsoft.Crm.Web.Sfa.WorkflowDetailPage::get_IsAsynchronousWorkflow()
0x4207e  brfalse  loc_42160
0x42083  ldarg.2
0x42084  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x42089  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x4208e  ldarg.2
0x4208f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x42094  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x42099  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x4209e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x420a3  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x420a8  stloc.s  5
0x420aa  ldloc.s  5
0x420ac  ldarg.0
0x420ad  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x420b2  ldstr    aMenuLabelConve// "Menu_Label_ConvertToSyncWorkflowType"
0x420b7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x420bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x420c1  ldloc.s  5
0x420c3  ldc.i4.5
0x420c4  newarr   [mscorlib]System.String
0x420c9  dup
0x420ca  ldc.i4.0
0x420cb  ldstr    aMscrmFormactio// "Mscrm.FormAction.convertWorkflow("
0x420d0  stelem.ref
0x420d1  dup
0x420d2  ldc.i4.1
0x420d3  ldarg.0
0x420d4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x420d9  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x420de  stloc.0
0x420df  ldloca.s 0
0x420e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x420e6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x420eb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x420f0  stelem.ref
0x420f1  dup
0x420f2  ldc.i4.2
0x420f3  ldstr    asc_12EE00// ","
0x420f8  stelem.ref
0x420f9  dup
0x420fa  ldc.i4.3
0x420fb  ldarg.0
0x420fc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x42101  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x42106  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x4210b  stelem.ref
0x4210c  dup
  ... truncated ...
```
