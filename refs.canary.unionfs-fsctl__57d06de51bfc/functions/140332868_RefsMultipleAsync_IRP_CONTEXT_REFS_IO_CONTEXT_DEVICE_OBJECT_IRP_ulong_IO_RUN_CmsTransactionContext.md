# RefsMultipleAsync(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_DEVICE_OBJECT *,_IRP *,ulong,IO_RUN *,CmsTransactionContext *)

- ea: `0x140332868`
- end: `0x140332c2d`
- name: `?RefsMultipleAsync@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_DEVICE_OBJECT@@PEAU_IRP@@KPEAUIO_RUN@@PEAVCmsTransactionContext@@@Z`
- size: `965`
- prototype: `void(struct _IRP_CONTEXT *, struct REFS_IO_CONTEXT *, struct _DEVICE_OBJECT *, struct _IRP *, unsigned int, struct IO_RUN *, struct CmsTransactionContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14033b8d0`

## callees

- `0x14008e5d0`
- `0x14009b060`
- `0x14009f140`
- `0x1400aec80`
- `0x1400cb9d0`
- `0x1400d8ec0`
- `0x140113738`
- `0x140332868`
- `0x1403383d8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1403329e2`
- `ntoskrnl!IofCompleteRequest` at `0x140332a5b`
- `ntoskrnl!IofCompleteRequest` at `0x1403329e2`
- `ntoskrnl!IofCompleteRequest` at `0x140332a5b`
- `ntoskrnl!IoInitializeWorkItem` at `0x140332afd`
- `ntoskrnl!IoInitializeWorkItem` at `0x140332afd`
- `ntoskrnl!IoUninitializeWorkItem` at `0x140332b65`
- `ntoskrnl!IoUninitializeWorkItem` at `0x140332b65`
- `ntoskrnl!IoFreeWorkItem` at `0x140332b8d`
- `ntoskrnl!IoFreeWorkItem` at `0x140332b8d`
- `ntoskrnl!IofCallDriver` at `0x140332bce`
- `ntoskrnl!IofCallDriver` at `0x140332bce`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14033293d`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14033293d`
- `ntoskrnl!IoSetIoPriorityHint` at `0x140332a79`
- `ntoskrnl!IoSetIoPriorityHint` at `0x140332a79`
- `ntoskrnl!IoAllocateWorkItem` at `0x140332b0b`
- `ntoskrnl!IoAllocateWorkItem` at `0x140332b0b`
- `ntoskrnl!IoTryQueueWorkItem` at `0x140332b42`
- `ntoskrnl!IoTryQueueWorkItem` at `0x140332b42`

## pseudocode

```c

```
