# Microsoft.Crm.Setup.Common.UI.PathSelectControl::RaisePathChanged

- ea: `0xa540`
- end: `0xa556`
- name: `Microsoft.Crm.Setup.Common.UI.PathSelectControl::RaisePathChanged`
- size: `22`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa480`
- `0xae30`
- `0xaeb0`
- `0xaed0`
- `0xb060`

## callees

- `0xa540`
- `0x17a90`

## pseudocode

```c

```

## disassembly

```asm
0xa540  ldarg.0
0xa541  ldfld    class PathChangedEventHandler Microsoft.Crm.Setup.Common.UI.PathSelectControl::PathChanged
0xa546  brfalse.s loc_A555
0xa548  ldarg.0
0xa549  ldfld    class PathChangedEventHandler Microsoft.Crm.Setup.Common.UI.PathSelectControl::PathChanged
0xa54e  ldarg.1
0xa54f  ldarg.2
0xa550  callvirt instance void PathChangedEventHandler::Invoke(object sender, class [mscorlib]System.EventArgs e)
0xa555  ret
```
