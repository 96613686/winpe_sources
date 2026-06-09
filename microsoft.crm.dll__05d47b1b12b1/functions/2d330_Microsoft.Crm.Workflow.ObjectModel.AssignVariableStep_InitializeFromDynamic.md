# Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::InitializeFromDynamic

- ea: `0x2d330`
- end: `0x2d671`
- name: `Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::InitializeFromDynamic`
- size: `833`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x2d330`
- `0x30ca0`
- `0x30ef0`
- `0x3a980`

## string_xrefs

- `0x2d39c`: `readOnly`
- `0x2d3e5`: `readOnly`

## pseudocode

```c

```

## disassembly

```asm
0x2d330  ldarg.1
0x2d331  brfalse  loc_2D670
0x2d336  ldarg.0
0x2d337  ldarg.1
0x2d338  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::InitializeFromDynamic(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> deserializedObject)
0x2d33d  ldarg.1
0x2d33e  ldstr    aVariablename// "variableName"
0x2d343  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2d348  brfalse.s loc_2D39B
0x2d34a  ldarg.0
0x2d34b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__27::<>p__0
0x2d350  brtrue.s loc_2D376
0x2d352  ldc.i4.0
0x2d353  ldtoken  [mscorlib]System.String
0x2d358  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d35d  ldtoken  Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x2d362  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d367  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d36c  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x2d371  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__27::<>p__0
0x2d376  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__27::<>p__0
0x2d37b  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x2d380  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__27::<>p__0
0x2d385  ldarg.0
0x2d386  ldarg.1
0x2d387  ldstr    aVariablename// "variableName"
0x2d38c  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2d391  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x2d396  stfld    string Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::variableName
0x2d39b  ldarg.1
0x2d39c  ldstr    aReadonly// "readOnly"
0x2d3a1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2d3a6  brfalse.s loc_2D3F9
0x2d3a8  ldarg.0
0x2d3a9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__27::<>p__1
0x2d3ae  brtrue.s loc_2D3D4
0x2d3b0  ldc.i4.0
0x2d3b1  ldtoken  [mscorlib]System.Boolean
0x2d3b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d3bb  ldtoken  Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x2d3c0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d3c5  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d3ca  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Create(!!T0)
0x2d3cf  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__27::<>p__1
0x2d3d4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__27::<>p__1
0x2d3d9  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Target
0x2d3de  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__27::<>p__1
0x2d3e3  ldarg.0
0x2d3e4  ldarg.1
0x2d3e5  ldstr    aReadonly// "readOnly"
0x2d3ea  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2d3ef  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>::Invoke(bool, var<u1>)
0x2d3f4  stfld    bool Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::readOnly
0x2d3f9  ldarg.1
0x2d3fa  ldstr    aDirection// "direction"
0x2d3ff  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2d404  brfalse.s loc_2D458
0x2d406  ldarg.0
0x2d407  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection>> <>o__27::<>p__2
0x2d40c  brtrue.s loc_2D433
0x2d40e  ldc.i4.s 0x10
0x2d410  ldtoken  [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection
0x2d415  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d41a  ldtoken  Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x2d41f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d424  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d429  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection>>::Create(!!T0)
0x2d42e  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection>> <>o__27::<>p__2
0x2d433  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection>> <>o__27::<>p__2
0x2d438  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection>>::Target
0x2d43d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection>> <>o__27::<>p__2
0x2d442  ldarg.0
0x2d443  ldarg.1
0x2d444  ldstr    aDirection// "direction"
0x2d449  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2d44e  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection>::Invoke(bool, var<u1>)
0x2d453  stfld    valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::direction
0x2d458  ldarg.1
0x2d459  ldstr    aDatatype// "dataType"
0x2d45e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2d463  brfalse  loc_2D4FC
0x2d468  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType>> <>o__27::<>p__3
0x2d46d  brtrue.s loc_2D494
0x2d46f  ldc.i4.s 0x10
0x2d471  ldtoken  Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType
0x2d476  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d47b  ldtoken  Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x2d480  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d485  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d48a  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType>>::Create(!!T0)
0x2d48f  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType>> <>o__27::<>p__3
0x2d494  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType>> <>o__27::<>p__3
0x2d499  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType>>::Target
0x2d49e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType>> <>o__27::<>p__3
0x2d4a3  ldarg.0
0x2d4a4  ldarg.1
0x2d4a5  ldstr    aDatatype// "dataType"
0x2d4aa  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2d4af  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType>::Invoke(bool, var<u1>)
0x2d4b4  stloc.0
0x2d4b5  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, class [mscorlib]System.Type> Microsoft.Crm.Workflow.ObjectModel.CustomOperationArgumentHelper::get_ArgumentDataTypes()
0x2d4ba  ldloc.0
0x2d4bb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, class [mscorlib]System.Type>::ContainsKey(var<u1>)
0x2d4c0  brtrue.s loc_2D4EB
0x2d4c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2d4c7  ldstr    aArgument0DoesN// "Argument {0} does not exist"
0x2d4cc  ldc.i4.1
0x2d4cd  newarr   [mscorlib]System.Object
0x2d4d2  dup
0x2d4d3  ldc.i4.0
0x2d4d4  ldloc.0
0x2d4d5  box      Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType
0x2d4da  stelem.ref
0x2d4db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d4e0  ldc.i4   0x80040216
0x2d4e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2d4ea  throw
0x2d4eb  ldarg.0
0x2d4ec  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, class [mscorlib]System.Type> Microsoft.Crm.Workflow.ObjectModel.CustomOperationArgumentHelper::get_ArgumentDataTypes()
0x2d4f1  ldloc.0
0x2d4f2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, class [mscorlib]System.Type>::get_Item(void)
0x2d4f7  stfld    class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::dataType
0x2d4fc  ldarg.1
0x2d4fd  ldstr    aValueexpressio// "valueExpression"
0x2d502  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2d507  brfalse  loc_2D670
0x2d50c  ldarg.0
0x2d50d  ldarg.1
0x2d50e  ldstr    aValueexpressio// "valueExpression"
0x2d513  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2d518  stloc.1
0x2d519  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__27::<>p__6
0x2d51e  brtrue.s loc_2D544
0x2d520  ldc.i4.0
0x2d521  ldtoken  Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x2d526  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d52b  ldtoken  Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x2d530  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d535  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d53a  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>>::Create(!!T0)
0x2d53f  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__27::<>p__6
0x2d544  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__27::<>p__6
0x2d549  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>>::Target
0x2d54e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__27::<>p__6
0x2d553  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__27::<>p__5
0x2d558  brtrue.s loc_2D595
0x2d55a  ldc.i4.0
0x2d55b  ldstr    aBuildexpressio// "BuildExpression"
0x2d560  ldnull
0x2d561  ldtoken  Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x2d566  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d56b  ldc.i4.2
0x2d56c  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2d571  dup
0x2d572  ldc.i4.0
0x2d573  ldc.i4.s 0x21
0x2d575  ldnull
0x2d576  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2d57b  stelem.ref
0x2d57c  dup
0x2d57d  ldc.i4.1
0x2d57e  ldc.i4.0
0x2d57f  ldnull
0x2d580  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2d585  stelem.ref
0x2d586  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2d58b  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x2d590  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__27::<>p__5
0x2d595  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__27::<>p__5
0x2d59a  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Target
0x2d59f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__27::<>p__5
0x2d5a4  ldtoken  Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory
0x2d5a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d5ae  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__27::<>p__4
0x2d5b3  brtrue.s loc_2D5E9
0x2d5b5  ldc.i4.0
0x2d5b6  ldtoken  Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x2d5bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d5c0  ldc.i4.2
0x2d5c1  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2d5c6  dup
0x2d5c7  ldc.i4.0
0x2d5c8  ldc.i4.0
0x2d5c9  ldnull
0x2d5ca  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2d5cf  stelem.ref
0x2d5d0  dup
0x2d5d1  ldc.i4.1
0x2d5d2  ldc.i4.3
0x2d5d3  ldnull
0x2d5d4  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2d5d9  stelem.ref
0x2d5da  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetIndex(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2d5df  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x2d5e4  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__27::<>p__4
0x2d5e9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__27::<>p__4
0x2d5ee  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x2d5f3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__27::<>p__4
0x2d5f8  ldloc.1
0x2d5f9  ldstr    aClass// "__class"
0x2d5fe  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x2d603  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>::Invoke(char, var<u1>, !!T0)
0x2d608  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Invoke(bool, var<u1>)
0x2d60d  stloc.2
0x2d60e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__27::<>p__7
0x2d613  brtrue.s loc_2D653
0x2d615  ldc.i4   0x100
0x2d61a  ldstr    aInitializefrom// "InitializeFromDynamic"
0x2d61f  ldnull
0x2d620  ldtoken  Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x2d625  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d62a  ldc.i4.2
0x2d62b  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2d630  dup
0x2d631  ldc.i4.0
0x2d632  ldc.i4.1
0x2d633  ldnull
0x2d634  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2d639  stelem.ref
0x2d63a  dup
0x2d63b  ldc.i4.1
0x2d63c  ldc.i4.0
0x2d63d  ldnull
0x2d63e  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2d643  stelem.ref
0x2d644  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2d649  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>>::Create(!!T0)
0x2d64e  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__27::<>p__7
0x2d653  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__27::<>p__7
0x2d658  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>>::Target
0x2d65d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__27::<>p__7
0x2d662  ldloc.2
0x2d663  ldloc.1
0x2d664  callvirt instance void class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>::Invoke(var<u1>, !!T0, var<u1>)
0x2d669  ldarg.0
0x2d66a  ldloc.2
0x2d66b  stfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::valueExpression
0x2d670  ret
```
