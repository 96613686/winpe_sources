# Microsoft.Crm.PrivacyFileBuilder::BuildPrivacyXml

- ea: `0x22bd0`
- end: `0x22bf1`
- name: `Microsoft.Crm.PrivacyFileBuilder::BuildPrivacyXml`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x22bb0`
- `0x22bc0`

## string_xrefs

- `0x22bd0`: `<?xml version="1.0"?>\n			<META xmlns="http://www.w3.org/2002/01/P3Pv1">\n			  <POLICY-REFERENCES>\n				<POLICY-REF about="{0}">\n				  <INCLUDE>/*</INCLUDE>\n				</POLICY-REF>\n			  </POLICY-REFERENCES>\n			</META>`

## pseudocode

```c

```

## disassembly

```asm
0x22bd0  ldstr    aXmlVersion10Me// "<?xml version=\"1.0\"?>\r\n\t\t\t<META "...
0x22bd5  stloc.0
0x22bd6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22bdb  ldloc.0
0x22bdc  ldc.i4.1
0x22bdd  newarr   [mscorlib]System.Object
0x22be2  dup
0x22be3  ldc.i4.0
0x22be4  ldarg.0
0x22be5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x22bea  stelem.ref
0x22beb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22bf0  ret
```
