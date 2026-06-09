# Microsoft.Crm.Asynchronous.ServerConfiguration::get_MessageIdCacheRetentionTime

- ea: `0xc5e0`
- end: `0xc606`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_MessageIdCacheRetentionTime`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc5e0`
- `0xc960`

## string_xrefs

- `0xc5e5`: `ECMessageIDCacheRetentionTime`

## pseudocode

```c

```

## disassembly

```asm
0xc5e0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xc5e5  ldstr    aEcmessageidcac_0// "ECMessageIDCacheRetentionTime"
0xc5ea  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xc5ef  dup
0xc5f0  brtrue.s loc_C5FA
0xc5f2  pop
0xc5f3  ldc.i4.s 0x3C
0xc5f5  box      [mscorlib]System.Int32
0xc5fa  unbox.any [mscorlib]System.Int32
0xc5ff  conv.r8
0xc600  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0xc605  ret
```
