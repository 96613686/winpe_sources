# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::.ctor

- ea: `0x134e0`
- end: `0x13524`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::.ctor`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x11e40`

## callees

- `0x133d0`
- `0x133f0`
- `0x13410`
- `0x13430`
- `0x13450`
- `0x13470`
- `0x13490`
- `0x134b0`

## pseudocode

```c

```

## disassembly

```asm
0x134e0  ldarg.0
0x134e1  call     instance void [mscorlib]System.Object::.ctor()
0x134e6  ldarg.0
0x134e7  ldarg.1
0x134e8  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_AssociatedActionCardTypeId(valuetype [mscorlib]System.Guid value)
0x134ed  ldarg.0
0x134ee  ldarg.2
0x134ef  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_EntityTypeCode(int32 value)
0x134f4  ldarg.0
0x134f5  ldarg.3
0x134f6  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_EntityLogicalName(string value)
0x134fb  ldarg.0
0x134fc  ldarg.s  8
0x134fe  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_CardType(valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType value)
0x13503  ldarg.0
0x13504  ldarg.s  4
0x13506  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_EntityId(string value)
0x1350b  ldarg.0
0x1350c  ldarg.s  5
0x1350e  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_GetEntitySubject(class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> value)
0x13513  ldarg.0
0x13514  ldarg.s  6
0x13516  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_Subject(string value)
0x1351b  ldarg.0
0x1351c  ldarg.s  7
0x1351e  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_CardBodyResourceId(string value)
0x13523  ret
```
