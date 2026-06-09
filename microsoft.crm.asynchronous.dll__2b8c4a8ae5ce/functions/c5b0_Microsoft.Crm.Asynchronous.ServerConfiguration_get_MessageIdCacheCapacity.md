# Microsoft.Crm.Asynchronous.ServerConfiguration::get_MessageIdCacheCapacity

- ea: `0xc5b0`
- end: `0xc5d3`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_MessageIdCacheCapacity`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc5b0`
- `0xc960`

## string_xrefs

- `0xc5b5`: `ECMessageIDCacheCapacity`

## pseudocode

```c

```

## disassembly

```asm
0xc5b0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xc5b5  ldstr    aEcmessageidcac// "ECMessageIDCacheCapacity"
0xc5ba  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xc5bf  dup
0xc5c0  brtrue.s loc_C5CD
0xc5c2  pop
0xc5c3  ldc.i4   0x186A0
0xc5c8  box      [mscorlib]System.Int32
0xc5cd  unbox.any [mscorlib]System.Int32
0xc5d2  ret
```
