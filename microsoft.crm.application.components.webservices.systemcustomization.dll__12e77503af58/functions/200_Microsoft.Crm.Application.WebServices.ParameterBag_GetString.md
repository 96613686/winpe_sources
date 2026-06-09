# Microsoft.Crm.Application.WebServices.ParameterBag::GetString

- ea: `0x200`
- end: `0x214`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetString`
- size: `20`
- prototype: ``
- caller_count: `33`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x220`
- `0x240`
- `0x290`
- `0x2c0`
- `0x310`
- `0x340`
- `0x430`
- `0xbe0`
- `0x1000`
- `0x1400`
- `0x1740`
- `0x17d0`
- `0x1a10`
- `0x1e90`
- `0x2a00`
- `0x2ab0`
- `0x2d80`
- `0x2dc0`
- `0x3450`
- `0x3920`
- `0x39a0`
- `0x39c0`
- `0x3d20`
- `0x3d60`
- `0x4020`
- `0x9850`
- `0x9a10`
- `0x9bd0`
- `0x9e50`
- `0xa0c0`
- `0xa300`
- `0xa7f0`
- `0xaac0`

## callees

- `0x70`
- `0x200`

## pseudocode

```c

```

## disassembly

```asm
0x200  ldarg.0
0x201  ldarg.1
0x202  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.ParameterBag::GetNode(string name)
0x207  stloc.0
0x208  ldloc.0
0x209  brtrue.s loc_20D
0x20b  ldarg.2
0x20c  ret
0x20d  ldloc.0
0x20e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x213  ret
```
