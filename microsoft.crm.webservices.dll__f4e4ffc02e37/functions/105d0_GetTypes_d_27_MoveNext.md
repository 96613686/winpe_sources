# <GetTypes>d__27::MoveNext

- ea: `0x105d0`
- end: `0x1066b`
- name: `<GetTypes>d__27::MoveNext`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x105d0`

## pseudocode

```c

```

## disassembly

```asm
0x105d0  ldarg.0
0x105d1  ldfld    int32 <GetTypes>d__27::<>1__state
0x105d6  stloc.0
0x105d7  ldarg.0
0x105d8  ldfld    class Microsoft.Crm.Sdk.ServiceDescription <GetTypes>d__27::<>4__this
0x105dd  stloc.1
0x105de  ldloc.0
0x105df  brfalse.s loc_105E7
0x105e1  ldloc.0
0x105e2  ldc.i4.1
0x105e3  beq.s    loc_1063D
0x105e5  ldc.i4.0
0x105e6  ret
0x105e7  ldarg.0
0x105e8  ldc.i4.m1
0x105e9  stfld    int32 <GetTypes>d__27::<>1__state
0x105ee  ldarg.0
0x105ef  ldloc.1
0x105f0  ldfld    class [mscorlib]System.Type[] Microsoft.Crm.Sdk.ServiceDescription::_types
0x105f5  stfld    class [mscorlib]System.Type[] <GetTypes>d__27::<>7__wrap1
0x105fa  ldarg.0
0x105fb  ldc.i4.0
0x105fc  stfld    int32 <GetTypes>d__27::<>7__wrap2
0x10601  br.s     loc_10652
0x10603  ldarg.0
0x10604  ldfld    class [mscorlib]System.Type[] <GetTypes>d__27::<>7__wrap1
0x10609  ldarg.0
0x1060a  ldfld    int32 <GetTypes>d__27::<>7__wrap2
0x1060f  ldelem.ref
0x10610  stloc.2
0x10611  ldloc.2
0x10612  callvirt instance bool [mscorlib]System.Type::get_IsAbstract()
0x10617  brtrue.s loc_10644
0x10619  ldloc.2
0x1061a  ldarg.0
0x1061b  ldfld    string <GetTypes>d__27::interfaceName
0x10620  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetInterface(string)
0x10625  ldnull
0x10626  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1062b  brfalse.s loc_10644
0x1062d  ldarg.0
0x1062e  ldloc.2
0x1062f  stfld    object <GetTypes>d__27::<>2__current
0x10634  ldarg.0
0x10635  ldc.i4.1
0x10636  stfld    int32 <GetTypes>d__27::<>1__state
0x1063b  ldc.i4.1
0x1063c  ret
0x1063d  ldarg.0
0x1063e  ldc.i4.m1
0x1063f  stfld    int32 <GetTypes>d__27::<>1__state
0x10644  ldarg.0
0x10645  ldarg.0
0x10646  ldfld    int32 <GetTypes>d__27::<>7__wrap2
0x1064b  ldc.i4.1
0x1064c  add
0x1064d  stfld    int32 <GetTypes>d__27::<>7__wrap2
0x10652  ldarg.0
0x10653  ldfld    int32 <GetTypes>d__27::<>7__wrap2
0x10658  ldarg.0
0x10659  ldfld    class [mscorlib]System.Type[] <GetTypes>d__27::<>7__wrap1
0x1065e  ldlen
0x1065f  conv.i4
0x10660  blt.s    loc_10603
0x10662  ldarg.0
0x10663  ldnull
0x10664  stfld    class [mscorlib]System.Type[] <GetTypes>d__27::<>7__wrap1
0x10669  ldc.i4.0
0x1066a  ret
```
