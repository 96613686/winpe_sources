# Microsoft.Crm.Application.Components.UI.FullTree::get_OnInitComplete

- ea: `0x190e0`
- end: `0x190f6`
- name: `Microsoft.Crm.Application.Components.UI.FullTree::get_OnInitComplete`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x190e6`: `initCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x190e0  ldarg.0
0x190e1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.UI.FullTree::_customEvents
0x190e6  ldstr    aInitcompleted// "initCompleted"
0x190eb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x190f0  castclass [mscorlib]System.String
0x190f5  ret
```
