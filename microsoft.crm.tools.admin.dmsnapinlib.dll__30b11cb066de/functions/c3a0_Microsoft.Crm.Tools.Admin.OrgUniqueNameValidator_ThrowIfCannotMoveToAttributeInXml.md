# Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::ThrowIfCannotMoveToAttributeInXml

- ea: `0xc3a0`
- end: `0xc3bb`
- name: `Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::ThrowIfCannotMoveToAttributeInXml`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc230`

## callees

- `0xc3a0`

## string_xrefs

- `0xc3a9`: `Invalid XML format in the file: `

## pseudocode

```c

```

## disassembly

```asm
0xc3a0  ldarg.0
0xc3a1  ldarg.1
0xc3a2  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToAttribute(string)
0xc3a7  brtrue.s loc_C3BA
0xc3a9  ldstr    aInvalidXmlForm// "Invalid XML format in the file: "
0xc3ae  ldarg.2
0xc3af  call     string [mscorlib]System.String::Concat(string, string)
0xc3b4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xc3b9  throw
0xc3ba  ret
```
