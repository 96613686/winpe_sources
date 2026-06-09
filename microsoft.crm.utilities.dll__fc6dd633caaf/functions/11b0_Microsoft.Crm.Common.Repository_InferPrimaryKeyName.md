# Microsoft.Crm.Common.Repository::InferPrimaryKeyName

- ea: `0x11b0`
- end: `0x1236`
- name: `Microsoft.Crm.Common.Repository::InferPrimaryKeyName`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf40`
- `0x1010`

## callees

- `0x11b0`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  ldarg.0
0x11b1  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, string> Microsoft.Crm.Common.Repository::_primaryKeyName
0x11b6  ldarg.1
0x11b7  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, string>::ContainsKey(var<u1>)
0x11bc  brfalse.s loc_11CB
0x11be  ldarg.0
0x11bf  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, string> Microsoft.Crm.Common.Repository::_primaryKeyName
0x11c4  ldarg.1
0x11c5  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, string>::get_Item(void)
0x11ca  ret
0x11cb  ldnull
0x11cc  stloc.0
0x11cd  ldarg.1
0x11ce  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0x11d3  stloc.1
0x11d4  ldc.i4.0
0x11d5  stloc.2
0x11d6  br.s     loc_1221
0x11d8  ldloc.1
0x11d9  ldloc.2
0x11da  ldelem.ref
0x11db  stloc.3
0x11dc  ldloc.3
0x11dd  ldtoken  [System.ComponentModel.DataAnnotations]System.ComponentModel.DataAnnotations.KeyAttribute
0x11e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11e7  ldc.i4.0
0x11e8  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x11ed  stloc.s  4
0x11ef  ldloc.s  4
0x11f1  brfalse.s loc_121D
0x11f3  ldloc.s  4
0x11f5  ldlen
0x11f6  brfalse.s loc_121D
0x11f8  ldloc.0
0x11f9  brfalse.s loc_1216
0x11fb  ldstr    aObject// "Object ["
0x1200  ldarg.1
0x1201  callvirt instance string [mscorlib]System.Object::ToString()
0x1206  ldstr    aHasMultipleAtt// "] has multiple attributes with the Key "...
0x120b  call     string [mscorlib]System.String::Concat(string, string, string)
0x1210  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1215  throw
0x1216  ldloc.3
0x1217  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x121c  stloc.0
0x121d  ldloc.2
0x121e  ldc.i4.1
0x121f  add
0x1220  stloc.2
0x1221  ldloc.2
0x1222  ldloc.1
0x1223  ldlen
0x1224  conv.i4
0x1225  blt.s    loc_11D8
0x1227  ldarg.0
0x1228  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, string> Microsoft.Crm.Common.Repository::_primaryKeyName
0x122d  ldarg.1
0x122e  ldloc.0
0x122f  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, string>::set_Item(var<u1>, !!T0)
0x1234  ldloc.0
0x1235  ret
```
