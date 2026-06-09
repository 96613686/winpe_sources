# EnumSources(bool,ushort const *,ushort const *,ulong,ulong,ulong,ulong *,ushort *,ulong *,ushort *,ulong *)

- ea: `0x180169460`
- end: `0x1801699bf`
- name: `?EnumSources@@YAI_NPEBG1KKKPEAKPEAG232@Z`
- size: `1375`
- prototype: `unsigned int(bool, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int *, unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `22`
- tags: `authz_impersonation`

## callers

- `0x1801a7810`
- `0x1801a7b20`
- `0x1801a7c80`
- `0x1801a7f00`

## callees

- `0x18000c4bc`
- `0x180013b7c`
- `0x180014160`
- `0x180014e38`
- `0x18003e40c`
- `0x180046538`
- `0x180046f50`
- `0x180048214`
- `0x1800491f0`
- `0x18005acbc`
- `0x18006dc80`
- `0x1800c00c8`
- `0x1800f049c`
- `0x180169460`
- `0x1801699c8`
- `0x18021c908`
- `0x18023b0e4`
- `0x18023c8d0`
- `0x18023ca20`
- `0x18023d720`
- `0x18023de94`
- `0x180265240`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18016960f`
- `KERNEL32!GlobalFree` at `0x1801696be`
- `KERNEL32!GlobalFree` at `0x1801697af`
- `KERNEL32!GlobalFree` at `0x180169965`
- `KERNEL32!GlobalFree` at `0x180169994`
- `KERNEL32!GlobalFree` at `0x18016960f`
- `KERNEL32!GlobalFree` at `0x1801696be`
- `KERNEL32!GlobalFree` at `0x1801697af`
- `KERNEL32!GlobalFree` at `0x180169965`
- `KERNEL32!GlobalFree` at `0x180169994`
- `USER32!CharUpperW` at `0x180169553`
- `USER32!CharUpperW` at `0x180169553`

## string_xrefs

- `0x1801695cf`: `Failed to get the current user SID with error code=%d`

## pseudocode

```c

```
