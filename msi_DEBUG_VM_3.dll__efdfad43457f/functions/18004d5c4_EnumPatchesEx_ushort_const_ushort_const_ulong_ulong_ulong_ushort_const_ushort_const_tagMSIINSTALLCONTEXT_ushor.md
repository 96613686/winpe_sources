# EnumPatchesEx(ushort const *,ushort const *,ulong,ulong,ulong,ushort * const,ushort * const,tagMSIINSTALLCONTEXT *,ushort *,ulong *,tagMSIPATCHSTATE *)

- ea: `0x18004d5c4`
- end: `0x18004e3a5`
- name: `?EnumPatchesEx@@YAIPEBG0KKKQEAG1PEAW4tagMSIINSTALLCONTEXT@@PEAGPEAKPEAW4tagMSIPATCHSTATE@@@Z`
- size: `3553`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned __int16 *const, unsigned __int16 *const, enum tagMSIINSTALLCONTEXT *, unsigned __int16 *, unsigned int *, enum tagMSIPATCHSTATE *)`
- caller_count: `3`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005a51c`
- `0x180128480`
- `0x18019d0f0`

## callees

- `0x180015690`
- `0x180015ac0`
- `0x180017a84`
- `0x18001de18`
- `0x18001e9f8`
- `0x1800250d4`
- `0x180025560`
- `0x180025a18`
- `0x18004d38c`
- `0x18004d5c4`
- `0x18004ec1c`
- `0x18004ec7c`
- `0x18004f75c`
- `0x18004f7a4`
- `0x18004fc48`
- `0x180050ec4`
- `0x180064a78`
- `0x180074bd0`
- `0x180131bec`
- `0x18019b2e8`
- `0x1801d3bac`
- `0x180212ddc`
- `0x180212f98`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18004d9fb`
- `KERNEL32!LeaveCriticalSection` at `0x18004e38b`
- `KERNEL32!LeaveCriticalSection` at `0x18004d9fb`
- `KERNEL32!LeaveCriticalSection` at `0x18004e38b`
- `KERNEL32!EnterCriticalSection` at `0x18004d997`
- `KERNEL32!EnterCriticalSection` at `0x18004d997`
- `KERNEL32!GlobalFree` at `0x18004d7f4`
- `KERNEL32!GlobalFree` at `0x18004d836`
- `KERNEL32!GlobalFree` at `0x18004dbd8`
- `KERNEL32!GlobalFree` at `0x18004dc16`
- `KERNEL32!GlobalFree` at `0x18004dc2d`
- `KERNEL32!GlobalFree` at `0x18004dc6b`
- `KERNEL32!GlobalFree` at `0x18004dcef`
- `KERNEL32!GlobalFree` at `0x18004dd2d`
- `KERNEL32!GlobalFree` at `0x18004dd66`
- `KERNEL32!GlobalFree` at `0x18004dda4`
- `KERNEL32!GlobalFree` at `0x18004de6b`
- `KERNEL32!GlobalFree` at `0x18004de92`
- `KERNEL32!GlobalFree` at `0x18004ded0`
- `KERNEL32!GlobalFree` at `0x18004df3a`
- `KERNEL32!GlobalFree` at `0x18004df78`
- `KERNEL32!GlobalFree` at `0x18004dfa0`
- `KERNEL32!GlobalFree` at `0x18004e035`
- `KERNEL32!GlobalFree` at `0x18004e284`
- `KERNEL32!GlobalFree` at `0x18004e293`
- `KERNEL32!GlobalFree` at `0x18004e2a2`
- `KERNEL32!GlobalFree` at `0x18004e346`
- `KERNEL32!GlobalFree` at `0x18004e37d`
- `KERNEL32!GlobalFree` at `0x18004e39a`
- `KERNEL32!GlobalFree` at `0x18004d7f4`
- `KERNEL32!GlobalFree` at `0x18004d836`
- `KERNEL32!GlobalFree` at `0x18004dbd8`
- `KERNEL32!GlobalFree` at `0x18004dc16`
- `KERNEL32!GlobalFree` at `0x18004dc2d`
- `KERNEL32!GlobalFree` at `0x18004dc6b`
- `KERNEL32!GlobalFree` at `0x18004dcef`
- `KERNEL32!GlobalFree` at `0x18004dd2d`
- `KERNEL32!GlobalFree` at `0x18004dd66`
- `KERNEL32!GlobalFree` at `0x18004dda4`
- `KERNEL32!GlobalFree` at `0x18004de6b`
- `KERNEL32!GlobalFree` at `0x18004de92`
- `KERNEL32!GlobalFree` at `0x18004ded0`
- `KERNEL32!GlobalFree` at `0x18004df3a`
- `KERNEL32!GlobalFree` at `0x18004df78`
- `KERNEL32!GlobalFree` at `0x18004dfa0`
- `KERNEL32!GlobalFree` at `0x18004e035`
- `KERNEL32!GlobalFree` at `0x18004e284`
- `KERNEL32!GlobalFree` at `0x18004e293`
- `KERNEL32!GlobalFree` at `0x18004e2a2`
- `KERNEL32!GlobalFree` at `0x18004e346`
- `KERNEL32!GlobalFree` at `0x18004e37d`
- `KERNEL32!GlobalFree` at `0x18004e39a`
- `KERNEL32!lstrcmpiW` at `0x18004dfe5`
- `KERNEL32!lstrcmpiW` at `0x18004dfe5`
- `USER32!CharUpperW` at `0x18004d6c8`
- `USER32!CharUpperW` at `0x18004d6c8`

## string_xrefs

- `0x18004d77f`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18004e0c8`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18004e109`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18004e069`: `Software\Microsoft\Windows\CurrentVersion\Installer\Managed`
- `0x18004d881`: `Failed to get the current user SID with error code=%d`

## pseudocode

```c

```
