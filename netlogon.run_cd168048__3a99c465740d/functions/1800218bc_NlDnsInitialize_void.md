# NlDnsInitialize(void)

- ea: `0x1800218bc`
- end: `0x180021daa`
- name: `?NlDnsInitialize@@YAKXZ`
- size: `1262`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800747cc`

## callees

- `0x180007518`
- `0x180016a70`
- `0x180020f74`
- `0x1800218bc`
- `0x180025114`
- `0x180041390`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800219b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800219b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180021942`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180021942`
- `ntdll!RtlLeaveCriticalSection` at `0x180021923`
- `ntdll!RtlLeaveCriticalSection` at `0x180021d82`
- `ntdll!RtlLeaveCriticalSection` at `0x180021923`
- `ntdll!RtlLeaveCriticalSection` at `0x180021d82`
- `ntdll!RtlEnterCriticalSection` at `0x1800218e6`
- `ntdll!RtlEnterCriticalSection` at `0x180021936`
- `ntdll!RtlEnterCriticalSection` at `0x1800218e6`
- `ntdll!RtlEnterCriticalSection` at `0x180021936`
- `DNSAPI!DnsValidateName_UTF8` at `0x180021b4c`
- `DNSAPI!DnsValidateName_UTF8` at `0x180021bbd`
- `DNSAPI!DnsValidateName_UTF8` at `0x180021b4c`
- `DNSAPI!DnsValidateName_UTF8` at `0x180021bbd`

## string_xrefs

- `0x1800219c4`: `\system32\config\netlogon.dnb`
- `0x180021a0c`: `NlDnsInitialize: error reading binary log %ws: %ld.\n`
- `0x180021c88`: `NlDnsInitialize: Bogus DnsUpdateLocation: %lx.\n`

## pseudocode

```c

```
