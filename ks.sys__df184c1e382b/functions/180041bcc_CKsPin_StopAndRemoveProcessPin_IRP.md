# CKsPin::StopAndRemoveProcessPin(_IRP *)

- ea: `0x180041bcc`
- end: `0x180041d26`
- name: `?StopAndRemoveProcessPin@CKsPin@@AEAAXPEAU_IRP@@@Z`
- size: `346`
- prototype: `void __fastcall(CKsPin *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003edd0`

## callees

- `0x18000b7bc`
- `0x18000ef7c`
- `0x180019cb0`
- `0x180041bcc`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180041d07`
- `ntoskrnl!KeReleaseMutex` at `0x180041d07`
- `ntoskrnl!KeWaitForSingleObject` at `0x180041c99`
- `ntoskrnl!KeWaitForSingleObject` at `0x180041c99`

## pseudocode

```c

```
