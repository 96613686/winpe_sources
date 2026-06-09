# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::GetReportControlTable

- ea: `0x25000`
- end: `0x251ea`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::GetReportControlTable`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x24f30`

## callees

- `0x189e0`
- `0x25000`
- `0x251f0`
- `0x25290`
- `0x253d0`

## pseudocode

```c

```

## disassembly

```asm
0x25000  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::.ctor()
0x25005  stloc.0
0x25006  ldloc.0
0x25007  ldstr    a100// "100%"
0x2500c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::set_Height(string)
0x25011  ldloc.0
0x25012  ldstr    a100// "100%"
0x25017  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::set_Width(string)
0x2501c  ldloc.0
0x2501d  ldc.i4.0
0x2501e  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::set_CellSpacing(int32)
0x25023  ldloc.0
0x25024  ldc.i4.0
0x25025  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::set_CellPadding(int32)
0x2502a  ldloc.0
0x2502b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x25030  ldstr    aTableLayout// "table-layout"
0x25035  ldstr    aFixed_0// "fixed"
0x2503a  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2503f  ldloc.0
0x25040  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x25045  ldstr    aClass// "class"
0x2504a  ldstr    aMsCrmReportcon// "ms-crm-ReportControl"
0x2504f  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x25054  ldnull
0x25055  stloc.1
0x25056  ldnull
0x25057  stloc.2
0x25058  ldnull
0x25059  stloc.3
0x2505a  ldnull
0x2505b  stloc.s  4
0x2505d  ldnull
0x2505e  stloc.s  5
0x25060  ldnull
0x25061  stloc.s  6
0x25063  ldnull
0x25064  stloc.s  7
0x25066  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0x2506b  stloc.1
0x2506c  ldloc.1
0x2506d  ldstr    aReportcontrolf_0// "ReportControlFrameRow"
0x25072  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x25077  ldloc.1
0x25078  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2507d  ldstr    aStyle// "style"
0x25082  ldstr    aDisplayNone_2// "display:none"
0x25087  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2508c  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x25091  stloc.2
0x25092  ldarg.0
0x25093  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::GetReportControlFrame()
0x25098  stloc.3
0x25099  ldloc.2
0x2509a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2509f  ldloc.3
0x250a0  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x250a5  ldloc.1
0x250a6  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x250ab  ldloc.2
0x250ac  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x250b1  ldloc.0
0x250b2  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x250b7  ldloc.1
0x250b8  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x250bd  ldloc.1
0x250be  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x250c3  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0x250c8  stloc.1
0x250c9  ldloc.1
0x250ca  ldstr    aReportcontrolp// "ReportControlProgressRow"
0x250cf  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x250d4  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x250d9  stloc.s  4
0x250db  ldloc.s  4
0x250dd  ldstr    aCenter// "center"
0x250e2  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_Align(string)
0x250e7  ldarg.0
0x250e8  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::GetProgressTable()
0x250ed  stloc.s  5
0x250ef  ldloc.s  4
0x250f1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x250f6  ldloc.s  5
0x250f8  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x250fd  ldloc.1
0x250fe  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x25103  ldloc.s  4
0x25105  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2510a  ldloc.0
0x2510b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x25110  ldloc.1
0x25111  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x25116  ldarg.0
0x25117  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OnDemandCrmWebFormControl::get_LoadDataOnDemand()
0x2511c  brfalse.s loc_2518C
0x2511e  ldloc.1
0x2511f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x25124  ldstr    aStyle// "style"
0x25129  ldstr    aDisplayNone_2// "display:none"
0x2512e  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x25133  ldloc.1
0x25134  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x25139  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0x2513e  stloc.1
0x2513f  ldloc.1
0x25140  ldstr    aReportcontroll// "ReportControlLoadOnDemandRow"
0x25145  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2514a  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x2514f  stloc.s  6
0x25151  ldloc.s  6
0x25153  ldstr    aCenter// "center"
0x25158  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_Align(string)
0x2515d  ldarg.0
0x2515e  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::GetLoadOnDemandSpan()
0x25163  stloc.s  7
0x25165  ldloc.s  6
0x25167  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2516c  ldloc.s  7
0x2516e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x25173  ldloc.1
0x25174  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x25179  ldloc.s  6
0x2517b  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x25180  ldloc.0
0x25181  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x25186  ldloc.1
0x25187  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2518c  leave.s  loc_251E8
0x2518e  ldloc.1
0x2518f  brfalse.s loc_25199
0x25191  ldloc.1
0x25192  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x25197  ldnull
0x25198  stloc.1
0x25199  ldloc.2
0x2519a  brfalse.s loc_251A4
0x2519c  ldloc.2
0x2519d  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x251a2  ldnull
0x251a3  stloc.2
0x251a4  ldloc.3
0x251a5  brfalse.s loc_251AF
0x251a7  ldloc.3
0x251a8  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x251ad  ldnull
0x251ae  stloc.3
0x251af  ldloc.s  4
0x251b1  brfalse.s loc_251BD
0x251b3  ldloc.s  4
0x251b5  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x251ba  ldnull
0x251bb  stloc.s  4
0x251bd  ldloc.s  5
0x251bf  brfalse.s loc_251CB
0x251c1  ldloc.s  5
0x251c3  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x251c8  ldnull
0x251c9  stloc.s  5
0x251cb  ldloc.s  6
0x251cd  brfalse.s loc_251D9
0x251cf  ldloc.s  6
0x251d1  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x251d6  ldnull
0x251d7  stloc.s  6
0x251d9  ldloc.s  7
0x251db  brfalse.s loc_251E7
0x251dd  ldloc.s  7
0x251df  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x251e4  ldnull
0x251e5  stloc.s  7
0x251e7  endfinally
0x251e8  ldloc.0
0x251e9  ret
```
