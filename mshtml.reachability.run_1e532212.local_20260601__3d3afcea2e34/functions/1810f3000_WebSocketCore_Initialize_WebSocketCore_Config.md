# WebSocketCore::Initialize(WebSocketCore::Config *)

- ea: `0x1810f3000`
- end: `0x1810f35a5`
- name: `?Initialize@WebSocketCore@@AEAAJPEAUConfig@1@@Z`
- size: `1445`
- prototype: `__int64 __fastcall(WebSocketCore *__hidden this, struct WebSocketCore::Config *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1810f2d14`

## callees

- `0x1800168c0`
- `0x18005d080`
- `0x1804e4c1c`
- `0x1810f2720`
- `0x1810f28c0`
- `0x1810f3000`
- `0x1810f36bc`
- `0x1810f3710`
- `0x1810f3e10`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1810f3385`
- `KERNEL32!GetLastError` at `0x1810f3385`
- `KERNEL32!LeaveCriticalSection` at `0x1810f30fd`
- `KERNEL32!LeaveCriticalSection` at `0x1810f30fd`
- `KERNEL32!EnterCriticalSection` at `0x1810f30c1`
- `KERNEL32!EnterCriticalSection` at `0x1810f30c1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1810f30dc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1810f30dc`
- `WININET!HttpOpenRequestW` at `0x1810f3370`
- `WININET!HttpOpenRequestW` at `0x1810f3370`
- `WININET!InternetSetOptionW` at `0x1810f31cc`
- `WININET!InternetSetOptionW` at `0x1810f33bd`
- `WININET!InternetSetOptionW` at `0x1810f33df`
- `WININET!InternetSetOptionW` at `0x1810f3403`
- `WININET!InternetSetOptionW` at `0x1810f3424`
- `WININET!InternetSetOptionW` at `0x1810f31cc`
- `WININET!InternetSetOptionW` at `0x1810f33bd`
- `WININET!InternetSetOptionW` at `0x1810f33df`
- `WININET!InternetSetOptionW` at `0x1810f3403`
- `WININET!InternetSetOptionW` at `0x1810f3424`
- `WININET!InternetOpenW` at `0x1810f312b`
- `WININET!InternetOpenW` at `0x1810f312b`
- `WININET!InternetSetStatusCallbackW` at `0x1810f314f`
- `WININET!InternetSetStatusCallbackW` at `0x1810f314f`
- `WININET!InternetConnectW` at `0x1810f3305`
- `WININET!InternetConnectW` at `0x1810f3305`
- `OLEAUT32!__imp_SysFreeString` at `0x1810f3184`
- `OLEAUT32!__imp_SysFreeString` at `0x1810f3184`
- `OLEAUT32!__imp_SysStringLen` at `0x1810f321e`
- `OLEAUT32!__imp_SysStringLen` at `0x1810f321e`

## string_xrefs

- `0x1810f34ba`: `Sec-WebSocket-Protocol: `
- `0x1810f352b`: `Sec-WebSocket-Protocol: `

## pseudocode

```c

```
