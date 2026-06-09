# LsapCompareDomainNames

- ea: `0x18001f340`
- end: `0x18001f512`
- name: `LsapCompareDomainNames`
- size: `466`
- prototype: `__int64 __fastcall(PUNICODE_STRING DomainName1, PUNICODE_STRING DomainName2, PUNICODE_STRING)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cc60`
- `0x180020270`
- `0x1801065e4`

## callees

- `0x18001f340`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f45d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f476`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f45d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f476`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f36f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f3d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f36f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f3d4`
- `ntdll!RtlEqualDomainName` at `0x18001f425`
- `ntdll!RtlEqualDomainName` at `0x18001f4d4`
- `ntdll!RtlEqualDomainName` at `0x18001f425`
- `ntdll!RtlEqualDomainName` at `0x18001f4d4`
- `DNSAPI!DnsNameCompare_W` at `0x18001f43f`
- `DNSAPI!DnsNameCompare_W` at `0x18001f4fc`
- `DNSAPI!DnsNameCompare_W` at `0x18001f43f`
- `DNSAPI!DnsNameCompare_W` at `0x18001f4fc`

## pseudocode

```c

```
