# Microsoft.Crm.Sandbox.SandboxServiceProvider::GetService

- ea: `0x1c00`
- end: `0x1c1f`
- name: `Microsoft.Crm.Sandbox.SandboxServiceProvider::GetService`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7b0`
- `0x1240`

## callees

- `0x1c00`

## pseudocode

```c

```

## disassembly

```asm
0x1c00  ldarg.1
0x1c01  ldnull
0x1c02  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c07  brfalse.s loc_1C0B
0x1c09  ldnull
0x1c0a  ret
0x1c0b  ldarg.0
0x1c0c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Sandbox.SandboxServiceProvider::_serviceProviderLookUp
0x1c11  ldarg.1
0x1c12  ldloca.s 0
0x1c14  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::TryGetValue(var<u1>, !!T0)
0x1c19  brfalse.s loc_1C1D
0x1c1b  ldloc.0
0x1c1c  ret
0x1c1d  ldnull
0x1c1e  ret
```
