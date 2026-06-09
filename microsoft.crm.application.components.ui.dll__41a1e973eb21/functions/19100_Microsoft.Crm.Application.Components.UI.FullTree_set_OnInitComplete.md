# Microsoft.Crm.Application.Components.UI.FullTree::set_OnInitComplete

- ea: `0x19100`
- end: `0x19112`
- name: `Microsoft.Crm.Application.Components.UI.FullTree::set_OnInitComplete`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x19106`: `initCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x19100  ldarg.0
0x19101  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.UI.FullTree::_customEvents
0x19106  ldstr    aInitcompleted// "initCompleted"
0x1910b  ldarg.1
0x1910c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x19111  ret
```
