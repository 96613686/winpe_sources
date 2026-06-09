# ndisInvokeNextReceiveCompleteHandler(_NET_BUFFER_LIST *,ulong,_NDIS_OBJECT_HEADER *,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong))

- ea: `0x140023470`
- end: `0x1400238f5`
- name: `?ndisInvokeNextReceiveCompleteHandler@@YAXPEAU_NET_BUFFER_LIST@@KPEAU_NDIS_OBJECT_HEADER@@1PEAXP6AX20K@Z@Z`
- size: `1157`
- prototype: `void __usercall(struct _NET_BUFFER_LIST *@<rcx>, unsigned int@<edx>, struct _NDIS_OBJECT_HEADER *@<r8>, struct _NDIS_OBJECT_HEADER *@<r9>, void *, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int))`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140026c50`
- `0x1400843a0`
- `0x14009af30`

## callees

- `0x140023470`
- `0x140023900`
- `0x140025d30`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400234a5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400234a5`
- `ntoskrnl!IoGetStackLimits` at `0x14002351d`
- `ntoskrnl!IoGetStackLimits` at `0x14002351d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400236c1`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400236c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140023737`
- `ntoskrnl!KeReleaseSpinLock` at `0x140023737`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400236e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400236e8`

## pseudocode

```c

```
