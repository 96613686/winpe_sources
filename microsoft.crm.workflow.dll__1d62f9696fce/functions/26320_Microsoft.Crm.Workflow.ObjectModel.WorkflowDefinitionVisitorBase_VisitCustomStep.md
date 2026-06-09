# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitCustomStep

- ea: `0x26320`
- end: `0x265ab`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitCustomStep`
- size: `651`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x26300`
- `0x26310`

## callees

- `0xf490`
- `0x262f0`
- `0x26320`
- `0x29e50`
- `0x2adb0`
- `0x2b4c0`
- `0x2d0b0`
- `0x2d170`
- `0x2d190`
- `0x2e260`
- `0x2e290`
- `0x2e2b0`
- `0x2e2d0`
- `0x2e310`

## string_xrefs

- `0x264a9`: `{0}, {1}, Version={2}, Culture={3}, PublicKeyToken={4}`

## pseudocode

```c

```

## disassembly

```asm
0x26320  ldarg.1
0x26321  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_IsInvalid()
0x26326  brfalse.s loc_2632E
0x26328  ldarg.0
0x26329  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ThrowInvalidActivityReference()
0x2632e  newobj   instance void Microsoft.Crm.Workflow.Activities.Composite::.ctor()
0x26333  dup
0x26334  ldarg.1
0x26335  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x2633a  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2633f  stloc.0
0x26340  ldarg.1
0x26341  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x26346  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2634b  brtrue.s loc_26369
0x2634d  ldloc.0
0x2634e  dup
0x2634f  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x26354  ldstr    asc_3C24E// ": "
0x26359  ldarg.1
0x2635a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x2635f  call     string [mscorlib]System.String::Concat(string, string, string)
0x26364  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x26369  ldarg.0
0x2636a  ldloc.0
0x2636b  call     instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivity(class [System.Activities]System.Activities.Activity activity)
0x26370  stloc.1
0x26371  ldarg.0
0x26372  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x26377  stloc.2
0x26378  ldarg.0
0x26379  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2637e  stloc.3
0x2637f  ldarg.0
0x26380  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x26385  ldloc.1
0x26386  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2638b  ldarg.0
0x2638c  ldloc.0
0x2638d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x26392  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x26397  ldarg.0
0x26398  ldloc.0
0x26399  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.Activities.Composite::get_Variables()
0x2639e  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x263a3  ldarg.1
0x263a4  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep
0x263a9  brfalse  loc_26467
0x263ae  ldarg.1
0x263af  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x263b4  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo
0x263b9  stloc.s  7
0x263bb  ldsfld   string [mscorlib]System.String::Empty
0x263c0  stloc.s  8
0x263c2  ldloc.s  7
0x263c4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::get_SdkMessageName()
0x263c9  brfalse.s loc_26411
0x263cb  ldloc.s  7
0x263cd  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::get_SdkMessageEntityName()
0x263d2  brfalse.s loc_26411
0x263d4  ldloc.s  7
0x263d6  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::get_SdkMessageName()
0x263db  ldstr    asc_3A406// "_"
0x263e0  ldloc.s  7
0x263e2  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::get_SdkMessageEntityName()
0x263e7  call     string [mscorlib]System.String::Concat(string, string, string)
0x263ec  stloc.s  9
0x263ee  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0x263f3  ldloc.s  9
0x263f5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x263fa  brtrue.s loc_26403
0x263fc  ldsfld   string [mscorlib]System.String::Empty
0x26401  br.s     loc_2640F
0x26403  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageRequestSuffixHelper::get_RequestSuffixDictionary()
0x26408  ldloc.s  9
0x2640a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x2640f  stloc.s  8
0x26411  newobj   instance void Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::.ctor()
0x26416  dup
0x26417  ldloc.0
0x26418  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x2641d  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x26422  dup
0x26423  ldloc.s  7
0x26425  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::get_SdkMessageId()
0x2642a  stloc.s  0xA
0x2642c  ldloca.s 0xA
0x2642e  constrained. [mscorlib]System.Guid
0x26434  callvirt instance string [mscorlib]System.Object::ToString()
0x26439  callvirt instance void Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::set_SdkMessageId(string value)
0x2643e  dup
0x2643f  ldloc.s  7
0x26441  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::get_SdkMessageName()
0x26446  callvirt instance void Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::set_SdkMessageName(string value)
0x2644b  dup
0x2644c  ldloc.s  7
0x2644e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::get_SdkMessageEntityName()
0x26453  callvirt instance void Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::set_SdkMessageEntityName(string value)
0x26458  dup
0x26459  ldloc.s  8
0x2645b  callvirt instance void Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::set_SdkMessageRequestSuffix(string value)
0x26460  stloc.s  4
0x26462  br       loc_2651C
0x26467  ldarg.1
0x26468  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_IsWebPluginActivity()
0x2646d  brfalse.s loc_264A4
0x2646f  newobj   instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.WebActivityReference::.ctor()
0x26474  dup
0x26475  ldloc.0
0x26476  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x2647b  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x26480  dup
0x26481  ldarg.1
0x26482  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x26487  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_PluginTypeId()
0x2648c  stloc.s  0xA
0x2648e  ldloca.s 0xA
0x26490  constrained. [mscorlib]System.Guid
0x26496  callvirt instance string [mscorlib]System.Object::ToString()
0x2649b  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.WebActivityReference::set_PluginTypeId(string)
0x264a0  stloc.s  4
0x264a2  br.s     loc_2651C
0x264a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x264a9  ldstr    a01Version2Cult// "{0}, {1}, Version={2}, Culture={3}, Pub"...
0x264ae  ldc.i4.5
0x264af  newarr   [mscorlib]System.Object
0x264b4  dup
0x264b5  ldc.i4.0
0x264b6  ldarg.1
0x264b7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x264bc  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_TypeName()
0x264c1  stelem.ref
0x264c2  dup
0x264c3  ldc.i4.1
0x264c4  ldarg.1
0x264c5  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x264ca  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_AssemblyName()
0x264cf  stelem.ref
0x264d0  dup
0x264d1  ldc.i4.2
0x264d2  ldarg.1
0x264d3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x264d8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_AssemblyVersion()
0x264dd  stelem.ref
0x264de  dup
0x264df  ldc.i4.3
0x264e0  ldarg.1
0x264e1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x264e6  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_Culture()
0x264eb  stelem.ref
0x264ec  dup
0x264ed  ldc.i4.4
0x264ee  ldarg.1
0x264ef  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x264f4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_PublicKeyToken()
0x264f9  stelem.ref
0x264fa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x264ff  stloc.s  0xB
0x26501  newobj   instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::.ctor()
0x26506  dup
0x26507  ldloc.0
0x26508  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x2650d  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x26512  dup
0x26513  ldloc.s  0xB
0x26515  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::set_AssemblyQualifiedName(string)
0x2651a  stloc.s  4
0x2651c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x26521  stloc.s  5
0x26523  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Activities]System.Activities.Statements.If>::.ctor()
0x26528  stloc.s  6
0x2652a  ldarg.1
0x2652b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x26530  brfalse.s loc_2653D
0x26532  ldarg.0
0x26533  ldarg.1
0x26534  ldloc.s  4
0x26536  ldloc.s  5
0x26538  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ProcessInputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase customStep, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference customReference, class [mscorlib]System.Collections.Generic.List`1<string> processedInOutArgs)
0x2653d  ldarg.1
0x2653e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Outputs()
0x26543  brfalse.s loc_26552
0x26545  ldarg.0
0x26546  ldarg.1
0x26547  ldloc.s  4
0x26549  ldloc.s  5
0x2654b  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [System.Activities]System.Activities.Statements.If> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ProcessOutputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase customStep, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference customReference, class [mscorlib]System.Collections.Generic.List`1<string> processedInOutArgs)
0x26550  stloc.s  6
0x26552  ldarg.0
0x26553  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x26558  ldloc.s  4
0x2655a  castclass [System.Activities]System.Activities.NativeActivity
0x2655f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x26564  ldloc.s  6
0x26566  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Activities]System.Activities.Statements.If>::GetEnumerator()
0x2656b  stloc.s  0xC
0x2656d  br.s     loc_26585
0x2656f  ldloc.s  0xC
0x26571  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Statements.If>::get_Current()
0x26576  stloc.s  0xD
0x26578  ldarg.0
0x26579  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2657e  ldloc.s  0xD
0x26580  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x26585  ldloc.s  0xC
0x26587  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2658c  brtrue.s loc_2656F
0x2658e  leave.s  loc_2659C
0x26590  ldloc.s  0xC
0x26592  brfalse.s loc_2659B
0x26594  ldloc.s  0xC
0x26596  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2659b  endfinally
0x2659c  ldarg.0
0x2659d  ldloc.2
0x2659e  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x265a3  ldarg.0
0x265a4  ldloc.3
0x265a5  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x265aa  ret
```
