# NlQueryClientSiteViaDNS(_DOMAIN_INFO *,ushort const *,ushort const *,sockaddr *,_NL_SITE_ENTRY * *)

- ea: `0x180077d88`
- end: `0x1800782fb`
- name: `?NlQueryClientSiteViaDNS@@YAKPEAU_DOMAIN_INFO@@PEBG1PEAUsockaddr@@PEAPEAU_NL_SITE_ENTRY@@@Z`
- size: `1395`
- prototype: `unsigned int(struct _DOMAIN_INFO *, const unsigned __int16 *, const unsigned __int16 *, struct sockaddr *, struct _NL_SITE_ENTRY **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180077cb0`

## callees

- `0x180003340`
- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x18000f3e4`
- `0x180077d88`
- `0x180078bd0`
- `0x180079a60`
- `0x180090180`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078251`
- `DNSAPI!DnsFree` at `0x1800782a3`
- `DNSAPI!DnsFree` at `0x1800782bb`
- `DNSAPI!DnsFree` at `0x1800782a3`
- `DNSAPI!DnsFree` at `0x1800782bb`
- `DNSAPI!DnsQuery_W` at `0x180077ebd`
- `DNSAPI!DnsQuery_W` at `0x180077f11`
- `DNSAPI!DnsQuery_W` at `0x180077ebd`
- `DNSAPI!DnsQuery_W` at `0x180077f11`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsQueryDnsHostNameForNetLogon` at `0x180077dec`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsQueryDnsHostNameForNetLogon` at `0x180077dec`

## string_xrefs

- `0x1800781d3`: `onecore\ds\netapi\svcdlls\logonsrv\server\netlogon.cxx`

## pseudocode

```c

```
