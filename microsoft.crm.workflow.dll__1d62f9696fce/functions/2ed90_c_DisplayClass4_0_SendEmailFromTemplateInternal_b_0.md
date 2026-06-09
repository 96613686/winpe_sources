# <>c__DisplayClass4_0::<SendEmailFromTemplateInternal>b__0

- ea: `0x2ed90`
- end: `0x2ee48`
- name: `<>c__DisplayClass4_0::<SendEmailFromTemplateInternal>b__0`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14790`
- `0x14e90`

## string_xrefs

- `0x2ed9b`: `isworkflowcreated`

## pseudocode

```c

```

## disassembly

```asm
0x2ed90  ldarg.0
0x2ed91  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::emailEntity
0x2ed96  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2ed9b  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x2eda0  ldc.i4.1
0x2eda1  box      [mscorlib]System.Boolean
0x2eda6  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x2edab  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailFromTemplateRequest::.ctor()
0x2edb0  stloc.0
0x2edb1  ldloc.0
0x2edb2  ldarg.0
0x2edb3  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::regardingId
0x2edb8  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailFromTemplateRequest::set_RegardingId(valuetype [mscorlib]System.Guid)
0x2edbd  ldloc.0
0x2edbe  ldarg.0
0x2edbf  ldfld    string <>c__DisplayClass4_0::regardingType
0x2edc4  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailFromTemplateRequest::set_RegardingType(string)
0x2edc9  ldloc.0
0x2edca  ldarg.0
0x2edcb  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::templateId
0x2edd0  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailFromTemplateRequest::set_TemplateId(valuetype [mscorlib]System.Guid)
0x2edd5  ldloc.0
0x2edd6  ldarg.0
0x2edd7  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::emailEntity
0x2eddc  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailFromTemplateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x2ede1  ldarg.1
0x2ede2  ldloc.0
0x2ede3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x2ede8  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailFromTemplateResponse
0x2eded  stloc.1
0x2edee  ldarg.0
0x2edef  ldfld    class Microsoft.Crm.Workflow.Services.SendEmailFromTemplateActivityService <>c__DisplayClass4_0::<>4__this
0x2edf4  ldstr    aEmail// "email"
0x2edf9  ldloc.1
0x2edfa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailFromTemplateResponse::get_Id()
0x2edff  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetStepRegardingRecord(string entityName, valuetype [mscorlib]System.Guid entityId)
0x2ee04  ldarg.0
0x2ee05  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::emailEntity
0x2ee0a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2ee0f  ldstr    aActivityid// "activityid"
0x2ee14  ldloc.1
0x2ee15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailFromTemplateResponse::get_Id()
0x2ee1a  box      [mscorlib]System.Guid
0x2ee1f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x2ee24  ldarg.0
0x2ee25  ldarg.0
0x2ee26  ldfld    class Microsoft.Crm.Workflow.Services.SendEmailFromTemplateActivityService <>c__DisplayClass4_0::<>4__this
0x2ee2b  ldarg.0
0x2ee2c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::emailEntity
0x2ee31  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2ee36  ldloc.1
0x2ee37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailFromTemplateResponse::get_Id()
0x2ee3c  ldarg.1
0x2ee3d  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.Services.ActivityServiceBase::RetrieveEntityInternal(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x2ee42  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x2ee47  ret
```
