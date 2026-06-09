# WicaPostInstall_ArpChanged(_PCA_EVENT_TYPE,void *)

- ea: `0x180054430`
- end: `0x18005485a`
- name: `?WicaPostInstall_ArpChanged@@YAKW4_PCA_EVENT_TYPE@@PEAX@Z`
- size: `1066`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callees

- `0x180012920`
- `0x18001b320`
- `0x1800212b0`
- `0x180054430`
- `0x180056256`
- `0x180056262`
- `0x18007a9cf`
- `0x1800ae6fc`
- `0x1800f1f10`
- `0x1800f1fd0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180054546`
- `msvcrt!_wcsicmp` at `0x180054546`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800544e1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800547d6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800544e1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800547d6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005475e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054833`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005475e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054833`
- `ntdll!RtlReAllocateHeap` at `0x18005473b`
- `ntdll!RtlReAllocateHeap` at `0x18005473b`
- `ntdll!RtlAllocateHeap` at `0x18005471b`
- `ntdll!RtlAllocateHeap` at `0x18005471b`

## string_xrefs

- `0x180054790`: `WicaPostInstallp_RemoveNotificationsForExe Failed [%d]`
- `0x1800547b9`: `Removed notifications for EXE %ls.`
- `0x18005449b`: `WicaPostInstall_ArpChanged`
- `0x1800544b4`: `WicaPostInstall_ArpChanged`
- `0x1800544c3`: `ARP key: %ls has been created or modified.`

## pseudocode

```c

```
