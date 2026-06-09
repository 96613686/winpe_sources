# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetLocalizedDayCheckBoxes

- ea: `0xe4f0`
- end: `0xe641`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetLocalizedDayCheckBoxes`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xdb30`

## callees

- `0xe190`
- `0xe1e0`
- `0xe4f0`

## pseudocode

```c

```

## disassembly

```asm
0xe4f0  ldstr    aDiv// "div"
0xe4f5  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xe4fa  stloc.0
0xe4fb  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::.ctor()
0xe500  stloc.1
0xe501  ldloc.1
0xe502  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe507  ldstr    aClass// "class"
0xe50c  ldstr    aStdtable// "stdTable"
0xe511  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xe516  ldc.i4.2
0xe517  newarr   [System.Web]System.Web.UI.HtmlControls.HtmlTableRow
0xe51c  stloc.2
0xe51d  ldloc.2
0xe51e  ldc.i4.0
0xe51f  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0xe524  stelem.ref
0xe525  ldloc.2
0xe526  ldc.i4.1
0xe527  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0xe52c  stelem.ref
0xe52d  ldstr    aChkweekday// "chkWeekday"
0xe532  stloc.3
0xe533  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xe538  stloc.s  4
0xe53a  ldc.i4.0
0xe53b  stloc.s  5
0xe53d  br       loc_E60F
0xe542  ldarg.0
0xe543  ldarg.0
0xe544  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_firstDayOfWeek
0xe549  ldloc.s  5
0xe54b  add
0xe54c  ldc.i4.7
0xe54d  rem
0xe54e  call     instance valuetype [mscorlib]System.DayOfWeek Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::DayOfWeekFromInt(int32 day)
0xe553  stloc.s  6
0xe555  ldarg.0
0xe556  ldloc.s  6
0xe558  call     instance int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetDaysOfWeekMask(valuetype [mscorlib]System.DayOfWeek dayIndex)
0xe55d  stloc.s  7
0xe55f  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::.ctor()
0xe564  stloc.s  8
0xe566  ldloc.s  8
0xe568  ldloc.3
0xe569  ldloca.s 7
0xe56b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe570  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe575  call     string [mscorlib]System.String::Concat(string, string)
0xe57a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xe57f  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0xe584  stloc.s  9
0xe586  newobj   instance void [System.Web]System.Web.UI.WebControls.Label::.ctor()
0xe58b  stloc.s  0xA
0xe58d  ldloc.s  0xA
0xe58f  ldloc.s  8
0xe591  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xe596  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_AssociatedControlID(string)
0xe59b  ldloc.s  0xA
0xe59d  ldloc.s  4
0xe59f  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xe5a4  ldloc.s  6
0xe5a6  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::GetDayName(valuetype [mscorlib]System.DayOfWeek)
0xe5ab  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0xe5b0  ldloc.s  9
0xe5b2  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe5b7  ldstr    aTitle// "title"
0xe5bc  ldloc.s  0xA
0xe5be  callvirt instance string [System.Web]System.Web.UI.WebControls.Label::get_Text()
0xe5c3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xe5c8  ldloc.s  9
0xe5ca  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xe5cf  ldloc.s  8
0xe5d1  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xe5d6  ldloc.s  9
0xe5d8  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xe5dd  ldloc.s  0xA
0xe5df  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xe5e4  ldloc.s  5
0xe5e6  ldc.i4.4
0xe5e7  bge.s    loc_E5FA
0xe5e9  ldloc.2
0xe5ea  ldc.i4.0
0xe5eb  ldelem.ref
0xe5ec  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::get_Cells()
0xe5f1  ldloc.s  9
0xe5f3  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell)
0xe5f8  br.s     loc_E609
0xe5fa  ldloc.2
0xe5fb  ldc.i4.1
0xe5fc  ldelem.ref
0xe5fd  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::get_Cells()
0xe602  ldloc.s  9
0xe604  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell)
0xe609  ldloc.s  5
0xe60b  ldc.i4.1
0xe60c  add
0xe60d  stloc.s  5
0xe60f  ldloc.s  5
0xe611  ldc.i4.7
0xe612  blt      loc_E542
0xe617  ldloc.1
0xe618  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0xe61d  ldloc.2
0xe61e  ldc.i4.0
0xe61f  ldelem.ref
0xe620  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow)
0xe625  ldloc.1
0xe626  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0xe62b  ldloc.2
0xe62c  ldc.i4.1
0xe62d  ldelem.ref
0xe62e  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow)
0xe633  ldloc.0
0xe634  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xe639  ldloc.1
0xe63a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xe63f  ldloc.0
0xe640  ret
```
