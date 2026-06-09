# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_IsUnlinkedInCrm

- ea: `0x54ca0`
- end: `0x54cca`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_IsUnlinkedInCrm`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x53830`
- `0x53f30`
- `0x5d9e0`

## callees

- `0x54ca0`
- `0x54f20`

## string_xrefs

- `0x54ca6`: `isunlinkedincrm`
- `0x54cba`: `isunlinkedincrm`

## pseudocode

```c

```

## disassembly

```asm
0x54ca0  ldarg.0
0x54ca1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_InnerEntity()
0x54ca6  ldstr    aIsunlinkedincr// "isunlinkedincrm"
0x54cab  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x54cb0  brtrue.s loc_54CB4
0x54cb2  ldc.i4.0
0x54cb3  ret
0x54cb4  ldarg.0
0x54cb5  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_InnerEntity()
0x54cba  ldstr    aIsunlinkedincr// "isunlinkedincrm"
0x54cbf  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x54cc4  unbox.any [mscorlib]System.Boolean
0x54cc9  ret
```
