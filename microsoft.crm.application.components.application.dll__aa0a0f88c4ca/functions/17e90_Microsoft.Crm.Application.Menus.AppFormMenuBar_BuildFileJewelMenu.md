# Microsoft.Crm.Application.Menus.AppFormMenuBar::BuildFileJewelMenu

- ea: `0x17e90`
- end: `0x18207`
- name: `Microsoft.Crm.Application.Menus.AppFormMenuBar::BuildFileJewelMenu`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x17e50`

## callees

- `0x17e60`
- `0x17e90`
- `0x19620`
- `0x24210`
- `0x242a0`
- `0x242b0`
- `0x243f0`
- `0x24550`
- `0x24950`
- `0x26470`
- `0x26510`
- `0x26530`
- `0x8d1a0`

## string_xrefs

- `0x180a6`: `MenuItem_Label_SaveAsCompleted`
- `0x180b0`: `SaveAsCompleted();`
- `0x180fa`: `(new Mscrm.CrmDialog(Mscrm.CrmUri.create('/_forms/properties/properties.aspx?id=`

## pseudocode

```c

```

## disassembly

```asm
0x17e90  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0x17e95  stloc.0
0x17e96  ldloc.0
0x17e97  ldarg.0
0x17e98  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x17e9d  ldstr    aFile// "file"
0x17ea2  call     string [mscorlib]System.String::Concat(string, string)
0x17ea7  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x17eac  ldloc.0
0x17ead  ldarg.0
0x17eae  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x17eb3  ldstr    aMenuLabelFile// "Menu_Label_File"
0x17eb8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17ebd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x17ec2  ldloc.0
0x17ec3  ldloc.0
0x17ec4  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x17ec9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x17ece  ldloc.0
0x17ecf  ldc.i4.1
0x17ed0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_JewelMenu(bool)
0x17ed5  ldloc.0
0x17ed6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x17edb  stloc.1
0x17edc  ldarg.0
0x17edd  ldc.i4.1
0x17ede  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x17ee3  brfalse.s loc_17EEC
0x17ee5  ldarg.0
0x17ee6  ldloc.1
0x17ee7  call     instance void Microsoft.Crm.Application.Menus.AppMenuBar::BuildNewObjectMenu(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu menuObject)
0x17eec  ldarg.0
0x17eed  ldc.i4.2
0x17eee  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x17ef3  brfalse.s loc_17EFD
0x17ef5  ldarg.0
0x17ef6  ldloc.1
0x17ef7  call     instance bool Microsoft.Crm.Application.Menus.AppMenuBar::BuildNewActivityMenu(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu parentMenu)
0x17efc  pop
0x17efd  ldloc.1
0x17efe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x17f03  ldarg.0
0x17f04  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x17f09  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanCreate()
0x17f0e  brtrue.s loc_17F20
0x17f10  ldarg.0
0x17f11  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x17f16  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x17f1b  brfalse  loc_180BB
0x17f20  ldarg.0
0x17f21  ldc.i4.4
0x17f22  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x17f27  brfalse.s loc_17F6E
0x17f29  ldarg.0
0x17f2a  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CanSaveEntityForm()
0x17f2f  brfalse.s loc_17F6E
0x17f31  ldarg.0
0x17f32  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x17f37  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanRead()
0x17f3c  brfalse.s loc_17F6E
0x17f3e  ldloc.1
0x17f3f  ldarg.0
0x17f40  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x17f45  ldstr    aMenuitemLabelS// "MenuItem_Label_Save"
0x17f4a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17f4f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17f54  ldstr    aFind0Save// "$find('{0}').Save();"
0x17f59  ldc.i4.1
0x17f5a  newarr   [mscorlib]System.Object
0x17f5f  dup
0x17f60  ldc.i4.0
0x17f61  ldarg.1
0x17f62  stelem.ref
0x17f63  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17f68  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x17f6d  pop
0x17f6e  ldarg.0
0x17f6f  ldc.i4   0x200
0x17f74  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x17f79  brfalse.s loc_17FB1
0x17f7b  ldarg.0
0x17f7c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x17f81  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanRead()
0x17f86  brfalse.s loc_17FB1
0x17f88  ldarg.0
0x17f89  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x17f8e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanCreate()
0x17f93  brfalse.s loc_17FB1
0x17f95  ldloc.1
0x17f96  ldarg.0
0x17f97  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x17f9c  ldstr    aMenuitemLabelS_0// "MenuItem_Label_SaveAs"
0x17fa1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17fa6  ldstr    aSaveas// "SaveAs();"
0x17fab  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x17fb0  pop
0x17fb1  ldarg.0
0x17fb2  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CanSaveEntityForm()
0x17fb7  brfalse  loc_180BB
0x17fbc  ldarg.0
0x17fbd  ldc.i4.8
0x17fbe  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x17fc3  brfalse.s loc_17FF5
0x17fc5  ldloc.1
0x17fc6  ldarg.0
0x17fc7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x17fcc  ldstr    aMenuitemLabelS_1// "MenuItem_Label_SaveClose"
0x17fd1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17fd6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17fdb  ldstr    aFind0Saveandcl// "$find('{0}').SaveAndClose();"
0x17fe0  ldc.i4.1
0x17fe1  newarr   [mscorlib]System.Object
0x17fe6  dup
0x17fe7  ldc.i4.0
0x17fe8  ldarg.1
0x17fe9  stelem.ref
0x17fea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17fef  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x17ff4  pop
0x17ff5  ldarg.0
0x17ff6  ldc.i4   0x100
0x17ffb  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x18000  brfalse  loc_18085
0x18005  ldarg.0
0x18006  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x1800b  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanCreate()
0x18010  brfalse.s loc_18085
0x18012  ldarg.0
0x18013  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18018  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x1801d  callvirt instance valuetype Microsoft.Crm.Application.Forms.FormState Microsoft.Crm.Application.Forms.AppForm::get_State()
0x18022  ldc.i4.1
0x18023  beq.s    loc_18032
0x18025  ldarg.0
0x18026  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x1802b  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x18030  brfalse.s loc_18085
0x18032  ldarg.0
0x18033  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x18038  ldstr    aSaveandnewenab// "_saveAndNewEnabled"
0x1803d  ldc.i4.1
0x1803e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x18043  ldloc.1
0x18044  ldarg.0
0x18045  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1804a  ldstr    aMenuitemLabelS_2// "MenuItem_Label_SaveAndNew"
0x1804f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18054  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18059  ldstr    aFind0Submitcrm// "$find('{0}').SubmitCrmForm({1}, true, t"...
0x1805e  ldc.i4.2
0x1805f  newarr   [mscorlib]System.Object
0x18064  dup
0x18065  ldc.i4.0
0x18066  ldarg.1
0x18067  stelem.ref
0x18068  dup
0x18069  ldc.i4.1
0x1806a  ldc.i4.s 0x3B
0x1806c  stloc.2
0x1806d  ldloca.s 2
0x1806f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18074  call     instance string [mscorlib]System.UInt32::ToString(class [mscorlib]System.IFormatProvider)
0x18079  stelem.ref
0x1807a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1807f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x18084  pop
0x18085  ldarg.0
0x18086  ldc.i4   0x80
0x1808b  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x18090  brfalse.s loc_180BB
0x18092  ldarg.0
0x18093  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x18098  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x1809d  brfalse.s loc_180BB
0x1809f  ldloc.1
0x180a0  ldarg.0
0x180a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x180a6  ldstr    aMenuitemLabelS_3// "MenuItem_Label_SaveAsCompleted"
0x180ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x180b0  ldstr    aSaveascomplete// "SaveAsCompleted();"
0x180b5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x180ba  pop
0x180bb  ldarg.0
0x180bc  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x180c1  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x180c6  callvirt instance valuetype Microsoft.Crm.Application.Forms.FormState Microsoft.Crm.Application.Forms.AppForm::get_State()
0x180cb  ldc.i4.2
0x180cc  bne.un   loc_181AA
0x180d1  ldloc.1
0x180d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x180d7  ldarg.0
0x180d8  ldc.i4.s 0x20
0x180da  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x180df  brfalse.s loc_1815E
0x180e1  ldloc.1
0x180e2  ldarg.0
0x180e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x180e8  ldstr    aMenuLabelPrope// "Menu_Label_Properties"
0x180ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x180f2  ldc.i4.5
0x180f3  newarr   [mscorlib]System.String
0x180f8  dup
0x180f9  ldc.i4.0
0x180fa  ldstr    aNewMscrmCrmdia// "(new Mscrm.CrmDialog(Mscrm.CrmUri.creat"...
0x180ff  stelem.ref
0x18100  dup
0x18101  ldc.i4.1
0x18102  ldarg.0
0x18103  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18108  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x1810d  callvirt instance string Microsoft.Crm.Application.Forms.AppForm::get_EntityId()
0x18112  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x18117  stelem.ref
0x18118  dup
0x18119  ldc.i4.2
0x1811a  ldstr    aObjtypecode// "&objTypeCode="
0x1811f  stelem.ref
0x18120  dup
0x18121  ldc.i4.3
0x18122  ldarg.0
0x18123  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18128  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x1812d  callvirt instance int32 Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x18132  stloc.3
0x18133  ldloca.s 3
0x18135  ldstr    aD// "D"
0x1813a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1813f  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18144  stelem.ref
0x18145  dup
0x18146  ldc.i4.4
0x18147  ldstr    aNull460505Null// "'), null, 460, 505, null)).show()"
0x1814c  stelem.ref
0x1814d  call     string [mscorlib]System.String::Concat(string[])
0x18152  ldnull
0x18153  ldstr    aMnuProperties// "mnu_properties"
0x18158  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri, string)
0x1815d  pop
0x1815e  ldarg.0
0x1815f  ldc.i4.s 0x10
0x18161  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x18166  brfalse.s loc_181AA
0x18168  ldarg.0
0x18169  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1816e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18173  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIosDevice(class [System.Web]System.Web.HttpRequest)
0x18178  brtrue.s loc_181AA
0x1817a  ldloc.1
0x1817b  ldarg.0
0x1817c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18181  ldstr    aRibbonJewelPri// "Ribbon.Jewel.PrintPreview"
0x18186  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1818b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18190  ldstr    aFind0Print// "$find('{0}').Print();"
0x18195  ldc.i4.1
0x18196  newarr   [mscorlib]System.Object
0x1819b  dup
0x1819c  ldc.i4.0
0x1819d  ldarg.1
0x1819e  stelem.ref
0x1819f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x181a4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x181a9  pop
0x181aa  ldarg.0
0x181ab  ldloc.1
0x181ac  ldc.i4   0x100
0x181b1  call     instance void Microsoft.Crm.Application.Menus.AppMenuBar::RaiseMenuReadyEvent(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu menu, int32 menuId)
0x181b6  ldloc.1
0x181b7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x181bc  ldloc.1
0x181bd  ldarg.0
0x181be  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x181c3  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x181c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x181cd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x181d2  ldstr    aFind0Closereco// "$find('{0}').CloseRecord();"
0x181d7  ldc.i4.1
0x181d8  newarr   [mscorlib]System.Object
0x181dd  dup
0x181de  ldc.i4.0
0x181df  ldarg.1
0x181e0  stelem.ref
0x181e1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x181e6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x181eb  pop
0x181ec  ldarg.0
0x181ed  ldloc.1
0x181ee  ldc.i4.1
0x181ef  call     instance void Microsoft.Crm.Application.Menus.AppMenuBar::RaiseMenuReadyEvent(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu menu, int32 menuId)
0x181f4  ldarg.0
0x181f5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x181fa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x181ff  ldloc.0
0x18200  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x18205  pop
0x18206  ret
```
