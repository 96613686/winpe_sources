# Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::BuildControllerList

- ea: `0x35c0`
- end: `0x3650`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::BuildControllerList`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1750`
- `0x1760`
- `0x35c0`

## pseudocode

```c

```

## disassembly

```asm
0x35c0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ScaleGroupApi.Models.SGController>::.ctor()
0x35c5  stloc.0
0x35c6  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x35cb  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Reflection.Assembly::GetTypes()
0x35d0  stloc.1
0x35d1  ldc.i4.0
0x35d2  stloc.2
0x35d3  br.s     loc_361F
0x35d5  ldloc.1
0x35d6  ldloc.2
0x35d7  ldelem.ref
0x35d8  stloc.3
0x35d9  ldloc.3
0x35da  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x35df  ldstr    aMicrosoftCrmSc// "Microsoft.Crm.ScaleGroupApi.Controllers"
0x35e4  ldc.i4.5
0x35e5  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x35ea  brfalse.s loc_361B
0x35ec  ldloc.3
0x35ed  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x35f2  ldstr    aController// "Controller"
0x35f7  ldc.i4.5
0x35f8  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x35fd  brfalse.s loc_361B
0x35ff  newobj   instance void Microsoft.Crm.ScaleGroupApi.Models.SGController::.ctor()
0x3604  stloc.s  4
0x3606  ldloc.s  4
0x3608  ldloc.3
0x3609  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x360e  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGController::set_Name(string value)
0x3613  ldloc.0
0x3614  ldloc.s  4
0x3616  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ScaleGroupApi.Models.SGController>::Add(var<u1>)
0x361b  ldloc.2
0x361c  ldc.i4.1
0x361d  add
0x361e  stloc.2
0x361f  ldloc.2
0x3620  ldloc.1
0x3621  ldlen
0x3622  conv.i4
0x3623  blt.s    loc_35D5
0x3625  ldloc.0
0x3626  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.ScaleGroupApi.Models.SGController, string> <>c::<>9__3_0
0x362b  dup
0x362c  brtrue.s loc_3645
0x362e  pop
0x362f  ldsfld   class <>c <>c::<>9
0x3634  ldftn    instance string <>c::<BuildControllerList>b__3_0(class Microsoft.Crm.ScaleGroupApi.Models.SGController x)
0x363a  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.ScaleGroupApi.Models.SGController, string>::.ctor(object, native int)
0x363f  dup
0x3640  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.ScaleGroupApi.Models.SGController, string> <>c::<>9__3_0
0x3645  call     T0x2B000015
0x364a  call     T0x2B000016
0x364f  ret
```
