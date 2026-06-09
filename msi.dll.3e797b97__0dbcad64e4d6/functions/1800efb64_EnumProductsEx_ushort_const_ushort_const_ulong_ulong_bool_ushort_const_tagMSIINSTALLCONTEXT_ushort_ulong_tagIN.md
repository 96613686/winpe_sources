# EnumProductsEx(ushort const *,ushort const *,ulong,ulong,bool,ushort * const,tagMSIINSTALLCONTEXT *,ushort *,ulong *,tagINSTALLSTATE *)

- ea: `0x1800efb64`
- end: `0x1800f0493`
- name: `?EnumProductsEx@@YAIPEBG0KK_NQEAGPEAW4tagMSIINSTALLCONTEXT@@PEAGPEAKPEAW4tagINSTALLSTATE@@@Z`
- size: `2351`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, wchar_t *String1@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, bool, unsigned __int16 *const, enum tagMSIINSTALLCONTEXT *, unsigned __int16 *, unsigned int *, enum tagINSTALLSTATE *)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800eefe4`
- `0x1800efa10`
- `0x1801a4630`

## callees

- `0x18000c4bc`
- `0x180013b7c`
- `0x180014160`
- `0x180014e38`
- `0x18003bd60`
- `0x18003e40c`
- `0x180046538`
- `0x180046f50`
- `0x180048214`
- `0x180048294`
- `0x180048588`
- `0x1800491f0`
- `0x18006dc80`
- `0x18008593c`
- `0x1800c00c8`
- `0x1800efb64`
- `0x1800f049c`
- `0x18013773c`
- `0x1801a2264`
- `0x18021c600`
- `0x18021c738`
- `0x18021c908`
- `0x180265240`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800efd5c`
- `msvcrt!_wcsicmp` at `0x1800efd5c`
- `KERNEL32!GlobalFree` at `0x1800efd15`
- `KERNEL32!GlobalFree` at `0x1800efd3a`
- `KERNEL32!GlobalFree` at `0x1800efdfd`
- `KERNEL32!GlobalFree` at `0x1800efe4c`
- `KERNEL32!GlobalFree` at `0x1800efe71`
- `KERNEL32!GlobalFree` at `0x1800efef0`
- `KERNEL32!GlobalFree` at `0x1800eff15`
- `KERNEL32!GlobalFree` at `0x1800f03f0`
- `KERNEL32!GlobalFree` at `0x1800f0415`
- `KERNEL32!GlobalFree` at `0x1800f0432`
- `KERNEL32!GlobalFree` at `0x1800f0457`
- `KERNEL32!GlobalFree` at `0x1800efd15`
- `KERNEL32!GlobalFree` at `0x1800efd3a`
- `KERNEL32!GlobalFree` at `0x1800efdfd`
- `KERNEL32!GlobalFree` at `0x1800efe4c`
- `KERNEL32!GlobalFree` at `0x1800efe71`
- `KERNEL32!GlobalFree` at `0x1800efef0`
- `KERNEL32!GlobalFree` at `0x1800eff15`
- `KERNEL32!GlobalFree` at `0x1800f03f0`
- `KERNEL32!GlobalFree` at `0x1800f0415`
- `KERNEL32!GlobalFree` at `0x1800f0432`
- `KERNEL32!GlobalFree` at `0x1800f0457`
- `USER32!CharUpperW` at `0x1800efc67`
- `USER32!CharUpperW` at `0x1800efc67`

## string_xrefs

- `0x1800f01fe`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x1800f0066`: `Software\Microsoft\Windows\CurrentVersion\Installer\Managed`
- `0x1800efdbf`: `Failed to get the current user SID with error code=%d`
- `0x1800f0126`: `Local System sid is getting ignored. Specify machine context through dwContext parameter`

## pseudocode

```c

```
