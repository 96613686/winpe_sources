# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetEntityStages

- ea: `0x5390`
- end: `0x56a9`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetEntityStages`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x3620`

## callees

- `0x35f0`
- `0x3780`
- `0x4b60`
- `0x5390`
- `0x56b0`
- `0x56d0`

## string_xrefs

- `0x54c9`: `traversedpath`
- `0x552d`: `createdon`
- `0x554a`: `completedon`
- `0x561a`: `{{"activeStageId":"{0}", "activeStageStartedOn":"{1}", "traversedPath":"{2}", "navigationEntities":{3}, "businessProcessInstanceId":"{4}", "businessProcessState":"{5}", "businessProcessStatus":"{6}", "businessProcessInstanceName":"{7}", "selectedStageId":"{8}", "createdOn":"{9}", "completedOn":"{10}"}}`
- `0x5680`: `{{"activeStageId":"{0}", "traversedPath":"{1}", "navigationEntities":{2}}}`

## pseudocode

```c

```

## disassembly

```asm
0x5390  ldarg.1
0x5391  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetId(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0x5396  stloc.0
0x5397  ldarg.0
0x5398  ldloc.0
0x5399  ldarg.1
0x539a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x539f  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x53a4  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::InitializeProcess(valuetype [mscorlib]System.Guid entityId, int32 entityTypeCode)
0x53a9  ldarg.0
0x53aa  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_ProcessInstanceEntity()
0x53af  stloc.1
0x53b0  ldarg.0
0x53b1  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x53b6  brfalse  loc_54A8
0x53bb  ldarg.0
0x53bc  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x53c1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x53c6  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Count()
0x53cb  ldc.i4.0
0x53cc  ble      loc_54A8
0x53d1  ldarg.1
0x53d2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x53d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x53dc  brtrue   loc_54A8
0x53e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x53e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x53eb  ldc.i4.0
0x53ec  ldc.i4.0
0x53ed  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x53f2  stloc.s  5
0x53f4  ldloca.s 6
0x53f6  ldarg.1
0x53f7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x53fc  call     instance void [mscorlib]System.Guid::.ctor(string)
0x5401  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x5406  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x540b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ProcessUnification()
0x5410  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5415  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x541a  brfalse.s loc_5477
0x541c  call     class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_QueryParameters()
0x5421  ldstr    aProcessinstanc// "processinstanceid"
0x5426  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x542b  stloc.s  7
0x542d  ldnull
0x542e  stloc.s  8
0x5430  ldloc.s  7
0x5432  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5437  brtrue.s loc_5450
0x5439  ldloca.s 9
0x543b  ldloc.s  7
0x543d  call     instance void [mscorlib]System.Guid::.ctor(string)
0x5442  ldstr    aBusinessproces_0// "businessprocessflowinstance"
0x5447  ldloc.s  9
0x5449  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x544e  stloc.s  8
0x5450  ldloc.1
0x5451  brtrue.s loc_549A
0x5453  ldarg.0
0x5454  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x5459  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x545e  ldloc.s  8
0x5460  ldloc.s  6
0x5462  ldarg.1
0x5463  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_LogicalName()
0x5468  ldloc.s  5
0x546a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveProcessActiveStageCommand::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x546f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveProcessActiveStageCommand::Execute()
0x5474  stloc.1
0x5475  leave.s  loc_54A8
0x5477  ldloc.1
0x5478  brtrue.s loc_549A
0x547a  ldarg.0
0x547b  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x5480  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x5485  ldloc.s  6
0x5487  ldarg.1
0x5488  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_LogicalName()
0x548d  ldloc.s  5
0x548f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveProcessActiveStageCommand::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5494  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveProcessActiveStageCommand::Execute()
0x5499  stloc.1
0x549a  leave.s  loc_54A8
0x549c  ldloc.s  5
0x549e  brfalse.s loc_54A7
0x54a0  ldloc.s  5
0x54a2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54a7  endfinally
0x54a8  ldloc.1
0x54a9  brtrue.s loc_54B2
0x54ab  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54b0  br.s     loc_54BD
0x54b2  ldloc.1
0x54b3  ldstr    aProcessstageid// "processstageid"
0x54b8  callvirt T0x2B000001
0x54bd  stloc.2
0x54be  ldloc.1
0x54bf  brtrue.s loc_54C8
0x54c1  ldsfld   string [mscorlib]System.String::Empty
0x54c6  br.s     loc_54D3
0x54c8  ldloc.1
0x54c9  ldstr    aTraversedpath// "traversedpath"
0x54ce  callvirt T0x2B000002
0x54d3  stloc.3
0x54d4  ldloc.1
0x54d5  brtrue.s loc_54DE
0x54d7  ldstr    asc_3629C// "[]"
0x54dc  br.s     loc_54E4
0x54de  ldloc.1
0x54df  call     string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::CreateNavigationEntities(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activeStageEntity)
0x54e4  stloc.s  4
0x54e6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x54eb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x54f0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ProcessUnification()
0x54f5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x54fa  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x54ff  brfalse  loc_567B
0x5504  ldloc.1
0x5505  brtrue.s loc_550E
0x5507  ldsfld   string [mscorlib]System.String::Empty
0x550c  br.s     loc_551F
0x550e  ldarg.0
0x550f  ldloc.1
0x5510  ldstr    aActivestagesta// "activestagestartedon"
0x5515  callvirt T0x2B000003
0x551a  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::UTCDateToJSON(valuetype [mscorlib]System.DateTime utcDate)
0x551f  stloc.s  0xA
0x5521  ldloc.1
0x5522  brtrue.s loc_552B
0x5524  ldsfld   string [mscorlib]System.String::Empty
0x5529  br.s     loc_553C
0x552b  ldarg.0
0x552c  ldloc.1
0x552d  ldstr    aCreatedon// "createdon"
0x5532  callvirt T0x2B000003
0x5537  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::UTCDateToJSON(valuetype [mscorlib]System.DateTime utcDate)
0x553c  stloc.s  0xB
0x553e  ldloc.1
0x553f  brtrue.s loc_5548
0x5541  ldsfld   string [mscorlib]System.String::Empty
0x5546  br.s     loc_5559
0x5548  ldarg.0
0x5549  ldloc.1
0x554a  ldstr    aCompletedon// "completedon"
0x554f  callvirt T0x2B000003
0x5554  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::UTCDateToJSON(valuetype [mscorlib]System.DateTime utcDate)
0x5559  stloc.s  0xC
0x555b  ldloc.1
0x555c  brtrue.s loc_5570
0x555e  ldarg.0
0x555f  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::processInstanceId
0x5564  ldstr    aD// "D"
0x5569  call     instance string [mscorlib]System.Guid::ToString(string)
0x556e  br.s     loc_5589
0x5570  ldloc.1
0x5571  ldstr    aBusinessproces_1// "businessprocessflowinstanceid"
0x5576  callvirt T0x2B000001
0x557b  stloc.s  0x11
0x557d  ldloca.s 0x11
0x557f  ldstr    aD// "D"
0x5584  call     instance string [mscorlib]System.Guid::ToString(string)
0x5589  stloc.s  0xD
0x558b  ldloc.1
0x558c  brtrue.s loc_5595
0x558e  ldsfld   string [mscorlib]System.String::Empty
0x5593  br.s     loc_55AE
0x5595  ldloc.1
0x5596  ldstr    aStatecode// "statecode"
0x559b  callvirt T0x2B000004
0x55a0  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x55a5  stloc.s  0x12
0x55a7  ldloca.s 0x12
0x55a9  call     instance string [mscorlib]System.Int32::ToString()
0x55ae  stloc.s  0xE
0x55b0  ldloc.1
0x55b1  brtrue.s loc_55BA
0x55b3  ldsfld   string [mscorlib]System.String::Empty
0x55b8  br.s     loc_55D3
0x55ba  ldloc.1
0x55bb  ldstr    aStatuscode// "statuscode"
0x55c0  callvirt T0x2B000004
0x55c5  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x55ca  stloc.s  0x12
0x55cc  ldloca.s 0x12
0x55ce  call     instance string [mscorlib]System.Int32::ToString()
0x55d3  stloc.s  0xF
0x55d5  ldloc.1
0x55d6  brtrue.s loc_55DF
0x55d8  ldsfld   string [mscorlib]System.String::Empty
0x55dd  br.s     loc_55EA
0x55df  ldloc.1
0x55e0  ldstr    aName// "name"
0x55e5  callvirt T0x2B000002
0x55ea  stloc.s  0x10
0x55ec  ldloc.s  0xF
0x55ee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x55f3  brtrue.s loc_5615
0x55f5  call     class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Items()
0x55fa  ldstr    aBusinessproces_2// "BusinessProcessInstanceActive"
0x55ff  ldloc.s  0xF
0x5601  ldstr    a1_0// "1"
0x5606  callvirt instance bool [mscorlib]System.String::Equals(string)
0x560b  box      [mscorlib]System.Boolean
0x5610  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x5615  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x561a  ldstr    aActivestageid0// "{{\"activeStageId\":\"{0}\", \"activeSt"...
0x561f  ldc.i4.s 0xB
0x5621  newarr   [mscorlib]System.Object
0x5626  dup
0x5627  ldc.i4.0
0x5628  ldloca.s 2
0x562a  ldstr    aD// "D"
0x562f  call     instance string [mscorlib]System.Guid::ToString(string)
0x5634  stelem.ref
0x5635  dup
0x5636  ldc.i4.1
0x5637  ldloc.s  0xA
0x5639  stelem.ref
0x563a  dup
0x563b  ldc.i4.2
0x563c  ldloc.3
0x563d  stelem.ref
0x563e  dup
0x563f  ldc.i4.3
0x5640  ldloc.s  4
0x5642  stelem.ref
0x5643  dup
0x5644  ldc.i4.4
0x5645  ldloc.s  0xD
0x5647  stelem.ref
0x5648  dup
0x5649  ldc.i4.5
0x564a  ldloc.s  0xE
0x564c  stelem.ref
0x564d  dup
0x564e  ldc.i4.6
0x564f  ldloc.s  0xF
0x5651  stelem.ref
0x5652  dup
0x5653  ldc.i4.7
0x5654  ldloc.s  0x10
0x5656  stelem.ref
0x5657  dup
0x5658  ldc.i4.8
0x5659  call     class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_QueryParameters()
0x565e  ldstr    aSelectedstagei// "selectedstageid"
0x5663  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5668  stelem.ref
0x5669  dup
0x566a  ldc.i4.s 9
0x566c  ldloc.s  0xB
0x566e  stelem.ref
0x566f  dup
0x5670  ldc.i4.s 0xA
0x5672  ldloc.s  0xC
0x5674  stelem.ref
0x5675  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x567a  ret
0x567b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5680  ldstr    aActivestageid0_0// "{{\"activeStageId\":\"{0}\", \"traverse"...
0x5685  ldc.i4.3
0x5686  newarr   [mscorlib]System.Object
0x568b  dup
0x568c  ldc.i4.0
0x568d  ldloca.s 2
0x568f  ldstr    aD// "D"
0x5694  call     instance string [mscorlib]System.Guid::ToString(string)
0x5699  stelem.ref
0x569a  dup
0x569b  ldc.i4.1
0x569c  ldloc.3
0x569d  stelem.ref
0x569e  dup
0x569f  ldc.i4.2
0x56a0  ldloc.s  4
0x56a2  stelem.ref
0x56a3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x56a8  ret
```
