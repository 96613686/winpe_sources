# Windows::Rtl::SystemImplementation::CFile::WriteFileAsync(ulong,_LBLOB const &,unsigned __int64 *,void (*)(void *,_IO_STATUS_BLOCK *,ulong),void *,_IO_STATUS_BLOCK *,ulong *)

- ea: `0x1802531a0`
- end: `0x1802536a3`
- name: `?WriteFileAsync@CFile@SystemImplementation@Rtl@Windows@@UEAAJKAEBU_LBLOB@@PEA_KP6AXPEAXPEAU_IO_STATUS_BLOCK@@K@Z23PEAK@Z`
- size: `1283`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CFile *__hidden this, unsigned int, const struct _LBLOB *, unsigned __int64 *, void (*)(void *, struct _IO_STATUS_BLOCK *, unsigned int), void *, struct _IO_STATUS_BLOCK *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callees

- `0x180010cc0`
- `0x18004a680`
- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800c21b0`
- `0x1800eb920`
- `0x1800ef360`
- `0x180211e04`
- `0x180213704`
- `0x18024fbc8`
- `0x1802531a0`
- `0x1802d5010`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x1802535a0`
- `ntdll!NtWaitForSingleObject` at `0x1802535a0`
- `ntdll!NtCreateEvent` at `0x180253375`
- `ntdll!NtCreateEvent` at `0x180253375`
- `ntdll!TpStartAsyncIoOperation` at `0x1802534a1`
- `ntdll!TpStartAsyncIoOperation` at `0x1802534a1`

## string_xrefs

- `0x18025339b`: `::NtCreateEvent( WaitEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, NotificationEvent, 0 )`
- `0x180253229`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`
- `0x18025340f`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`
- `0x180253456`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`
- `0x1802535ca`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`

## pseudocode

```c

```
