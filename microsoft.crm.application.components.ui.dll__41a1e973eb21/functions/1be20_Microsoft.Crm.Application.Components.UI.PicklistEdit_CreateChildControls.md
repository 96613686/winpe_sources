# Microsoft.Crm.Application.Components.UI.PicklistEdit::CreateChildControls

- ea: `0x1be20`
- end: `0x1bf40`
- name: `Microsoft.Crm.Application.Components.UI.PicklistEdit::CreateChildControls`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1c780`
- `0x20970`
- `0x209b0`
- `0x209f0`
- `0x20c70`
- `0x22890`
- `0x22d20`
- `0x23c20`
- `0x23c30`
- `0x23c50`

## pseudocode

```c

```

## disassembly

```asm
0x1be20  ldarg.0
0x1be21  newobj   instance void Microsoft.Crm.Application.Components.UI.Number::.ctor()
0x1be26  stfld    class Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Components.UI.PicklistEdit::_numBox
0x1be2b  ldarg.0
0x1be2c  ldfld    class Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Components.UI.PicklistEdit::_numBox
0x1be31  ldarg.0
0x1be32  ldstr    aTxtitemval// "txtItemVal"
0x1be37  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::GetOptionItemId(string fieldName)
0x1be3c  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1be41  ldarg.0
0x1be42  ldfld    class Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Components.UI.PicklistEdit::_numBox
0x1be47  ldc.r8   0.0
0x1be50  callvirt instance void Microsoft.Crm.Application.Components.UI.Number::set_MinValue(float64 value)
0x1be55  ldarg.0
0x1be56  ldfld    class Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Components.UI.PicklistEdit::_numBox
0x1be5b  ldc.i4.0
0x1be5c  callvirt instance void Microsoft.Crm.Application.Components.UI.Number::set_Precision(int32 value)
0x1be61  ldarg.0
0x1be62  ldfld    class Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Components.UI.PicklistEdit::_numBox
0x1be67  ldarg.0
0x1be68  ldfld    int32 Microsoft.Crm.Application.Components.UI.PicklistEdit::_maxValue
0x1be6d  conv.r8
0x1be6e  callvirt instance void Microsoft.Crm.Application.Components.UI.Number::set_MaxValue(float64 value)
0x1be73  ldarg.0
0x1be74  ldfld    class Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Components.UI.PicklistEdit::_numBox
0x1be79  ldarg.0
0x1be7a  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1be7f  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1be84  ldarg.0
0x1be85  ldfld    class Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Components.UI.PicklistEdit::_numBox
0x1be8a  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1be8f  ldarg.0
0x1be90  newobj   instance void Microsoft.Crm.Application.Components.UI.TextArea::.ctor()
0x1be95  stfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtDesc
0x1be9a  ldarg.0
0x1be9b  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtDesc
0x1bea0  ldarg.0
0x1bea1  ldstr    aTxtitemdesc// "txtItemDesc"
0x1bea6  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::GetOptionItemId(string fieldName)
0x1beab  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1beb0  ldarg.0
0x1beb1  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtDesc
0x1beb6  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1bebb  ldarg.0
0x1bebc  newobj   instance void Microsoft.Crm.Application.Components.UI.TextBox::.ctor()
0x1bec1  stfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtLb
0x1bec6  ldarg.0
0x1bec7  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtLb
0x1becc  ldarg.0
0x1becd  ldstr    aTxtitemlb// "txtItemLb"
0x1bed2  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::GetOptionItemId(string fieldName)
0x1bed7  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1bedc  ldarg.0
0x1bedd  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtLb
0x1bee2  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1bee7  ldarg.0
0x1bee8  newobj   instance void Microsoft.Crm.Application.Components.UI.TextBox::.ctor()
0x1beed  stfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtExtName
0x1bef2  ldarg.0
0x1bef3  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtExtName
0x1bef8  ldarg.0
0x1bef9  ldstr    aTxtitemextname// "txtItemExtName"
0x1befe  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::GetOptionItemId(string fieldName)
0x1bf03  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1bf08  ldarg.0
0x1bf09  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtExtName
0x1bf0e  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1bf13  ldarg.0
0x1bf14  newobj   instance void Microsoft.Crm.Application.Components.UI.TextBox::.ctor()
0x1bf19  stfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtColor
0x1bf1e  ldarg.0
0x1bf1f  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtColor
0x1bf24  ldarg.0
0x1bf25  ldstr    aTxtitemcolor// "txtItemColor"
0x1bf2a  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::GetOptionItemId(string fieldName)
0x1bf2f  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1bf34  ldarg.0
0x1bf35  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtColor
0x1bf3a  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1bf3f  ret
```
