# GetComponentStateEx(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,ushort const *,tagINSTALLSTATE *)

- ea: `0x180212884`
- end: `0x180212bd1`
- name: `?GetComponentStateEx@@YAKPEBG0W4tagMSIINSTALLCONTEXT@@0PEAW4tagINSTALLSTATE@@@Z`
- size: `845`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, enum tagMSIINSTALLCONTEXT, const unsigned __int16 *, enum tagINSTALLSTATE *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18019f450`
- `0x18019f650`

## callees

- `0x180014288`
- `0x180017a84`
- `0x180020d40`
- `0x1800250d4`
- `0x180025560`
- `0x180025a18`
- `0x18004b560`
- `0x18004ceb0`
- `0x180064a78`
- `0x18008eac8`
- `0x180212884`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180212a26`
- `KERNEL32!GlobalFree` at `0x180212a61`
- `KERNEL32!GlobalFree` at `0x180212aeb`
- `KERNEL32!GlobalFree` at `0x180212b6c`
- `KERNEL32!GlobalFree` at `0x180212b88`
- `KERNEL32!GlobalFree` at `0x180212b9c`
- `KERNEL32!GlobalFree` at `0x180212a26`
- `KERNEL32!GlobalFree` at `0x180212a61`
- `KERNEL32!GlobalFree` at `0x180212aeb`
- `KERNEL32!GlobalFree` at `0x180212b6c`
- `KERNEL32!GlobalFree` at `0x180212b88`
- `KERNEL32!GlobalFree` at `0x180212b9c`
- `USER32!CharUpperW` at `0x1802128f0`
- `USER32!CharUpperW` at `0x180212920`
- `USER32!CharUpperW` at `0x1802128f0`
- `USER32!CharUpperW` at `0x180212920`

## string_xrefs

- `0x1802129ea`: `Failed to get the current user SID with error code=%d`

## pseudocode

```c

```
