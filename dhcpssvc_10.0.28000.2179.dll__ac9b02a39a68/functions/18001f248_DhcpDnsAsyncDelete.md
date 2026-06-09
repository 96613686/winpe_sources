# DhcpDnsAsyncDelete

- ea: `0x18001f248`
- end: `0x18001f717`
- name: `DhcpDnsAsyncDelete`
- size: `1231`
- prototype: `__int64 __usercall@<rax>(struct in_addr in@<ecx>, STRSAFE_LPCWSTR pszSrc@<rdx>, __int64, int)`
- caller_count: `4`
- callee_count: `14`
- tags: ``

## callers

- `0x180020094`
- `0x180020608`
- `0x180020bec`
- `0x180020f08`

## callees

- `0x18000282c`
- `0x180003228`
- `0x1800056ac`
- `0x1800058bc`
- `0x18001ebe4`
- `0x18001f248`
- `0x18001fd78`
- `0x18001ffe4`
- `0x180021a98`
- `0x180021e18`
- `0x1800220c4`
- `0x180022340`
- `0x18007c8fc`
- `0x18007d1fc`

## import_xrefs

- `DNSAPI!DnsDhcpSrvRegisterHostNameEx` at `0x18001f555`
- `DNSAPI!DnsDhcpSrvRegisterHostNameEx` at `0x18001f555`
- `WS2_32!__imp_htonl` at `0x18001f40f`
- `WS2_32!__imp_htonl` at `0x18001f40f`
- `WS2_32!__imp_inet_ntoa` at `0x18001f2de`
- `WS2_32!__imp_inet_ntoa` at `0x18001f5f7`
- `WS2_32!__imp_inet_ntoa` at `0x18001f2de`
- `WS2_32!__imp_inet_ntoa` at `0x18001f5f7`
- `KERNEL32!HeapFree` at `0x18001f580`
- `KERNEL32!HeapFree` at `0x18001f68c`
- `KERNEL32!HeapFree` at `0x18001f6e7`
- `KERNEL32!HeapFree` at `0x18001f580`
- `KERNEL32!HeapFree` at `0x18001f68c`
- `KERNEL32!HeapFree` at `0x18001f6e7`

## pseudocode

```c

```
