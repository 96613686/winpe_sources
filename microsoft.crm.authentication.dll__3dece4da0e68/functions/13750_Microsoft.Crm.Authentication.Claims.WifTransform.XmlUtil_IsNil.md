# Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::IsNil

- ea: `0x13750`
- end: `0x13772`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::IsNil`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x13750`

## string_xrefs

- `0x13756`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0x13750  ldarg.0
0x13751  ldstr    aNil// "nil"
0x13756  ldstr    aHttpWwwW3Org20_3// "http://www.w3.org/2001/XMLSchema-instan"...
0x1375b  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string, string)
0x13760  stloc.0
0x13761  ldloc.0
0x13762  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13767  brtrue.s loc_13770
0x13769  ldloc.0
0x1376a  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x1376f  ret
0x13770  ldc.i4.0
0x13771  ret
```
