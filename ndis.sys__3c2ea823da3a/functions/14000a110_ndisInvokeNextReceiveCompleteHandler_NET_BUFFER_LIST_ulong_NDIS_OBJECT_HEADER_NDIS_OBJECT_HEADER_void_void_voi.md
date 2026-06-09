# ndisInvokeNextReceiveCompleteHandler(_NET_BUFFER_LIST *,ulong,_NDIS_OBJECT_HEADER *,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong))

- ea: `0x14000a110`
- end: `0x14000a595`
- name: `?ndisInvokeNextReceiveCompleteHandler@@YAXPEAU_NET_BUFFER_LIST@@KPEAU_NDIS_OBJECT_HEADER@@1PEAXP6AX20K@Z@Z`
- size: `1157`
- prototype: `void __usercall(struct _NET_BUFFER_LIST *@<rcx>, unsigned int@<edx>, struct _NDIS_OBJECT_HEADER *@<r8>, struct _NDIS_OBJECT_HEADER *@<r9>, void *, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int))`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f060`
- `0x14002c8d0`
- `0x140095cb0`

## callees

- `0x14000a110`
- `0x14000a5a0`
- `0x14000de20`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000a145`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a145`
- `ntoskrnl!IoGetStackLimits` at `0x14000a1bd`
- `ntoskrnl!IoGetStackLimits` at `0x14000a1bd`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000a361`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000a361`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a3d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a3d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a388`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a388`

## pseudocode

```c

```
