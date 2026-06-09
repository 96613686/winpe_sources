# CKsNotification::UpdatePinState(_KSCAMERA_FRAMESERVER_UNIQUEID *,uchar,ulong,ulong,_KSFILTER *)

- ea: `0x1800590c0`
- end: `0x180059290`
- name: `?UpdatePinState@CKsNotification@@UEAAJPEAU_KSCAMERA_FRAMESERVER_UNIQUEID@@EKKPEAU_KSFILTER@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(CKsNotification *this, struct _KSCAMERA_FRAMESERVER_UNIQUEID *, char, unsigned int, unsigned int, struct _KSFILTER *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000b7bc`
- `0x1800185b8`
- `0x1800590c0`
- `0x180059298`
- `0x18005934c`
- `0x1800651a8`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18005913c`
- `ntoskrnl!KeReleaseMutex` at `0x18005913c`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800591ab`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800591ab`
- `ntoskrnl!KeWaitForSingleObject` at `0x180059108`
- `ntoskrnl!KeWaitForSingleObject` at `0x180059108`

## pseudocode

```c

```
