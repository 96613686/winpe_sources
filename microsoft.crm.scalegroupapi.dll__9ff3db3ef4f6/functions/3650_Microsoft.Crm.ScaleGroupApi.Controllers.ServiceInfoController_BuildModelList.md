# Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::BuildModelList

- ea: `0x3650`
- end: `0x36f2`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::BuildModelList`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1790`
- `0x17b0`
- `0x17c0`
- `0x3650`
- `0x3700`

## pseudocode

```c

```

## disassembly

```asm
0x3650  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ScaleGroupApi.Models.SGModel>::.ctor()
0x3655  stloc.0
0x3656  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x365b  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Reflection.Assembly::GetTypes()
0x3660  stloc.1
0x3661  ldc.i4.0
0x3662  stloc.2
0x3663  br.s     loc_36C1
0x3665  ldloc.1
0x3666  ldloc.2
0x3667  ldelem.ref
0x3668  stloc.3
0x3669  ldloc.3
0x366a  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x366f  ldstr    aMicrosoftCrmSc_0// "Microsoft.Crm.ScaleGroupApi.Models"
0x3674  ldc.i4.5
0x3675  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x367a  brfalse.s loc_36BD
0x367c  ldloc.3
0x367d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3682  ldstr    aSg// "SG"
0x3687  ldc.i4.5
0x3688  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x368d  brfalse.s loc_36BD
0x368f  newobj   instance void Microsoft.Crm.ScaleGroupApi.Models.SGModel::.ctor()
0x3694  stloc.s  4
0x3696  ldloc.s  4
0x3698  ldloc.3
0x3699  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x369e  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGModel::set_Name(string value)
0x36a3  ldloc.s  4
0x36a5  ldloc.3
0x36a6  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.ScaleGroupApi.Models.SGModelProperty> Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::ConstructModelProperties(class [mscorlib]System.Type modelType)
0x36ab  call     T0x2B000017
0x36b0  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGModel::set_ModelProperties(class Microsoft.Crm.ScaleGroupApi.Models.SGModelProperty[] value)
0x36b5  ldloc.0
0x36b6  ldloc.s  4
0x36b8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ScaleGroupApi.Models.SGModel>::Add(var<u1>)
0x36bd  ldloc.2
0x36be  ldc.i4.1
0x36bf  add
0x36c0  stloc.2
0x36c1  ldloc.2
0x36c2  ldloc.1
0x36c3  ldlen
0x36c4  conv.i4
0x36c5  blt.s    loc_3665
0x36c7  ldloc.0
0x36c8  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.ScaleGroupApi.Models.SGModel, string> <>c::<>9__4_0
0x36cd  dup
0x36ce  brtrue.s loc_36E7
0x36d0  pop
0x36d1  ldsfld   class <>c <>c::<>9
0x36d6  ldftn    instance string <>c::<BuildModelList>b__4_0(class Microsoft.Crm.ScaleGroupApi.Models.SGModel x)
0x36dc  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.ScaleGroupApi.Models.SGModel, string>::.ctor(object, native int)
0x36e1  dup
0x36e2  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.ScaleGroupApi.Models.SGModel, string> <>c::<>9__4_0
0x36e7  call     T0x2B000018
0x36ec  call     T0x2B000019
0x36f1  ret
```
