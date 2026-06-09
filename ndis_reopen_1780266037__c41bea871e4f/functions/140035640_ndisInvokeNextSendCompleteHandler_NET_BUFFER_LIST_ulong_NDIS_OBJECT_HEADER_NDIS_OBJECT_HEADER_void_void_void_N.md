# ndisInvokeNextSendCompleteHandler(_NET_BUFFER_LIST *,ulong,_NDIS_OBJECT_HEADER *,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong))

- ea: `0x140035640`
- end: `0x140035abd`
- name: `?ndisInvokeNextSendCompleteHandler@@YAXPEAU_NET_BUFFER_LIST@@KPEAU_NDIS_OBJECT_HEADER@@1PEAXP6AX20K@Z@Z`
- size: `1149`
- prototype: `void __usercall(struct _NET_BUFFER_LIST *@<rcx>, unsigned int@<edx>, struct _NDIS_OBJECT_HEADER *@<r8>, struct _NDIS_OBJECT_HEADER *@<r9>, void *, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int))`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140026410`
- `0x140034070`
- `0x14005b960`
- `0x14009b010`

## callees

- `0x140023900`
- `0x140025d30`
- `0x140035640`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14003566c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003566c`
- `ntoskrnl!IoGetStackLimits` at `0x140035887`
- `ntoskrnl!IoGetStackLimits` at `0x140035887`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003594e`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14003594e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400359c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400359c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035976`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035976`

## pseudocode

```c

```
