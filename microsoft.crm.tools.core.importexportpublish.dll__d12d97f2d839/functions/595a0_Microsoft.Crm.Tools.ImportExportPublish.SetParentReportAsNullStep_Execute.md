# Microsoft.Crm.Tools.ImportExportPublish.SetParentReportAsNullStep::Execute

- ea: `0x595a0`
- end: `0x59610`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SetParentReportAsNullStep::Execute`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x595a0`

## string_xrefs

- `0x595a5`: `ReportLink`
- `0x595bc`: `ReportLink`
- `0x595b2`: `reportlinkid`
- `0x595c9`: `linkedreportid`

## pseudocode

```c

```

## disassembly

```asm
0x595a0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ReportLinkService::.ctor()
0x595a5  ldstr    aReportlink// "ReportLink"
0x595aa  ldarg.3
0x595ab  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x595b0  stloc.0
0x595b1  ldloc.0
0x595b2  ldstr    aReportlinkid// "reportlinkid"
0x595b7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x595bc  ldstr    aReportlink// "ReportLink"
0x595c1  ldarg.3
0x595c2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x595c7  stloc.1
0x595c8  ldloc.1
0x595c9  ldstr    aLinkedreportid// "linkedreportid"
0x595ce  ldc.i4.0
0x595cf  ldarg.1
0x595d0  ldstr    aReportid// "reportid"
0x595d5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x595da  unbox.any [mscorlib]System.Guid
0x595df  box      [mscorlib]System.Guid
0x595e4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x595e9  pop
0x595ea  ldloc.1
0x595eb  ldloc.0
0x595ec  ldarg.3
0x595ed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x595f2  stloc.2
0x595f3  ldloc.2
0x595f4  brfalse.s loc_5960F
0x595f6  ldloc.2
0x595f7  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x595fc  ldc.i4.0
0x595fd  ble.s    loc_5960F
0x595ff  ldarg.1
0x59600  ldstr    aParentreportid// "parentreportid"
0x59605  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5960a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5960f  ret
```
