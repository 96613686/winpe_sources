# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::Dispose_0

- ea: `0x1270`
- end: `0x128e`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::Dispose_0`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1230`
- `0x1250`

## callees

- `0x1270`

## pseudocode

```c

```

## disassembly

```asm
0x1270  ldarg.0
0x1271  ldfld    bool Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_disposed
0x1276  brtrue.s loc_128D
0x1278  ldarg.1
0x1279  brfalse.s loc_1286
0x127b  ldarg.0
0x127c  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_completionEvent
0x1281  callvirt instance void [mscorlib]System.Threading.WaitHandle::Dispose()
0x1286  ldarg.0
0x1287  ldc.i4.1
0x1288  stfld    bool Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_disposed
0x128d  ret
```
