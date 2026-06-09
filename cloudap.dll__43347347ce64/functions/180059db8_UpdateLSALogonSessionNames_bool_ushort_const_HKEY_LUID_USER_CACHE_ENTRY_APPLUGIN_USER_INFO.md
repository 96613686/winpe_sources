# UpdateLSALogonSessionNames(bool,ushort const *,HKEY__ *,_LUID *,_USER_CACHE_ENTRY *,_APPLUGIN_USER_INFO *)

- ea: `0x180059db8`
- end: `0x18005a08d`
- name: `?UpdateLSALogonSessionNames@@YAJ_NPEBGPEAUHKEY__@@PEAU_LUID@@PEAU_USER_CACHE_ENTRY@@PEAU_APPLUGIN_USER_INFO@@@Z`
- size: `725`
- prototype: `int(bool, const unsigned __int16 *, HKEY, struct _LUID *, struct _USER_CACHE_ENTRY *, struct _APPLUGIN_USER_INFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180011960`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x1800307d0`
- `0x180042410`
- `0x180059db8`
- `0x180081010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180059f02`
- `ntdll!RtlInitUnicodeString` at `0x180059f22`
- `ntdll!RtlInitUnicodeString` at `0x180059f4d`
- `ntdll!RtlInitUnicodeString` at `0x180059f79`
- `ntdll!RtlInitUnicodeString` at `0x180059fac`
- `ntdll!RtlInitUnicodeString` at `0x180059fe3`
- `ntdll!RtlInitUnicodeString` at `0x180059f02`
- `ntdll!RtlInitUnicodeString` at `0x180059f22`
- `ntdll!RtlInitUnicodeString` at `0x180059f4d`
- `ntdll!RtlInitUnicodeString` at `0x180059f79`
- `ntdll!RtlInitUnicodeString` at `0x180059fac`
- `ntdll!RtlInitUnicodeString` at `0x180059fe3`
- `LSASRV!LsaIAddNamesToLogonSession` at `0x18005a00e`
- `LSASRV!LsaIAddNamesToLogonSession` at `0x18005a00e`

## string_xrefs

- `0x180059e60`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180059ec8`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005a01a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`

## pseudocode

```c

```
