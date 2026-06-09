# Microsoft.Crm.RibbonConstants::get_CommandAttributes

- ea: `0x22e10`
- end: `0x22e88`
- name: `Microsoft.Crm.RibbonConstants::get_CommandAttributes`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x22e10`

## string_xrefs

- `0x22e20`: `Command`
- `0x22e28`: `QueryCommand`
- `0x22e30`: `CommandPreview`
- `0x22e38`: `CommandRevert`
- `0x22e40`: `CommandMenuOpen`
- `0x22e48`: `CommandMenuClose`
- `0x22e50`: `CommandPreviewRevert`
- `0x22e58`: `PopulateQueryCommand`
- `0x22e60`: `MenuCommand`
- `0x22e69`: `TabSwitchCommand`
- `0x22e72`: `RootEventCommand`

## pseudocode

```c

```

## disassembly

```asm
0x22e10  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.RibbonConstants::_commandAttributes
0x22e15  brtrue.s loc_22E82
0x22e17  ldc.i4.s 0xB
0x22e19  newarr   [mscorlib]System.String
0x22e1e  dup
0x22e1f  ldc.i4.0
0x22e20  ldstr    aCommand// "Command"
0x22e25  stelem.ref
0x22e26  dup
0x22e27  ldc.i4.1
0x22e28  ldstr    aQuerycommand// "QueryCommand"
0x22e2d  stelem.ref
0x22e2e  dup
0x22e2f  ldc.i4.2
0x22e30  ldstr    aCommandpreview// "CommandPreview"
0x22e35  stelem.ref
0x22e36  dup
0x22e37  ldc.i4.3
0x22e38  ldstr    aCommandrevert// "CommandRevert"
0x22e3d  stelem.ref
0x22e3e  dup
0x22e3f  ldc.i4.4
0x22e40  ldstr    aCommandmenuope// "CommandMenuOpen"
0x22e45  stelem.ref
0x22e46  dup
0x22e47  ldc.i4.5
0x22e48  ldstr    aCommandmenuclo// "CommandMenuClose"
0x22e4d  stelem.ref
0x22e4e  dup
0x22e4f  ldc.i4.6
0x22e50  ldstr    aCommandpreview_0// "CommandPreviewRevert"
0x22e55  stelem.ref
0x22e56  dup
0x22e57  ldc.i4.7
0x22e58  ldstr    aPopulatequeryc// "PopulateQueryCommand"
0x22e5d  stelem.ref
0x22e5e  dup
0x22e5f  ldc.i4.8
0x22e60  ldstr    aMenucommand// "MenuCommand"
0x22e65  stelem.ref
0x22e66  dup
0x22e67  ldc.i4.s 9
0x22e69  ldstr    aTabswitchcomma// "TabSwitchCommand"
0x22e6e  stelem.ref
0x22e6f  dup
0x22e70  ldc.i4.s 0xA
0x22e72  ldstr    aRooteventcomma// "RootEventCommand"
0x22e77  stelem.ref
0x22e78  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x22e7d  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.RibbonConstants::_commandAttributes
0x22e82  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.RibbonConstants::_commandAttributes
0x22e87  ret
```
