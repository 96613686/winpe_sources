# KsSynchronousIoControlDevice

- ea: `0x180051360`
- end: `0x180051533`
- name: `KsSynchronousIoControlDevice`
- size: `467`
- prototype: `NTSTATUS __stdcall(PFILE_OBJECT FileObject, KPROCESSOR_MODE RequestorMode, ULONG IoControl, PVOID InBuffer, ULONG InSize, PVOID OutBuffer, ULONG OutSize, PULONG BytesReturned)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180033ba0`
- `0x180034890`
- `0x180038edc`
- `0x1800391d8`
- `0x18003ca00`
- `0x18003cac0`
- `0x18003d490`
- `0x18003d550`
- `0x18003d5f0`
- `0x18003f9b0`
- `0x18003fad0`
- `0x18003fbec`
- `0x18003fcc0`
- `0x18003fd80`
- `0x18003fe20`
- `0x180041220`
- `0x1800430dc`
- `0x180051100`
- `0x180051200`
- `0x1800604d0`

## callees

- `0x180019cb0`
- `0x180051360`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180051418`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180051418`
- `ntoskrnl!ObfReferenceObject` at `0x18005143e`
- `ntoskrnl!ObfReferenceObject` at `0x18005143e`
- `ntoskrnl!IofCallDriver` at `0x18005145f`
- `ntoskrnl!IofCallDriver` at `0x18005145f`
- `ntoskrnl!ExGetPreviousMode` at `0x1800513ba`
- `ntoskrnl!ExGetPreviousMode` at `0x1800513ba`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180051392`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180051392`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005148b`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005148b`
- `ntoskrnl!KeInitializeEvent` at `0x1800513d8`
- `ntoskrnl!KeInitializeEvent` at `0x1800513d8`

## pseudocode

```c

```
