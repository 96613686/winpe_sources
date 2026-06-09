# RegistrationStoreData::LoadKey(HSTRING__ *,HSTRING__ *,_UNICODE_STRING &,ulong,ulong,RegistryKey &)

- ea: `0x180165028`
- end: `0x180165333`
- name: `?LoadKey@RegistrationStoreData@@YAJPEAUHSTRING__@@0AEAU_UNICODE_STRING@@KKAEAVRegistryKey@@@Z`
- size: `779`
- prototype: `HRESULT __fastcall(HSTRING__ *packageId, HSTRING__ *privateHivePath, _UNICODE_STRING *mountPath, unsigned int flags, unsigned int samDesired, RegistryKey *hiveKey)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180125638`

## callees

- `0x180001fe4`
- `0x18004fa14`
- `0x1800517e4`
- `0x180090780`
- `0x1800c4250`
- `0x18011e41c`
- `0x18012281c`
- `0x1801365ec`
- `0x180164ffc`
- `0x180165028`
- `0x180179024`
- `0x18018ab84`
- `0x1801a317c`
- `0x1801a4880`
- `0x1801a4a98`

## import_xrefs

- `ntdll!NtLoadKeyEx` at `0x180165120`
- `ntdll!NtLoadKeyEx` at `0x18016517e`
- `ntdll!NtLoadKeyEx` at `0x180165120`
- `ntdll!NtLoadKeyEx` at `0x18016517e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180165082`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180165082`
- `ntdll!RtlFreeUnicodeString` at `0x180165301`
- `ntdll!RtlFreeUnicodeString` at `0x180165301`
- `ntdll!RtlNtStatusToDosError` at `0x1801651b6`
- `ntdll!RtlNtStatusToDosError` at `0x1801651b6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18016514f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18016514f`

## string_xrefs

- `0x180165093`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x180165321`: `onecore\com\combase\registrationstore\privateuserhive.cpp`

## pseudocode

```c

```
