# GetComponentPathEx(ushort const *,ushort const *,ushort const *,tagMSIINSTALLCONTEXT,ushort *,ulong *)

- ea: `0x180014674`
- end: `0x180014c8b`
- name: `?GetComponentPathEx@@YA?AW4tagINSTALLSTATE@@PEBG00W4tagMSIINSTALLCONTEXT@@PEAGPEAK@Z`
- size: `1559`
- prototype: `enum tagINSTALLSTATE __usercall@<eax>(LPCWSTR lpString@<rcx>, LPCWSTR@<rdx>, const unsigned __int16 *@<r8>, enum tagMSIINSTALLCONTEXT@<r9d>, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180015e80`
- `0x1801a4db0`

## callees

- `0x180014160`
- `0x180014674`
- `0x180014c94`
- `0x180014d38`
- `0x180014dc0`
- `0x180014e38`
- `0x180015000`
- `0x1800150b4`
- `0x180015230`
- `0x1800152dc`
- `0x18003e40c`
- `0x180265240`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x180014c37`
- `KERNEL32!GlobalAlloc` at `0x180014c37`
- `KERNEL32!lstrlenW` at `0x1800146e4`
- `KERNEL32!lstrlenW` at `0x1800147bf`
- `KERNEL32!lstrlenW` at `0x1800146e4`
- `KERNEL32!lstrlenW` at `0x1800147bf`
- `KERNEL32!GlobalFree` at `0x1800149cb`
- `KERNEL32!GlobalFree` at `0x1800149dd`
- `KERNEL32!GlobalFree` at `0x180014c5b`
- `KERNEL32!GlobalFree` at `0x1800149cb`
- `KERNEL32!GlobalFree` at `0x1800149dd`
- `KERNEL32!GlobalFree` at `0x180014c5b`

## pseudocode

```c

```
