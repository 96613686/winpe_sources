# Microsoft.Crm.Asynchronous.ServerConfiguration::get_TestEmailConfigurationRetryInterval

- ea: `0xc610`
- end: `0xc635`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_TestEmailConfigurationRetryInterval`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc610`
- `0xc960`

## string_xrefs

- `0xc615`: `ECTestEmailConfigurationRetryInterval`

## pseudocode

```c

```

## disassembly

```asm
0xc610  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xc615  ldstr    aEctestemailcon// "ECTestEmailConfigurationRetryInterval"
0xc61a  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xc61f  dup
0xc620  brtrue.s loc_C629
0xc622  pop
0xc623  ldc.i4.5
0xc624  box      [mscorlib]System.Int32
0xc629  unbox.any [mscorlib]System.Int32
0xc62e  conv.r8
0xc62f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0xc634  ret
```
