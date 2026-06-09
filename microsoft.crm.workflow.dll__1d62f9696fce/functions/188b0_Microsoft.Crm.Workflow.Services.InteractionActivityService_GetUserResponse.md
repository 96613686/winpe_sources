# Microsoft.Crm.Workflow.Services.InteractionActivityService::GetUserResponse

- ea: `0x188b0`
- end: `0x18a7d`
- name: `Microsoft.Crm.Workflow.Services.InteractionActivityService::GetUserResponse`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xdee0`
- `0xdf40`
- `0xdfe0`
- `0xe0b0`
- `0xe650`
- `0xe6f0`
- `0xe750`
- `0xe820`
- `0xe920`
- `0xe9b0`
- `0x14770`
- `0x14840`
- `0x14930`
- `0x18870`
- `0x18890`
- `0x188b0`
- `0x18a80`
- `0x18c00`

## string_xrefs

- `0x188ef`: `GetPromptOrResponseXml: Getting Interaction ui definition  for Prompt '{0}', for interactive workflow '{1}'.`
- `0x18958`: `GetPromptOrResponseXml: Setting response value for interaction response received for prompt '{0}', for interactive workflow '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x188b0  ldarg.0
0x188b1  ldarg.1
0x188b2  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x188b7  call     instance string Microsoft.Crm.Workflow.Services.ActivityServiceBase::FindStepId(string stepIdAndDescription)
0x188bc  stloc.0
0x188bd  ldnull
0x188be  stloc.1
0x188bf  ldsfld   string [mscorlib]System.String::Empty
0x188c4  stloc.2
0x188c5  ldarg.s  9
0x188c7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x188cc  brtrue.s loc_188D1
0x188ce  ldc.i4.0
0x188cf  br.s     loc_188D2
0x188d1  ldc.i4.1
0x188d2  stloc.3
0x188d3  ldarg.0
0x188d4  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.InteractionActivityService::get_InteractiveWorkflowInputContext()
0x188d9  callvirt instance bool Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_UnderResumeBookmarkProcessing()
0x188de  brtrue.s loc_18951
0x188e0  ldarg.0
0x188e1  ldarg.1
0x188e2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog(class [System.Activities]System.Activities.Activity activity)
0x188e7  pop
0x188e8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x188ed  ldc.i4.s 0x1E
0x188ef  ldstr    aGetpromptorres// "GetPromptOrResponseXml: Getting Interac"...
0x188f4  ldc.i4.2
0x188f5  newarr   [mscorlib]System.Object
0x188fa  dup
0x188fb  ldc.i4.0
0x188fc  ldarg.1
0x188fd  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x18902  stelem.ref
0x18903  dup
0x18904  ldc.i4.1
0x18905  ldarg.0
0x18906  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x1890b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x18910  box      [mscorlib]System.Guid
0x18915  stelem.ref
0x18916  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1891b  ldloc.0
0x1891c  ldarg.s  4
0x1891e  ldarg.3
0x1891f  ldarg.s  5
0x18921  ldarg.s  6
0x18923  ldarg.2
0x18924  ldarg.s  0xA
0x18926  ldloc.3
0x18927  ldarg.s  0xC
0x18929  ldarg.s  7
0x1892b  ldarg.s  8
0x1892d  ldarg.s  9
0x1892f  ldarg.s  0xD
0x18931  ldarg.s  0xB
0x18933  newobj   instance void Microsoft.Crm.Workflow.InteractionActivityDetail::.ctor(string name, int32 responseMetadataType, int32 responseContainerType, bool isResponseMetadataSpecified, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource metadata, string promptText, string cueText, bool isResponseStatic, string responseDefaultValue, string staticResponseValues, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection dynamicQueryResult, string dynamicQueryAttributeList, string separator, bool logResponse)
0x18938  stloc.s  4
0x1893a  ldarg.0
0x1893b  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.Services.InteractionActivityService::get_InteractiveWorkflowOutputContext()
0x18940  callvirt instance class Microsoft.Crm.Workflow.PageUIDetail Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext::get_PageUIDetail()
0x18945  ldloc.s  4
0x18947  callvirt instance void Microsoft.Crm.Workflow.PageUIDetail::AddInteractionActivityDetail(class Microsoft.Crm.Workflow.InteractionActivityDetail iaDetails)
0x1894c  br       loc_18A7B
0x18951  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18956  ldc.i4.s 0x1E
0x18958  ldstr    aGetpromptorres_0// "GetPromptOrResponseXml: Setting respons"...
0x1895d  ldc.i4.2
0x1895e  newarr   [mscorlib]System.Object
0x18963  dup
0x18964  ldc.i4.0
0x18965  ldarg.1
0x18966  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x1896b  stelem.ref
0x1896c  dup
0x1896d  ldc.i4.1
0x1896e  ldarg.0
0x1896f  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18974  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x18979  box      [mscorlib]System.Guid
0x1897e  stelem.ref
0x1897f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18984  ldarg.0
0x18985  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.InteractionActivityService::get_InteractiveWorkflowInputContext()
0x1898a  callvirt instance class Microsoft.Crm.Workflow.PageResult Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_PageResult()
0x1898f  ldc.i4.0
0x18990  stloc.s  5
0x18992  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityResult> Microsoft.Crm.Workflow.PageResult::get_InteractionActivitiesResults()
0x18997  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::GetEnumerator()
0x1899c  stloc.s  6
0x1899e  br       loc_18A4D
0x189a3  ldloc.s  6
0x189a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::get_Current()
0x189aa  stloc.s  7
0x189ac  ldloc.s  7
0x189ae  callvirt instance string Microsoft.Crm.Workflow.InteractionActivityResult::get_Name()
0x189b3  stloc.s  8
0x189b5  ldloc.0
0x189b6  ldloc.s  8
0x189b8  ldc.i4.4
0x189b9  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x189be  brfalse  loc_18A4D
0x189c3  ldloc.3
0x189c4  brtrue.s loc_18A28
0x189c6  ldc.i4.0
0x189c7  stloc.s  9
0x189c9  br.s     loc_18A16
0x189cb  ldarg.s  8
0x189cd  ldloc.s  9
0x189cf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x189d4  stloc.s  0xA
0x189d6  ldloc.s  7
0x189d8  callvirt instance object Microsoft.Crm.Workflow.InteractionActivityResult::get_ResponseValue()
0x189dd  callvirt instance string [mscorlib]System.Object::ToString()
0x189e2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x189e7  ldloc.s  0xA
0x189e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x189ee  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x189f3  brfalse.s loc_18A10
0x189f5  ldloc.s  7
0x189f7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.InteractionActivityResult::get_SelectedEntity()
0x189fc  ldloc.0
0x189fd  ldstr    aInteractionres_0// "_interactionResponseValue"
0x18a02  call     string [mscorlib]System.String::Concat(string, string)
0x18a07  ldloc.s  0xA
0x18a09  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>, !!T0)
0x18a0e  br.s     loc_18A3B
0x18a10  ldloc.s  9
0x18a12  ldc.i4.1
0x18a13  add
0x18a14  stloc.s  9
0x18a16  ldloc.s  9
0x18a18  ldarg.s  8
0x18a1a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x18a1f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x18a24  blt.s    loc_189CB
0x18a26  br.s     loc_18A3B
0x18a28  ldarg.3
0x18a29  ldc.i4.7
0x18a2a  bne.un.s loc_18A3B
0x18a2c  ldarg.0
0x18a2d  ldarg.s  5
0x18a2f  ldarg.s  6
0x18a31  ldloc.0
0x18a32  ldloc.s  7
0x18a34  ldarg.s  0xB
0x18a36  call     instance void Microsoft.Crm.Workflow.Services.InteractionActivityService::HandleLookupResponse(bool isResponseMetadataSpecified, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource responseMetadataSource, string activityStepId, class Microsoft.Crm.Workflow.InteractionActivityResult iaResult, bool logResponse)
0x18a3b  ldloc.s  7
0x18a3d  stloc.1
0x18a3e  ldc.i4.1
0x18a3f  stloc.s  5
0x18a41  ldloc.s  7
0x18a43  ldarg.s  0xB
0x18a45  callvirt instance string Microsoft.Crm.Workflow.InteractionActivityResult::InteractionActivityResponseXml(bool logResponse)
0x18a4a  stloc.2
0x18a4b  leave.s  loc_18A67
0x18a4d  ldloc.s  6
0x18a4f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x18a54  brtrue   loc_189A3
0x18a59  leave.s  loc_18A67
0x18a5b  ldloc.s  6
0x18a5d  brfalse.s loc_18A66
0x18a5f  ldloc.s  6
0x18a61  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18a66  endfinally
0x18a67  ldloc.s  5
0x18a69  ldstr    aOnBookmarkResu// "On Bookmark Resume InteractionPage shou"...
0x18a6e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x18a73  ldarg.0
0x18a74  ldarg.1
0x18a75  ldloc.2
0x18a76  call     instance void Microsoft.Crm.Workflow.Services.InteractionActivityService::LogSuccess(class Microsoft.Crm.Workflow.Activities.Interaction interactionActivity, string logResponseXml)
0x18a7b  ldloc.1
0x18a7c  ret
```
