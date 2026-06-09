# NlSetOutgoingPassword(_CLIENT_SESSION *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong)

- ea: `0x180038ad0`
- end: `0x180038dc7`
- name: `?NlSetOutgoingPassword@@YAJPEAU_CLIENT_SESSION@@PEAU_UNICODE_STRING@@1KK@Z`
- size: `759`
- prototype: `__int64 __usercall@<rax>(struct _CLIENT_SESSION *@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180033a34`

## callees

- `0x180007278`
- `0x18000e270`
- `0x18000ed34`
- `0x1800366e8`
- `0x180038ad0`
- `0x18003e71c`
- `0x18003f054`
- `0x18003f540`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180038be1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180038be1`
- `LSASRV!LsarClose` at `0x180038d1a`
- `LSASRV!LsarClose` at `0x180038d1a`
- `LSASRV!LsarSetSecret` at `0x180038dae`
- `LSASRV!LsarSetSecret` at `0x180038dae`
- `LSASRV!LsaIIsContainerized` at `0x180038b5c`
- `LSASRV!LsaIIsContainerized` at `0x180038b5c`
- `LSASRV!LsarSetTrustedDomainInfoByName` at `0x180038c66`
- `LSASRV!LsarSetTrustedDomainInfoByName` at `0x180038c66`
- `ntdll!RtlInitUnicodeString` at `0x180038b3f`
- `ntdll!RtlInitUnicodeString` at `0x180038b56`
- `ntdll!RtlInitUnicodeString` at `0x180038b3f`
- `ntdll!RtlInitUnicodeString` at `0x180038b56`

## string_xrefs

- `0x180038d54`: `NlSetOutgoiningPassword: cannot NlOpenSecret 0x%lx\n`

## pseudocode

```c

```
