# Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::TransformXmlForAssembly

- ea: `0x5500`
- end: `0x551c`
- name: `Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::TransformXmlForAssembly`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5370`

## string_xrefs

- `0x5501`: `rawAuthXml`

## pseudocode

```c

```

## disassembly

```asm
0x5500  ldarg.0
0x5501  ldstr    aRawauthxml// "rawAuthXml"
0x5506  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x550b  ldarg.0
0x550c  ldstr    aMicrosoftCrmVe// "Microsoft.Crm, Version"
0x5511  ldstr    aMicrosoftCrmAu_2// "Microsoft.Crm.Authentication, Version"
0x5516  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x551b  ret
```
