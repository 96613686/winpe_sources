# <ConstructModelProperties>d__5::MoveNext

- ea: `0x5300`
- end: `0x53db`
- name: `<ConstructModelProperties>d__5::MoveNext`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x17f0`
- `0x1810`
- `0x1820`
- `0x52e0`
- `0x5300`
- `0x53e0`

## pseudocode

```c

```

## disassembly

```asm
0x5300  ldarg.0
0x5301  ldfld    int32 <ConstructModelProperties>d__5::<>1__state
0x5306  stloc.1
0x5307  ldloc.1
0x5308  brfalse.s loc_5318
0x530a  ldloc.1
0x530b  ldc.i4.1
0x530c  beq      loc_53AC
0x5311  ldc.i4.0
0x5312  stloc.0
0x5313  leave    loc_53D9
0x5318  ldarg.0
0x5319  ldc.i4.m1
0x531a  stfld    int32 <ConstructModelProperties>d__5::<>1__state
0x531f  ldarg.0
0x5320  ldfld    class [mscorlib]System.Type <ConstructModelProperties>d__5::modelType
0x5325  ldc.i4.s 0x14
0x5327  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties(valuetype [mscorlib]System.Reflection.BindingFlags)
0x532c  stloc.2
0x532d  ldarg.0
0x532e  ldloc.2
0x532f  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Reflection.PropertyInfo, string> <>c::<>9__5_0
0x5334  dup
0x5335  brtrue.s loc_534E
0x5337  pop
0x5338  ldsfld   class <>c <>c::<>9
0x533d  ldftn    instance string <>c::<ConstructModelProperties>b__5_0(class [mscorlib]System.Reflection.PropertyInfo x)
0x5343  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Reflection.PropertyInfo, string>::.ctor(object, native int)
0x5348  dup
0x5349  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Reflection.PropertyInfo, string> <>c::<>9__5_0
0x534e  call     T0x2B00002D
0x5353  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Reflection.PropertyInfo>::GetEnumerator()
0x5358  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.PropertyInfo> <ConstructModelProperties>d__5::<>7__wrap1
0x535d  ldarg.0
0x535e  ldc.i4.s 0xFD
0x5360  stfld    int32 <ConstructModelProperties>d__5::<>1__state
0x5365  br.s     loc_53B4
0x5367  ldarg.0
0x5368  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.PropertyInfo> <ConstructModelProperties>d__5::<>7__wrap1
0x536d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.PropertyInfo>::get_Current()
0x5372  stloc.3
0x5373  newobj   instance void Microsoft.Crm.ScaleGroupApi.Models.SGModelProperty::.ctor()
0x5378  stloc.s  4
0x537a  ldloc.s  4
0x537c  ldloc.3
0x537d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x5382  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGModelProperty::set_PropertyName(string value)
0x5387  ldloc.s  4
0x5389  ldloc.3
0x538a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x538f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x5394  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGModelProperty::set_PropertyType(string value)
0x5399  ldarg.0
0x539a  ldloc.s  4
0x539c  stfld    class Microsoft.Crm.ScaleGroupApi.Models.SGModelProperty <ConstructModelProperties>d__5::<>2__current
0x53a1  ldarg.0
0x53a2  ldc.i4.1
0x53a3  stfld    int32 <ConstructModelProperties>d__5::<>1__state
0x53a8  ldc.i4.1
0x53a9  stloc.0
0x53aa  leave.s  loc_53D9
0x53ac  ldarg.0
0x53ad  ldc.i4.s 0xFD
0x53af  stfld    int32 <ConstructModelProperties>d__5::<>1__state
0x53b4  ldarg.0
0x53b5  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.PropertyInfo> <ConstructModelProperties>d__5::<>7__wrap1
0x53ba  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x53bf  brtrue.s loc_5367
0x53c1  ldarg.0
0x53c2  call     instance void <ConstructModelProperties>d__5::<>m__Finally1()
0x53c7  ldarg.0
0x53c8  ldnull
0x53c9  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.PropertyInfo> <ConstructModelProperties>d__5::<>7__wrap1
0x53ce  ldc.i4.0
0x53cf  stloc.0
0x53d0  leave.s  loc_53D9
0x53d2  ldarg.0
0x53d3  call     instance void <ConstructModelProperties>d__5::System.IDisposable.Dispose()
0x53d8  endfinally
0x53d9  ldloc.0
0x53da  ret
```
