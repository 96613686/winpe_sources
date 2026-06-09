# NlDnsInitialize(void)

- ea: `0x180020978`
- end: `0x180020e2f`
- name: `?NlDnsInitialize@@YAKXZ`
- size: `1207`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18006f490`

## callees

- `0x180007278`
- `0x18001606c`
- `0x1800200a8`
- `0x180020978`
- `0x180024074`
- `0x18003eb40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020e01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020e01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020a56`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020a56`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800209ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800209ec`
- `ntdll!RtlLeaveCriticalSection` at `0x1800209d9`
- `ntdll!RtlLeaveCriticalSection` at `0x180020e0e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800209d9`
- `ntdll!RtlLeaveCriticalSection` at `0x180020e0e`
- `ntdll!RtlEnterCriticalSection` at `0x1800209a2`
- `ntdll!RtlEnterCriticalSection` at `0x1800209e6`
- `ntdll!RtlEnterCriticalSection` at `0x1800209a2`
- `ntdll!RtlEnterCriticalSection` at `0x1800209e6`
- `DNSAPI!DnsValidateName_UTF8` at `0x180020bea`
- `DNSAPI!DnsValidateName_UTF8` at `0x180020c55`
- `DNSAPI!DnsValidateName_UTF8` at `0x180020bea`
- `DNSAPI!DnsValidateName_UTF8` at `0x180020c55`

## string_xrefs

- `0x180020a62`: `\system32\config\netlogon.dnb`
- `0x180020aaa`: `NlDnsInitialize: error reading binary log %ws: %ld.\n`
- `0x180020d1a`: `NlDnsInitialize: Bogus DnsUpdateLocation: %lx.\n`

## pseudocode

```c

```
