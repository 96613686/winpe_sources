# Microsoft.Crm.Application.Menus.AppFormMenuBar::BuildFileToolbar

- ea: `0x18210`
- end: `0x18612`
- name: `Microsoft.Crm.Application.Menus.AppFormMenuBar::BuildFileToolbar`
- size: `1026`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x17e50`

## callees

- `0x17e60`
- `0x18210`
- `0x19620`
- `0x24210`
- `0x24240`
- `0x242a0`
- `0x26470`
- `0x8d1a0`

## string_xrefs

- `0x1857b`: `MenuItem_Label_SaveAsCompleted`
- `0x18551`: `SaveAsCompleted();`
- `0x1850c`: `/_imgs/ico/16_l_saveopen.gif`
- `0x1856b`: `/_imgs/ico/16_savecompleted.gif`

## pseudocode

```c

```

## disassembly

```asm
0x18210  ldarg.0
0x18211  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x18216  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanCreate()
0x1821b  brtrue.s loc_1822D
0x1821d  ldarg.0
0x1821e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x18223  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x18228  brfalse  loc_1858B
0x1822d  ldarg.0
0x1822e  ldc.i4.4
0x1822f  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x18234  brfalse  loc_1832A
0x18239  ldarg.0
0x1823a  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CanSaveEntityForm()
0x1823f  brfalse  loc_1832A
0x18244  ldarg.0
0x18245  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x1824a  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanRead()
0x1824f  brfalse  loc_1832A
0x18254  ldarg.0
0x18255  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x1825a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_EntityName()
0x1825f  ldstr    aEmailsignature// "emailsignature"
0x18264  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18269  brfalse.s loc_182D1
0x1826b  ldarg.0
0x1826c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x18271  ldarg.0
0x18272  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18277  ldstr    aButtonLabelSav// "Button_Label_Save"
0x1827c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18281  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18286  ldstr    aFind0Save// "$find('{0}').Save();"
0x1828b  ldc.i4.1
0x1828c  newarr   [mscorlib]System.Object
0x18291  dup
0x18292  ldc.i4.0
0x18293  ldarg.1
0x18294  stelem.ref
0x18295  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1829a  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1829f  ldc.i4.1
0x182a0  newarr   [mscorlib]System.Char
0x182a5  dup
0x182a6  ldc.i4.0
0x182a7  ldc.i4.s 0x2F
0x182a9  stelem.i2
0x182aa  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x182af  ldstr    aImgsIco16SaveG// "/_imgs/ico/16_save.gif"
0x182b4  call     string [mscorlib]System.String::Concat(string, string)
0x182b9  ldarg.0
0x182ba  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x182bf  ldstr    aMenuitemLabelS// "MenuItem_Label_Save"
0x182c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x182c9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x182ce  pop
0x182cf  br.s     loc_1832A
0x182d1  ldarg.0
0x182d2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x182d7  ldsfld   string [mscorlib]System.String::Empty
0x182dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x182e1  ldstr    aFind0Save// "$find('{0}').Save();"
0x182e6  ldc.i4.1
0x182e7  newarr   [mscorlib]System.Object
0x182ec  dup
0x182ed  ldc.i4.0
0x182ee  ldarg.1
0x182ef  stelem.ref
0x182f0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x182f5  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x182fa  ldc.i4.1
0x182fb  newarr   [mscorlib]System.Char
0x18300  dup
0x18301  ldc.i4.0
0x18302  ldc.i4.s 0x2F
0x18304  stelem.i2
0x18305  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1830a  ldstr    aImgsIco16SaveG// "/_imgs/ico/16_save.gif"
0x1830f  call     string [mscorlib]System.String::Concat(string, string)
0x18314  ldarg.0
0x18315  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1831a  ldstr    aMenuitemLabelS// "MenuItem_Label_Save"
0x1831f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18324  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x18329  pop
0x1832a  ldarg.0
0x1832b  ldc.i4   0x200
0x18330  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x18335  brfalse.s loc_183A1
0x18337  ldarg.0
0x18338  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x1833d  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanRead()
0x18342  brfalse.s loc_183A1
0x18344  ldarg.0
0x18345  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x1834a  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanCreate()
0x1834f  brfalse.s loc_183A1
0x18351  ldarg.0
0x18352  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x18357  ldarg.0
0x18358  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1835d  ldstr    aMenuitemLabelS_0// "MenuItem_Label_SaveAs"
0x18362  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18367  ldstr    aSaveas// "SaveAs();"
0x1836c  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x18371  ldc.i4.1
0x18372  newarr   [mscorlib]System.Char
0x18377  dup
0x18378  ldc.i4.0
0x18379  ldc.i4.s 0x2F
0x1837b  stelem.i2
0x1837c  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x18381  ldstr    aImgsAdvfindSav// "/_imgs/advfind/saveas.gif"
0x18386  call     string [mscorlib]System.String::Concat(string, string)
0x1838b  ldarg.0
0x1838c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18391  ldstr    aMenuitemLabelS_0// "MenuItem_Label_SaveAs"
0x18396  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1839b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x183a0  pop
0x183a1  ldarg.0
0x183a2  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CanSaveEntityForm()
0x183a7  brfalse  loc_1858B
0x183ac  ldarg.0
0x183ad  ldc.i4.8
0x183ae  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x183b3  brfalse.s loc_1841B
0x183b5  ldarg.0
0x183b6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x183bb  ldarg.0
0x183bc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x183c1  ldstr    aMenuitemLabelS_1// "MenuItem_Label_SaveClose"
0x183c6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x183cb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x183d0  ldstr    aFind0Saveandcl// "$find('{0}').SaveAndClose();"
0x183d5  ldc.i4.1
0x183d6  newarr   [mscorlib]System.Object
0x183db  dup
0x183dc  ldc.i4.0
0x183dd  ldarg.1
0x183de  stelem.ref
0x183df  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x183e4  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x183e9  ldc.i4.1
0x183ea  newarr   [mscorlib]System.Char
0x183ef  dup
0x183f0  ldc.i4.0
0x183f1  ldc.i4.s 0x2F
0x183f3  stelem.i2
0x183f4  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x183f9  ldstr    aImgsIco16Savec// "/_imgs/ico/16_saveclose.gif"
0x183fe  call     string [mscorlib]System.String::Concat(string, string)
0x18403  ldarg.0
0x18404  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18409  ldstr    aMenuitemLabelS_1// "MenuItem_Label_SaveClose"
0x1840e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18413  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x18418  pop
0x18419  br.s     loc_1847F
0x1841b  ldarg.0
0x1841c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x18421  ldarg.0
0x18422  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18427  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x1842c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18431  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18436  ldstr    aFind0Closereco// "$find('{0}').CloseRecord();"
0x1843b  ldc.i4.1
0x1843c  newarr   [mscorlib]System.Object
0x18441  dup
0x18442  ldc.i4.0
0x18443  ldarg.1
0x18444  stelem.ref
0x18445  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1844a  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1844f  ldc.i4.1
0x18450  newarr   [mscorlib]System.Char
0x18455  dup
0x18456  ldc.i4.0
0x18457  ldc.i4.s 0x2F
0x18459  stelem.i2
0x1845a  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1845f  ldstr    aImgsIco16Close// "/_imgs/ico/16_close.gif"
0x18464  call     string [mscorlib]System.String::Concat(string, string)
0x18469  ldarg.0
0x1846a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1846f  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x18474  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18479  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x1847e  pop
0x1847f  ldarg.0
0x18480  ldc.i4   0x100
0x18485  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x1848a  brfalse  loc_1852C
0x1848f  ldarg.0
0x18490  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x18495  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanCreate()
0x1849a  brfalse  loc_1852C
0x1849f  ldarg.0
0x184a0  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x184a5  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x184aa  callvirt instance valuetype Microsoft.Crm.Application.Forms.FormState Microsoft.Crm.Application.Forms.AppForm::get_State()
0x184af  ldc.i4.1
0x184b0  beq.s    loc_184BF
0x184b2  ldarg.0
0x184b3  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x184b8  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x184bd  brfalse.s loc_1852C
0x184bf  ldarg.0
0x184c0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x184c5  ldsfld   string [mscorlib]System.String::Empty
0x184ca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x184cf  ldstr    aFind0Submitcrm// "$find('{0}').SubmitCrmForm({1}, true, t"...
0x184d4  ldc.i4.2
0x184d5  newarr   [mscorlib]System.Object
0x184da  dup
0x184db  ldc.i4.0
0x184dc  ldarg.1
0x184dd  stelem.ref
0x184de  dup
0x184df  ldc.i4.1
0x184e0  ldc.i4.s 0x3B
0x184e2  box      [mscorlib]System.UInt32
0x184e7  stelem.ref
0x184e8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x184ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x184f2  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x184f7  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x184fc  ldc.i4.1
0x184fd  newarr   [mscorlib]System.Char
0x18502  dup
0x18503  ldc.i4.0
0x18504  ldc.i4.s 0x2F
0x18506  stelem.i2
0x18507  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1850c  ldstr    aImgsIco16LSave// "/_imgs/ico/16_l_saveopen.gif"
0x18511  call     string [mscorlib]System.String::Concat(string, string)
0x18516  ldarg.0
0x18517  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1851c  ldstr    aMenuitemLabelS_2// "MenuItem_Label_SaveAndNew"
0x18521  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18526  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x1852b  pop
0x1852c  ldarg.0
0x1852d  ldc.i4   0x80
0x18532  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormFileParameters fileParameter)
0x18537  brfalse.s loc_1858B
0x18539  ldarg.0
0x1853a  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x1853f  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x18544  brfalse.s loc_1858B
0x18546  ldarg.0
0x18547  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x1854c  ldsfld   string [mscorlib]System.String::Empty
0x18551  ldstr    aSaveascomplete// "SaveAsCompleted();"
0x18556  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1855b  ldc.i4.1
0x1855c  newarr   [mscorlib]System.Char
0x18561  dup
0x18562  ldc.i4.0
0x18563  ldc.i4.s 0x2F
0x18565  stelem.i2
0x18566  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1856b  ldstr    aImgsIco16Savec_0// "/_imgs/ico/16_savecompleted.gif"
0x18570  call     string [mscorlib]System.String::Concat(string, string)
0x18575  ldarg.0
0x18576  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1857b  ldstr    aMenuitemLabelS_3// "MenuItem_Label_SaveAsCompleted"
0x18580  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18585  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x1858a  pop
0x1858b  ldarg.0
0x1858c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x18591  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanCreate()
0x18596  brtrue.s loc_185A5
0x18598  ldarg.0
0x18599  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x1859e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x185a3  brfalse.s loc_185AD
0x185a5  ldarg.0
0x185a6  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CanSaveEntityForm()
0x185ab  brtrue.s loc_18611
0x185ad  ldarg.0
0x185ae  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x185b3  ldarg.0
0x185b4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x185b9  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x185be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x185c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x185c8  ldstr    aFind0Closereco// "$find('{0}').CloseRecord();"
0x185cd  ldc.i4.1
0x185ce  newarr   [mscorlib]System.Object
0x185d3  dup
0x185d4  ldc.i4.0
0x185d5  ldarg.1
0x185d6  stelem.ref
0x185d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x185dc  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x185e1  ldc.i4.1
0x185e2  newarr   [mscorlib]System.Char
  ... truncated ...
```
