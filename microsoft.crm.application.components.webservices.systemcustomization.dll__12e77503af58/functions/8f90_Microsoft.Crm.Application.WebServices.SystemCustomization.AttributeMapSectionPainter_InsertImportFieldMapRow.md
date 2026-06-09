# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InsertImportFieldMapRow

- ea: `0x8f90`
- end: `0x9055`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InsertImportFieldMapRow`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x87a0`
- `0x8a00`

## callees

- `0x8f90`

## pseudocode

```c

```

## disassembly

```asm
0x8f90  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0x8f95  stloc.0
0x8f96  ldarg.3
0x8f97  brfalse.s loc_8FB0
0x8f99  ldloc.0
0x8f9a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8f9f  ldstr    aClass// "class"
0x8fa4  ldstr    aMandatoryrowMs// "MandatoryRow mscrm-iw-AMP-MapSectionDat"...
0x8fa9  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x8fae  br.s     loc_8FC5
0x8fb0  ldloc.0
0x8fb1  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8fb6  ldstr    aClass// "class"
0x8fbb  ldstr    aOtherfieldsrow// "OtherFieldsRow mscrm-iw-AMP-MapSectionD"...
0x8fc0  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x8fc5  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x8fca  stloc.1
0x8fcb  ldloc.1
0x8fcc  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8fd1  ldstr    aClass// "class"
0x8fd6  ldstr    aMscrmIwAmpCol1_0// "mscrm-iw-AMP-Col1"
0x8fdb  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8fe0  ldloc.1
0x8fe1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x8fe6  ldarg.1
0x8fe7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x8fec  ldloc.0
0x8fed  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::get_Cells()
0x8ff2  ldloc.1
0x8ff3  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell)
0x8ff8  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x8ffd  stloc.2
0x8ffe  ldloc.2
0x8fff  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9004  ldstr    aClass// "class"
0x9009  ldstr    aMscrmIwAmpCol2// "mscrm-iw-AMP-Col2"
0x900e  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9013  ldloc.2
0x9014  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x9019  ldarg.2
0x901a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x901f  ldloc.0
0x9020  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::get_Cells()
0x9025  ldloc.2
0x9026  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell)
0x902b  ldarg.3
0x902c  brfalse.s loc_9042
0x902e  ldarg.0
0x902f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x9034  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0x9039  ldc.i4.1
0x903a  ldloc.0
0x903b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::Insert(int32, class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow)
0x9040  br.s     loc_9053
0x9042  ldarg.0
0x9043  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x9048  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0x904d  ldloc.0
0x904e  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow)
0x9053  ldloc.0
0x9054  ret
```
