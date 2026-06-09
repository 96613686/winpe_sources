# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::CreateChildControls

- ea: `0x1d9e0`
- end: `0x1dae9`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::CreateChildControls`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x154b0`
- `0x1e6b0`
- `0x210c0`
- `0x22890`
- `0x22d20`
- `0x23c50`
- `0x26750`

## pseudocode

```c

```

## disassembly

```asm
0x1d9e0  ldarg.0
0x1d9e1  newobj   instance void Microsoft.Crm.Application.Components.UI.TextArea::.ctor()
0x1d9e6  stfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtDesc
0x1d9eb  ldarg.0
0x1d9ec  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtDesc
0x1d9f1  ldarg.0
0x1d9f2  ldstr    aTxtitemdesc// "txtItemDesc"
0x1d9f7  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetOptionItemId(string fieldName)
0x1d9fc  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1da01  ldarg.0
0x1da02  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtDesc
0x1da07  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1da0c  ldarg.0
0x1da0d  newobj   instance void Microsoft.Crm.Application.Components.UI.TextBox::.ctor()
0x1da12  stfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtName
0x1da17  ldarg.0
0x1da18  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtName
0x1da1d  ldarg.0
0x1da1e  ldstr    aTxtitemname// "txtItemName"
0x1da23  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetOptionItemId(string fieldName)
0x1da28  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1da2d  ldarg.0
0x1da2e  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtName
0x1da33  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1da38  ldarg.0
0x1da39  newobj   instance void Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x1da3e  stfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstType
0x1da43  ldarg.0
0x1da44  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstType
0x1da49  ldarg.0
0x1da4a  ldstr    aTxtitemtype// "txtItemType"
0x1da4f  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetOptionItemId(string fieldName)
0x1da54  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1da59  ldarg.0
0x1da5a  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstType
0x1da5f  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1da64  ldarg.0
0x1da65  newobj   instance void Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x1da6a  stfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstEntity
0x1da6f  ldarg.0
0x1da70  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstEntity
0x1da75  ldarg.0
0x1da76  ldstr    aTxtitementity// "txtItemEntity"
0x1da7b  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetOptionItemId(string fieldName)
0x1da80  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1da85  ldarg.0
0x1da86  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstEntity
0x1da8b  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1da90  ldarg.0
0x1da91  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBox::.ctor()
0x1da96  stfld    class Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_chkRequired
0x1da9b  ldarg.0
0x1da9c  ldfld    class Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_chkRequired
0x1daa1  ldarg.0
0x1daa2  ldstr    aChkrequired// "chkRequired"
0x1daa7  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetOptionItemId(string fieldName)
0x1daac  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1dab1  ldarg.0
0x1dab2  ldfld    class Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_chkRequired
0x1dab7  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1dabc  ldarg.0
0x1dabd  newobj   instance void Microsoft.Crm.Application.Components.UI.Radio::.ctor()
0x1dac2  stfld    class Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_direction
0x1dac7  ldarg.0
0x1dac8  ldfld    class Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_direction
0x1dacd  ldarg.0
0x1dace  ldstr    aDirection// "direction"
0x1dad3  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetOptionItemId(string fieldName)
0x1dad8  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1dadd  ldarg.0
0x1dade  ldfld    class Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_direction
0x1dae3  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1dae8  ret
```
