# Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::Find_0

- ea: `0xd10`
- end: `0xd9f`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::Find_0`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd00`
- `0xd10`
- `0xda0`
- `0xe00`

## pseudocode

```c

```

## disassembly

```asm
0xd10  ldtoken  mvar<u1>
0xd15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd1a  stloc.0
0xd1b  ldarg.1
0xd1c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd21  brfalse.s loc_D2C
0xd23  ldarg.0
0xd24  ldloc.0
0xd25  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::GetDefaultSectionName(class [mscorlib]System.Type type)
0xd2a  starg.s  1
0xd2c  call     T0x2B00001F
0xd31  stloc.1
0xd32  ldloc.0
0xd33  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0xd38  ldarg.0
0xd39  ldftn    T0x2B000020
0xd3f  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Reflection.PropertyInfo, bool>::.ctor(object, native int)
0xd44  call     T0x2B000021
0xd49  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Reflection.PropertyInfo>::GetEnumerator()
0xd4e  stloc.2
0xd4f  br.s     loc_D89
0xd51  ldloc.2
0xd52  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.PropertyInfo>::get_Current()
0xd57  stloc.3
0xd58  ldarg.0
0xd59  ldarg.1
0xd5a  ldloc.3
0xd5b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xd60  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::Find(string sectionName, string parameterName)
0xd65  stloc.s  4
0xd67  ldloc.s  4
0xd69  brfalse.s loc_D89
0xd6b  ldarg.0
0xd6c  ldloc.s  4
0xd6e  ldloc.3
0xd6f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0xd74  callvirt instance object Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::Convert(string value, class [mscorlib]System.Type type)
0xd79  stloc.s  5
0xd7b  ldloc.3
0xd7c  ldloc.1
0xd7d  box      mvar<u1>
0xd82  ldloc.s  5
0xd84  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object)
0xd89  ldloc.2
0xd8a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd8f  brtrue.s loc_D51
0xd91  leave.s  loc_D9D
0xd93  ldloc.2
0xd94  brfalse.s loc_D9C
0xd96  ldloc.2
0xd97  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd9c  endfinally
0xd9d  ldloc.1
0xd9e  ret
```
