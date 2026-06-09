# cdp::Socket::Thread::CloseSocket(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> &)

- ea: `0x180087998`
- end: `0x180087aec`
- name: `?CloseSocket@Thread@Socket@cdp@@QEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@@Z`
- size: `340`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180087690`
- `0x180171560`
- `0x1802da4e0`

## callees

- `0x1800110f8`
- `0x1800874fc`
- `0x180087560`
- `0x180087998`
- `0x180087af4`
- `0x18008dbc0`
- `0x1801fc5e8`
- `0x1802cc148`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087a88`
- `msvcp_win!_Mtx_unlock` at `0x180087ad6`
- `msvcp_win!_Mtx_unlock` at `0x180087ad6`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180087a7e`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180087a7e`
- `WS2_32!__imp_closesocket` at `0x180087a57`
- `WS2_32!__imp_closesocket` at `0x180087abc`
- `WS2_32!__imp_closesocket` at `0x180087a57`
- `WS2_32!__imp_closesocket` at `0x180087abc`

## pseudocode

```c

```
