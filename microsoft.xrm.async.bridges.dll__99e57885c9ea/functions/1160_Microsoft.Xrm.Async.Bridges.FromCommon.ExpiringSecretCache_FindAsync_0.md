# Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::FindAsync_0

- ea: `0x1160`
- end: `0x11ab`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::FindAsync_0`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x11b0`
- `0x3530`

## string_xrefs

- `0x117a`: `secretUri`

## pseudocode

```c

```

## disassembly

```asm
0x1160  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x1165  stloc.0
0x1166  ldloc.0
0x1167  ldarg.0
0x1168  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache <>c__DisplayClass7_0::<>4__this
0x116d  ldloc.0
0x116e  ldarg.1
0x116f  stfld    class [System]System.Uri <>c__DisplayClass7_0::secretUri
0x1174  ldloc.0
0x1175  ldfld    class [System]System.Uri <>c__DisplayClass7_0::secretUri
0x117a  ldstr    aSecreturi// "secretUri"
0x117f  call     T0x2B00000F
0x1184  call     T0x2B000010
0x1189  pop
0x118a  ldloc.0
0x118b  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<string> <>c__DisplayClass7_0::<FindAsync>b__0(valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions x)
0x1191  newobj   instance void class [mscorlib]System.Func`2<valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions, class [mscorlib]System.Threading.Tasks.Task`1<string>>::.ctor(object, native int)
0x1196  stloc.1
0x1197  ldarg.0
0x1198  ldloc.0
0x1199  ldfld    class [System]System.Uri <>c__DisplayClass7_0::secretUri
0x119e  callvirt instance string [mscorlib]System.Object::ToString()
0x11a3  ldarg.2
0x11a4  ldloc.1
0x11a5  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::InternalFindAsync(string key, valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions options, class [mscorlib]System.Func`2<valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions, class [mscorlib]System.Threading.Tasks.Task`1<string>> innerFindFunc)
0x11aa  ret
```
