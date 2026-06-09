# Microsoft.Crm.Sandbox.SandboxHostManager::UpdateBadCount

- ea: `0x16c0`
- end: `0x16f7`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::UpdateBadCount`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x85d0`

## callees

- `0x16c0`

## pseudocode

```c

```

## disassembly

```asm
0x16c0  ldarg.0
0x16c1  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::GetEnumerator()
0x16c6  stloc.0
0x16c7  br.s     loc_16DD
0x16c9  ldloca.s 0
0x16cb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::get_Current()
0x16d0  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<bool>::get_Result()
0x16d5  brtrue.s loc_16DD
0x16d7  ldarg.1
0x16d8  ldarg.1
0x16d9  ldind.i4
0x16da  ldc.i4.1
0x16db  add
0x16dc  stind.i4
0x16dd  ldloca.s 0
0x16df  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::MoveNext()
0x16e4  brtrue.s loc_16C9
0x16e6  leave.s  loc_16F6
0x16e8  ldloca.s 0
0x16ea  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.Tasks.Task`1<bool>>
0x16f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16f5  endfinally
0x16f6  ret
```
