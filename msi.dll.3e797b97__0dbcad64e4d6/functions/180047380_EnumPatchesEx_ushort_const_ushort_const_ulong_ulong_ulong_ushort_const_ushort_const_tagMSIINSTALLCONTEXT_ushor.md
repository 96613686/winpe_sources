# EnumPatchesEx(ushort const *,ushort const *,ulong,ulong,ulong,ushort * const,ushort * const,tagMSIINSTALLCONTEXT *,ushort *,ulong *,tagMSIPATCHSTATE *)

- ea: `0x180047380`
- end: `0x18004820d`
- name: `?EnumPatchesEx@@YAIPEBG0KKKQEAG1PEAW4tagMSIINSTALLCONTEXT@@PEAGPEAKPEAW4tagMSIPATCHSTATE@@@Z`
- size: `3725`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned __int16 *const, unsigned __int16 *const, enum tagMSIINSTALLCONTEXT *, unsigned __int16 *, unsigned int *, enum tagMSIPATCHSTATE *)`
- caller_count: `3`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005acec`
- `0x18012e310`
- `0x1801a40b0`

## callees

- `0x18000c4bc`
- `0x18000ca3c`
- `0x18000d6d8`
- `0x180013b7c`
- `0x180014160`
- `0x180014e38`
- `0x18003bd60`
- `0x18003c1d0`
- `0x18003e40c`
- `0x180046538`
- `0x180046f00`
- `0x180046f50`
- `0x180047380`
- `0x180048214`
- `0x180048294`
- `0x180048588`
- `0x18006dc80`
- `0x1800f049c`
- `0x18013773c`
- `0x1801a2264`
- `0x1801dc920`
- `0x18021c738`
- `0x18021c908`
- `0x180265240`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800477d0`
- `KERNEL32!LeaveCriticalSection` at `0x1800481e7`
- `KERNEL32!LeaveCriticalSection` at `0x1800477d0`
- `KERNEL32!LeaveCriticalSection` at `0x1800481e7`
- `KERNEL32!EnterCriticalSection` at `0x180047766`
- `KERNEL32!EnterCriticalSection` at `0x180047766`
- `KERNEL32!GlobalFree` at `0x1800475b7`
- `KERNEL32!GlobalFree` at `0x1800475ff`
- `KERNEL32!GlobalFree` at `0x1800479b3`
- `KERNEL32!GlobalFree` at `0x1800479f7`
- `KERNEL32!GlobalFree` at `0x180047a14`
- `KERNEL32!GlobalFree` at `0x180047a58`
- `KERNEL32!GlobalFree` at `0x180047ae2`
- `KERNEL32!GlobalFree` at `0x180047b26`
- `KERNEL32!GlobalFree` at `0x180047b65`
- `KERNEL32!GlobalFree` at `0x180047ba9`
- `KERNEL32!GlobalFree` at `0x180047c76`
- `KERNEL32!GlobalFree` at `0x180047ca3`
- `KERNEL32!GlobalFree` at `0x180047ce7`
- `KERNEL32!GlobalFree` at `0x180047d5a`
- `KERNEL32!GlobalFree` at `0x180047d9e`
- `KERNEL32!GlobalFree` at `0x180047dcc`
- `KERNEL32!GlobalFree` at `0x180047e6d`
- `KERNEL32!GlobalFree` at `0x1800480c2`
- `KERNEL32!GlobalFree` at `0x1800480d7`
- `KERNEL32!GlobalFree` at `0x1800480ec`
- `KERNEL32!GlobalFree` at `0x180048196`
- `KERNEL32!GlobalFree` at `0x1800481d3`
- `KERNEL32!GlobalFree` at `0x1800481fc`
- `KERNEL32!GlobalFree` at `0x1800475b7`
- `KERNEL32!GlobalFree` at `0x1800475ff`
- `KERNEL32!GlobalFree` at `0x1800479b3`
- `KERNEL32!GlobalFree` at `0x1800479f7`
- `KERNEL32!GlobalFree` at `0x180047a14`
- `KERNEL32!GlobalFree` at `0x180047a58`
- `KERNEL32!GlobalFree` at `0x180047ae2`
- `KERNEL32!GlobalFree` at `0x180047b26`
- `KERNEL32!GlobalFree` at `0x180047b65`
- `KERNEL32!GlobalFree` at `0x180047ba9`
- `KERNEL32!GlobalFree` at `0x180047c76`
- `KERNEL32!GlobalFree` at `0x180047ca3`
- `KERNEL32!GlobalFree` at `0x180047ce7`
- `KERNEL32!GlobalFree` at `0x180047d5a`
- `KERNEL32!GlobalFree` at `0x180047d9e`
- `KERNEL32!GlobalFree` at `0x180047dcc`
- `KERNEL32!GlobalFree` at `0x180047e6d`
- `KERNEL32!GlobalFree` at `0x1800480c2`
- `KERNEL32!GlobalFree` at `0x1800480d7`
- `KERNEL32!GlobalFree` at `0x1800480ec`
- `KERNEL32!GlobalFree` at `0x180048196`
- `KERNEL32!GlobalFree` at `0x1800481d3`
- `KERNEL32!GlobalFree` at `0x1800481fc`
- `KERNEL32!lstrcmpiW` at `0x180047e17`
- `KERNEL32!lstrcmpiW` at `0x180047e17`
- `USER32!CharUpperW` at `0x180047485`
- `USER32!CharUpperW` at `0x180047485`

## string_xrefs

- `0x180047f06`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x180047f47`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x180047ea7`: `Software\Microsoft\Windows\CurrentVersion\Installer\Managed`
- `0x180047650`: `Failed to get the current user SID with error code=%d`

## pseudocode

```c

```
