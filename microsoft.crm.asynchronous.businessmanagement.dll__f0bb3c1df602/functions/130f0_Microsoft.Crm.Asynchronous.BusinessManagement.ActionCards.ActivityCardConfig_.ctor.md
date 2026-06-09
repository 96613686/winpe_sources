# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor

- ea: `0x130f0`
- end: `0x1313c`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x11040`

## callees

- `0x12fe0`
- `0x13000`
- `0x13020`
- `0x13040`
- `0x13060`
- `0x13080`
- `0x130a0`
- `0x130c0`
- `0x130e0`

## pseudocode

```c

```

## disassembly

```asm
0x130f0  ldarg.0
0x130f1  call     instance void [mscorlib]System.Object::.ctor()
0x130f6  ldarg.0
0x130f7  ldarg.1
0x130f8  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::set_EntityTypeCode(int32 value)
0x130fd  ldarg.0
0x130fe  ldarg.2
0x130ff  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::set_EntityLogicalName(string value)
0x13104  ldarg.0
0x13105  ldarg.3
0x13106  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::set_Priority(valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority value)
0x1310b  ldarg.0
0x1310c  ldarg.s  4
0x1310e  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::set_Visibility(bool value)
0x13113  ldarg.0
0x13114  ldarg.s  5
0x13116  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::set_StartDate(valuetype [mscorlib]System.DateTime value)
0x1311b  ldarg.0
0x1311c  ldarg.s  6
0x1311e  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::set_EndDate(valuetype [mscorlib]System.DateTime value)
0x13123  ldarg.0
0x13124  ldarg.s  7
0x13126  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::set_CardType(valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType value)
0x1312b  ldarg.0
0x1312c  ldarg.s  8
0x1312e  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::set_AssociatedActionCardTypeId(valuetype [mscorlib]System.Guid value)
0x13133  ldarg.0
0x13134  ldarg.s  9
0x13136  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::set_CardBodyResourceId(string value)
0x1313b  ret
```
