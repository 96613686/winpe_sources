# CRdpUdpConnection::OnDataReceived(uchar *,unsigned __int64)

- ea: `0x1800bf4b8`
- end: `0x1800c07a0`
- name: `?OnDataReceived@CRdpUdpConnection@@QEAAJPEAE_K@Z`
- size: `4840`
- prototype: `__int64 __fastcall(CRdpUdpConnection *__hidden this, unsigned __int8 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x1800bd310`

## callees

- `0x180001130`
- `0x180003280`
- `0x1800033b4`
- `0x180003e34`
- `0x180005dec`
- `0x18000a610`
- `0x18000a7d0`
- `0x18000a8d0`
- `0x18000aabc`
- `0x18000ab80`
- `0x18000adf0`
- `0x1800186a0`
- `0x1800186d0`
- `0x180024b40`
- `0x180024c14`
- `0x180082910`
- `0x1800829d4`
- `0x1800bf4b8`
- `0x1804306e0`
- `0x18043089c`
- `0x1804313c0`
- `0x180431420`
- `0x1804314e4`
- `0x180688f1a`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800c0412`
- `msvcrt!memcpy_s` at `0x1800c056a`
- `msvcrt!memcpy_s` at `0x1800c0412`
- `msvcrt!memcpy_s` at `0x1800c056a`
- `ADVAPI32!EventActivityIdControl` at `0x1800bf9c0`
- `ADVAPI32!EventActivityIdControl` at `0x1800bf9c0`
- `WS2_32!__imp_ntohl` at `0x1800bfe05`
- `WS2_32!__imp_ntohl` at `0x1800c043b`
- `WS2_32!__imp_ntohl` at `0x1800bfe05`
- `WS2_32!__imp_ntohl` at `0x1800c043b`
- `WS2_32!__imp_ntohs` at `0x1800bf698`
- `WS2_32!__imp_ntohs` at `0x1800bfdf3`
- `WS2_32!__imp_ntohs` at `0x1800c042e`
- `WS2_32!__imp_ntohs` at `0x1800bf698`
- `WS2_32!__imp_ntohs` at `0x1800bfdf3`
- `WS2_32!__imp_ntohs` at `0x1800c042e`

## string_xrefs

- `0x1800bf9ee`: `UDP connection security cookie matched found`
- `0x1800c067c`: `Dropping spurious packet`
- `0x1800c03ae`: `CRdpUdpConnection::OnDataReceived - Protocol v4+, SYNRECEIVED establishing connection immediately (no ACK processing)`
- `0x1800c04fd`: `CRdpUdpConnection::OnDataReceived - Valid ACK received, connection established (passive open)`

## pseudocode

```c

```
