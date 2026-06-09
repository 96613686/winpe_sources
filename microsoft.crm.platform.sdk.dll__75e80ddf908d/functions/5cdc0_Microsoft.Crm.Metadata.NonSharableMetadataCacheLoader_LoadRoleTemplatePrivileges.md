# Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadRoleTemplatePrivileges

- ea: `0x5cdc0`
- end: `0x5cdd4`
- name: `Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadRoleTemplatePrivileges`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5c6f0`

## callees

- `0x5cec0`

## string_xrefs

- `0x5cdc1`: `RoleTemplatePrivilege`
- `0x5cdc9`: `/metadata/roletemplateprivileges/roletemplateprivilege`

## pseudocode

```c

```

## disassembly

```asm
0x5cdc0  ldarg.0
0x5cdc1  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x5cdc6  ldarg.1
0x5cdc7  ldarg.2
0x5cdc8  ldarg.3
0x5cdc9  ldstr    aMetadataRolete// "/metadata/roletemplateprivileges/rolete"...
0x5cdce  call     instance void Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadDescriptionsFromXml(string name, class Microsoft.Crm.Metadata.IMetadataContainer container, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter, class [System.Xml]System.Xml.XPath.XPathNavigator nav, string path)
0x5cdd3  ret
```
