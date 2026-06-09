# CredpValidateTargetName

- ea: `0x18003db80`
- end: `0x18003e890`
- name: `CredpValidateTargetName`
- size: `3344`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, unsigned int@<edx>, __int64, __int64, __int64, PUNICODE_STRING DestinationString, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18003bb50`
- `0x180043e74`

## callees

- `0x180011278`
- `0x18003db80`
- `0x18003e8a0`
- `0x18003ee94`
- `0x18005608c`
- `0x180078c14`
- `0x1800827a0`
- `0x180088f64`
- `0x18008e360`
- `0x180097c3c`
- `0x18009829c`
- `0x1800af994`
- `0x1800bd6e0`
- `0x1800bd6ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003e30c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003e30c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003df19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003df6f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003df19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003df6f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003e5ac`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003e5ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003deab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e04e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e0ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e734`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e864`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003deab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e04e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e0ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e734`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e864`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ddb2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e4ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e5ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ddb2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e4ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e5ea`
- `ntdll!RtlEqualUnicodeString` at `0x18003e3b2`
- `ntdll!RtlEqualUnicodeString` at `0x18003e3b2`
- `ntdll!RtlInitUnicodeString` at `0x18003dbe8`
- `ntdll!RtlInitUnicodeString` at `0x18003e379`
- `ntdll!RtlInitUnicodeString` at `0x18003e390`
- `ntdll!RtlInitUnicodeString` at `0x18003dbe8`
- `ntdll!RtlInitUnicodeString` at `0x18003e379`
- `ntdll!RtlInitUnicodeString` at `0x18003e390`
- `DNSAPI!DnsValidateName_W` at `0x18003dfcc`
- `DNSAPI!DnsValidateName_W` at `0x18003e28b`
- `DNSAPI!DnsValidateName_W` at `0x18003dfcc`
- `DNSAPI!DnsValidateName_W` at `0x18003e28b`
- `netutils!NetpIsDomainNameValid` at `0x18003e3e1`
- `netutils!NetpIsDomainNameValid` at `0x18003e663`
- `netutils!NetpIsDomainNameValid` at `0x18003e3e1`
- `netutils!NetpIsDomainNameValid` at `0x18003e663`
- `netutils!NetpIsShareNameValid` at `0x18003e5c9`
- `netutils!NetpIsShareNameValid` at `0x18003e5c9`

## pseudocode

```c

```
