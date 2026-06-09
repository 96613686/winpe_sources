# <>c__DisplayClass36_0::<UpdateChildReportName>b__0

- ea: `0x87f0`
- end: `0x8812`
- name: `<>c__DisplayClass36_0::<UpdateChildReportName>b__0`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x87f0`

## pseudocode

```c

```

## disassembly

```asm
0x87f0  ldarg.1
0x87f1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x87f6  ldarg.0
0x87f7  ldfld    string <>c__DisplayClass36_0::originalName
0x87fc  ldc.i4.5
0x87fd  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x8802  brfalse.s loc_8810
0x8804  ldarg.1
0x8805  ldarg.0
0x8806  ldfld    string <>c__DisplayClass36_0::newName
0x880b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x8810  ldc.i4.1
0x8811  ret
```
