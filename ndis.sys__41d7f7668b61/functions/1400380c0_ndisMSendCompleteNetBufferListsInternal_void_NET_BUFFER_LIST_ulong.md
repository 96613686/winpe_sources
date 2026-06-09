# ndisMSendCompleteNetBufferListsInternal(void *,_NET_BUFFER_LIST *,ulong)

- ea: `0x1400380c0`
- end: `0x140038c6e`
- name: `?ndisMSendCompleteNetBufferListsInternal@@YAXPEAXPEAU_NET_BUFFER_LIST@@K@Z`
- size: `2990`
- prototype: `void(void *, struct _NET_BUFFER_LIST *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140037f00`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x1400260b0`
- `0x1400380c0`
- `0x140038c80`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140038c5d`
- `ntoskrnl!KeLowerIrql` at `0x140038c5d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140038733`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003878d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140038a39`
- `ntoskrnl!KeGetCurrentIrql` at `0x140038a8d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140038733`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003878d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140038a39`
- `ntoskrnl!KeGetCurrentIrql` at `0x140038a8d`
- `ntoskrnl!KfRaiseIrql` at `0x14003869c`
- `ntoskrnl!KfRaiseIrql` at `0x14003869c`

## pseudocode

```c

```
