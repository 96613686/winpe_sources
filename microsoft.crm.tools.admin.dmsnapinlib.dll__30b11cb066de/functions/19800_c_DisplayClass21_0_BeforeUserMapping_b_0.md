# <>c__DisplayClass21_0::<BeforeUserMapping>b__0

- ea: `0x19800`
- end: `0x19837`
- name: `<>c__DisplayClass21_0::<BeforeUserMapping>b__0`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x1982c`: `MappingConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x19800  ldarg.0
0x19801  ldfld    class Microsoft.Crm.Tools.Admin.MappingFileGenerator <>c__DisplayClass21_0::<>4__this
0x19806  ldarg.0
0x19807  ldfld    class Microsoft.Crm.Tools.Admin.MappingFileGenerator <>c__DisplayClass21_0::<>4__this
0x1980c  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Tools.Admin.MappingFileGenerator::_userMap
0x19811  ldarg.0
0x19812  ldfld    class [System.Xml]System.Xml.XmlWriterSettings <>c__DisplayClass21_0::writerSettings
0x19817  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x1981c  stfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Tools.Admin.MappingFileGenerator::_xmlwriter
0x19821  ldarg.0
0x19822  ldfld    class Microsoft.Crm.Tools.Admin.MappingFileGenerator <>c__DisplayClass21_0::<>4__this
0x19827  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Tools.Admin.MappingFileGenerator::_xmlwriter
0x1982c  ldstr    aMappingconfigu_1// "MappingConfiguration"
0x19831  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x19836  ret
```
