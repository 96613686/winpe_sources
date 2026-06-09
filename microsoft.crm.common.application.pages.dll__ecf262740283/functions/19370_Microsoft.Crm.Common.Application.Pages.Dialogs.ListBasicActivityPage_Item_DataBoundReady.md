# Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::Item_DataBoundReady

- ea: `0x19370`
- end: `0x193e2`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::Item_DataBoundReady`
- size: `114`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x19610`
- `0x197d0`
- `0x19950`
- `0x19aa0`
- `0x19c30`

## callees

- `0x18da0`
- `0x18db0`
- `0x19370`

## pseudocode

```c

```

## disassembly

```asm
0x19370  ldarg.0
0x19371  callvirt instance string[] Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetControlsToClearAndMakeReadOnlyOnItemDataBoundReady()
0x19376  stloc.0
0x19377  ldc.i4.0
0x19378  stloc.1
0x19379  br.s     loc_193A6
0x1937b  ldloc.0
0x1937c  ldloc.1
0x1937d  ldelem.ref
0x1937e  stloc.2
0x1937f  ldarg.2
0x19380  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x19385  ldloc.2
0x19386  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1938b  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x19390  stloc.3
0x19391  ldloc.3
0x19392  brfalse.s loc_193A2
0x19394  ldloc.3
0x19395  ldnull
0x19396  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x1939b  ldloc.3
0x1939c  ldc.i4.1
0x1939d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_ReadOnly(bool)
0x193a2  ldloc.1
0x193a3  ldc.i4.1
0x193a4  add
0x193a5  stloc.1
0x193a6  ldloc.1
0x193a7  ldloc.0
0x193a8  ldlen
0x193a9  conv.i4
0x193aa  blt.s    loc_1937B
0x193ac  ldarg.0
0x193ad  callvirt instance string[] Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetControlsToDisableOnItemDataBoundReady()
0x193b2  stloc.0
0x193b3  ldc.i4.0
0x193b4  stloc.1
0x193b5  br.s     loc_193DB
0x193b7  ldloc.0
0x193b8  ldloc.1
0x193b9  ldelem.ref
0x193ba  stloc.s  4
0x193bc  ldarg.2
0x193bd  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x193c2  ldloc.s  4
0x193c4  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x193c9  stloc.s  5
0x193cb  ldloc.s  5
0x193cd  brfalse.s loc_193D7
0x193cf  ldloc.s  5
0x193d1  ldc.i4.1
0x193d2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x193d7  ldloc.1
0x193d8  ldc.i4.1
0x193d9  add
0x193da  stloc.1
0x193db  ldloc.1
0x193dc  ldloc.0
0x193dd  ldlen
0x193de  conv.i4
0x193df  blt.s    loc_193B7
0x193e1  ret
```
