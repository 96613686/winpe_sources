# Microsoft.Crm.Common.PropertyOrder::Descending

- ea: `0xc10`
- end: `0xc24`
- name: `Microsoft.Crm.Common.PropertyOrder::Descending`
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
0xc10  newobj   instance void Microsoft.Crm.Common.PropertyOrder::.ctor()
0xc15  dup
0xc16  ldc.i4.0
0xc17  callvirt instance void Microsoft.Crm.Common.PropertyOrder::set_AscendingOrder(bool value)
0xc1c  dup
0xc1d  ldarg.0
0xc1e  callvirt instance void Microsoft.Crm.Common.PropertyOrder::set_Property(string value)
0xc23  ret
```
