# Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::ThrowIfCannotReadToDescendantInXml

- ea: `0xc380`
- end: `0xc39b`
- name: `Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::ThrowIfCannotReadToDescendantInXml`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc230`

## callees

- `0xc380`

## string_xrefs

- `0xc389`: `Invalid XML format in the file: `

## pseudocode

```c

```

## disassembly

```asm
0xc380  ldarg.0
0xc381  ldarg.1
0xc382  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadToDescendant(string)
0xc387  brtrue.s loc_C39A
0xc389  ldstr    aInvalidXmlForm// "Invalid XML format in the file: "
0xc38e  ldarg.2
0xc38f  call     string [mscorlib]System.String::Concat(string, string)
0xc394  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xc399  throw
0xc39a  ret
```
