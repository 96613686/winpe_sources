# Mso::Http::CHttpRequest_WinHttp_Base::SetHttpProtocolUsed(void)

- ea: `0x1800e18a8`
- end: `0x1800e1bf1`
- name: `?SetHttpProtocolUsed@CHttpRequest_WinHttp_Base@Http@Mso@@IEAAXXZ`
- size: `841`
- prototype: `void __fastcall(Mso::Http::CHttpRequest_WinHttp_Base *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800e5728`
- `0x1800e8e88`

## callees

- `0x18000adf0`
- `0x180012bf8`
- `0x18003e690`
- `0x18005ace0`
- `0x1800de970`
- `0x1800df75c`
- `0x1800e18a8`
- `0x1800f3d10`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e1986`
- `KERNEL32!GetLastError` at `0x1800e1986`
- `WINHTTP!WinHttpQueryOption` at `0x1800e1975`
- `WINHTTP!WinHttpQueryOption` at `0x1800e1b8c`
- `WINHTTP!WinHttpQueryOption` at `0x1800e1975`
- `WINHTTP!WinHttpQueryOption` at `0x1800e1b8c`

## string_xrefs

- `0x1800e198f`: `ActualProtocol`
- `0x1800e19b4`: `CurrentDesiredProtocol`
- `0x1800e1aae`: `SetHttpProtocolUsed()`

## pseudocode

```c

```
