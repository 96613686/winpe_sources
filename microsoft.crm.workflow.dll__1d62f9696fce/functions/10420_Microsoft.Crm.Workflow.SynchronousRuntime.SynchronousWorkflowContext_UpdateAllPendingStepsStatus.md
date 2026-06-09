# Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::UpdateAllPendingStepsStatus

- ea: `0x10420`
- end: `0x106ed`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::UpdateAllPendingStepsStatus`
- size: `717`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1f0`
- `0xcd0`
- `0x7450`
- `0x74d0`
- `0x7580`
- `0x75d0`
- `0x7710`
- `0x7d90`
- `0x7e90`
- `0x10160`
- `0x10170`
- `0x10180`
- `0x10190`
- `0x101a0`
- `0x101b0`
- `0x10270`
- `0x10420`
- `0x1af00`
- `0x1af20`

## string_xrefs

- `0x105d3`: `completedon`
- `0x10663`: `completedon`
- `0x10474`: `processid`
- `0x10578`: `comments`

## pseudocode

```c

```

## disassembly

```asm
0x10420  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10425  stloc.0
0x10426  ldarg.0
0x10427  call     instance bool Microsoft.Crm.Workflow.WorkflowContextBase::get_IsLoggingEnabled()
0x1042c  brfalse  loc_106DA
0x10431  ldarg.0
0x10432  ldfld    class Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::synchronousWorkflowContextDependencies
0x10437  ldarg.0
0x10438  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::get_OrganizationId()
0x1043d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies::CreateExecutionContext(valuetype [mscorlib]System.Guid organizationId)
0x10442  stloc.1
0x10443  ldloc.1
0x10444  ldarg.0
0x10445  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::get_UserId()
0x1044a  ldc.i4.1
0x1044b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x10450  ldarg.0
0x10451  ldfld    class Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::synchronousWorkflowContextDependencies
0x10456  ldstr    aProcesssession// "ProcessSession"
0x1045b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies::CreateBusinessProcessObject(string platformName)
0x10460  stloc.2
0x10461  ldarg.0
0x10462  ldfld    class Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::synchronousWorkflowContextDependencies
0x10467  ldarg.0
0x10468  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::get_OrganizationId()
0x1046d  callvirt instance class Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies::CreateProcessSession(valuetype [mscorlib]System.Guid organizationId)
0x10472  stloc.3
0x10473  ldloc.3
0x10474  ldstr    aProcessid// "processid"
0x10479  ldarg.0
0x1047a  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Workflow.WorkflowContextBase::get_OwningExtension()
0x1047f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x10484  box      [mscorlib]System.Guid
0x10489  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x1048e  ldarg.0
0x1048f  ldfld    class Microsoft.Crm.Asynchronous.IGenericEventData Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x10494  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.IGenericEventData::get_RegardingObject()
0x10499  brfalse  loc_10577
0x1049e  ldarg.0
0x1049f  ldfld    class Microsoft.Crm.Asynchronous.IGenericEventData Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x104a4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.IGenericEventData::get_RegardingObject()
0x104a9  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0x104ae  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x104b3  brtrue   loc_10577
0x104b8  ldarg.0
0x104b9  ldfld    class Microsoft.Crm.Asynchronous.IGenericEventData Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x104be  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.IGenericEventData::get_RegardingObject()
0x104c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x104c8  stloc.s  6
0x104ca  ldloc.s  6
0x104cc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x104d1  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x104d6  brfalse.s loc_1053E
0x104d8  ldarg.0
0x104d9  ldfld    class Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::synchronousWorkflowContextDependencies
0x104de  ldarg.0
0x104df  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::get_OrganizationId()
0x104e4  ldarg.0
0x104e5  ldftn    instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::<UpdateAllPendingStepsStatus>b__40_0()
0x104eb  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::.ctor(object, native int)
0x104f0  callvirt instance class Microsoft.Crm.Workflow.IRegardingObjectUtility Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies::GetRegardingObjectUtility(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Func`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService> organizationService)
0x104f5  stloc.s  8
0x104f7  ldloc.s  8
0x104f9  brfalse.s loc_1052C
0x104fb  ldloc.s  8
0x104fd  ldarg.0
0x104fe  ldfld    class Microsoft.Crm.Asynchronous.IGenericEventData Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x10503  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.IGenericEventData::get_RegardingObject()
0x10508  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0x1050d  ldloc.s  6
0x1050f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Workflow.IRegardingObjectUtility::CreateLookup(string entityName, valuetype [mscorlib]System.Guid entityId)
0x10514  stloc.s  9
0x10516  ldloc.s  9
0x10518  brfalse.s loc_1052C
0x1051a  ldloc.3
0x1051b  ldstr    aRegardingobjec// "regardingobjectidname"
0x10520  ldloc.s  9
0x10522  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x10527  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x1052c  ldloc.3
0x1052d  ldstr    aRegardingobjec_0// "regardingobjectid"
0x10532  ldloc.s  6
0x10534  box      [mscorlib]System.Guid
0x10539  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x1053e  ldarg.0
0x1053f  ldfld    class Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::synchronousWorkflowContextDependencies
0x10544  ldarg.0
0x10545  ldfld    class Microsoft.Crm.Asynchronous.IGenericEventData Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x1054a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.IGenericEventData::get_RegardingObject()
0x1054f  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0x10554  ldloc.1
0x10555  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies::TryGetEntityMetadata(string entityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityExecutionContext context)
0x1055a  stloc.s  7
0x1055c  ldloc.s  7
0x1055e  brfalse.s loc_10577
0x10560  ldloc.3
0x10561  ldstr    aRegardingobjec_1// "regardingobjecttypecode"
0x10566  ldloc.s  7
0x10568  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1056d  box      [mscorlib]System.Int32
0x10572  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x10577  ldloc.3
0x10578  ldstr    aComments// "comments"
0x1057d  ldstr    aSyncWorkflowFa// "Sync workflow failed with error message"...
0x10582  ldarg.1
0x10583  ldarga.s 2
0x10585  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1058a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1058f  call     string [mscorlib]System.String::Format(string, object, object)
0x10594  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x10599  ldloc.3
0x1059a  ldstr    aStatecode// "statecode"
0x1059f  ldc.i4.1
0x105a0  box      [mscorlib]System.Int32
0x105a5  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x105aa  ldloc.3
0x105ab  ldstr    aStatuscode// "statuscode"
0x105b0  ldc.i4.6
0x105b1  box      [mscorlib]System.Int32
0x105b6  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x105bb  ldloc.3
0x105bc  ldstr    aName// "name"
0x105c1  ldarg.0
0x105c2  ldfld    class Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::synchronousWorkflowContextDependencies
0x105c7  ldloc.1
0x105c8  callvirt instance string Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies::GetWorkflowCategoryDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityExecutionContext context)
0x105cd  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x105d2  ldloc.3
0x105d3  ldstr    aCompletedon// "completedon"
0x105d8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x105dd  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x105e2  ldloc.3
0x105e3  ldstr    aStartedby// "startedby"
0x105e8  ldarg.0
0x105e9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::get_UserId()
0x105ee  box      [mscorlib]System.Guid
0x105f3  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x105f8  ldarg.0
0x105f9  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.WorkflowContextBase::get_OperationCreatedOn()
0x105fe  ldc.i4.1
0x105ff  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x10604  stloc.s  4
0x10606  ldloc.3
0x10607  ldstr    aStartedon// "startedon"
0x1060c  ldloc.s  4
0x1060e  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::set_Item(string attributeName, object value)
0x10613  ldloc.2
0x10614  ldloc.3
0x10615  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Workflow.ObjectModel.IBusinessEntityWrapper::get_BusinessEntity()
0x1061a  ldloc.1
0x1061b  isinst   [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext
0x10620  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x10625  stloc.s  5
0x10627  ldloc.s  5
0x10629  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x1062e  stloc.0
0x1062f  ldarg.0
0x10630  ldfld    class Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::synchronousWorkflowContextDependencies
0x10635  ldstr    aWorkflowlog_0// "WorkflowLog"
0x1063a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject Microsoft.Crm.Workflow.SynchronousRuntime.ISynchronousWorkflowContextDependencies::CreateBusinessProcessObject(string platformName)
0x1063f  stloc.2
0x10640  ldarg.0
0x10641  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::workflowLogs
0x10646  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::GetEnumerator()
0x1064b  stloc.s  0xA
0x1064d  br.s     loc_106A6
0x1064f  ldloca.s 0xA
0x10651  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Current()
0x10656  stloc.s  0xB
0x10658  ldloca.s 0xB
0x1065a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Value()
0x1065f  stloc.s  0xC
0x10661  ldloc.s  0xC
0x10663  ldstr    aCompletedon// "completedon"
0x10668  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1066d  brtrue.s loc_1067F
0x1066f  ldarg.0
0x10670  ldloca.s 0xB
0x10672  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Key()
0x10677  ldarg.2
0x10678  ldarg.1
0x10679  ldarg.3
0x1067a  callvirt instance void Microsoft.Crm.Workflow.WorkflowContextBase::UpdateWorkflowLog(valuetype [mscorlib]System.Guid logId, int32 errorCode, string errorMessage, int32 status)
0x1067f  ldloc.s  0xC
0x10681  ldstr    aAsyncoperation_0// "asyncoperationid"
0x10686  ldloc.s  5
0x10688  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x1068d  box      [mscorlib]System.Guid
0x10692  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x10697  ldloc.2
0x10698  ldloc.s  0xC
0x1069a  ldloc.1
0x1069b  isinst   [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext
0x106a0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x106a5  pop
0x106a6  ldloca.s 0xA
0x106a8  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::MoveNext()
0x106ad  brtrue.s loc_1064F
0x106af  leave.s  loc_106BF
0x106b1  ldloca.s 0xA
0x106b3  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>
0x106b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x106be  endfinally
0x106bf  ldloc.1
0x106c0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityExecutionContext::OnEndRequest()
0x106c5  leave.s  loc_106DA
0x106c7  pop
0x106c8  ldloc.1
0x106c9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityExecutionContext::OnErrorRequest()
0x106ce  rethrow
0x106d0  ldloc.1
0x106d1  brfalse.s loc_106D9
0x106d3  ldloc.1
0x106d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x106d9  endfinally
0x106da  ldarg.0
0x106db  call     instance bool Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_ActionLogEnabled()
0x106e0  brfalse.s loc_106EC
0x106e2  ldloc.0
0x106e3  ldc.i4.3
0x106e4  ldarg.2
0x106e5  ldarg.1
0x106e6  ldarg.0
0x106e7  call     void Microsoft.Crm.Workflow.WorkflowContextBase::CreateActionLog(valuetype [mscorlib]System.Guid sessionId, int32 status, int32 errorCode, string errorMessage, class Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext synchronousWorkflowContext)
0x106ec  ret
```
