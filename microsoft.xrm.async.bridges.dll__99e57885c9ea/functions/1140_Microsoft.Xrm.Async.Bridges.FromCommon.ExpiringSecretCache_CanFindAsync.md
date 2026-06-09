# Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::CanFindAsync

- ea: `0x1140`
- end: `0x115f`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::CanFindAsync`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1530`

## string_xrefs

- `0x1141`: `secretUri`

## pseudocode

```c

```

## disassembly

```asm
0x1140  ldarg.1
0x1141  ldstr    aSecreturi// "secretUri"
0x1146  call     T0x2B00000F
0x114b  call     T0x2B000010
0x1150  pop
0x1151  ldarg.0
0x1152  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookup Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::inner
0x1157  ldarg.1
0x1158  ldarg.2
0x1159  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookup::CanFindAsync(class [System]System.Uri secretUri, [opt] valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions options)
0x115e  ret
```
