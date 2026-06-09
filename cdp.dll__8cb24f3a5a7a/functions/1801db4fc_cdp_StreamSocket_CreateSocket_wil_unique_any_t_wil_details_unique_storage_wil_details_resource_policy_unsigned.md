# cdp::StreamSocket::CreateSocket(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> &,shared::EndpointType)

- ea: `0x1801db4fc`
- end: `0x1801db651`
- name: `?CreateSocket@StreamSocket@cdp@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@W4EndpointType@shared@@@Z`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802d9ac8`

## callees

- `0x18008dbc0`
- `0x1800f06e4`
- `0x1800f5c4c`
- `0x1801db4fc`
- `0x1801db658`
- `0x1801fcb36`
- `0x1802a3cec`

## import_xrefs

- `WS2_32!WSASocketW` at `0x1801db548`
- `WS2_32!WSASocketW` at `0x1801db548`
- `WS2_32!__imp_setsockopt` at `0x1801db5d3`
- `WS2_32!__imp_setsockopt` at `0x1801db5d3`
- `WS2_32!__imp_WSAGetLastError` at `0x1801db55f`
- `WS2_32!__imp_WSAGetLastError` at `0x1801db5de`
- `WS2_32!__imp_WSAGetLastError` at `0x1801db55f`
- `WS2_32!__imp_WSAGetLastError` at `0x1801db5de`

## string_xrefs

- `0x1801db622`: `{"text":"StreamSocket enabled ERTM (RfComm)"}`
- `0x1801db5f2`: `Failed to set ERTM mode (Rfcomm stream socket), WSA error %d`

## pseudocode

```c

```
