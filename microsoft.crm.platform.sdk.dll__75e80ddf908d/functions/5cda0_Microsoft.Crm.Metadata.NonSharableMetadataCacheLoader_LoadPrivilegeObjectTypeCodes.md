# Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadPrivilegeObjectTypeCodes

- ea: `0x5cda0`
- end: `0x5cdb4`
- name: `Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadPrivilegeObjectTypeCodes`
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

- `0x5cda1`: `PrivilegeObjectTypeCode`
- `0x5cda9`: `/metadata/privilegeobjecttypecodeslist/privilegeobjecttypecodes`

## pseudocode

```c

```

## disassembly

```asm
0x5cda0  ldarg.0
0x5cda1  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x5cda6  ldarg.1
0x5cda7  ldarg.2
0x5cda8  ldarg.3
0x5cda9  ldstr    aMetadataPrivil_0// "/metadata/privilegeobjecttypecodeslist/"...
0x5cdae  call     instance void Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadDescriptionsFromXml(string name, class Microsoft.Crm.Metadata.IMetadataContainer container, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter, class [System.Xml]System.Xml.XPath.XPathNavigator nav, string path)
0x5cdb3  ret
```
