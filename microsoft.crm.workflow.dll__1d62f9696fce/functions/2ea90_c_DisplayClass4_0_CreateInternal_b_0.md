# <>c__DisplayClass4_0::<CreateInternal>b__0

- ea: `0x2ea90`
- end: `0x2ed0a`
- name: `<>c__DisplayClass4_0::<CreateInternal>b__0`
- size: `634`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14770`
- `0x14790`
- `0x14ca0`
- `0x14e90`
- `0x16bd0`
- `0x2ea90`

## pseudocode

```c

```

## disassembly

```asm
0x2ea90  ldarg.0
0x2ea91  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2ea96  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2ea9b  ldstr    aAnnotation// "annotation"
0x2eaa0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2eaa5  brfalse  loc_2EBA8
0x2eaaa  ldnull
0x2eaab  stloc.1
0x2eaac  ldarg.0
0x2eaad  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2eab2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2eab7  ldstr    aObjectid// "objectid"
0x2eabc  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x2eac1  brfalse.s loc_2EAD9
0x2eac3  ldarg.0
0x2eac4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2eac9  ldstr    aObjectid// "objectid"
0x2eace  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x2ead3  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x2ead8  stloc.1
0x2ead9  ldloc.1
0x2eada  brfalse.s loc_2EAF4
0x2eadc  ldarg.0
0x2eadd  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2eae2  ldstr    aObjecttypecode// "objecttypecode"
0x2eae7  ldloc.1
0x2eae8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x2eaed  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x2eaf2  br.s     loc_2EB4E
0x2eaf4  ldarg.0
0x2eaf5  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2eafa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2eaff  ldstr    aObjectid// "objectid"
0x2eb04  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x2eb09  brfalse.s loc_2EB21
0x2eb0b  ldarg.0
0x2eb0c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2eb11  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2eb16  ldstr    aObjectid// "objectid"
0x2eb1b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Remove(var<u1>)
0x2eb20  pop
0x2eb21  ldarg.0
0x2eb22  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2eb27  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2eb2c  ldstr    aObjecttypecode// "objecttypecode"
0x2eb31  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x2eb36  brfalse.s loc_2EB4E
0x2eb38  ldarg.0
0x2eb39  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2eb3e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2eb43  ldstr    aObjecttypecode// "objecttypecode"
0x2eb48  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Remove(var<u1>)
0x2eb4d  pop
0x2eb4e  ldarg.0
0x2eb4f  ldfld    class Microsoft.Crm.Workflow.Services.CreateActivityService <>c__DisplayClass4_0::<>4__this
0x2eb54  ldarg.0
0x2eb55  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2eb5a  ldarg.0
0x2eb5b  ldfld    class Microsoft.Crm.Workflow.Services.CreateActivityService <>c__DisplayClass4_0::<>4__this
0x2eb60  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x2eb65  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x2eb6a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2eb6f  ldarg.0
0x2eb70  ldfld    string <>c__DisplayClass4_0::StepId
0x2eb75  ldarg.1
0x2eb76  call     instance void Microsoft.Crm.Workflow.Services.CreateActivityService::AttachAnnotationAttachment(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, valuetype [mscorlib]System.Guid workflowActivationId, string stepId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x2eb7b  ldarg.0
0x2eb7c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2eb81  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2eb86  ldstr    aStepid// "stepid"
0x2eb8b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x2eb90  brfalse.s loc_2EBA8
0x2eb92  ldarg.0
0x2eb93  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2eb98  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2eb9d  ldstr    aStepid// "stepid"
0x2eba2  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Remove(var<u1>)
0x2eba7  pop
0x2eba8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2ebad  stloc.0
0x2ebae  ldarg.0
0x2ebaf  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2ebb4  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2ebb9  ldstr    aQueueitem// "queueitem"
0x2ebbe  callvirt instance bool [mscorlib]System.String::Equals(string)
0x2ebc3  brfalse  loc_2EC88
0x2ebc8  ldarg.0
0x2ebc9  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2ebce  ldstr    aObjectid// "objectid"
0x2ebd3  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x2ebd8  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x2ebdd  stloc.2
0x2ebde  ldarg.0
0x2ebdf  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2ebe4  ldstr    aQueueid// "queueid"
0x2ebe9  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x2ebee  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x2ebf3  stloc.3
0x2ebf4  ldloc.2
0x2ebf5  brtrue.s loc_2EC08
0x2ebf7  ldc.i4   0x80040529
0x2ebfc  ldc.i4.0
0x2ebfd  newarr   [mscorlib]System.Object
0x2ec02  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2ec07  throw
0x2ec08  ldloc.3
0x2ec09  brtrue.s loc_2EC1C
0x2ec0b  ldc.i4   0x80040528
0x2ec10  ldc.i4.0
0x2ec11  newarr   [mscorlib]System.Object
0x2ec16  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2ec1b  throw
0x2ec1c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor()
0x2ec21  stloc.s  4
0x2ec23  ldloc.s  4
0x2ec25  ldloc.2
0x2ec26  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2ec2b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_Id(valuetype [mscorlib]System.Guid)
0x2ec30  ldloc.s  4
0x2ec32  ldloc.2
0x2ec33  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x2ec38  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_LogicalName(string)
0x2ec3d  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueRequest::.ctor()
0x2ec42  stloc.s  5
0x2ec44  ldloc.s  5
0x2ec46  ldloc.s  4
0x2ec48  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x2ec4d  ldloc.s  5
0x2ec4f  ldloc.3
0x2ec50  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2ec55  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueRequest::set_DestinationQueueId(valuetype [mscorlib]System.Guid)
0x2ec5a  ldloc.s  5
0x2ec5c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2ec61  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueRequest::set_SourceQueueId(valuetype [mscorlib]System.Guid)
0x2ec66  ldloc.s  5
0x2ec68  ldarg.0
0x2ec69  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2ec6e  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueRequest::set_QueueItemProperties(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x2ec73  ldarg.1
0x2ec74  ldloc.s  5
0x2ec76  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x2ec7b  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueResponse
0x2ec80  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueResponse::get_QueueItemId()
0x2ec85  stloc.0
0x2ec86  br.s     loc_2EC95
0x2ec88  ldarg.1
0x2ec89  ldarg.0
0x2ec8a  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2ec8f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x2ec94  stloc.0
0x2ec95  ldarg.0
0x2ec96  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2ec9b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2eca0  ldstr    aEmail// "email"
0x2eca5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ecaa  brfalse.s loc_2ECD4
0x2ecac  ldarg.0
0x2ecad  ldfld    class Microsoft.Crm.Workflow.Services.CreateActivityService <>c__DisplayClass4_0::<>4__this
0x2ecb2  ldarg.0
0x2ecb3  ldfld    class Microsoft.Crm.Workflow.Services.CreateActivityService <>c__DisplayClass4_0::<>4__this
0x2ecb8  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x2ecbd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x2ecc2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2ecc7  ldarg.0
0x2ecc8  ldfld    string <>c__DisplayClass4_0::StepId
0x2eccd  ldloc.0
0x2ecce  ldarg.1
0x2eccf  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::AttachMimeEmailAttachment(valuetype [mscorlib]System.Guid workflowActivationId, string stepId, valuetype [mscorlib]System.Guid emailId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x2ecd4  ldarg.0
0x2ecd5  ldfld    class Microsoft.Crm.Workflow.Services.CreateActivityService <>c__DisplayClass4_0::<>4__this
0x2ecda  ldarg.0
0x2ecdb  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2ece0  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2ece5  ldloc.0
0x2ece6  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetStepRegardingRecord(string entityName, valuetype [mscorlib]System.Guid entityId)
0x2eceb  ldarg.0
0x2ecec  ldarg.0
0x2eced  ldfld    class Microsoft.Crm.Workflow.Services.CreateActivityService <>c__DisplayClass4_0::<>4__this
0x2ecf2  ldarg.0
0x2ecf3  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2ecf8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2ecfd  ldloc.0
0x2ecfe  ldarg.1
0x2ecff  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.Services.ActivityServiceBase::RetrieveEntityInternal(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x2ed04  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x2ed09  ret
```
