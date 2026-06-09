# Microsoft.Crm.Workflow.ObjectModel.ActionStep::InitializeFromDynamic

- ea: `0x29400`
- end: `0x298b2`
- name: `Microsoft.Crm.Workflow.ObjectModel.ActionStep::InitializeFromDynamic`
- size: `1202`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x29400`
- `0x29ab0`
- `0x2de60`
- `0x30ef0`

## string_xrefs

- `0x29602`: `processId`

## pseudocode

```c

```

## disassembly

```asm
0x29400  ldarg.1
0x29401  brfalse  loc_298B1
0x29406  ldarg.0
0x29407  ldarg.1
0x29408  call     instance void Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::InitializeFromDynamic(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> deserializedObject)
0x2940d  ldarg.0
0x2940e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__32::<>p__0
0x29413  brtrue.s loc_29439
0x29415  ldc.i4.0
0x29416  ldtoken  [mscorlib]System.String
0x2941b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29420  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x29425  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2942a  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2942f  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x29434  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__32::<>p__0
0x29439  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__32::<>p__0
0x2943e  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x29443  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__32::<>p__0
0x29448  ldarg.0
0x29449  ldarg.1
0x2944a  ldstr    aActionid// "actionId"
0x2944f  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x29454  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x29459  stfld    string Microsoft.Crm.Workflow.ObjectModel.ActionStep::actionId
0x2945e  ldarg.0
0x2945f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__32::<>p__2
0x29464  brtrue.s loc_2948A
0x29466  ldc.i4.0
0x29467  ldtoken  [mscorlib]System.Int32
0x2946c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29471  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x29476  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2947b  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x29480  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>>::Create(!!T0)
0x29485  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__32::<>p__2
0x2948a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__32::<>p__2
0x2948f  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>>::Target
0x29494  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__32::<>p__2
0x29499  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__32::<>p__1
0x2949e  brtrue.s loc_294DB
0x294a0  ldc.i4.0
0x294a1  ldstr    aParse// "Parse"
0x294a6  ldnull
0x294a7  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x294ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x294b1  ldc.i4.2
0x294b2  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x294b7  dup
0x294b8  ldc.i4.0
0x294b9  ldc.i4.s 0x21
0x294bb  ldnull
0x294bc  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x294c1  stelem.ref
0x294c2  dup
0x294c3  ldc.i4.1
0x294c4  ldc.i4.0
0x294c5  ldnull
0x294c6  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x294cb  stelem.ref
0x294cc  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x294d1  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x294d6  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__32::<>p__1
0x294db  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__32::<>p__1
0x294e0  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Target
0x294e5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__32::<>p__1
0x294ea  ldtoken  [mscorlib]System.Int32
0x294ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x294f4  ldarg.0
0x294f5  ldarg.1
0x294f6  ldstr    aActiontype// "actionType"
0x294fb  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x29500  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>::Invoke(char, var<u1>, !!T0)
0x29505  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>::Invoke(bool, var<u1>)
0x2950a  stfld    int32 Microsoft.Crm.Workflow.ObjectModel.ActionStep::actionType
0x2950f  ldarg.0
0x29510  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__32::<>p__3
0x29515  brtrue.s loc_2953B
0x29517  ldc.i4.0
0x29518  ldtoken  [mscorlib]System.String
0x2951d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29522  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x29527  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2952c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x29531  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x29536  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__32::<>p__3
0x2953b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__32::<>p__3
0x29540  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x29545  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__32::<>p__3
0x2954a  ldarg.0
0x2954b  ldarg.1
0x2954c  ldstr    aUniquename// "uniqueName"
0x29551  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x29556  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x2955b  stfld    string Microsoft.Crm.Workflow.ObjectModel.ActionStep::uniqueName
0x29560  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__5
0x29565  brtrue.s loc_2958B
0x29567  ldc.i4.0
0x29568  ldtoken  [mscorlib]System.Boolean
0x2956d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29572  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x29577  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2957c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x29581  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Create(!!T0)
0x29586  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__5
0x2958b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__5
0x29590  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Target
0x29595  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__5
0x2959a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>F{00000008}`5<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid, object>> <>o__32::<>p__4
0x2959f  brtrue.s loc_295E7
0x295a1  ldc.i4.0
0x295a2  ldstr    aTryparse// "TryParse"
0x295a7  ldnull
0x295a8  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x295ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x295b2  ldc.i4.3
0x295b3  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x295b8  dup
0x295b9  ldc.i4.0
0x295ba  ldc.i4.s 0x21
0x295bc  ldnull
0x295bd  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x295c2  stelem.ref
0x295c3  dup
0x295c4  ldc.i4.1
0x295c5  ldc.i4.0
0x295c6  ldnull
0x295c7  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x295cc  stelem.ref
0x295cd  dup
0x295ce  ldc.i4.2
0x295cf  ldc.i4.s 0x11
0x295d1  ldnull
0x295d2  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x295d7  stelem.ref
0x295d8  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x295dd  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>F{00000008}`5<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid, object>>::Create(!!T0)
0x295e2  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>F{00000008}`5<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid, object>> <>o__32::<>p__4
0x295e7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>F{00000008}`5<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid, object>> <>o__32::<>p__4
0x295ec  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>F{00000008}`5<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid, object>>::Target
0x295f1  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>F{00000008}`5<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid, object>> <>o__32::<>p__4
0x295f6  ldtoken  [mscorlib]System.Guid
0x295fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29600  ldarg.0
0x29601  ldarg.1
0x29602  ldstr    aProcessid// "processId"
0x29607  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2960c  ldloca.s 0
0x2960e  callvirt instance var<u1> class <>F{00000008}`5<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid, object>::Invoke(int8, var<u1>, !!T0, var<u1>)
0x29613  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>::Invoke(bool, var<u1>)
0x29618  brfalse.s loc_2962E
0x2961a  ldloc.0
0x2961b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29620  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x29625  brfalse.s loc_2962E
0x29627  ldarg.0
0x29628  ldloc.0
0x29629  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ObjectModel.ActionStep::processId
0x2962e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData>::.ctor()
0x29633  stloc.1
0x29634  ldarg.1
0x29635  ldstr    aTriggerevents// "triggerEvents"
0x2963a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2963f  brfalse  loc_29737
0x29644  ldarg.0
0x29645  ldarg.1
0x29646  ldstr    aTriggerevents// "triggerEvents"
0x2964b  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x29650  stloc.2
0x29651  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [mscorlib]System.Collections.IEnumerable>> <>o__32::<>p__7
0x29656  brtrue.s loc_2967C
0x29658  ldc.i4.0
0x29659  ldtoken  [mscorlib]System.Collections.IEnumerable
0x2965e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29663  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x29668  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2966d  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x29672  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [mscorlib]System.Collections.IEnumerable>>::Create(!!T0)
0x29677  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [mscorlib]System.Collections.IEnumerable>> <>o__32::<>p__7
0x2967c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [mscorlib]System.Collections.IEnumerable>> <>o__32::<>p__7
0x29681  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [mscorlib]System.Collections.IEnumerable>>::Target
0x29686  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [mscorlib]System.Collections.IEnumerable>> <>o__32::<>p__7
0x2968b  ldloc.2
0x2968c  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [mscorlib]System.Collections.IEnumerable>::Invoke(bool, var<u1>)
0x29691  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x29696  stloc.3
0x29697  br.s     loc_2970D
0x29699  ldloc.3
0x2969a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2969f  stloc.s  4
0x296a1  newobj   instance void Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData::.ctor()
0x296a6  stloc.s  5
0x296a8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData, object>> <>o__32::<>p__6
0x296ad  brtrue.s loc_296ED
0x296af  ldc.i4   0x100
0x296b4  ldstr    aInitializefrom// "InitializeFromDynamic"
0x296b9  ldnull
0x296ba  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x296bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x296c4  ldc.i4.2
0x296c5  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x296ca  dup
0x296cb  ldc.i4.0
0x296cc  ldc.i4.1
0x296cd  ldnull
0x296ce  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x296d3  stelem.ref
0x296d4  dup
0x296d5  ldc.i4.1
0x296d6  ldc.i4.0
0x296d7  ldnull
0x296d8  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x296dd  stelem.ref
0x296de  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x296e3  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData, object>>::Create(!!T0)
0x296e8  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData, object>> <>o__32::<>p__6
0x296ed  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData, object>> <>o__32::<>p__6
0x296f2  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData, object>>::Target
0x296f7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData, object>> <>o__32::<>p__6
0x296fc  ldloc.s  5
0x296fe  ldloc.s  4
0x29700  callvirt instance void class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData, object>::Invoke(var<u1>, !!T0, var<u1>)
0x29705  ldloc.1
0x29706  ldloc.s  5
0x29708  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData>::Add(var<u1>)
0x2970d  ldloc.3
0x2970e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x29713  brtrue.s loc_29699
0x29715  leave.s  loc_2972B
0x29717  ldloc.3
0x29718  isinst   [mscorlib]System.IDisposable
0x2971d  stloc.s  6
0x2971f  ldloc.s  6
0x29721  brfalse.s loc_2972A
0x29723  ldloc.s  6
0x29725  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2972a  endfinally
0x2972b  ldarg.0
0x2972c  ldloc.1
0x2972d  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData>::ToArray()
0x29732  stfld    class Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[] Microsoft.Crm.Workflow.ObjectModel.ActionStep::triggerEvents
0x29737  ldarg.1
0x29738  ldstr    aActioncontrol// "actionControl"
0x2973d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x29742  brfalse  loc_298B1
0x29747  ldarg.1
0x29748  ldstr    aActioncontrol// "actionControl"
0x2974d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x29752  stloc.s  7
0x29754  ldarg.0
0x29755  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.ObjectModel.ControlStep>> <>o__32::<>p__10
0x2975a  brtrue.s loc_29781
0x2975c  ldc.i4.s 0x10
0x2975e  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x29763  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29768  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x2976d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29772  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x29777  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.ObjectModel.ControlStep>>::Create(!!T0)
0x2977c  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.ObjectModel.ControlStep>> <>o__32::<>p__10
0x29781  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.ObjectModel.ControlStep>> <>o__32::<>p__10
0x29786  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.ObjectModel.ControlStep>>::Target
0x2978b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.ObjectModel.ControlStep>> <>o__32::<>p__10
0x29790  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__32::<>p__9
0x29795  brtrue.s loc_297D2
0x29797  ldc.i4.0
0x29798  ldstr    aBuildstep// "BuildStep"
0x2979d  ldnull
0x2979e  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x297a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x297a8  ldc.i4.2
0x297a9  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x297ae  dup
0x297af  ldc.i4.0
0x297b0  ldc.i4.s 0x21
0x297b2  ldnull
0x297b3  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x297b8  stelem.ref
0x297b9  dup
0x297ba  ldc.i4.1
0x297bb  ldc.i4.0
0x297bc  ldnull
0x297bd  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x297c2  stelem.ref
0x297c3  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x297c8  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x297cd  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__32::<>p__9
0x297d2  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__32::<>p__9
0x297d7  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Target
0x297dc  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__32::<>p__9
0x297e1  ldtoken  Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory
0x297e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x297eb  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__8
0x297f0  brtrue.s loc_29826
0x297f2  ldc.i4.0
0x297f3  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x297f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x297fd  ldc.i4.2
0x297fe  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x29803  dup
  ... truncated ...
```
