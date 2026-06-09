# CKsNotification::UpdatePinState(_KSCAMERA_FRAMESERVER_UNIQUEID *,uchar,ulong,ulong,_KSFILTER *)

- ea: `0x180058f20`
- end: `0x1800590f0`
- name: `?UpdatePinState@CKsNotification@@UEAAJPEAU_KSCAMERA_FRAMESERVER_UNIQUEID@@EKKPEAU_KSFILTER@@@Z`
- size: `464`
- prototype: `__int64 __usercall@<rax>(CKsNotification *__hidden this@<rcx>, struct _KSCAMERA_FRAMESERVER_UNIQUEID *@<rdx>, unsigned __int8@<r8b>, unsigned int@<r9d>, unsigned int, struct _KSFILTER *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000b7bc`
- `0x180018568`
- `0x180058f20`
- `0x1800590f8`
- `0x1800591ac`
- `0x180065008`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180058f9c`
- `ntoskrnl!KeReleaseMutex` at `0x180058f9c`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x18005900b`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x18005900b`
- `ntoskrnl!KeWaitForSingleObject` at `0x180058f68`
- `ntoskrnl!KeWaitForSingleObject` at `0x180058f68`

## pseudocode

```c

```
