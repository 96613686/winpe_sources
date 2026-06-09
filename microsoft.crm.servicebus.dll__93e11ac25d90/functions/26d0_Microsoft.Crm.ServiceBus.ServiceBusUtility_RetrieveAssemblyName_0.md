# Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName_0

- ea: `0x26d0`
- end: `0x26f6`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName_0`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26b0`

## callees

- `0x26d0`

## pseudocode

```c

```

## disassembly

```asm
0x26d0  ldarg.0
0x26d1  ldstr    aAssemblyname// "assemblyName"
0x26d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x26db  ldarg.1
0x26dc  brtrue.s loc_26E6
0x26de  ldarg.0
0x26df  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x26e4  br.s     loc_26EC
0x26e6  ldarg.0
0x26e7  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_FullName()
0x26ec  ldc.i4.s 0x2C
0x26ee  ldc.i4.s 0x3A
0x26f0  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x26f5  ret
```
