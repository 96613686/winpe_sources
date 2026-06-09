# CKsNotification::UpdatePowerState(_IRP *)

- ea: `0x180045a40`
- end: `0x180045b3d`
- name: `?UpdatePowerState@CKsNotification@@UEAAXPEAU_IRP@@@Z`
- size: `253`
- prototype: `void __fastcall(CKsNotification *__hidden this, struct _IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800110e8`
- `0x1800113ac`
- `0x180045a40`
- `0x180060130`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180045b04`
- `ntoskrnl!KeReleaseMutex` at `0x180045b04`
- `ntoskrnl!KeWaitForSingleObject` at `0x180045aea`
- `ntoskrnl!KeWaitForSingleObject` at `0x180045aea`
- `HAL!KeQueryPerformanceCounter` at `0x180045b18`
- `HAL!KeQueryPerformanceCounter` at `0x180045b18`

## pseudocode

```c

```
