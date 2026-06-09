# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_IsDeletedInExchange

- ea: `0x54c50`
- end: `0x54c7a`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_IsDeletedInExchange`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x53830`
- `0x53f30`
- `0x5c270`

## callees

- `0x54c50`
- `0x54f20`

## string_xrefs

- `0x54c56`: `isdeletedinexchange`
- `0x54c6a`: `isdeletedinexchange`

## pseudocode

```c

```

## disassembly

```asm
0x54c50  ldarg.0
0x54c51  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_InnerEntity()
0x54c56  ldstr    aIsdeletedinexc// "isdeletedinexchange"
0x54c5b  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x54c60  brtrue.s loc_54C64
0x54c62  ldc.i4.0
0x54c63  ret
0x54c64  ldarg.0
0x54c65  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_InnerEntity()
0x54c6a  ldstr    aIsdeletedinexc// "isdeletedinexchange"
0x54c6f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x54c74  unbox.any [mscorlib]System.Boolean
0x54c79  ret
```
