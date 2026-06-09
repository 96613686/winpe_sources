# Microsoft.Crm.ObjectModel.BusinessProcessFlowServiceInternalHandler`1::RetrieveProcessActiveStage

- ea: `0x1d5390`
- end: `0x1d5718`
- name: `Microsoft.Crm.ObjectModel.BusinessProcessFlowServiceInternalHandler`1::RetrieveProcessActiveStage`
- size: `904`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1d5390`

## string_xrefs

- `0x1d5424`: `processid`
- `0x1d54ad`: `processid`
- `0x1d5635`: `processid`
- `0x1d565d`: `processid`
- `0x1d550f`: `createdon`
- `0x1d54bd`: `traversedpath`
- `0x1d5517`: `completedon`
- `0x1d53bd`: `processId`
- `0x1d56e2`: `Error occurred while retrieving Business Process Flow instance record for entityid : {0}, logicalname: {1}, and processID: {2}, with error message: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x1d5390  ldarg.s  5
0x1d5392  ldstr    aContext// "context"
0x1d5397  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d539c  ldarg.1
0x1d539d  box      [mscorlib]System.Guid
0x1d53a2  ldstr    aEntityid_3// "entityId"
0x1d53a7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d53ac  ldarg.2
0x1d53ad  ldstr    aEntitylogicaln_3// "entityLogicalName"
0x1d53b2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d53b7  ldarg.3
0x1d53b8  box      [mscorlib]System.Guid
0x1d53bd  ldstr    aProcessid_1// "processId"
0x1d53c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d53c7  ldarg.0
0x1d53c8  ldarg.3
0x1d53c9  ldarg.s  5
0x1d53cb  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep class Microsoft.Crm.ObjectModel.BusinessProcessFlowServiceInternalHandler`1<var<u1>>::RetrieveProcessDefinition(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1d53d0  stloc.0
0x1d53d1  ldloc.0
0x1d53d2  brtrue.s loc_1D53DC
0x1d53d4  ldnull
0x1d53d5  stloc.s  6
0x1d53d7  leave    loc_1D5715
0x1d53dc  ldarg.2
0x1d53dd  ldloc.0
0x1d53de  call     valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetEntityPosition(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1d53e3  dup
0x1d53e4  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetAttributeNameForEntityId(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition)
0x1d53e9  stloc.1
0x1d53ea  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetAttributeNameForEntityOtc(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition)
0x1d53ef  stloc.2
0x1d53f0  ldarg.2
0x1d53f1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d53f6  brtrue.s loc_1D540D
0x1d53f8  ldarg.s  5
0x1d53fa  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d53ff  ldarg.2
0x1d5400  ldc.i4.1
0x1d5401  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1d5406  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1d540b  br.s     loc_1D540E
0x1d540d  ldc.i4.0
0x1d540e  stloc.3
0x1d540f  ldstr    aBusinessproces_0// "BusinessProcessFlowInstance"
0x1d5414  ldarg.s  5
0x1d5416  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1d541b  stloc.s  4
0x1d541d  ldloc.s  4
0x1d541f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1d5424  ldstr    aProcessid// "processid"
0x1d5429  ldc.i4.0
0x1d542a  ldarg.3
0x1d542b  box      [mscorlib]System.Guid
0x1d5430  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1d5435  pop
0x1d5436  ldloc.s  4
0x1d5438  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1d543d  ldloc.1
0x1d543e  ldc.i4.0
0x1d543f  ldarg.1
0x1d5440  box      [mscorlib]System.Guid
0x1d5445  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1d544a  pop
0x1d544b  ldloc.s  4
0x1d544d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1d5452  ldloc.2
0x1d5453  ldc.i4.0
0x1d5454  ldloc.3
0x1d5455  box      [mscorlib]System.Int32
0x1d545a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1d545f  pop
0x1d5460  ldarg.s  4
0x1d5462  brfalse.s loc_1D5496
0x1d5464  ldarg.s  4
0x1d5466  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1d546b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d5470  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1d5475  brfalse.s loc_1D5496
0x1d5477  ldloc.s  4
0x1d5479  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1d547e  ldstr    aBusinessproces// "businessprocessflowinstanceid"
0x1d5483  ldc.i4.0
0x1d5484  ldarg.s  4
0x1d5486  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1d548b  box      [mscorlib]System.Guid
0x1d5490  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1d5495  pop
0x1d5496  ldloc.s  4
0x1d5498  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1d549d  ldc.i4.4
0x1d549e  newarr   [mscorlib]System.String
0x1d54a3  dup
0x1d54a4  ldc.i4.0
0x1d54a5  ldstr    aBusinessproces// "businessprocessflowinstanceid"
0x1d54aa  stelem.ref
0x1d54ab  dup
0x1d54ac  ldc.i4.1
0x1d54ad  ldstr    aProcessid// "processid"
0x1d54b2  stelem.ref
0x1d54b3  dup
0x1d54b4  ldc.i4.2
0x1d54b5  ldstr    aProcessstageid// "processstageid"
0x1d54ba  stelem.ref
0x1d54bb  dup
0x1d54bc  ldc.i4.3
0x1d54bd  ldstr    aTraversedpath// "traversedpath"
0x1d54c2  stelem.ref
0x1d54c3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1d54c8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1d54cd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1d54d2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ProcessUnification()
0x1d54d7  ldarg.s  5
0x1d54d9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d54de  brfalse.s loc_1D5522
0x1d54e0  ldloc.s  4
0x1d54e2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1d54e7  ldc.i4.6
0x1d54e8  newarr   [mscorlib]System.String
0x1d54ed  dup
0x1d54ee  ldc.i4.0
0x1d54ef  ldstr    aStatecode// "statecode"
0x1d54f4  stelem.ref
0x1d54f5  dup
0x1d54f6  ldc.i4.1
0x1d54f7  ldstr    aStatuscode// "statuscode"
0x1d54fc  stelem.ref
0x1d54fd  dup
0x1d54fe  ldc.i4.2
0x1d54ff  ldstr    aName// "name"
0x1d5504  stelem.ref
0x1d5505  dup
0x1d5506  ldc.i4.3
0x1d5507  ldstr    aActivestagesta// "activestagestartedon"
0x1d550c  stelem.ref
0x1d550d  dup
0x1d550e  ldc.i4.4
0x1d550f  ldstr    aCreatedon// "createdon"
0x1d5514  stelem.ref
0x1d5515  dup
0x1d5516  ldc.i4.5
0x1d5517  ldstr    aCompletedon// "completedon"
0x1d551c  stelem.ref
0x1d551d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1d5522  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetEntityPositions()
0x1d5527  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition>::GetEnumerator()
0x1d552c  stloc.s  7
0x1d552e  br.s     loc_1D5562
0x1d5530  ldloc.s  7
0x1d5532  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition>::get_Current()
0x1d5537  dup
0x1d5538  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetAttributeNameForEntityId(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition)
0x1d553d  stloc.s  8
0x1d553f  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetAttributeNameForEntityOtc(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition)
0x1d5544  stloc.s  9
0x1d5546  ldloc.s  4
0x1d5548  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1d554d  ldc.i4.2
0x1d554e  newarr   [mscorlib]System.String
0x1d5553  dup
0x1d5554  ldc.i4.0
0x1d5555  ldloc.s  8
0x1d5557  stelem.ref
0x1d5558  dup
0x1d5559  ldc.i4.1
0x1d555a  ldloc.s  9
0x1d555c  stelem.ref
0x1d555d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1d5562  ldloc.s  7
0x1d5564  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d5569  brtrue.s loc_1D5530
0x1d556b  leave.s  loc_1D5579
0x1d556d  ldloc.s  7
0x1d556f  brfalse.s loc_1D5578
0x1d5571  ldloc.s  7
0x1d5573  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d5578  endfinally
0x1d5579  ldnull
0x1d557a  stloc.s  5
0x1d557c  ldarg.s  4
0x1d557e  brfalse.s loc_1D55C4
0x1d5580  ldarg.s  4
0x1d5582  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1d5587  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d558c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1d5591  brfalse.s loc_1D55C4
0x1d5593  ldarg.s  4
0x1d5595  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1d559a  ldstr    aBusinessproces_0// "BusinessProcessFlowInstance"
0x1d559f  ldarg.s  5
0x1d55a1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d55a6  stloc.s  0xA
0x1d55a8  ldarg.0
0x1d55a9  ldloc.s  0xA
0x1d55ab  ldloc.s  4
0x1d55ad  ldarg.s  5
0x1d55af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1d55b4  stloc.s  5
0x1d55b6  leave    loc_1D56D5
0x1d55bb  pop
0x1d55bc  ldnull
0x1d55bd  stloc.s  5
0x1d55bf  leave    loc_1D56D5
0x1d55c4  ldarg.0
0x1d55c5  ldloc.s  4
0x1d55c7  ldarg.s  5
0x1d55c9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1d55ce  stloc.s  0xB
0x1d55d0  ldloc.s  0xB
0x1d55d2  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1d55d7  ldc.i4.1
0x1d55d8  bne.un.s loc_1D55E9
0x1d55da  ldloc.s  0xB
0x1d55dc  ldc.i4.0
0x1d55dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1d55e2  stloc.s  5
0x1d55e4  br       loc_1D56D5
0x1d55e9  ldloc.s  0xB
0x1d55eb  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1d55f0  ldc.i4.1
0x1d55f1  ble      loc_1D56D5
0x1d55f6  ldarg.0
0x1d55f7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory class Microsoft.Crm.ObjectModel.BusinessProcessFlowServiceInternalHandler`1<var<u1>>::factory
0x1d55fc  ldarg.s  5
0x1d55fe  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateExecutionContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1d5603  stloc.s  0xC
0x1d5605  ldarg.0
0x1d5606  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory class Microsoft.Crm.ObjectModel.BusinessProcessFlowServiceInternalHandler`1<var<u1>>::factory
0x1d560b  ldloc.s  0xC
0x1d560d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IProcessUnificationFeature [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateProcessUnificationFeature(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext)
0x1d5612  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IProcessUnificationFeature::get_FeatureEnabled()
0x1d5617  brfalse  loc_1D56AE
0x1d561c  ldarg.0
0x1d561d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory class Microsoft.Crm.ObjectModel.BusinessProcessFlowServiceInternalHandler`1<var<u1>>::factory
0x1d5622  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IProcessSelectionService [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateProcessSelectionService()
0x1d5627  ldarg.1
0x1d5628  ldloc.3
0x1d5629  ldarg.2
0x1d562a  ldloc.s  0xC
0x1d562c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IProcessSelectionService::RetrieveDefaultProcessInstance(valuetype [mscorlib]System.Guid, int32, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext)
0x1d5631  stloc.s  0xD
0x1d5633  ldloc.s  0xD
0x1d5635  ldstr    aProcessid// "processid"
0x1d563a  ldloca.s 0xE
0x1d563c  callvirt T0x2B0000EF
0x1d5641  pop
0x1d5642  ldloc.s  0xB
0x1d5644  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1d5649  stloc.s  0xF
0x1d564b  br.s     loc_1D568E
0x1d564d  ldloc.s  0xF
0x1d564f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1d5654  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1d5659  stloc.s  0x10
0x1d565b  ldloc.s  0x10
0x1d565d  ldstr    aProcessid// "processid"
0x1d5662  ldloca.s 0x11
0x1d5664  callvirt T0x2B00003B
0x1d5669  pop
0x1d566a  ldloc.s  0x11
0x1d566c  ldloc.s  0xE
0x1d566e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1d5673  brfalse.s loc_1D568E
0x1d5675  ldloc.s  0x10
0x1d5677  stloc.s  5
0x1d5679  ldloc.s  0x10
0x1d567b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x1d5680  ldloc.s  0xD
0x1d5682  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x1d5687  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1d568c  brtrue.s loc_1D5697
0x1d568e  ldloc.s  0xF
0x1d5690  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d5695  brtrue.s loc_1D564D
0x1d5697  leave.s  loc_1D56D5
0x1d5699  ldloc.s  0xF
0x1d569b  isinst   [mscorlib]System.IDisposable
0x1d56a0  stloc.s  0x12
0x1d56a2  ldloc.s  0x12
0x1d56a4  brfalse.s loc_1D56AD
0x1d56a6  ldloc.s  0x12
0x1d56a8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d56ad  endfinally
0x1d56ae  ldloc.s  0xB
0x1d56b0  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1d56b5  ldc.i4.1
0x1d56b6  ceq
0x1d56b8  ldstr    aMoreThanOneGlo// "More than one Global Active stages foun"...
0x1d56bd  ldc.i4.2
0x1d56be  newarr   [mscorlib]System.Object
0x1d56c3  dup
0x1d56c4  ldc.i4.0
0x1d56c5  ldarg.1
0x1d56c6  box      [mscorlib]System.Guid
0x1d56cb  stelem.ref
0x1d56cc  dup
0x1d56cd  ldc.i4.1
0x1d56ce  ldarg.2
0x1d56cf  stelem.ref
0x1d56d0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
  ... truncated ...
```
