# Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor_1

- ea: `0x10640`
- end: `0x106b0`
- name: `Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor_1`
- size: `112`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x10610`
- `0x10630`
- `0x111a0`

## callees

- `0x10640`
- `0x107d0`
- `0x10810`
- `0x10830`
- `0x11750`
- `0x11810`
- `0x118f0`
- `0x11a30`

## pseudocode

```c

```

## disassembly

```asm
0x10640  ldarg.0
0x10641  ldc.i4.1
0x10642  stfld    valuetype CommandBarButtonStyle Microsoft.Crm.Controls.ReadFormCommandBarButton::_buttonStyle
0x10647  ldarg.0
0x10648  ldc.i4.1
0x10649  stfld    bool Microsoft.Crm.Controls.ReadFormCommandBarButton::_isAvailableOffline
0x1064e  ldarg.0
0x1064f  ldc.i4.1
0x10650  stfld    bool Microsoft.Crm.Controls.ReadFormCommandBarButton::_isAvailableOnline
0x10655  ldarg.0
0x10656  ldstr    aMsCrmMenu// "ms-crm-Menu"
0x1065b  stfld    string Microsoft.Crm.Controls.ReadFormCommandBarButton::_cssClass
0x10660  ldarg.0
0x10661  ldc.i4.1
0x10662  stfld    bool Microsoft.Crm.Controls.ReadFormCommandBarButton::_visible
0x10667  ldarg.0
0x10668  call     instance void Microsoft.Crm.Controls.CommandBarControl::.ctor()
0x1066d  ldarg.0
0x1066e  ldc.i4.0
0x1066f  call     instance void Microsoft.Crm.Controls.ReadFormCommandBarButton::set_FlipImageInRightToLeft(bool value)
0x10674  ldarg.0
0x10675  ldarg.1
0x10676  callvirt instance void Microsoft.Crm.Controls.CommandBarControl::set_Title(string value)
0x1067b  ldarg.0
0x1067c  ldarg.2
0x1067d  callvirt instance void Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string value)
0x10682  ldarg.0
0x10683  ldarg.3
0x10684  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x10689  ldarg.0
0x1068a  ldc.i4.0
0x1068b  call     instance void Microsoft.Crm.Controls.ReadFormCommandBarButton::set_IsTrimmed(bool value)
0x10690  ldarg.0
0x10691  ldc.i4.1
0x10692  newarr   [mscorlib]System.Int32
0x10697  call     instance void Microsoft.Crm.Controls.ReadFormCommandBarButton::set_VisibilityRules(int32[] value)
0x1069c  ldarg.s  4
0x1069e  brfalse.s loc_106A8
0x106a0  ldarg.0
0x106a1  ldarg.s  4
0x106a3  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::_customProperties
0x106a8  ldarg.0
0x106a9  ldc.i4.0
0x106aa  call     instance void Microsoft.Crm.Controls.CommandBarControl::set_InternalType(valuetype Microsoft.Crm.Controls.CommandBarControlType value)
0x106af  ret
```
