# FetchXml::RetrieveMultiple_0

- ea: `0x15f00`
- end: `0x15f11`
- name: `FetchXml::RetrieveMultiple_0`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x15260`

## callees

- `0x15ed0`
- `0x15f20`

## pseudocode

```c

```

## disassembly

```asm
0x15f00  ldarg.0
0x15f01  ldarg.1
0x15f02  ldarg.2
0x15f03  ldarg.3
0x15f04  ldarg.s  4
0x15f06  call     string FetchXml::CreateXml(string xml, string cookie, int32 page, int32 maxPageSize)
0x15f0b  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection FetchXml::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService service, string fetchXml)
0x15f10  ret
```
