# Microsoft.Crm.Asynchronous.ServerConfiguration::get_MaximumIncomingEmailSizeInBytes

- ea: `0xc520`
- end: `0xc543`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_MaximumIncomingEmailSizeInBytes`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc520`
- `0xc960`

## string_xrefs

- `0xc525`: `ECIncomingEmailMaximumSizeLimit`

## pseudocode

```c

```

## disassembly

```asm
0xc520  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xc525  ldstr    aEcincomingemai// "ECIncomingEmailMaximumSizeLimit"
0xc52a  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xc52f  dup
0xc530  brtrue.s loc_C53D
0xc532  pop
0xc533  ldc.i4   0x2FAF080
0xc538  box      [mscorlib]System.Int32
0xc53d  unbox.any [mscorlib]System.Int32
0xc542  ret
```
