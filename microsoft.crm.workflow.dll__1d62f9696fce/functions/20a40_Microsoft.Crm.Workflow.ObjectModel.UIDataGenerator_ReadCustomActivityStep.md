# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomActivityStep

- ea: `0x20a40`
- end: `0x20bb3`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomActivityStep`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1b540`
- `0x1b8b0`
- `0x1b900`
- `0x20a40`
- `0x20f40`
- `0x21060`
- `0x21270`
- `0x22ce0`
- `0x2d170`

## pseudocode

```c

```

## disassembly

```asm
0x20a40  ldc.i4.0
0x20a41  stloc.0
0x20a42  ldarg.0
0x20a43  ldarg.2
0x20a44  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x20a49  ldtoken  [System.Workflow.Runtime]System.Activities.Statements.Interop
0x20a4e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20a53  ldc.i4.1
0x20a54  ldloca.s 0
0x20a56  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x20a5b  pop
0x20a5c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20a61  stloc.1
0x20a62  ldc.i4.0
0x20a63  stloc.2
0x20a64  ldarg.2
0x20a65  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x20a6a  ldloc.0
0x20a6b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x20a70  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase
0x20a75  stloc.3
0x20a76  ldarg.2
0x20a77  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x20a7c  ldloc.0
0x20a7d  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x20a82  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.WebActivityReference
0x20a87  stloc.s  4
0x20a89  ldarg.2
0x20a8a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x20a8f  ldloc.0
0x20a90  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x20a95  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference
0x20a9a  stloc.s  5
0x20a9c  ldloc.s  4
0x20a9e  brfalse.s loc_20AB2
0x20aa0  ldloca.s 1
0x20aa2  ldloc.s  4
0x20aa4  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.WebActivityReference::get_PluginTypeId()
0x20aa9  call     instance void [mscorlib]System.Guid::.ctor(string)
0x20aae  ldc.i4.1
0x20aaf  stloc.2
0x20ab0  br.s     loc_20AF8
0x20ab2  ldloc.s  5
0x20ab4  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::get_AssemblyQualifiedName()
0x20ab9  ldloca.s 0xB
0x20abb  ldloca.s 0xA
0x20abd  ldloca.s 0xC
0x20abf  ldloca.s 0xD
0x20ac1  ldloca.s 0xE
0x20ac3  call     void Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::GetTypeDetails(string assemblyQualifiedName, [out] string& typeName, [out] string& assemblyName, [out] string& version, [out] string& culture, [out] string& publicKeyToken)
0x20ac8  ldsfld   string [mscorlib]System.String::Empty
0x20acd  ldsfld   string [mscorlib]System.String::Empty
0x20ad2  ldloc.s  0xB
0x20ad4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20ad9  ldloc.s  0xA
0x20adb  ldloc.s  0xE
0x20add  ldloc.s  0xD
0x20adf  ldloc.s  0xC
0x20ae1  ldc.i4.0
0x20ae2  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo::.ctor(string, string, string, valuetype [mscorlib]System.Guid, string, string, string, string, bool)
0x20ae7  stloc.s  0xF
0x20ae9  ldarg.0
0x20aea  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_customActivityInfoProvider
0x20aef  ldloc.s  0xF
0x20af1  ldc.i4.1
0x20af2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider::GetActivityPluginId(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo activityInfo, bool ignoreWeb)
0x20af7  stloc.1
0x20af8  ldloc.1
0x20af9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20afe  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20b03  brfalse.s loc_20B14
0x20b05  ldarg.0
0x20b06  ldarg.1
0x20b07  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ClearCustomStepOutputs(string stepId)
0x20b0c  ldarg.1
0x20b0d  ldc.i4.1
0x20b0e  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep::.ctor(string, bool)
0x20b13  ret
0x20b14  ldarg.0
0x20b15  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_customActivityInfoProvider
0x20b1a  ldloc.1
0x20b1b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider::GetCustomActivityInfo(valuetype [mscorlib]System.Guid pluginTypeId)
0x20b20  stloc.s  6
0x20b22  ldloc.s  6
0x20b24  brtrue.s loc_20B35
0x20b26  ldarg.0
0x20b27  ldarg.1
0x20b28  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ClearCustomStepOutputs(string stepId)
0x20b2d  ldarg.1
0x20b2e  ldc.i4.1
0x20b2f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep::.ctor(string, bool)
0x20b34  ret
0x20b35  ldloc.s  6
0x20b37  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_CustomActivityInfo()
0x20b3c  ldloc.1
0x20b3d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::set_PluginTypeId(valuetype [mscorlib]System.Guid)
0x20b42  ldnull
0x20b43  stloc.s  7
0x20b45  ldnull
0x20b46  stloc.s  8
0x20b48  ldnull
0x20b49  stloc.s  9
0x20b4b  ldloc.s  6
0x20b4d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[] [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_Inputs()
0x20b52  stloc.s  7
0x20b54  ldloc.s  6
0x20b56  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[] [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_Outputs()
0x20b5b  stloc.s  8
0x20b5d  ldarg.0
0x20b5e  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x20b63  ldloc.s  6
0x20b65  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_CustomActivityInfo()
0x20b6a  ldloc.s  7
0x20b6c  ldloc.s  8
0x20b6e  ldloc.2
0x20b6f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[], class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[], bool)
0x20b74  stloc.s  9
0x20b76  leave.s  loc_20B8B
0x20b78  pop
0x20b79  ldarg.0
0x20b7a  ldarg.1
0x20b7b  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ClearCustomStepOutputs(string stepId)
0x20b80  ldarg.1
0x20b81  ldc.i4.1
0x20b82  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep::.ctor(string, bool)
0x20b87  stloc.s  0x10
0x20b89  leave.s  loc_20BB0
0x20b8b  ldarg.0
0x20b8c  ldloc.s  7
0x20b8e  stloc.s  0x11
0x20b90  ldloc.s  0x11
0x20b92  ldloc.3
0x20b93  ldloc.s  9
0x20b95  ldarg.1
0x20b96  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomStepInputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase[] inParameters, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference customReference, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase customStep, string stepId)
0x20b9b  ldarg.0
0x20b9c  ldloc.s  9
0x20b9e  ldloc.3
0x20b9f  ldarg.1
0x20ba0  ldnull
0x20ba1  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomStepOutputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase customStep, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference customReference, string stepId, [opt] class [mscorlib]System.Collections.Generic.IList`1<string> mismatchOutputs)
0x20ba6  ldarg.0
0x20ba7  ldarg.1
0x20ba8  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ClearCustomStepOutputs(string stepId)
0x20bad  ldloc.s  9
0x20baf  ret
0x20bb0  ldloc.s  0x10
0x20bb2  ret
```
