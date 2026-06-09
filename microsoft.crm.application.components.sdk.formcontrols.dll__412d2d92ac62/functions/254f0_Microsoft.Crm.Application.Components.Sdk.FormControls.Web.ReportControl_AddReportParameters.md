# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::AddReportParameters

- ea: `0x254f0`
- end: `0x25690`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::AddReportParameters`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x25440`

## callees

- `0x24e50`
- `0x254f0`
- `0x25690`

## string_xrefs

- `0x25513`: `isscheduledreport`
- `0x255b8`: `isscheduledreport`
- `0x255b2`: `isScheduledReport`

## pseudocode

```c

```

## disassembly

```asm
0x254f0  ldstr    aReport// "report"
0x254f5  ldarg.0
0x254f6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::_reportId
0x254fb  ldc.i4.6
0x254fc  newarr   [mscorlib]System.String
0x25501  dup
0x25502  ldc.i4.0
0x25503  ldstr    aName// "name"
0x25508  stelem.ref
0x25509  dup
0x2550a  ldc.i4.1
0x2550b  ldstr    aDefaultfilter// "defaultfilter"
0x25510  stelem.ref
0x25511  dup
0x25512  ldc.i4.2
0x25513  ldstr    aIsscheduledrep// "isscheduledreport"
0x25518  stelem.ref
0x25519  dup
0x2551a  ldc.i4.3
0x2551b  ldstr    aSignatureid// "signatureid"
0x25520  stelem.ref
0x25521  dup
0x25522  ldc.i4.4
0x25523  ldstr    aIscustomreport// "iscustomreport"
0x25528  stelem.ref
0x25529  dup
0x2552a  ldc.i4.5
0x2552b  ldstr    aReportnameonsr// "reportnameonsrs"
0x25530  stelem.ref
0x25531  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25536  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2553b  stloc.0
0x2553c  ldarg.0
0x2553d  ldarg.1
0x2553e  ldstr    aId// "id"
0x25543  ldarg.0
0x25544  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::_reportId
0x25549  constrained. [mscorlib]System.Guid
0x2554f  callvirt instance string [mscorlib]System.Object::ToString()
0x25554  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::AddParameter(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl parametersDivControl, string name, string value)
0x25559  ldarg.0
0x2555a  ldarg.1
0x2555b  ldstr    aUniquename// "uniquename"
0x25560  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25565  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2556a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::AddParameter(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl parametersDivControl, string name, string value)
0x2556f  ldarg.0
0x25570  ldarg.1
0x25571  ldstr    aIscustomreport// "iscustomreport"
0x25576  ldloc.0
0x25577  ldstr    aSignatureid// "signatureid"
0x2557c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x25581  brfalse.s loc_2558A
0x25583  ldstr    aFalse// "false"
0x25588  br.s     loc_2558F
0x2558a  ldstr    aTrue// "true"
0x2558f  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::AddParameter(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl parametersDivControl, string name, string value)
0x25594  ldarg.0
0x25595  ldarg.1
0x25596  ldstr    aReportnameonsr// "reportnameonsrs"
0x2559b  ldloc.0
0x2559c  ldstr    aReportnameonsr// "reportnameonsrs"
0x255a1  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x255a6  castclass [mscorlib]System.String
0x255ab  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::AddParameter(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl parametersDivControl, string name, string value)
0x255b0  ldarg.0
0x255b1  ldarg.1
0x255b2  ldstr    aIsscheduledrep_0// "isScheduledReport"
0x255b7  ldloc.0
0x255b8  ldstr    aIsscheduledrep// "isscheduledreport"
0x255bd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x255c2  unbox.any [mscorlib]System.Boolean
0x255c7  brtrue.s loc_255D0
0x255c9  ldstr    aFalse// "false"
0x255ce  br.s     loc_255D5
0x255d0  ldstr    aTrue// "true"
0x255d5  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::AddParameter(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl parametersDivControl, string name, string value)
0x255da  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x255df  stloc.3
0x255e0  ldloca.s 3
0x255e2  ldarg.0
0x255e3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::_snapshotId
0x255e8  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x255ed  brtrue.s loc_2560C
0x255ef  ldarg.0
0x255f0  ldarg.1
0x255f1  ldstr    aSnapshotid// "snapshotId"
0x255f6  ldarg.0
0x255f7  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::_snapshotId
0x255fc  constrained. [mscorlib]System.Guid
0x25602  callvirt instance string [mscorlib]System.Object::ToString()
0x25607  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::AddParameter(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl parametersDivControl, string name, string value)
0x2560c  ldnull
0x2560d  stloc.1
0x2560e  ldloc.0
0x2560f  ldstr    aDefaultfilter// "defaultfilter"
0x25614  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x25619  stloc.2
0x2561a  ldloc.2
0x2561b  brfalse.s loc_2562C
0x2561d  ldloc.2
0x2561e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x25623  beq.s    loc_2562C
0x25625  ldloc.2
0x25626  castclass [mscorlib]System.String
0x2562b  stloc.1
0x2562c  ldloc.1
0x2562d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25632  brtrue.s loc_2566F
0x25634  ldloc.1
0x25635  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Reports.ReportUtility::GetAndVerifyFilter(string)
0x2563a  stloc.s  4
0x2563c  ldarg.0
0x2563d  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppFilterEditor::.ctor()
0x25642  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppFilterEditor Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::_filterEditorControl
0x25647  ldarg.0
0x25648  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppFilterEditor Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::_filterEditorControl
0x2564d  ldarg.0
0x2564e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x25653  ldstr    aReportcontrolf_2// "_ReportControlFilterEditor"
0x25658  call     string [mscorlib]System.String::Concat(string, string)
0x2565d  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x25662  ldarg.0
0x25663  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppFilterEditor Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::_filterEditorControl
0x25668  ldloc.s  4
0x2566a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppFilterEditor::set_DefaultFilter(class [System.Xml]System.Xml.XmlDocument)
0x2566f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x25674  brfalse.s loc_2568F
0x25676  ldarg.0
0x25677  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::get_PromptAreaCollapsed()
0x2567c  brfalse.s loc_2568F
0x2567e  ldarg.0
0x2567f  ldarg.1
0x25680  ldstr    aPromptareacoll// "PromptAreaCollapsed"
0x25685  ldstr    aTrue// "true"
0x2568a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::AddParameter(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl parametersDivControl, string name, string value)
0x2568f  ret
```
