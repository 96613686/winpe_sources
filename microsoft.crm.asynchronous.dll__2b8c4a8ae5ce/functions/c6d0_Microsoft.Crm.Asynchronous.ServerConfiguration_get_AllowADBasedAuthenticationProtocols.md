# Microsoft.Crm.Asynchronous.ServerConfiguration::get_AllowADBasedAuthenticationProtocols

- ea: `0xc6d0`
- end: `0xc6fe`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_AllowADBasedAuthenticationProtocols`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc6d0`
- `0xc960`

## string_xrefs

- `0xc6d5`: `ECAllowADBasedAuthenticationProtocols`

## pseudocode

```c

```

## disassembly

```asm
0xc6d0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xc6d5  ldstr    aEcallowadbased// "ECAllowADBasedAuthenticationProtocols"
0xc6da  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xc6df  dup
0xc6e0  brtrue.s loc_C6F8
0xc6e2  pop
0xc6e3  ldc.i4.2
0xc6e4  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xc6e9  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xc6ee  ceq
0xc6f0  ldc.i4.0
0xc6f1  ceq
0xc6f3  box      [mscorlib]System.Boolean
0xc6f8  unbox.any [mscorlib]System.Boolean
0xc6fd  ret
```
