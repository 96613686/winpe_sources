# Microsoft.Crm.Authentication.Claims.ClaimsUtility::LoadValues

- ea: `0xbf90`
- end: `0xc050`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsUtility::LoadValues`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbeb0`

## callees

- `0xbf60`
- `0xbf90`

## string_xrefs

- `0xbff7`: `configuration`

## pseudocode

```c

```

## disassembly

```asm
0xbf90  ldarg.1
0xbf91  brtrue.s loc_BF9A
0xbf93  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0xbf98  starg.s  1
0xbf9a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xbf9f  stloc.0
0xbfa0  ldarg.0
0xbfa1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbfa6  brtrue   loc_C04E
0xbfab  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0xbfb0  stloc.1
0xbfb1  ldloc.1
0xbfb2  ldc.i4.1
0xbfb3  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_IgnoreProcessingInstructions(bool)
0xbfb8  ldloc.1
0xbfb9  ldc.i4.1
0xbfba  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_IgnoreWhitespace(bool)
0xbfbf  ldloc.1
0xbfc0  ldc.i4.0
0xbfc1  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_CheckCharacters(bool)
0xbfc6  ldloc.1
0xbfc7  ldc.i4.1
0xbfc8  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_IgnoreComments(bool)
0xbfcd  ldloc.1
0xbfce  ldc.i4.1
0xbfcf  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_CloseInput(bool)
0xbfd4  ldloc.1
0xbfd5  ldc.i4.0
0xbfd6  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_ValidationType(valuetype [System.Xml]System.Xml.ValidationType)
0xbfdb  ldarg.0
0xbfdc  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0xbfe1  ldloc.1
0xbfe2  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0xbfe7  stloc.2
0xbfe8  br.s     loc_C03A
0xbfea  ldloc.2
0xbfeb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xbff0  pop
0xbff1  ldloc.2
0xbff2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xbff7  ldstr    aConfiguration// "configuration"
0xbffc  ldc.i4.5
0xbffd  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xc002  brtrue.s loc_C03A
0xc004  ldloc.2
0xc005  ldstr    aValue// "value"
0xc00a  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xc00f  stloc.3
0xc010  ldloc.3
0xc011  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc016  brtrue.s loc_C03A
0xc018  ldarg.1
0xc019  ldloc.3
0xc01a  callvirt instance bool [System]System.Collections.Specialized.StringCollection::Contains(string)
0xc01f  brtrue.s loc_C03A
0xc021  call     class [System]System.Collections.Specialized.StringCollection Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_LocationsToAuthWithoutRedirect()
0xc026  ldloc.3
0xc027  callvirt instance bool [System]System.Collections.Specialized.StringCollection::Contains(string)
0xc02c  brtrue.s loc_C03A
0xc02e  ldloc.0
0xc02f  ldloc.3
0xc030  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xc035  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc03a  ldloc.2
0xc03b  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xc040  brtrue.s loc_BFEA
0xc042  leave.s  loc_C04E
0xc044  ldloc.2
0xc045  brfalse.s loc_C04D
0xc047  ldloc.2
0xc048  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc04d  endfinally
0xc04e  ldloc.0
0xc04f  ret
```
