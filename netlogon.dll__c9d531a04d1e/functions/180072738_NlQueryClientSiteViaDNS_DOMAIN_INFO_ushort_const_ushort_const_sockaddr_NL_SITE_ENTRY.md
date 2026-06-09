# NlQueryClientSiteViaDNS(_DOMAIN_INFO *,ushort const *,ushort const *,sockaddr *,_NL_SITE_ENTRY * *)

- ea: `0x180072738`
- end: `0x180072c8a`
- name: `?NlQueryClientSiteViaDNS@@YAKPEAU_DOMAIN_INFO@@PEBG1PEAUsockaddr@@PEAPEAU_NL_SITE_ENTRY@@@Z`
- size: `1362`
- prototype: `unsigned int(struct _DOMAIN_INFO *, const unsigned __int16 *, const unsigned __int16 *, struct sockaddr *, struct _NL_SITE_ENTRY **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180072660`

## callees

- `0x180003220`
- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x180072738`
- `0x1800734e8`
- `0x180089a30`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072bf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072bf3`
- `DNSAPI!DnsFree` at `0x180072c3f`
- `DNSAPI!DnsFree` at `0x180072c51`
- `DNSAPI!DnsFree` at `0x180072c3f`
- `DNSAPI!DnsFree` at `0x180072c51`
- `DNSAPI!DnsQuery_W` at `0x18007286b`
- `DNSAPI!DnsQuery_W` at `0x1800728b9`
- `DNSAPI!DnsQuery_W` at `0x18007286b`
- `DNSAPI!DnsQuery_W` at `0x1800728b9`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsQueryDnsHostNameForNetLogon` at `0x18007279c`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsQueryDnsHostNameForNetLogon` at `0x18007279c`

## string_xrefs

- `0x180072b75`: `onecore\ds\netapi\svcdlls\logonsrv\server\netlogon.cxx`

## pseudocode

```c

```
