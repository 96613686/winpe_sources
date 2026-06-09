# Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadPrivileges_0

- ea: `0x5cd50`
- end: `0x5cd94`
- name: `Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadPrivileges_0`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5c6f0`

## callees

- `0x5cf20`
- `0xac510`
- `0xac830`

## string_xrefs

- `0x5cd5e`: `Privilege`
- `0x5cd7c`: `/metadata/privileges/privilege`

## pseudocode

```c

```

## disassembly

```asm
0x5cd50  newobj   instance void <>c__DisplayClass85_0::.ctor()
0x5cd55  stloc.0
0x5cd56  ldloc.0
0x5cd57  ldarg.1
0x5cd58  stfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass85_0::container
0x5cd5d  ldarg.0
0x5cd5e  ldstr    aPrivilege// "Privilege"
0x5cd63  ldloc.0
0x5cd64  ldfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass85_0::container
0x5cd69  ldarg.2
0x5cd6a  ldc.i4.1
0x5cd6b  newarr   [System.Xml]System.Xml.XPath.XPathNavigator
0x5cd70  dup
0x5cd71  ldc.i4.0
0x5cd72  ldarg.3
0x5cd73  stelem.ref
0x5cd74  ldc.i4.1
0x5cd75  newarr   [mscorlib]System.String
0x5cd7a  dup
0x5cd7b  ldc.i4.0
0x5cd7c  ldstr    aMetadataPrivil// "/metadata/privileges/privilege"
0x5cd81  stelem.ref
0x5cd82  ldloc.0
0x5cd83  ldftn    instance void <>c__DisplayClass85_0::<LoadPrivileges>b__0(class Microsoft.Crm.Metadata.IFillableMetadataDescription description, class [System.Xml]System.Xml.XmlNode node, bool newIterator)
0x5cd89  newobj   instance void LoadDescriptionFromXmlDelegate::.ctor(object object, native int method)
0x5cd8e  call     instance void Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadDescriptionsFromXml(string name, class Microsoft.Crm.Metadata.IMetadataContainer container, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml]System.Xml.XPath.XPathNavigator> navs, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> paths, class LoadDescriptionFromXmlDelegate LoadDescriptionFromXmlDelegate)
0x5cd93  ret
```
