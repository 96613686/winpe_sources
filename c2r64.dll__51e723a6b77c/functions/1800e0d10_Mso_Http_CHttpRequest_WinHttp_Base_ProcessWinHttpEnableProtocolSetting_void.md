# Mso::Http::CHttpRequest_WinHttp_Base::ProcessWinHttpEnableProtocolSetting(void)

- ea: `0x1800e0d10`
- end: `0x1800e1027`
- name: `?ProcessWinHttpEnableProtocolSetting@CHttpRequest_WinHttp_Base@Http@Mso@@IEAAXXZ`
- size: `791`
- prototype: `void __fastcall(Mso::Http::CHttpRequest_WinHttp_Base *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800e4d80`
- `0x1800eb26c`

## callees

- `0x18000adf0`
- `0x180012bf8`
- `0x18003e690`
- `0x18005ace0`
- `0x1800deb40`
- `0x1800def9c`
- `0x1800df75c`
- `0x1800e0d10`
- `0x1800f3d10`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e0dd6`
- `KERNEL32!GetLastError` at `0x1800e0dd6`
- `WINHTTP!WinHttpSetOption` at `0x1800e0dc1`
- `WINHTTP!WinHttpSetOption` at `0x1800e0ff4`
- `WINHTTP!WinHttpSetOption` at `0x1800e0dc1`
- `WINHTTP!WinHttpSetOption` at `0x1800e0ff4`

## string_xrefs

- `0x1800e0f24`: `WindowsEnabledHttpProtocol`
- `0x1800e0e42`: `DesiredHttpProtocol`
- `0x1800e0ea8`: `ProcessWinHttpEnableProtocolSetting() Setting the enabled Http protocol.`
- `0x1800e0fa3`: `Setting WINHTTP_OPTION_ENABLE_HTTP_PROTOCOL on the WinHttp request handle`

## pseudocode

```c

```
