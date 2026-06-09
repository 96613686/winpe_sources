# Microsoft.Crm.Controls.CommandBarMenuXmlGenerator::Serialize

- ea: `0x12480`
- end: `0x12509`
- name: `Microsoft.Crm.Controls.CommandBarMenuXmlGenerator::Serialize`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x11c50`
- `0x123b0`

## callees

- `0xecf0`
- `0xed80`
- `0xeff0`
- `0x12480`
- `0x126c0`
- `0x126e0`
- `0x12700`
- `0x12780`

## pseudocode

```c

```

## disassembly

```asm
0x12480  ldc.i4.0
0x12481  stloc.0
0x12482  ldc.i4.0
0x12483  stloc.1
0x12484  ldarg.1
0x12485  callvirt instance class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1248a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1248f  stloc.2
0x12490  br.s     loc_124EA
0x12492  ldloc.2
0x12493  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x12498  castclass Microsoft.Crm.Controls.ICrmCommandBarControl
0x1249d  stloc.3
0x1249e  ldloc.3
0x1249f  callvirt instance valuetype Microsoft.Crm.Controls.CommandBarAlignment Microsoft.Crm.Controls.ICrmCommandBarControl::get_Alignment()
0x124a4  ldarg.1
0x124a5  callvirt instance valuetype Microsoft.Crm.Controls.CommandBarAlignment Microsoft.Crm.Controls.CommandBar::get_Alignment()
0x124aa  beq.s    loc_124B4
0x124ac  ldloc.3
0x124ad  callvirt instance valuetype Microsoft.Crm.Controls.CommandBarAlignment Microsoft.Crm.Controls.ICrmCommandBarControl::get_Alignment()
0x124b2  brtrue.s loc_124EA
0x124b4  ldloc.3
0x124b5  callvirt instance bool Microsoft.Crm.Controls.ICrmCommandBarControl::get_Visible()
0x124ba  brfalse.s loc_124E0
0x124bc  ldloc.3
0x124bd  callvirt instance bool Microsoft.Crm.Controls.ICrmCommandBarControl::get_StartGroup()
0x124c2  ldloc.0
0x124c3  or
0x124c4  brfalse.s loc_124D3
0x124c6  ldloc.1
0x124c7  ldc.i4.0
0x124c8  ble.s    loc_124D3
0x124ca  ldc.i4.0
0x124cb  stloc.0
0x124cc  ldarg.1
0x124cd  ldarg.0
0x124ce  callvirt instance void Microsoft.Crm.Controls.CommandBar::RenderSpacer(class [System.Xml]System.Xml.XmlWriter writer)
0x124d3  ldloc.3
0x124d4  ldarg.0
0x124d5  callvirt instance void Microsoft.Crm.Controls.ICrmCommandBarControl::SerializeToXml(class [System.Xml]System.Xml.XmlWriter writer)
0x124da  ldloc.1
0x124db  ldc.i4.1
0x124dc  add
0x124dd  stloc.1
0x124de  br.s     loc_124EA
0x124e0  ldloc.3
0x124e1  callvirt instance bool Microsoft.Crm.Controls.ICrmCommandBarControl::get_StartGroup()
0x124e6  brfalse.s loc_124EA
0x124e8  ldc.i4.1
0x124e9  stloc.0
0x124ea  ldloc.2
0x124eb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x124f0  brtrue.s loc_12492
0x124f2  leave.s  loc_12508
0x124f4  ldloc.2
0x124f5  isinst   [mscorlib]System.IDisposable
0x124fa  stloc.s  4
0x124fc  ldloc.s  4
0x124fe  brfalse.s loc_12507
0x12500  ldloc.s  4
0x12502  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12507  endfinally
0x12508  ret
```
