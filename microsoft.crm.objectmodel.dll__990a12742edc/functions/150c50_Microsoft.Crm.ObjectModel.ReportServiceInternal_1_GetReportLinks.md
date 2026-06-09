# Microsoft.Crm.ObjectModel.ReportServiceInternal`1::GetReportLinks

- ea: `0x150c50`
- end: `0x150cce`
- name: `Microsoft.Crm.ObjectModel.ReportServiceInternal`1::GetReportLinks`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x150c50`: `ReportLink`
- `0x150c93`: `ReportLink`
- `0x150c68`: `linkedreportid`
- `0x150c73`: `linkedreportname`
- `0x150c5d`: `reportlinkid`
- `0x150c7e`: `linktypecode`
- `0x150cb3`: `linktypecode`

## pseudocode

```c

```

## disassembly

```asm
0x150c50  ldstr    aReportlink// "ReportLink"
0x150c55  ldarg.3
0x150c56  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x150c5b  stloc.0
0x150c5c  ldloc.0
0x150c5d  ldstr    aReportlinkid// "reportlinkid"
0x150c62  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x150c67  ldloc.0
0x150c68  ldstr    aLinkedreportid// "linkedreportid"
0x150c6d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x150c72  ldloc.0
0x150c73  ldstr    aLinkedreportna// "linkedreportname"
0x150c78  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x150c7d  ldloc.0
0x150c7e  ldstr    aLinktypecode// "linktypecode"
0x150c83  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x150c88  ldloc.0
0x150c89  ldstr    aReportid// "reportid"
0x150c8e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x150c93  ldstr    aReportlink// "ReportLink"
0x150c98  ldarg.3
0x150c99  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x150c9e  stloc.1
0x150c9f  ldloc.1
0x150ca0  ldstr    aReportid// "reportid"
0x150ca5  ldc.i4.0
0x150ca6  ldarg.1
0x150ca7  box      [mscorlib]System.Guid
0x150cac  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x150cb1  pop
0x150cb2  ldloc.1
0x150cb3  ldstr    aLinktypecode// "linktypecode"
0x150cb8  ldc.i4.8
0x150cb9  ldarg.2
0x150cba  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x150cbf  pop
0x150cc0  newobj   instance void class Microsoft.Crm.ObjectModel.ReportLinkServiceInternal`1<var<u1>>::.ctor()
0x150cc5  ldloc.1
0x150cc6  ldloc.0
0x150cc7  ldarg.3
0x150cc8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x150ccd  ret
```
