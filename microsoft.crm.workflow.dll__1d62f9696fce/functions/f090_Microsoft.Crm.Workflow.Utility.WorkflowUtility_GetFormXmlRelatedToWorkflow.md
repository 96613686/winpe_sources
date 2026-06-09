# Microsoft.Crm.Workflow.Utility.WorkflowUtility::GetFormXmlRelatedToWorkflow

- ea: `0xf090`
- end: `0xf176`
- name: `Microsoft.Crm.Workflow.Utility.WorkflowUtility::GetFormXmlRelatedToWorkflow`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xf090`

## string_xrefs

- `0xf0f4`: `componentstate`
- `0xf13c`: `formxml`
- `0xf162`: `formxml`

## pseudocode

```c

```

## disassembly

```asm
0xf090  ldarg.0
0xf091  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_FormId()
0xf096  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf09b  brfalse.s loc_F09F
0xf09d  ldnull
0xf09e  ret
0xf09f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf0a4  stloc.0
0xf0a5  ldarg.0
0xf0a6  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_FormId()
0xf0ab  ldloca.s 0
0xf0ad  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xf0b2  brfalse  loc_F174
0xf0b7  ldnull
0xf0b8  stloc.1
0xf0b9  ldloc.0
0xf0ba  ldstr    aSystemform// "SystemForm"
0xf0bf  ldarg.1
0xf0c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xf0c5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0xf0ca  ldstr    aSystemform// "SystemForm"
0xf0cf  ldarg.1
0xf0d0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xf0d5  stloc.2
0xf0d6  ldloc.2
0xf0d7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf0dc  ldstr    aFormid// "formid"
0xf0e1  ldc.i4.0
0xf0e2  ldloc.0
0xf0e3  box      [mscorlib]System.Guid
0xf0e8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf0ed  pop
0xf0ee  ldloc.2
0xf0ef  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf0f4  ldstr    aComponentstate// "componentstate"
0xf0f9  ldc.i4.0
0xf0fa  ldc.i4.0
0xf0fb  box      [mscorlib]System.Int32
0xf100  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf105  pop
0xf106  ldloc.2
0xf107  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf10c  ldstr    aType// "type"
0xf111  ldc.i4.1
0xf112  ldc.i4.4
0xf113  box      [mscorlib]System.Int32
0xf118  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf11d  pop
0xf11e  ldloc.2
0xf11f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf124  ldstr    aSolutionid// "solutionid"
0xf129  ldc.i4.0
0xf12a  ldarg.2
0xf12b  box      [mscorlib]System.Guid
0xf130  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf135  pop
0xf136  ldloc.2
0xf137  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xf13c  ldstr    aFormxml// "formxml"
0xf141  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xf146  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0xf14b  ldloc.2
0xf14c  ldarg.1
0xf14d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity[] [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::ReadRawEntityRows(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf152  stloc.3
0xf153  ldloc.3
0xf154  brfalse.s loc_F172
0xf156  ldloc.3
0xf157  call     T0x2B000006
0xf15c  ldc.i4.0
0xf15d  ble.s    loc_F172
0xf15f  ldloc.3
0xf160  ldc.i4.0
0xf161  ldelem.ref
0xf162  ldstr    aFormxml// "formxml"
0xf167  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xf16c  isinst   [mscorlib]System.String
0xf171  stloc.1
0xf172  ldloc.1
0xf173  ret
0xf174  ldnull
0xf175  ret
```
