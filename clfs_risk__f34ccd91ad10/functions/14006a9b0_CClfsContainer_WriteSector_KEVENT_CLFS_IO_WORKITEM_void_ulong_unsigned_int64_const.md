# CClfsContainer::WriteSector(_KEVENT *,_CLFS_IO_WORKITEM *,void *,ulong,unsigned __int64 * const)

- ea: `0x14006a9b0`
- end: `0x14006aef0`
- name: `?WriteSector@CClfsContainer@@QEAAJPEAU_KEVENT@@PEAU_CLFS_IO_WORKITEM@@PEAXKQEA_K@Z`
- size: `1344`
- prototype: `__int64 __usercall@<rax>(ULONG_PTR BugCheckParameter3@<rcx>, struct _KEVENT *@<rdx>, struct _CLFS_IO_WORKITEM *@<r8>, void *@<r9>, unsigned int, unsigned __int64 *const)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x140010630`
- `0x14001091c`
- `0x14003a310`
- `0x14003a3f0`
- `0x14003cee8`
- `0x14003d418`
- `0x14003fb20`
- `0x14003fb8c`
- `0x14006a734`

## callees

- `0x14000bc14`
- `0x1400104f4`
- `0x140018280`
- `0x14006a9b0`
- `0x14006bc84`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14006ace0`
- `ntoskrnl!ObfReferenceObject` at `0x14006ace0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006add4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006add4`
- `ntoskrnl!KeClearEvent` at `0x14006ab61`
- `ntoskrnl!KeClearEvent` at `0x14006ab61`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006a9e3`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006a9e3`
- `ntoskrnl!KeBugCheckEx` at `0x14006aa64`
- `ntoskrnl!KeBugCheckEx` at `0x14006aad2`
- `ntoskrnl!KeBugCheckEx` at `0x14006ab31`
- `ntoskrnl!KeBugCheckEx` at `0x14006ae9b`
- `ntoskrnl!KeBugCheckEx` at `0x14006aebd`
- `ntoskrnl!KeBugCheckEx` at `0x14006aee3`
- `ntoskrnl!KeBugCheckEx` at `0x14006aa64`
- `ntoskrnl!KeBugCheckEx` at `0x14006aad2`
- `ntoskrnl!KeBugCheckEx` at `0x14006ab31`
- `ntoskrnl!KeBugCheckEx` at `0x14006ae9b`
- `ntoskrnl!KeBugCheckEx` at `0x14006aebd`
- `ntoskrnl!KeBugCheckEx` at `0x14006aee3`
- `ntoskrnl!IofCallDriver` at `0x14006ad67`
- `ntoskrnl!IofCallDriver` at `0x14006ad8f`
- `ntoskrnl!IofCallDriver` at `0x14006ad67`
- `ntoskrnl!IofCallDriver` at `0x14006ad8f`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14006ac8a`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14006ac8a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14006ad12`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14006ad12`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006ad55`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006ad7b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006ad55`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006ad7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ae59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b4cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ae59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b4cd`
- `ntoskrnl!IoQueueWorkItem` at `0x14006ae41`
- `ntoskrnl!IoQueueWorkItem` at `0x14007b4af`
- `ntoskrnl!IoQueueWorkItem` at `0x14006ae41`
- `ntoskrnl!IoQueueWorkItem` at `0x14007b4af`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14006ab7d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14006ab7d`

## pseudocode

```c

```
