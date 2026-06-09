# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadInvokeSdkMessageStep

- ea: `0x20bc0`
- end: `0x20d05`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadInvokeSdkMessageStep`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1b910`
- `0x1b9f0`
- `0x20bc0`
- `0x20d10`
- `0x20f40`
- `0x21060`
- `0x21270`
- `0x21530`
- `0x22ce0`
- `0x2d170`
- `0x2e280`
- `0x2e2a0`
- `0x2e2c0`

## pseudocode

```c

```

## disassembly

```asm
0x20bc0  ldc.i4.0
0x20bc1  stloc.0
0x20bc2  ldc.i4.0
0x20bc3  stloc.1
0x20bc4  ldnull
0x20bc5  stloc.2
0x20bc6  ldnull
0x20bc7  stloc.3
0x20bc8  ldnull
0x20bc9  stloc.s  4
0x20bcb  ldarg.0
0x20bcc  ldarg.2
0x20bcd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x20bd2  ldtoken  [System.Workflow.Runtime]System.Activities.Statements.Interop
0x20bd7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20bdc  ldc.i4.1
0x20bdd  ldloca.s 0
0x20bdf  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x20be4  pop
0x20be5  ldarg.2
0x20be6  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x20beb  ldloc.0
0x20bec  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x20bf1  castclass Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity
0x20bf6  stloc.s  5
0x20bf8  ldarg.0
0x20bf9  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_customActivityInfoProvider
0x20bfe  isinst   Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase
0x20c03  brfalse.s loc_20C4F
0x20c05  ldarg.0
0x20c06  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_customActivityInfoProvider
0x20c0b  castclass Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase
0x20c10  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_Cache()
0x20c15  stloc.s  9
0x20c17  ldloc.s  5
0x20c19  callvirt instance string Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_SdkMessageEntityName()
0x20c1e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x20c23  brtrue.s loc_20C4F
0x20c25  ldloc.s  9
0x20c27  ldloc.s  5
0x20c29  callvirt instance string Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_SdkMessageEntityName()
0x20c2e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string)
0x20c33  stloc.s  0xA
0x20c35  ldloc.s  0xA
0x20c37  brfalse.s loc_20C4F
0x20c39  ldloc.s  0xA
0x20c3b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x20c40  brfalse.s loc_20C4F
0x20c42  ldloc.s  0xA
0x20c44  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x20c49  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x20c4e  stloc.1
0x20c4f  ldarg.0
0x20c50  ldloc.s  5
0x20c52  ldloca.s 2
0x20c54  ldloca.s 3
0x20c56  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSdkMessageParameters(class Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity invokeSdkMessage, [out] class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo[]& inputs, [out] class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo[]& outputs)
0x20c5b  ldarg.0
0x20c5c  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_customActivityInfoProvider
0x20c61  ldloc.s  5
0x20c63  callvirt instance string Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_SdkMessageId()
0x20c68  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x20c6d  ldloc.s  5
0x20c6f  callvirt instance string Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_SdkMessageName()
0x20c74  ldloc.s  5
0x20c76  callvirt instance string Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_SdkMessageEntityName()
0x20c7b  ldloc.1
0x20c7c  ldloc.2
0x20c7d  ldloc.3
0x20c7e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateInvokeSdkMessageActivityInfo Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider::GetInvokeSdkMessageInfo(valuetype [mscorlib]System.Guid sdkMessageId, string sdkMessageName, string sdkMessageEntityName, int32 objectTypeCode, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo[] inputs, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo[] outputs)
0x20c83  stloc.s  6
0x20c85  ldarg.0
0x20c86  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x20c8b  ldloc.s  6
0x20c8d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateInvokeSdkMessageActivityInfo::get_InvokeSdkMessageActivityInfo()
0x20c92  ldloc.s  6
0x20c94  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo[] [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateInvokeSdkMessageActivityInfo::get_Inputs()
0x20c99  ldloc.s  6
0x20c9b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo[] [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateInvokeSdkMessageActivityInfo::get_Outputs()
0x20ca0  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo[], class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo[])
0x20ca5  stloc.s  4
0x20ca7  leave.s  loc_20CBC
0x20ca9  pop
0x20caa  ldarg.0
0x20cab  ldarg.1
0x20cac  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ClearCustomStepOutputs(string stepId)
0x20cb1  ldarg.1
0x20cb2  ldc.i4.1
0x20cb3  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep::.ctor(string, bool)
0x20cb8  stloc.s  0xB
0x20cba  leave.s  loc_20D02
0x20cbc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x20cc1  stloc.s  7
0x20cc3  ldarg.0
0x20cc4  ldloc.s  4
0x20cc6  ldloc.s  7
0x20cc8  call     instance bool Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ValidateInvokeSdkMessageStepParameter(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep invokeSdkMessageStep, class [mscorlib]System.Collections.Generic.IList`1<string> mismatchOutputs)
0x20ccd  stloc.s  8
0x20ccf  ldloc.s  4
0x20cd1  ldloc.s  8
0x20cd3  ldc.i4.0
0x20cd4  ceq
0x20cd6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep::set_IsParameterObsolete(bool)
0x20cdb  ldarg.0
0x20cdc  ldloc.2
0x20cdd  stloc.s  0xC
0x20cdf  ldloc.s  0xC
0x20ce1  ldloc.s  5
0x20ce3  ldloc.s  4
0x20ce5  ldarg.1
0x20ce6  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomStepInputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase[] inParameters, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference customReference, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase customStep, string stepId)
0x20ceb  ldarg.0
0x20cec  ldloc.s  4
0x20cee  ldloc.s  5
0x20cf0  ldarg.1
0x20cf1  ldloc.s  7
0x20cf3  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomStepOutputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase customStep, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference customReference, string stepId, [opt] class [mscorlib]System.Collections.Generic.IList`1<string> mismatchOutputs)
0x20cf8  ldarg.0
0x20cf9  ldarg.1
0x20cfa  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ClearCustomStepOutputs(string stepId)
0x20cff  ldloc.s  4
0x20d01  ret
0x20d02  ldloc.s  0xB
0x20d04  ret
```
