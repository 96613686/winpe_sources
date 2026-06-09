# Microsoft.Crm.Workflow.Utility.WorkflowUtility::GetFormXmlRelatedToWorkflow_0

- ea: `0xf180`
- end: `0xf21e`
- name: `Microsoft.Crm.Workflow.Utility.WorkflowUtility::GetFormXmlRelatedToWorkflow_0`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1e6b0`

## callees

- `0xf180`

## string_xrefs

- `0xf1d0`: `componentstate`
- `0xf1e8`: `formxml`
- `0xf20a`: `formxml`

## pseudocode

```c

```

## disassembly

```asm
0xf180  ldarg.0
0xf181  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_FormId()
0xf186  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf18b  brfalse.s loc_F18F
0xf18d  ldnull
0xf18e  ret
0xf18f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf194  stloc.0
0xf195  ldarg.0
0xf196  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_FormId()
0xf19b  ldloca.s 0
0xf19d  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xf1a2  brfalse.s loc_F21C
0xf1a4  ldnull
0xf1a5  stloc.1
0xf1a6  ldstr    aSystemform// "SystemForm"
0xf1ab  ldarg.1
0xf1ac  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xf1b1  stloc.2
0xf1b2  ldloc.2
0xf1b3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf1b8  ldstr    aFormid// "formid"
0xf1bd  ldc.i4.0
0xf1be  ldloc.0
0xf1bf  box      [mscorlib]System.Guid
0xf1c4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf1c9  pop
0xf1ca  ldloc.2
0xf1cb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf1d0  ldstr    aComponentstate// "componentstate"
0xf1d5  ldc.i4.0
0xf1d6  ldc.i4.0
0xf1d7  box      [mscorlib]System.Int32
0xf1dc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf1e1  pop
0xf1e2  ldloc.2
0xf1e3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xf1e8  ldstr    aFormxml// "formxml"
0xf1ed  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xf1f2  ldarg.2
0xf1f3  ldloc.2
0xf1f4  ldarg.1
0xf1f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf1fa  stloc.3
0xf1fb  ldloc.3
0xf1fc  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xf201  brfalse.s loc_F21A
0xf203  ldloc.3
0xf204  ldc.i4.0
0xf205  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xf20a  ldstr    aFormxml// "formxml"
0xf20f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xf214  isinst   [mscorlib]System.String
0xf219  stloc.1
0xf21a  ldloc.1
0xf21b  ret
0xf21c  ldnull
0xf21d  ret
```
