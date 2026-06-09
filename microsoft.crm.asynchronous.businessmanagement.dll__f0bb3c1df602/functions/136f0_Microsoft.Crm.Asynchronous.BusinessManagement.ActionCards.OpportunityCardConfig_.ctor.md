# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::.ctor

- ea: `0x136f0`
- end: `0x1374c`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::.ctor`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x127d0`

## callees

- `0x135a0`
- `0x135c0`
- `0x135e0`
- `0x13600`
- `0x13620`
- `0x13640`
- `0x13660`
- `0x13680`
- `0x136a0`
- `0x136c0`
- `0x136e0`

## pseudocode

```c

```

## disassembly

```asm
0x136f0  ldarg.0
0x136f1  call     instance void [mscorlib]System.Object::.ctor()
0x136f6  ldarg.0
0x136f7  ldarg.1
0x136f8  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_AssociatedActionCardTypeId(valuetype [mscorlib]System.Guid value)
0x136fd  ldarg.0
0x136fe  ldarg.3
0x136ff  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_EntityTypeCode(int32 value)
0x13704  ldarg.0
0x13705  ldarg.2
0x13706  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_CardType(valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType value)
0x1370b  ldarg.0
0x1370c  ldarg.s  4
0x1370e  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_QueryStartDate(valuetype [mscorlib]System.DateTime value)
0x13713  ldarg.0
0x13714  ldarg.s  5
0x13716  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_QueryEndDate(valuetype [mscorlib]System.DateTime value)
0x1371b  ldarg.0
0x1371c  ldarg.s  6
0x1371e  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_Priority(valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority value)
0x13723  ldarg.0
0x13724  ldarg.s  7
0x13726  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_DaysToStartCard(int32 value)
0x1372b  ldarg.0
0x1372c  ldarg.s  8
0x1372e  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_DaysToEndCard(int32 value)
0x13733  ldarg.0
0x13734  ldarg.s  9
0x13736  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_TitleResourceId(string value)
0x1373b  ldarg.0
0x1373c  ldarg.s  0xA
0x1373e  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_BodyResourceId(string value)
0x13743  ldarg.0
0x13744  ldarg.s  0xB
0x13746  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::set_MiniCardResourceId(string value)
0x1374b  ret
```
