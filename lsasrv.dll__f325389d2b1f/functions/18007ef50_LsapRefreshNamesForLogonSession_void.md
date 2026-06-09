# LsapRefreshNamesForLogonSession(void *)

- ea: `0x18007ef50`
- end: `0x18007f3aa`
- name: `?LsapRefreshNamesForLogonSession@@YAKPEAX@Z`
- size: `1114`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003890`
- `0x180008340`
- `0x180009330`
- `0x1800093b0`
- `0x180009410`
- `0x18000c300`
- `0x18007ef50`
- `0x18007f3b0`
- `0x1800b86d0`
- `0x1800bd6e0`
- `0x1800cf0dc`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007f2be`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007f2be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007f035`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007f035`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007f007`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007f388`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007f007`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007f388`
- `ntdll!RtlReleaseResource` at `0x18007f170`
- `ntdll!RtlReleaseResource` at `0x18007f233`
- `ntdll!RtlReleaseResource` at `0x18007f338`
- `ntdll!RtlReleaseResource` at `0x18007f170`
- `ntdll!RtlReleaseResource` at `0x18007f233`
- `ntdll!RtlReleaseResource` at `0x18007f338`
- `ntdll!NtClose` at `0x18007efd2`
- `ntdll!NtClose` at `0x18007efd2`
- `ntdll!NtSetInformationThread` at `0x18007f2ff`
- `ntdll!NtSetInformationThread` at `0x18007f2ff`

## pseudocode

```c

```
