# NlSetOutgoingPassword(_CLIENT_SESSION *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong)

- ea: `0x18003ad18`
- end: `0x18003b03a`
- name: `?NlSetOutgoingPassword@@YAJPEAU_CLIENT_SESSION@@PEAU_UNICODE_STRING@@1KK@Z`
- size: `802`
- prototype: `__int64 __usercall@<rax>(struct _CLIENT_SESSION *@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180035924`

## callees

- `0x180007518`
- `0x18000e910`
- `0x18000f3e4`
- `0x1800387d8`
- `0x18003ad18`
- `0x180040f18`
- `0x180041944`
- `0x180041e68`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ae3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ae3b`
- `LSASRV!LsarClose` at `0x18003af80`
- `LSASRV!LsarClose` at `0x18003af80`
- `LSASRV!LsarSetSecret` at `0x18003b01b`
- `LSASRV!LsarSetSecret` at `0x18003b01b`
- `LSASRV!LsaIIsContainerized` at `0x18003adb0`
- `LSASRV!LsaIIsContainerized` at `0x18003adb0`
- `LSASRV!LsarSetTrustedDomainInfoByName` at `0x18003aec6`
- `LSASRV!LsarSetTrustedDomainInfoByName` at `0x18003aec6`
- `ntdll!RtlInitUnicodeString` at `0x18003ad87`
- `ntdll!RtlInitUnicodeString` at `0x18003ada4`
- `ntdll!RtlInitUnicodeString` at `0x18003ad87`
- `ntdll!RtlInitUnicodeString` at `0x18003ada4`

## string_xrefs

- `0x18003afc1`: `NlSetOutgoiningPassword: cannot NlOpenSecret 0x%lx\n`

## pseudocode

```c

```
