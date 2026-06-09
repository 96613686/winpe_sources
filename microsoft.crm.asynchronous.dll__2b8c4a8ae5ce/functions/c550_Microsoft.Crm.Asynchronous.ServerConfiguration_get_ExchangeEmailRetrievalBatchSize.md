# Microsoft.Crm.Asynchronous.ServerConfiguration::get_ExchangeEmailRetrievalBatchSize

- ea: `0xc550`
- end: `0xc570`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_ExchangeEmailRetrievalBatchSize`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc550`
- `0xc960`

## string_xrefs

- `0xc555`: `ECIncomingEmailExchangeEmailRetrievalBatchSize`

## pseudocode

```c

```

## disassembly

```asm
0xc550  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xc555  ldstr    aEcincomingemai_0// "ECIncomingEmailExchangeEmailRetrievalBa"...
0xc55a  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xc55f  dup
0xc560  brtrue.s loc_C56A
0xc562  pop
0xc563  ldc.i4.s 0xA
0xc565  box      [mscorlib]System.Int32
0xc56a  unbox.any [mscorlib]System.Int32
0xc56f  ret
```
