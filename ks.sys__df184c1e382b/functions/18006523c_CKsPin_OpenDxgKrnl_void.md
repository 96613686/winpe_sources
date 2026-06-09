# CKsPin::OpenDxgKrnl(void)

- ea: `0x18006523c`
- end: `0x180065382`
- name: `?OpenDxgKrnl@CKsPin@@QEAAJXZ`
- size: `326`
- prototype: `NTSTATUS __fastcall(CKsPin *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180040f20`

## callees

- `0x18006523c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180065277`
- `ntoskrnl!RtlInitUnicodeString` at `0x180065277`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180065307`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180065307`
- `ntoskrnl!IofCallDriver` at `0x18006531f`
- `ntoskrnl!IofCallDriver` at `0x18006531f`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x180065297`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x180065297`
- `ntoskrnl!KeWaitForSingleObject` at `0x180065347`
- `ntoskrnl!KeWaitForSingleObject` at `0x180065347`
- `ntoskrnl!KeInitializeEvent` at `0x1800652b8`
- `ntoskrnl!KeInitializeEvent` at `0x1800652b8`

## pseudocode

```c

```
