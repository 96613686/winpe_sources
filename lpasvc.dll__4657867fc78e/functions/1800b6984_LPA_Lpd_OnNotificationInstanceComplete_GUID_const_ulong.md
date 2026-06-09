# LPA::Lpd::OnNotificationInstanceComplete(_GUID const &,ulong &)

- ea: `0x1800b6984`
- end: `0x1800b6a44`
- name: `?OnNotificationInstanceComplete@Lpd@LPA@@AEAAXAEBU_GUID@@AEAK@Z`
- size: `192`
- prototype: `void __fastcall(LPA::Lpd *__hidden this, const struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b6a4c`

## callees

- `0x180061a4c`
- `0x180061ccc`
- `0x18006d8d0`
- `0x180071840`
- `0x1800718d0`
- `0x1800a23a4`
- `0x1800ad538`
- `0x1800b6984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b6a31`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b6a31`

## string_xrefs

- `0x1800b6a21`: `LpaServiceLpd`

## pseudocode

```c

```
