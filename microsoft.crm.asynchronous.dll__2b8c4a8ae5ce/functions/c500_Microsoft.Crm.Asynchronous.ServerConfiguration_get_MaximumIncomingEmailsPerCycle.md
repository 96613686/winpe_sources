# Microsoft.Crm.Asynchronous.ServerConfiguration::get_MaximumIncomingEmailsPerCycle

- ea: `0xc500`
- end: `0xc520`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_MaximumIncomingEmailsPerCycle`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc500`
- `0xc960`

## string_xrefs

- `0xc505`: `ECIncomingMaximumEmailsPerCycle`

## pseudocode

```c

```

## disassembly

```asm
0xc500  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xc505  ldstr    aEcincomingmaxi// "ECIncomingMaximumEmailsPerCycle"
0xc50a  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xc50f  dup
0xc510  brtrue.s loc_C51A
0xc512  pop
0xc513  ldc.i4.s 0x64
0xc515  box      [mscorlib]System.Int32
0xc51a  unbox.any [mscorlib]System.Int32
0xc51f  ret
```
