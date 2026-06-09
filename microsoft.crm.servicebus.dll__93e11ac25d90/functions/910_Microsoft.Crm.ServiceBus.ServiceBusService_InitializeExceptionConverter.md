# Microsoft.Crm.ServiceBus.ServiceBusService::InitializeExceptionConverter

- ea: `0x910`
- end: `0x932`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::InitializeExceptionConverter`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x940`
- `0x970`

## pseudocode

```c

```

## disassembly

```asm
0x910  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter Microsoft.Crm.ServiceBus.ServiceBusService::_exceptionConverter
0x915  ldc.i4.1
0x916  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::set_SkipCallStack(bool)
0x91b  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter Microsoft.Crm.ServiceBus.ServiceBusService::_exceptionConverter
0x920  ldc.i4.1
0x921  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::set_SkipExceptionMessage(bool)
0x926  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter Microsoft.Crm.ServiceBus.ServiceBusService::_exceptionConverter
0x92b  ldc.i4.1
0x92c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::set_SkipTraceText(bool)
0x931  ret
```
