# CRdpUdpConnection::OnDataReceived(uchar *,unsigned __int64)

- ea: `0x180148c44`
- end: `0x180149f0e`
- name: `?OnDataReceived@CRdpUdpConnection@@QEAAJPEAE_K@Z`
- size: `4810`
- prototype: `__int64 __fastcall(CRdpUdpConnection *this, u_short *, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x180134080`

## callees

- `0x1800021f4`
- `0x180002bc8`
- `0x180002c8c`
- `0x180003158`
- `0x180003e7c`
- `0x1800043c4`
- `0x180004714`
- `0x180004a94`
- `0x180004da8`
- `0x180007ac0`
- `0x180008400`
- `0x180008690`
- `0x180008900`
- `0x180019a80`
- `0x180019ab0`
- `0x18002a36c`
- `0x18002a5d8`
- `0x180078c20`
- `0x180079624`
- `0x180147bd0`
- `0x180147d78`
- `0x18014888c`
- `0x1801488e0`
- `0x1801489a4`
- `0x180148c44`
- `0x1801614b8`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180149145`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180149145`
- `WS2_32!__imp_ntohl` at `0x18014957c`
- `WS2_32!__imp_ntohl` at `0x180149bb1`
- `WS2_32!__imp_ntohl` at `0x18014957c`
- `WS2_32!__imp_ntohl` at `0x180149bb1`
- `WS2_32!__imp_ntohs` at `0x180148e1d`
- `WS2_32!__imp_ntohs` at `0x18014956a`
- `WS2_32!__imp_ntohs` at `0x180149ba4`
- `WS2_32!__imp_ntohs` at `0x180148e1d`
- `WS2_32!__imp_ntohs` at `0x18014956a`
- `WS2_32!__imp_ntohs` at `0x180149ba4`

## string_xrefs

- `0x180149173`: `UDP connection security cookie matched found`
- `0x180149b25`: `CRdpUdpConnection::OnDataReceived - Protocol v4+, SYNRECEIVED establishing connection immediately (no ACK processing)`
- `0x180149dea`: `Dropping spurious packet`
- `0x180149c73`: `CRdpUdpConnection::OnDataReceived - Valid ACK received, connection established (passive open)`

## pseudocode

```c

```
