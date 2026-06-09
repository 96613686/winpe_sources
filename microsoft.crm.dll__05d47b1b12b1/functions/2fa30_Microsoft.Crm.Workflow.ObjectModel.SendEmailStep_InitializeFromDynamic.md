# Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::InitializeFromDynamic

- ea: `0x2fa30`
- end: `0x2fd28`
- name: `Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::InitializeFromDynamic`
- size: `760`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x2fa30`
- `0x30ca0`
- `0x30ef0`
- `0x3cf30`

## string_xrefs

- `0x2fa95`: `emailTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x2fa30  ldarg.1
0x2fa31  brfalse  loc_2FD27
0x2fa36  ldarg.0
0x2fa37  ldarg.1
0x2fa38  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::InitializeFromDynamic(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> deserializedObject)
0x2fa3d  ldarg.0
0x2fa3e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid>> <>o__21::<>p__0
0x2fa43  brtrue.s loc_2FA7A
0x2fa45  ldc.i4.0
0x2fa46  ldtoken  Microsoft.Crm.Workflow.ObjectModel.SendEmailStep
0x2fa4b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fa50  ldc.i4.2
0x2fa51  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2fa56  dup
0x2fa57  ldc.i4.0
0x2fa58  ldc.i4.s 0x21
0x2fa5a  ldnull
0x2fa5b  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fa60  stelem.ref
0x2fa61  dup
0x2fa62  ldc.i4.1
0x2fa63  ldc.i4.0
0x2fa64  ldnull
0x2fa65  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fa6a  stelem.ref
0x2fa6b  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeConstructor(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2fa70  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid>>::Create(!!T0)
0x2fa75  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid>> <>o__21::<>p__0
0x2fa7a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid>> <>o__21::<>p__0
0x2fa7f  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid>>::Target
0x2fa84  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid>> <>o__21::<>p__0
0x2fa89  ldtoken  [mscorlib]System.Guid
0x2fa8e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fa93  ldarg.0
0x2fa94  ldarg.1
0x2fa95  ldstr    aEmailtemplatei// "emailTemplateId"
0x2fa9a  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2fa9f  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype [mscorlib]System.Guid>::Invoke(char, var<u1>, !!T0)
0x2faa4  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::emailTemplateId
0x2faa9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SendEmailType>> <>o__21::<>p__1
0x2faae  brtrue.s loc_2FAFA
0x2fab0  ldc.i4   0x100
0x2fab5  ldstr    aTryparse// "TryParse"
0x2faba  ldnull
0x2fabb  ldtoken  Microsoft.Crm.Workflow.ObjectModel.SendEmailStep
0x2fac0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fac5  ldc.i4.3
0x2fac6  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2facb  dup
0x2facc  ldc.i4.0
0x2facd  ldc.i4.s 0x21
0x2facf  ldnull
0x2fad0  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fad5  stelem.ref
0x2fad6  dup
0x2fad7  ldc.i4.1
0x2fad8  ldc.i4.0
0x2fad9  ldnull
0x2fada  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fadf  stelem.ref
0x2fae0  dup
0x2fae1  ldc.i4.2
0x2fae2  ldc.i4.s 0x11
0x2fae4  ldnull
0x2fae5  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2faea  stelem.ref
0x2faeb  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2faf0  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SendEmailType>>::Create(!!T0)
0x2faf5  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SendEmailType>> <>o__21::<>p__1
0x2fafa  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SendEmailType>> <>o__21::<>p__1
0x2faff  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SendEmailType>>::Target
0x2fb04  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SendEmailType>> <>o__21::<>p__1
0x2fb09  ldtoken  [mscorlib]System.Enum
0x2fb0e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fb13  ldarg.0
0x2fb14  ldarg.1
0x2fb15  ldstr    aSendemailtype// "sendEmailType"
0x2fb1a  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2fb1f  ldarg.0
0x2fb20  ldflda   valuetype Microsoft.Crm.Workflow.ObjectModel.SendEmailType Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::sendEmailType
0x2fb25  callvirt instance void class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SendEmailType>::Invoke(var<u1>, !!T0, var<u1>, void)
0x2fb2a  ldarg.1
0x2fb2b  ldstr    aEntity// "entity"
0x2fb30  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2fb35  brfalse.s loc_2FBB1
0x2fb37  ldarg.0
0x2fb38  ldsfld   string Microsoft.Crm.Workflow.Utils.StringUtility::Empty
0x2fb3d  newobj   instance void Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string entityName)
0x2fb42  stfld    class Microsoft.Crm.Workflow.Expressions.EntitySpecification Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::entity
0x2fb47  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntitySpecification, object>> <>o__21::<>p__2
0x2fb4c  brtrue.s loc_2FB8C
0x2fb4e  ldc.i4   0x100
0x2fb53  ldstr    aInitializefrom// "InitializeFromDynamic"
0x2fb58  ldnull
0x2fb59  ldtoken  Microsoft.Crm.Workflow.ObjectModel.SendEmailStep
0x2fb5e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fb63  ldc.i4.2
0x2fb64  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2fb69  dup
0x2fb6a  ldc.i4.0
0x2fb6b  ldc.i4.1
0x2fb6c  ldnull
0x2fb6d  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fb72  stelem.ref
0x2fb73  dup
0x2fb74  ldc.i4.1
0x2fb75  ldc.i4.0
0x2fb76  ldnull
0x2fb77  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fb7c  stelem.ref
0x2fb7d  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2fb82  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntitySpecification, object>>::Create(!!T0)
0x2fb87  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntitySpecification, object>> <>o__21::<>p__2
0x2fb8c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntitySpecification, object>> <>o__21::<>p__2
0x2fb91  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntitySpecification, object>>::Target
0x2fb96  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntitySpecification, object>> <>o__21::<>p__2
0x2fb9b  ldarg.0
0x2fb9c  ldfld    class Microsoft.Crm.Workflow.Expressions.EntitySpecification Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::entity
0x2fba1  ldarg.1
0x2fba2  ldstr    aEntity// "entity"
0x2fba7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2fbac  callvirt instance void class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntitySpecification, object>::Invoke(var<u1>, !!T0, var<u1>)
0x2fbb1  ldarg.1
0x2fbb2  ldstr    aRegardingentit// "regardingEntity"
0x2fbb7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2fbbc  brfalse  loc_2FD27
0x2fbc1  ldarg.1
0x2fbc2  ldstr    aRegardingentit// "regardingEntity"
0x2fbc7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2fbcc  stloc.0
0x2fbcd  ldarg.0
0x2fbce  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>> <>o__21::<>p__5
0x2fbd3  brtrue.s loc_2FBF9
0x2fbd5  ldc.i4.0
0x2fbd6  ldtoken  Microsoft.Crm.Workflow.Expressions.EntityBase
0x2fbdb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fbe0  ldtoken  Microsoft.Crm.Workflow.ObjectModel.SendEmailStep
0x2fbe5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fbea  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2fbef  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>>::Create(!!T0)
0x2fbf4  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>> <>o__21::<>p__5
0x2fbf9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>> <>o__21::<>p__5
0x2fbfe  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>>::Target
0x2fc03  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>> <>o__21::<>p__5
0x2fc08  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__21::<>p__4
0x2fc0d  brtrue.s loc_2FC4A
0x2fc0f  ldc.i4.0
0x2fc10  ldstr    aBuildentity// "BuildEntity"
0x2fc15  ldnull
0x2fc16  ldtoken  Microsoft.Crm.Workflow.ObjectModel.SendEmailStep
0x2fc1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fc20  ldc.i4.2
0x2fc21  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2fc26  dup
0x2fc27  ldc.i4.0
0x2fc28  ldc.i4.s 0x21
0x2fc2a  ldnull
0x2fc2b  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fc30  stelem.ref
0x2fc31  dup
0x2fc32  ldc.i4.1
0x2fc33  ldc.i4.0
0x2fc34  ldnull
0x2fc35  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fc3a  stelem.ref
0x2fc3b  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2fc40  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x2fc45  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__21::<>p__4
0x2fc4a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__21::<>p__4
0x2fc4f  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Target
0x2fc54  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__21::<>p__4
0x2fc59  ldtoken  Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory
0x2fc5e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fc63  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__3
0x2fc68  brtrue.s loc_2FC9E
0x2fc6a  ldc.i4.0
0x2fc6b  ldtoken  Microsoft.Crm.Workflow.ObjectModel.SendEmailStep
0x2fc70  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fc75  ldc.i4.2
0x2fc76  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2fc7b  dup
0x2fc7c  ldc.i4.0
0x2fc7d  ldc.i4.0
0x2fc7e  ldnull
0x2fc7f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fc84  stelem.ref
0x2fc85  dup
0x2fc86  ldc.i4.1
0x2fc87  ldc.i4.3
0x2fc88  ldnull
0x2fc89  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fc8e  stelem.ref
0x2fc8f  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetIndex(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2fc94  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x2fc99  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__3
0x2fc9e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__3
0x2fca3  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x2fca8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__3
0x2fcad  ldloc.0
0x2fcae  ldstr    aClass// "__class"
0x2fcb3  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x2fcb8  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>::Invoke(char, var<u1>, !!T0)
0x2fcbd  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>::Invoke(bool, var<u1>)
0x2fcc2  stfld    class Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::regardingEntity
0x2fcc7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntityBase, object>> <>o__21::<>p__6
0x2fccc  brtrue.s loc_2FD0C
0x2fcce  ldc.i4   0x100
0x2fcd3  ldstr    aInitializefrom// "InitializeFromDynamic"
0x2fcd8  ldnull
0x2fcd9  ldtoken  Microsoft.Crm.Workflow.ObjectModel.SendEmailStep
0x2fcde  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fce3  ldc.i4.2
0x2fce4  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2fce9  dup
0x2fcea  ldc.i4.0
0x2fceb  ldc.i4.1
0x2fcec  ldnull
0x2fced  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fcf2  stelem.ref
0x2fcf3  dup
0x2fcf4  ldc.i4.1
0x2fcf5  ldc.i4.0
0x2fcf6  ldnull
0x2fcf7  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2fcfc  stelem.ref
0x2fcfd  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2fd02  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntityBase, object>>::Create(!!T0)
0x2fd07  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntityBase, object>> <>o__21::<>p__6
0x2fd0c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntityBase, object>> <>o__21::<>p__6
0x2fd11  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntityBase, object>>::Target
0x2fd16  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntityBase, object>> <>o__21::<>p__6
0x2fd1b  ldarg.0
0x2fd1c  ldfld    class Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::regardingEntity
0x2fd21  ldloc.0
0x2fd22  callvirt instance void class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.EntityBase, object>::Invoke(var<u1>, !!T0, var<u1>)
0x2fd27  ret
```
