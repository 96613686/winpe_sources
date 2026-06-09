# GetFeatureStateEx(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,ushort const *,tagINSTALLSTATE *)

- ea: `0x1800e9668`
- end: `0x1800e99c7`
- name: `?GetFeatureStateEx@@YAKPEBG0W4tagMSIINSTALLCONTEXT@@0PEAW4tagINSTALLSTATE@@@Z`
- size: `863`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, enum tagMSIINSTALLCONTEXT, const unsigned __int16 *, enum tagINSTALLSTATE *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800e9540`
- `0x1801a6790`

## callees

- `0x18000c4bc`
- `0x18000f600`
- `0x180013b7c`
- `0x180014e38`
- `0x18003ae54`
- `0x18003e40c`
- `0x1800491f0`
- `0x18005acbc`
- `0x18008593c`
- `0x1800e9668`
- `0x180265240`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800e9809`
- `KERNEL32!GlobalFree` at `0x1800e9828`
- `KERNEL32!GlobalFree` at `0x1800e984a`
- `KERNEL32!GlobalFree` at `0x1800e9870`
- `KERNEL32!GlobalFree` at `0x1800e988d`
- `KERNEL32!GlobalFree` at `0x1800e98af`
- `KERNEL32!GlobalFree` at `0x1800e9809`
- `KERNEL32!GlobalFree` at `0x1800e9828`
- `KERNEL32!GlobalFree` at `0x1800e984a`
- `KERNEL32!GlobalFree` at `0x1800e9870`
- `KERNEL32!GlobalFree` at `0x1800e988d`
- `KERNEL32!GlobalFree` at `0x1800e98af`
- `USER32!CharUpperW` at `0x1800e971e`
- `USER32!CharUpperW` at `0x1800e971e`

## string_xrefs

- `0x1800e97cb`: `Failed to get the current user SID with error code=%d`

## pseudocode

```c

```
