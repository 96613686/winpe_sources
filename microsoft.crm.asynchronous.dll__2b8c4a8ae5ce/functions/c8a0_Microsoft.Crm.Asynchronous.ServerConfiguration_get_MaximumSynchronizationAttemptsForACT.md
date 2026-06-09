# Microsoft.Crm.Asynchronous.ServerConfiguration::get_MaximumSynchronizationAttemptsForACT

- ea: `0xc8a0`
- end: `0xc8bf`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_MaximumSynchronizationAttemptsForACT`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc8a0`
- `0xc960`

## string_xrefs

- `0xc8a5`: `MaximumSynchronizationAttemptsForACT`

## pseudocode

```c

```

## disassembly

```asm
0xc8a0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xc8a5  ldstr    aMaximumsynchro// "MaximumSynchronizationAttemptsForACT"
0xc8aa  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xc8af  dup
0xc8b0  brtrue.s loc_C8B9
0xc8b2  pop
0xc8b3  ldc.i4.5
0xc8b4  box      [mscorlib]System.Int32
0xc8b9  unbox.any [mscorlib]System.Int32
0xc8be  ret
```
