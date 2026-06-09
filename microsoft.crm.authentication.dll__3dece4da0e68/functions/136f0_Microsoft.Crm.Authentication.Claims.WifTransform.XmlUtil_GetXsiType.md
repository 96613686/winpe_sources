# Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::GetXsiType

- ea: `0x136f0`
- end: `0x1371a`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::GetXsiType`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x137f0`

## callees

- `0x136f0`
- `0x13790`

## string_xrefs

- `0x136f6`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0x136f0  ldarg.0
0x136f1  ldstr    aType_0// "type"
0x136f6  ldstr    aHttpWwwW3Org20_3// "http://www.w3.org/2001/XMLSchema-instan"...
0x136fb  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string, string)
0x13700  stloc.0
0x13701  ldarg.0
0x13702  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x13707  pop
0x13708  ldloc.0
0x13709  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1370e  brfalse.s loc_13712
0x13710  ldnull
0x13711  ret
0x13712  ldarg.0
0x13713  ldloc.0
0x13714  call     class [System.Xml]System.Xml.XmlQualifiedName Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::ResolveQName(class [System.Xml]System.Xml.XmlReader reader, string qstring)
0x13719  ret
```
