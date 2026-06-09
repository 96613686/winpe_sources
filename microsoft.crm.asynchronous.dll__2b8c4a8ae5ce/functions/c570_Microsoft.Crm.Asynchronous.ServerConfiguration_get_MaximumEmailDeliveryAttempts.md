# Microsoft.Crm.Asynchronous.ServerConfiguration::get_MaximumEmailDeliveryAttempts

- ea: `0xc570`
- end: `0xc590`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_MaximumEmailDeliveryAttempts`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc570`
- `0xc960`

## string_xrefs

- `0xc575`: `ECMaximumEmailDeliveryAttempts`

## pseudocode

```c

```

## disassembly

```asm
0xc570  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xc575  ldstr    aEcmaximumemail// "ECMaximumEmailDeliveryAttempts"
0xc57a  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xc57f  dup
0xc580  brtrue.s loc_C58A
0xc582  pop
0xc583  ldc.i4.s 0xF
0xc585  box      [mscorlib]System.Int32
0xc58a  unbox.any [mscorlib]System.Int32
0xc58f  ret
```
