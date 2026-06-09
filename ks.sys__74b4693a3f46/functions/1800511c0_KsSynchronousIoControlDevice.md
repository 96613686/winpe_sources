# KsSynchronousIoControlDevice

- ea: `0x1800511c0`
- end: `0x180051393`
- name: `KsSynchronousIoControlDevice`
- size: `467`
- prototype: `NTSTATUS __stdcall(PFILE_OBJECT FileObject, KPROCESSOR_MODE RequestorMode, ULONG IoControl, PVOID InBuffer, ULONG InSize, PVOID OutBuffer, ULONG OutSize, PULONG BytesReturned)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180033ba0`
- `0x180034840`
- `0x180038dcc`
- `0x1800390c8`
- `0x18003ca10`
- `0x18003cad0`
- `0x18003d4a0`
- `0x18003d560`
- `0x18003d600`
- `0x18003f9c0`
- `0x18003fae0`
- `0x18003fbfc`
- `0x18003fcd0`
- `0x18003fd90`
- `0x18003fe30`
- `0x180041220`
- `0x1800430dc`
- `0x180050f60`
- `0x180051060`
- `0x180060330`

## callees

- `0x180019c60`
- `0x1800511c0`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180051278`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180051278`
- `ntoskrnl!ObfReferenceObject` at `0x18005129e`
- `ntoskrnl!ObfReferenceObject` at `0x18005129e`
- `ntoskrnl!IofCallDriver` at `0x1800512bf`
- `ntoskrnl!IofCallDriver` at `0x1800512bf`
- `ntoskrnl!ExGetPreviousMode` at `0x18005121a`
- `ntoskrnl!ExGetPreviousMode` at `0x18005121a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1800511f2`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1800511f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800512eb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800512eb`
- `ntoskrnl!KeInitializeEvent` at `0x180051238`
- `ntoskrnl!KeInitializeEvent` at `0x180051238`

## pseudocode

```c

```
