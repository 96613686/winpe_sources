# Microsoft.Crm.Application.Components.UI.CrmUIControlBase::.ctor

- ea: `0x23ad0`
- end: `0x23ae5`
- name: `Microsoft.Crm.Application.Components.UI.CrmUIControlBase::.ctor`
- size: `21`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa930`
- `0xb890`
- `0xbec0`
- `0xee80`
- `0x11a30`
- `0x24040`
- `0x25150`
- `0x27560`

## callees

- `0x23f00`

## pseudocode

```c

```

## disassembly

```asm
0x23ad0  ldarg.0
0x23ad1  ldc.i4.1
0x23ad2  stfld    bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::UseParentEventManager
0x23ad7  ldarg.0
0x23ad8  call     instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::.ctor()
0x23add  ldarg.0
0x23ade  ldc.i4.1
0x23adf  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool value)
0x23ae4  ret
```
