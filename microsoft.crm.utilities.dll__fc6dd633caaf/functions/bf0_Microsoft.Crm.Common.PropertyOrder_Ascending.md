# Microsoft.Crm.Common.PropertyOrder::Ascending

- ea: `0xbf0`
- end: `0xc04`
- name: `Microsoft.Crm.Common.PropertyOrder::Ascending`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xbe0`
- `0xc40`
- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0xbf0  newobj   instance void Microsoft.Crm.Common.PropertyOrder::.ctor()
0xbf5  dup
0xbf6  ldc.i4.1
0xbf7  callvirt instance void Microsoft.Crm.Common.PropertyOrder::set_AscendingOrder(bool value)
0xbfc  dup
0xbfd  ldarg.0
0xbfe  callvirt instance void Microsoft.Crm.Common.PropertyOrder::set_Property(string value)
0xc03  ret
```
