# Microsoft.Crm.Reporting.SRSReport::EnsureChildNodeExists

- ea: `0x1440`
- end: `0x1456`
- name: `Microsoft.Crm.Reporting.SRSReport::EnsureChildNodeExists`
- size: `22`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf60`
- `0x1000`
- `0x15f0`
- `0x2090`
- `0x26f0`
- `0x2a60`

## callees

- `0x1440`
- `0x1460`

## pseudocode

```c

```

## disassembly

```asm
0x1440  ldarg.1
0x1441  ldarg.2
0x1442  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x1447  stloc.0
0x1448  ldloc.0
0x1449  brtrue.s loc_1454
0x144b  ldarg.0
0x144c  ldarg.1
0x144d  ldarg.2
0x144e  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::CreateChildNode(class [System.Xml]System.Xml.XmlNode parentNode, string childNodeName)
0x1453  stloc.0
0x1454  ldloc.0
0x1455  ret
```
