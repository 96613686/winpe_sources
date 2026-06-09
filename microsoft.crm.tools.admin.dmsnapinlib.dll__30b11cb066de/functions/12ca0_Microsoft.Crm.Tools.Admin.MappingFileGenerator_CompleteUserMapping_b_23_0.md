# Microsoft.Crm.Tools.Admin.MappingFileGenerator::<CompleteUserMapping>b__23_0

- ea: `0x12ca0`
- end: `0x12d7f`
- name: `Microsoft.Crm.Tools.Admin.MappingFileGenerator::<CompleteUserMapping>b__23_0`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12ab0`
- `0x12ad0`
- `0x12ae0`
- `0x12ca0`

## string_xrefs

- `0x12d54`: `GenerateMappingFile running. Generating Xml file with path={0}`

## pseudocode

```c

```

## disassembly

```asm
0x12ca0  ldarg.0
0x12ca1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.Crm.Tools.Admin.MappingFileGenerator::_domains
0x12ca6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Keys()
0x12cab  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, bool>::GetEnumerator()
0x12cb0  stloc.0
0x12cb1  br.s     loc_12CFC
0x12cb3  ldloca.s 0
0x12cb5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, bool>::get_Current()
0x12cba  stloc.1
0x12cbb  ldarg.0
0x12cbc  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Tools.Admin.MappingFileGenerator::_xmlwriter
0x12cc1  ldstr    aDomainmapping// "DomainMapping"
0x12cc6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x12ccb  ldarg.0
0x12ccc  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Tools.Admin.MappingFileGenerator::_xmlwriter
0x12cd1  ldstr    aOld// "old"
0x12cd6  ldloc.1
0x12cd7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x12cdc  ldarg.0
0x12cdd  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Tools.Admin.MappingFileGenerator::_xmlwriter
0x12ce2  ldstr    aNew// "new"
0x12ce7  ldsfld   string [mscorlib]System.String::Empty
0x12cec  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x12cf1  ldarg.0
0x12cf2  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Tools.Admin.MappingFileGenerator::_xmlwriter
0x12cf7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x12cfc  ldloca.s 0
0x12cfe  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, bool>::MoveNext()
0x12d03  brtrue.s loc_12CB3
0x12d05  leave.s  loc_12D15
0x12d07  ldloca.s 0
0x12d09  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, bool>
0x12d0f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12d14  endfinally
0x12d15  ldarg.0
0x12d16  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Tools.Admin.MappingFileGenerator::_xmlwriter
0x12d1b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x12d20  ldarg.0
0x12d21  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Tools.Admin.MappingFileGenerator::_xmlwriter
0x12d26  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x12d2b  ldarg.0
0x12d2c  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Tools.Admin.MappingFileGenerator::_xmlwriter
0x12d31  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x12d36  ldarg.0
0x12d37  ldarg.0
0x12d38  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Tools.Admin.MappingFileGenerator::_userMap
0x12d3d  callvirt instance string [mscorlib]System.Object::ToString()
0x12d42  call     instance void Microsoft.Crm.Tools.Admin.MappingFileGenerator::set_UserMappingString(string value)
0x12d47  ldarg.0
0x12d48  call     instance string Microsoft.Crm.Tools.Admin.MappingFileGenerator::get_FilePath()
0x12d4d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x12d52  brtrue.s loc_12D7E
0x12d54  ldstr    aGeneratemappin_1// "GenerateMappingFile running. Generating"...
0x12d59  ldc.i4.1
0x12d5a  newarr   [mscorlib]System.Object
0x12d5f  dup
0x12d60  ldc.i4.0
0x12d61  ldarg.0
0x12d62  call     instance string Microsoft.Crm.Tools.Admin.MappingFileGenerator::get_FilePath()
0x12d67  stelem.ref
0x12d68  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteFormat(string, object[])
0x12d6d  ldarg.0
0x12d6e  call     instance string Microsoft.Crm.Tools.Admin.MappingFileGenerator::get_FilePath()
0x12d73  ldarg.0
0x12d74  call     instance string Microsoft.Crm.Tools.Admin.MappingFileGenerator::get_UserMappingString()
0x12d79  call     void [mscorlib]System.IO.File::WriteAllText(string, string)
0x12d7e  ret
```
