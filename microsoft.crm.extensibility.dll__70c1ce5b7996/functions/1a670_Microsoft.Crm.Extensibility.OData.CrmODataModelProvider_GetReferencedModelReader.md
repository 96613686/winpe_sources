# Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::GetReferencedModelReader

- ea: `0x1a670`
- end: `0x1a694`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::GetReferencedModelReader`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1a6a0`

## callees

- `0x1a670`

## string_xrefs

- `0x1a676`: `http://vocabularies.odata.org/OData.Community.Display.V1.xml`

## pseudocode

```c

```

## disassembly

```asm
0x1a670  ldarg.0
0x1a671  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1a676  ldstr    aHttpVocabulari_0// "http://vocabularies.odata.org/OData.Com"...
0x1a67b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a680  brfalse.s loc_1A692
0x1a682  ldsfld   string Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::odataCommunityDisplayEdmx
0x1a687  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x1a68c  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x1a691  ret
0x1a692  ldnull
0x1a693  ret
```
