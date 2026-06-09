# Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::ValidateXsiType_0

- ea: `0x137f0`
- end: `0x1388f`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::ValidateXsiType_0`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x137e0`

## callees

- `0x136f0`
- `0x137f0`

## string_xrefs

- `0x1385e`: `An element of an unexpected type was encountered. To support extended types in SAML2 assertions, extend Saml2SecurityTokenHandler.\nExpected type name: '{0}'\nExpected type namespace: '{1}'\nEncountered type name: '{2}'\nEncountered type namespace: '{3}'`

## pseudocode

```c

```

## disassembly

```asm
0x137f0  ldarg.0
0x137f1  call     class [System.Xml]System.Xml.XmlQualifiedName Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::GetXsiType(class [System.Xml]System.Xml.XmlReader reader)
0x137f6  stloc.0
0x137f7  ldnull
0x137f8  ldloc.0
0x137f9  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x137fe  brfalse.s loc_13833
0x13800  ldarg.3
0x13801  brfalse  loc_1388E
0x13806  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1380b  ldstr    aAnAbstractElem// "An abstract element was encountered whi"...
0x13810  ldc.i4.2
0x13811  newarr   [mscorlib]System.Object
0x13816  dup
0x13817  ldc.i4.0
0x13818  ldarg.0
0x13819  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1381e  stelem.ref
0x1381f  dup
0x13820  ldc.i4.1
0x13821  ldarg.0
0x13822  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x13827  stelem.ref
0x13828  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1382d  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x13832  throw
0x13833  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_Ordinal()
0x13838  ldarg.2
0x13839  ldloc.0
0x1383a  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x1383f  callvirt instance bool [mscorlib]System.StringComparer::Equals(string, string)
0x13844  brfalse.s loc_13859
0x13846  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_Ordinal()
0x1384b  ldarg.1
0x1384c  ldloc.0
0x1384d  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x13852  callvirt instance bool [mscorlib]System.StringComparer::Equals(string, string)
0x13857  brtrue.s loc_1388E
0x13859  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1385e  ldstr    aAnElementOfAnU// "An element of an unexpected type was en"...
0x13863  ldc.i4.4
0x13864  newarr   [mscorlib]System.Object
0x13869  dup
0x1386a  ldc.i4.0
0x1386b  ldarg.1
0x1386c  stelem.ref
0x1386d  dup
0x1386e  ldc.i4.1
0x1386f  ldarg.2
0x13870  stelem.ref
0x13871  dup
0x13872  ldc.i4.2
0x13873  ldloc.0
0x13874  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x13879  stelem.ref
0x1387a  dup
0x1387b  ldc.i4.3
0x1387c  ldloc.0
0x1387d  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x13882  stelem.ref
0x13883  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13888  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1388d  throw
0x1388e  ret
```
