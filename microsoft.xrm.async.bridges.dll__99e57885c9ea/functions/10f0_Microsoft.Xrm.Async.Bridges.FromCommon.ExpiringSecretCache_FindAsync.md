# Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::FindAsync

- ea: `0x10f0`
- end: `0x1136`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::FindAsync`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xab0`
- `0x11b0`
- `0x34f0`

## pseudocode

```c

```

## disassembly

```asm
0x10f0  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x10f5  stloc.0
0x10f6  ldloc.0
0x10f7  ldarg.0
0x10f8  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache <>c__DisplayClass5_0::<>4__this
0x10fd  ldloc.0
0x10fe  ldarg.1
0x10ff  stfld    string <>c__DisplayClass5_0::key
0x1104  ldloc.0
0x1105  ldfld    string <>c__DisplayClass5_0::key
0x110a  ldstr    aKey// "key"
0x110f  call     T0x2B000024
0x1114  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x1119  pop
0x111a  ldloc.0
0x111b  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<string> <>c__DisplayClass5_0::<FindAsync>b__0(valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions x)
0x1121  newobj   instance void class [mscorlib]System.Func`2<valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions, class [mscorlib]System.Threading.Tasks.Task`1<string>>::.ctor(object, native int)
0x1126  stloc.1
0x1127  ldarg.0
0x1128  ldloc.0
0x1129  ldfld    string <>c__DisplayClass5_0::key
0x112e  ldarg.2
0x112f  ldloc.1
0x1130  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::InternalFindAsync(string key, valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions options, class [mscorlib]System.Func`2<valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions, class [mscorlib]System.Threading.Tasks.Task`1<string>> innerFindFunc)
0x1135  ret
```
