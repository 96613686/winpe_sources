# Microsoft.Crm.Application.Components.UI.LookupItem::.ctor_2

- ea: `0x1eab0`
- end: `0x1eac1`
- name: `Microsoft.Crm.Application.Components.UI.LookupItem::.ctor_2`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f240`

## callees

- `0x1ea30`

## string_xrefs

- `0x1eab4`: `openlui(new Sys.UI.DomEvent(event))`

## pseudocode

```c

```

## disassembly

```asm
0x1eab0  ldarg.0
0x1eab1  ldarg.1
0x1eab2  ldarg.2
0x1eab3  ldarg.3
0x1eab4  ldstr    aOpenluiNewSysU// "openlui(new Sys.UI.DomEvent(event))"
0x1eab9  ldnull
0x1eaba  ldc.i4.0
0x1eabb  call     instance void Microsoft.Crm.Application.Components.UI.LookupItem::.ctor(string name, string data, string style, string callback, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri icon, bool useTouchSkin)
0x1eac0  ret
```
