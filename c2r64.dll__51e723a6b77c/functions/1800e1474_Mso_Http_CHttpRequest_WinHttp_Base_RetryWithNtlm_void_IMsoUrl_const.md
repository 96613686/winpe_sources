# Mso::Http::CHttpRequest_WinHttp_Base::RetryWithNtlm(void *,IMsoUrl const &)

- ea: `0x1800e1474`
- end: `0x1800e1803`
- name: `?RetryWithNtlm@CHttpRequest_WinHttp_Base@Http@Mso@@IEAAXPEAXAEBUIMsoUrl@@@Z`
- size: `911`
- prototype: `void(Mso::Http::CHttpRequest_WinHttp_Base *__hidden this, void *, const struct IMsoUrl *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800e5728`
- `0x1800e8ef8`

## callees

- `0x18000adf0`
- `0x18000c2dc`
- `0x1800258b4`
- `0x18003aa9c`
- `0x18003e690`
- `0x180063814`
- `0x180074d44`
- `0x1800deab0`
- `0x1800deefc`
- `0x1800dfbc0`
- `0x1800e1474`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e162a`
- `KERNEL32!GetLastError` at `0x1800e16c2`
- `KERNEL32!GetLastError` at `0x1800e1729`
- `KERNEL32!GetLastError` at `0x1800e162a`
- `KERNEL32!GetLastError` at `0x1800e16c2`
- `KERNEL32!GetLastError` at `0x1800e1729`
- `WINHTTP!WinHttpSetOption` at `0x1800e1614`
- `WINHTTP!WinHttpSetOption` at `0x1800e1614`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x1800e14d9`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x1800e14d9`
- `WINHTTP!WinHttpSetCredentials` at `0x1800e16a8`
- `WINHTTP!WinHttpSetCredentials` at `0x1800e16a8`

## string_xrefs

- `0x1800e16e9`: `NTLM is not supported. Skipping retry attempt`
- `0x1800e1793`: `Failed to perform WinHttpQueryAuthSchemes on the request. Skipping retry attempt`

## pseudocode

```c

```
