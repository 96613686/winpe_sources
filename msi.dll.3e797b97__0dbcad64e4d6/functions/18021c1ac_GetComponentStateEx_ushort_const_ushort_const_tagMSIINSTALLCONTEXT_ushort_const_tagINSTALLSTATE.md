# GetComponentStateEx(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,ushort const *,tagINSTALLSTATE *)

- ea: `0x18021c1ac`
- end: `0x18021c52e`
- name: `?GetComponentStateEx@@YAKPEBG0W4tagMSIINSTALLCONTEXT@@0PEAW4tagINSTALLSTATE@@@Z`
- size: `898`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, wchar_t *String1, enum tagMSIINSTALLCONTEXT, const unsigned __int16 *, enum tagINSTALLSTATE *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801a6460`
- `0x1801a6660`

## callees

- `0x18000c4bc`
- `0x18000f600`
- `0x180013b7c`
- `0x180014160`
- `0x180014e38`
- `0x18003a820`
- `0x18003e40c`
- `0x1800491f0`
- `0x18004a014`
- `0x18008593c`
- `0x18021c1ac`
- `0x180265240`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18021c35e`
- `KERNEL32!GlobalFree` at `0x18021c39f`
- `KERNEL32!GlobalFree` at `0x18021c42f`
- `KERNEL32!GlobalFree` at `0x18021c4b6`
- `KERNEL32!GlobalFree` at `0x18021c4d8`
- `KERNEL32!GlobalFree` at `0x18021c4f2`
- `KERNEL32!GlobalFree` at `0x18021c35e`
- `KERNEL32!GlobalFree` at `0x18021c39f`
- `KERNEL32!GlobalFree` at `0x18021c42f`
- `KERNEL32!GlobalFree` at `0x18021c4b6`
- `KERNEL32!GlobalFree` at `0x18021c4d8`
- `KERNEL32!GlobalFree` at `0x18021c4f2`
- `USER32!CharUpperW` at `0x18021c218`
- `USER32!CharUpperW` at `0x18021c24e`
- `USER32!CharUpperW` at `0x18021c218`
- `USER32!CharUpperW` at `0x18021c24e`

## string_xrefs

- `0x18021c322`: `Failed to get the current user SID with error code=%d`

## pseudocode

```c

```
