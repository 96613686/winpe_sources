# Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::MenuReady

- ea: `0x76c0`
- end: `0x7811`
- name: `Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::MenuReady`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x76c0`

## pseudocode

```c

```

## disassembly

```asm
0x76c0  ldarg.2
0x76c1  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuId()
0x76c6  stloc.0
0x76c7  ldloc.0
0x76c8  ldc.i4.8
0x76c9  beq      loc_7810
0x76ce  ldloc.0
0x76cf  ldc.i4.s 0x20
0x76d1  bne.un   loc_7810
0x76d6  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteArticleTemplate()
0x76db  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x76e0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x76e5  brfalse  loc_7810
0x76ea  ldarg.0
0x76eb  ldfld    bool Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_isActive
0x76f0  brfalse  loc_7783
0x76f5  ldarg.2
0x76f6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x76fb  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x7700  ldarg.0
0x7701  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7706  ldstr    aMenuitemLabelD_0// "MenuItem_Label_DeactivateObject"
0x770b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7710  ldc.i4.1
0x7711  newarr   [mscorlib]System.Object
0x7716  dup
0x7717  ldc.i4.0
0x7718  ldarg.0
0x7719  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x771e  ldc.i4.1
0x771f  ldnull
0x7720  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x7725  stelem.ref
0x7726  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x772b  ldc.i4.5
0x772c  newarr   [mscorlib]System.String
0x7731  dup
0x7732  ldc.i4.0
0x7733  ldstr    aChangestateDea// "changeState('deactivate', "
0x7738  stelem.ref
0x7739  dup
0x773a  ldc.i4.1
0x773b  ldarg.0
0x773c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x7741  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x7746  stloc.0
0x7747  ldloca.s 0
0x7749  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x774e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7753  stelem.ref
0x7754  dup
0x7755  ldc.i4.2
0x7756  ldstr    asc_1D9C2// ","
0x775b  stelem.ref
0x775c  dup
0x775d  ldc.i4.3
0x775e  ldc.i4.5
0x775f  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId
0x7764  ldstr    aD// "D"
0x7769  call     instance string [mscorlib]System.Enum::ToString(string)
0x776e  stelem.ref
0x776f  dup
0x7770  ldc.i4.4
0x7771  ldstr    asc_1D9CA// ");"
0x7776  stelem.ref
0x7777  call     string [mscorlib]System.String::Concat(string[])
0x777c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x7781  pop
0x7782  ret
0x7783  ldarg.2
0x7784  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x7789  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x778e  ldarg.0
0x778f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7794  ldstr    aMenuitemLabelA// "MenuItem_Label_ActivateObject"
0x7799  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x779e  ldc.i4.1
0x779f  newarr   [mscorlib]System.Object
0x77a4  dup
0x77a5  ldc.i4.0
0x77a6  ldarg.0
0x77a7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x77ac  ldc.i4.1
0x77ad  ldnull
0x77ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x77b3  stelem.ref
0x77b4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x77b9  ldc.i4.5
0x77ba  newarr   [mscorlib]System.String
0x77bf  dup
0x77c0  ldc.i4.0
0x77c1  ldstr    aChangestateAct// "changeState('activate', "
0x77c6  stelem.ref
0x77c7  dup
0x77c8  ldc.i4.1
0x77c9  ldarg.0
0x77ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x77cf  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x77d4  stloc.0
0x77d5  ldloca.s 0
0x77d7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x77dc  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x77e1  stelem.ref
0x77e2  dup
0x77e3  ldc.i4.2
0x77e4  ldstr    asc_1D9C2// ","
0x77e9  stelem.ref
0x77ea  dup
0x77eb  ldc.i4.3
0x77ec  ldc.i4.6
0x77ed  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId
0x77f2  ldstr    aD// "D"
0x77f7  call     instance string [mscorlib]System.Enum::ToString(string)
0x77fc  stelem.ref
0x77fd  dup
0x77fe  ldc.i4.4
0x77ff  ldstr    asc_1D9CA// ");"
0x7804  stelem.ref
0x7805  call     string [mscorlib]System.String::Concat(string[])
0x780a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x780f  pop
0x7810  ret
```
