# Microsoft.Crm.Application.Controls.NotesDataControl::RenderContextMenu

- ea: `0xa8310`
- end: `0xa841f`
- name: `Microsoft.Crm.Application.Controls.NotesDataControl::RenderContextMenu`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xa8850`

## callees

- `0xa8310`
- `0xf3bb0`
- `0xf3c00`
- `0xf3c90`

## string_xrefs

- `0xa8357`: `MenuItem_Label_Delete`
- `0xa831e`: `Grid_RenderContextMenu_Label_Open`
- `0xa8332`: `var c=$find('{0}');c.openNote(null, c.get_currentNote());`
- `0xa834b`: `divMenu_Open`
- `0xa836b`: `var c=$find('{0}');c.closeContextMenu();c.deleteNote(null, c.get_currentNote());`
- `0xa8384`: `divMenu_Delete`

## pseudocode

```c

```

## disassembly

```asm
0xa8310  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8315  stloc.0
0xa8316  newobj   instance void ContextMenuDiv::.ctor()
0xa831b  stloc.1
0xa831c  ldloc.1
0xa831d  ldloc.0
0xa831e  ldstr    aGridRendercont// "Grid_RenderContextMenu_Label_Open"
0xa8323  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa8328  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa832d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8332  ldstr    aVarCFind0COpen// "var c=$find('{0}');c.openNote(null, c.g"...
0xa8337  ldc.i4.1
0xa8338  newarr   [mscorlib]System.Object
0xa833d  dup
0xa833e  ldc.i4.0
0xa833f  ldarg.0
0xa8340  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa8345  stelem.ref
0xa8346  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa834b  ldstr    aDivmenuOpen// "divMenu_Open"
0xa8350  callvirt instance void ContextMenuDiv::AddItem(string title, string action, string id)
0xa8355  ldloc.1
0xa8356  ldloc.0
0xa8357  ldstr    aMenuitemLabelD_1// "MenuItem_Label_Delete"
0xa835c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa8361  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa8366  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa836b  ldstr    aVarCFind0CClos// "var c=$find('{0}');c.closeContextMenu()"...
0xa8370  ldc.i4.1
0xa8371  newarr   [mscorlib]System.Object
0xa8376  dup
0xa8377  ldc.i4.0
0xa8378  ldarg.0
0xa8379  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa837e  stelem.ref
0xa837f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa8384  ldstr    aDivmenuDelete// "divMenu_Delete"
0xa8389  callvirt instance void ContextMenuDiv::AddItem(string title, string action, string id)
0xa838e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_Print()
0xa8393  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa8398  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa839d  brfalse.s loc_A83D8
0xa839f  ldloc.1
0xa83a0  ldloc.0
0xa83a1  ldstr    aContextmenuite// "ContextMenuItem_Label_Print"
0xa83a6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa83ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa83b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa83b5  ldstr    aVarCFind0CPrin// "var c=$find('{0}');c.printNote(null, c."...
0xa83ba  ldc.i4.1
0xa83bb  newarr   [mscorlib]System.Object
0xa83c0  dup
0xa83c1  ldc.i4.0
0xa83c2  ldarg.0
0xa83c3  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa83c8  stelem.ref
0xa83c9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa83ce  ldstr    aDivmenuPrint// "divMenu_Print"
0xa83d3  callvirt instance void ContextMenuDiv::AddItem(string title, string action, string id)
0xa83d8  ldloc.1
0xa83d9  callvirt instance void ContextMenuDiv::AddSpacer()
0xa83de  ldloc.1
0xa83df  ldloc.0
0xa83e0  ldstr    aGridRendercont_1// "Grid_RenderContextMenu_Label_RefreshGri"...
0xa83e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa83ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa83ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa83f4  ldstr    aFind0RefreshFa// "$find('{0}').refresh(false);"
0xa83f9  ldc.i4.1
0xa83fa  newarr   [mscorlib]System.Object
0xa83ff  dup
0xa8400  ldc.i4.0
0xa8401  ldarg.0
0xa8402  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa8407  stelem.ref
0xa8408  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa840d  ldstr    aDivmenuRefresh// "divMenu_Refresh"
0xa8412  callvirt instance void ContextMenuDiv::AddItem(string title, string action, string id)
0xa8417  ldloc.1
0xa8418  ldarg.1
0xa8419  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0xa841e  ret
```
