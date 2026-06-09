# Microsoft.Crm.Reporting.ReportPublisher::GetCustomReports

- ea: `0x45c0`
- end: `0x464d`
- name: `Microsoft.Crm.Reporting.ReportPublisher::GetCustomReports`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4410`

## callees

- `0x410`

## string_xrefs

- `0x4627`: `customreportxml`

## pseudocode

```c

```

## disassembly

```asm
0x45c0  ldstr    aReport_0// "Report"
0x45c5  ldarg.0
0x45c6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Reporting.ReportPublisher::_context
0x45cb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x45d0  stloc.0
0x45d1  ldloc.0
0x45d2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x45d7  ldstr    aIscustomreport// "iscustomreport"
0x45dc  ldc.i4.0
0x45dd  ldc.i4.1
0x45de  box      [mscorlib]System.Boolean
0x45e3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x45e8  pop
0x45e9  ldloc.0
0x45ea  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x45ef  ldstr    aLanguagecode// "languagecode"
0x45f4  ldc.i4.0
0x45f5  ldarg.1
0x45f6  box      [mscorlib]System.Int32
0x45fb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4600  pop
0x4601  ldloc.0
0x4602  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4607  ldc.i4.5
0x4608  newarr   [mscorlib]System.String
0x460d  dup
0x460e  ldc.i4.0
0x460f  ldstr    aName_0// "name"
0x4614  stelem.ref
0x4615  dup
0x4616  ldc.i4.1
0x4617  ldstr    aDescription// "description"
0x461c  stelem.ref
0x461d  dup
0x461e  ldc.i4.2
0x461f  ldstr    aDefaultfilter// "defaultfilter"
0x4624  stelem.ref
0x4625  dup
0x4626  ldc.i4.3
0x4627  ldstr    aCustomreportxm// "customreportxml"
0x462c  stelem.ref
0x462d  dup
0x462e  ldc.i4.4
0x462f  ldstr    aSolutionid// "solutionid"
0x4634  stelem.ref
0x4635  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x463a  ldarg.0
0x463b  ldfld    class Microsoft.Crm.Reporting.IReportService Microsoft.Crm.Reporting.ReportPublisher::_reportService
0x4640  ldloc.0
0x4641  ldarg.0
0x4642  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Reporting.ReportPublisher::_context
0x4647  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Reporting.IReportService::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x464c  ret
```
