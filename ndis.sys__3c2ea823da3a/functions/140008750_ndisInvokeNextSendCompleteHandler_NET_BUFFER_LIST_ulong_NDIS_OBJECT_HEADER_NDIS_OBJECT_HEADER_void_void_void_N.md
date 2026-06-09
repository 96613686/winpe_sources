# ndisInvokeNextSendCompleteHandler(_NET_BUFFER_LIST *,ulong,_NDIS_OBJECT_HEADER *,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong))

- ea: `0x140008750`
- end: `0x140008bcd`
- name: `?ndisInvokeNextSendCompleteHandler@@YAXPEAU_NET_BUFFER_LIST@@KPEAU_NDIS_OBJECT_HEADER@@1PEAXP6AX20K@Z@Z`
- size: `1149`
- prototype: `void __usercall(struct _NET_BUFFER_LIST *@<rcx>, unsigned int@<edx>, struct _NDIS_OBJECT_HEADER *@<r8>, struct _NDIS_OBJECT_HEADER *@<r9>, void *, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int))`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008520`
- `0x14000eb70`
- `0x140010300`
- `0x140095d90`

## callees

- `0x140008750`
- `0x14000a5a0`
- `0x14000de20`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000877c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000877c`
- `ntoskrnl!IoGetStackLimits` at `0x140008997`
- `ntoskrnl!IoGetStackLimits` at `0x140008997`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140008a5e`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140008a5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008ad5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008ad5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008a86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008a86`

## pseudocode

```c

```
