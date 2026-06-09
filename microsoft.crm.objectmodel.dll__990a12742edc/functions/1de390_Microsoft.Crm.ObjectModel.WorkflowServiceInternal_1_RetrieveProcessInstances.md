# Microsoft.Crm.ObjectModel.WorkflowServiceInternal`1::RetrieveProcessInstances

- ea: `0x1de390`
- end: `0x1de6a9`
- name: `Microsoft.Crm.ObjectModel.WorkflowServiceInternal`1::RetrieveProcessInstances`
- size: `793`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0xde580`
- `0x1de390`

## string_xrefs

- `0x1de3f0`: `processid`
- `0x1de513`: `processid`
- `0x1de53f`: `processid`
- `0x1de5d0`: `processid`
- `0x1de567`: `createdby`
- `0x1de55f`: `createdon`
- `0x1de56f`: `createdonbehalfby`
- `0x1de666`: `WorkflowServiceHandler`
- `0x1de66b`: `WorkflowServiceInternal.RetrieveProcessInstances`
- `0x1de67b`: `WorkflowServiceInternal retrieved {0} ProcessInstances.`

## pseudocode

```c

```

## disassembly

```asm
0x1de390  ldarg.1
0x1de391  ldstr    aEntityid_3// "entityId"
0x1de396  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1de39b  ldarg.2
0x1de39c  ldstr    aEntitylogicaln_3// "entityLogicalName"
0x1de3a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1de3a6  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x1de3ab  stloc.0
0x1de3ac  ldloc.0
0x1de3ad  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x1de3b2  ldstr    aWorkflow// "Workflow"
0x1de3b7  ldarg.3
0x1de3b8  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1de3bd  stloc.1
0x1de3be  ldloc.1
0x1de3bf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1de3c4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x1de3c9  ldloc.1
0x1de3ca  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1de3cf  ldc.i4.2
0x1de3d0  newarr   [mscorlib]System.String
0x1de3d5  dup
0x1de3d6  ldc.i4.0
0x1de3d7  ldstr    aProcessroleass// "processroleassignment"
0x1de3dc  stelem.ref
0x1de3dd  dup
0x1de3de  ldc.i4.1
0x1de3df  ldstr    aUniquename// "uniquename"
0x1de3e4  stelem.ref
0x1de3e5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1de3ea  ldloc.1
0x1de3eb  ldstr    aProcessstage// "ProcessStage"
0x1de3f0  ldstr    aProcessid// "processid"
0x1de3f5  ldstr    aWorkflowid// "workflowid"
0x1de3fa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0x1de3ff  dup
0x1de400  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x1de405  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x1de40a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1de40f  dup
0x1de410  ldstr    aProcessstage// "ProcessStage"
0x1de415  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::set_TableAlias(string)
0x1de41a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0x1de41f  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x1de424  ldc.i4.0
0x1de425  ldarg.3
0x1de426  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1de42b  ldarg.2
0x1de42c  ldc.i4.1
0x1de42d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1de432  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1de437  box      [mscorlib]System.Int32
0x1de43c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1de441  pop
0x1de442  ldloc.1
0x1de443  ldc.i4.1
0x1de444  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Distinct(bool)
0x1de449  ldloc.1
0x1de44a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1de44f  ldstr    aStatuscode// "statuscode"
0x1de454  ldc.i4.0
0x1de455  ldc.i4.2
0x1de456  box      [mscorlib]System.Int32
0x1de45b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1de460  pop
0x1de461  ldarg.0
0x1de462  ldloc.1
0x1de463  ldarg.3
0x1de464  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1de469  stloc.2
0x1de46a  ldarg.0
0x1de46b  call     instance class Microsoft.Crm.ObjectModel.BusinessProcessFlowServiceInternalHandler`1<var<u1>> class Microsoft.Crm.ObjectModel.WorkflowServiceInternal`1<var<u1>>::GetBusinessProcessFlowHandler()
0x1de470  ldloc.2
0x1de471  ldarg.3
0x1de472  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection class Microsoft.Crm.ObjectModel.BusinessProcessFlowServiceInternalHandler`1<var<u1>>::FilterProcessesByRole(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1de477  stloc.3
0x1de478  ldloc.3
0x1de479  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1de47e  ldc.i4.1
0x1de47f  bge.s    loc_1DE48D
0x1de481  ldstr    aBusinessproces_0// "BusinessProcessFlowInstance"
0x1de486  ldarg.3
0x1de487  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1de48c  ret
0x1de48d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1de492  stloc.s  4
0x1de494  ldloc.3
0x1de495  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1de49a  stloc.s  8
0x1de49c  br.s     loc_1DE4CE
0x1de49e  ldloc.s  8
0x1de4a0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1de4a5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1de4aa  stloc.s  9
0x1de4ac  ldloc.s  4
0x1de4ae  ldloc.s  9
0x1de4b0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1de4b5  ldstr    aWorkflowid// "workflowid"
0x1de4ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x1de4bf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1de4c4  unbox.any [mscorlib]System.Guid
0x1de4c9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1de4ce  ldloc.s  8
0x1de4d0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1de4d5  brtrue.s loc_1DE49E
0x1de4d7  leave.s  loc_1DE4EE
0x1de4d9  ldloc.s  8
0x1de4db  isinst   [mscorlib]System.IDisposable
0x1de4e0  stloc.s  0xA
0x1de4e2  ldloc.s  0xA
0x1de4e4  brfalse.s loc_1DE4ED
0x1de4e6  ldloc.s  0xA
0x1de4e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1de4ed  endfinally
0x1de4ee  ldstr    aBusinessproces_0// "BusinessProcessFlowInstance"
0x1de4f3  ldarg.3
0x1de4f4  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1de4f9  stloc.s  5
0x1de4fb  ldloc.s  5
0x1de4fd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1de502  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x1de507  ldloc.s  5
0x1de509  ldstr    aWorkflow// "Workflow"
0x1de50e  ldstr    aWorkflowid// "workflowid"
0x1de513  ldstr    aProcessid// "processid"
0x1de518  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0x1de51d  ldstr    aProcess// "Process"
0x1de522  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::set_TableAlias(string)
0x1de527  ldloc.s  5
0x1de529  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1de52e  ldc.i4.s 0xB
0x1de530  newarr   [mscorlib]System.String
0x1de535  dup
0x1de536  ldc.i4.0
0x1de537  ldstr    aProcessstageid// "processstageid"
0x1de53c  stelem.ref
0x1de53d  dup
0x1de53e  ldc.i4.1
0x1de53f  ldstr    aProcessid// "processid"
0x1de544  stelem.ref
0x1de545  dup
0x1de546  ldc.i4.2
0x1de547  ldstr    aStatecode// "statecode"
0x1de54c  stelem.ref
0x1de54d  dup
0x1de54e  ldc.i4.3
0x1de54f  ldstr    aStatuscode// "statuscode"
0x1de554  stelem.ref
0x1de555  dup
0x1de556  ldc.i4.4
0x1de557  ldstr    aName// "name"
0x1de55c  stelem.ref
0x1de55d  dup
0x1de55e  ldc.i4.5
0x1de55f  ldstr    aCreatedon// "createdon"
0x1de564  stelem.ref
0x1de565  dup
0x1de566  ldc.i4.6
0x1de567  ldstr    aCreatedby// "createdby"
0x1de56c  stelem.ref
0x1de56d  dup
0x1de56e  ldc.i4.7
0x1de56f  ldstr    aCreatedonbehal// "createdonbehalfby"
0x1de574  stelem.ref
0x1de575  dup
0x1de576  ldc.i4.8
0x1de577  ldstr    aModifiedon_0// "modifiedon"
0x1de57c  stelem.ref
0x1de57d  dup
0x1de57e  ldc.i4.s 9
0x1de580  ldstr    aModifiedby_0// "modifiedby"
0x1de585  stelem.ref
0x1de586  dup
0x1de587  ldc.i4.s 0xA
0x1de589  ldstr    aModifiedonbeha// "modifiedonbehalfby"
0x1de58e  stelem.ref
0x1de58f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1de594  ldloc.s  5
0x1de596  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x1de59b  ldc.i4.0
0x1de59c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>::get_Item(!!T0)
0x1de5a1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x1de5a6  ldc.i4.3
0x1de5a7  newarr   [mscorlib]System.String
0x1de5ac  dup
0x1de5ad  ldc.i4.0
0x1de5ae  ldstr    aName// "name"
0x1de5b3  stelem.ref
0x1de5b4  dup
0x1de5b5  ldc.i4.1
0x1de5b6  ldstr    aStatecode// "statecode"
0x1de5bb  stelem.ref
0x1de5bc  dup
0x1de5bd  ldc.i4.2
0x1de5be  ldstr    aStatuscode// "statuscode"
0x1de5c3  stelem.ref
0x1de5c4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1de5c9  ldloc.s  5
0x1de5cb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1de5d0  ldstr    aProcessid// "processid"
0x1de5d5  ldc.i4.8
0x1de5d6  ldloc.s  4
0x1de5d8  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x1de5dd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x1de5e2  pop
0x1de5e3  ldloc.s  5
0x1de5e5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0x1de5ea  ldstr    aModifiedon_0// "modifiedon"
0x1de5ef  ldc.i4.1
0x1de5f0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x1de5f5  ldloc.s  5
0x1de5f7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1de5fc  ldc.i4.1
0x1de5fd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1de602  stloc.s  6
0x1de604  ldc.i4.0
0x1de605  stloc.s  0xB
0x1de607  br.s     loc_1DE62B
0x1de609  ldloc.s  6
0x1de60b  ldc.i4.1
0x1de60c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1de611  ldloc.s  0xB
0x1de613  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetAttributeNameForEntityId(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition)
0x1de618  ldc.i4.0
0x1de619  ldarg.1
0x1de61a  box      [mscorlib]System.Guid
0x1de61f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1de624  pop
0x1de625  ldloc.s  0xB
0x1de627  ldc.i4.1
0x1de628  add
0x1de629  stloc.s  0xB
0x1de62b  ldloc.s  0xB
0x1de62d  ldc.i4.4
0x1de62e  ble.s    loc_1DE609
0x1de630  newobj   instance void Microsoft.Crm.ObjectModel.BusinessProcessFlowInstanceService::.ctor()
0x1de635  ldloc.s  5
0x1de637  ldarg.3
0x1de638  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1de63d  stloc.s  7
0x1de63f  ldloc.0
0x1de640  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x1de645  call     class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.WorkflowTelemetryEventSource [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.WorkflowTelemetryEventSource::get_Instance()
0x1de64a  ldarg.3
0x1de64b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1de650  ldarg.3
0x1de651  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0x1de656  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_RequestId()
0x1de65b  ldarg.3
0x1de65c  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0x1de661  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_CorrelationId()
0x1de666  ldstr    aWorkflowservic// "WorkflowServiceHandler"
0x1de66b  ldstr    aWorkflowservic_0// "WorkflowServiceInternal.RetrieveProcess"...
0x1de670  ldloc.0
0x1de671  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x1de676  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1de67b  ldstr    aWorkflowservic_1// "WorkflowServiceInternal retrieved {0} P"...
0x1de680  ldc.i4.1
0x1de681  newarr   [mscorlib]System.Object
0x1de686  dup
0x1de687  ldc.i4.0
0x1de688  ldloc.s  7
0x1de68a  brtrue.s loc_1DE68F
0x1de68c  ldc.i4.0
0x1de68d  br.s     loc_1DE696
0x1de68f  ldloc.s  7
0x1de691  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1de696  box      [mscorlib]System.Int32
0x1de69b  stelem.ref
0x1de69c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1de6a1  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.WorkflowTelemetryEventSource::LogProcessUnificationPerfExecutionTime(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, string, int64, string)
0x1de6a6  ldloc.s  7
0x1de6a8  ret
```
