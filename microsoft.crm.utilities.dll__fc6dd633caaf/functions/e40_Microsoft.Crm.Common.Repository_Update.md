# Microsoft.Crm.Common.Repository::Update

- ea: `0xe40`
- end: `0xec6`
- name: `Microsoft.Crm.Common.Repository::Update`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0xe40`
- `0x1e50`

## string_xrefs

- `0xe56`: `propertiesToUpdate`
- `0xea8`: `PropertiesToUpdate cannot be empty`

## pseudocode

```c

```

## disassembly

```asm
0xe40  ldarg.1
0xe41  box      mvar<u1>
0xe46  brtrue.s loc_E53
0xe48  ldstr    aObj// "obj"
0xe4d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe52  throw
0xe53  ldarg.2
0xe54  brtrue.s loc_E61
0xe56  ldstr    aPropertiestoup// "propertiesToUpdate"
0xe5b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe60  throw
0xe61  ldarg.2
0xe62  isinst   string[]
0xe67  stloc.0
0xe68  ldloc.0
0xe69  brtrue.s loc_EA4
0xe6b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xe70  stloc.1
0xe71  ldarg.2
0xe72  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xe77  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0xe7c  stloc.2
0xe7d  ldc.i4.0
0xe7e  stloc.3
0xe7f  br.s     loc_E97
0xe81  ldloc.2
0xe82  ldloc.3
0xe83  ldelem.ref
0xe84  stloc.s  4
0xe86  ldloc.1
0xe87  ldloc.s  4
0xe89  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xe8e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xe93  ldloc.3
0xe94  ldc.i4.1
0xe95  add
0xe96  stloc.3
0xe97  ldloc.3
0xe98  ldloc.2
0xe99  ldlen
0xe9a  conv.i4
0xe9b  blt.s    loc_E81
0xe9d  ldloc.1
0xe9e  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0xea3  stloc.0
0xea4  ldloc.0
0xea5  ldlen
0xea6  brtrue.s loc_EB3
0xea8  ldstr    aPropertiestoup_0// "PropertiesToUpdate cannot be empty"
0xead  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xeb2  throw
0xeb3  ldarg.0
0xeb4  call     T0x2B000004
0xeb9  callvirt instance class Microsoft.Crm.Common.IDataProvider TypeInformation::get_DataProvider()
0xebe  ldarg.1
0xebf  ldloc.0
0xec0  callvirt T0x2B000005
0xec5  ret
```
