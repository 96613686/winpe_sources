# Microsoft.Crm.Application.Components.UI.LookupItem::.ctor_1

- ea: `0x1ea90`
- end: `0x1eaa2`
- name: `Microsoft.Crm.Application.Components.UI.LookupItem::.ctor_1`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ead0`
- `0x1eae0`

## callees

- `0x1ea30`

## string_xrefs

- `0x1ea94`: `openlui(new Sys.UI.DomEvent(event))`

## pseudocode

```c

```

## disassembly

```asm
0x1ea90  ldarg.0
0x1ea91  ldarg.1
0x1ea92  ldarg.2
0x1ea93  ldarg.3
0x1ea94  ldstr    aOpenluiNewSysU// "openlui(new Sys.UI.DomEvent(event))"
0x1ea99  ldnull
0x1ea9a  ldarg.s  4
0x1ea9c  call     instance void Microsoft.Crm.Application.Components.UI.LookupItem::.ctor(string name, string data, string style, string callback, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri icon, bool useTouchSkin)
0x1eaa1  ret
```
