# Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName

- ea: `0x26b0`
- end: `0x26c8`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d0`
- `0x7b0`
- `0x870`
- `0x9d0`
- `0xa50`

## callees

- `0x26d0`

## pseudocode

```c

```

## disassembly

```asm
0x26b0  ldarg.0
0x26b1  ldstr    aAssembly// "assembly"
0x26b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x26bb  ldarg.0
0x26bc  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x26c1  ldc.i4.1
0x26c2  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.AssemblyName assemblyName, bool isStrongNameSigned)
0x26c7  ret
```
