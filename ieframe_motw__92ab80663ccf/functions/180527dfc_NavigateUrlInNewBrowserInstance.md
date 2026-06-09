# NavigateUrlInNewBrowserInstance

- ea: `0x180527dfc`
- end: `0x180528152`
- name: `NavigateUrlInNewBrowserInstance`
- size: `854`
- prototype: `__int64 __fastcall(OLECHAR *psz)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cfc30`
- `0x18011f500`
- `0x180190e80`
- `0x1803c8bf0`
- `0x180528158`
- `0x18052aea0`
- `0x180589c6c`

## callees

- `0x1800c562c`
- `0x1805279c8`
- `0x180527dfc`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180527e7d`
- `KERNEL32!GetCurrentThreadId` at `0x180527e7d`
- `USER32!AllowSetForegroundWindow` at `0x180527ed0`
- `USER32!AllowSetForegroundWindow` at `0x180528003`
- `USER32!AllowSetForegroundWindow` at `0x180527ed0`
- `USER32!AllowSetForegroundWindow` at `0x180528003`
- `OLEAUT32!__imp_SysAllocString` at `0x18052807a`
- `OLEAUT32!__imp_SysAllocString` at `0x18052807a`
- `OLEAUT32!__imp_SysFreeString` at `0x1805280e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1805280f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180528109`
- `OLEAUT32!__imp_SysFreeString` at `0x18052812b`
- `OLEAUT32!__imp_SysFreeString` at `0x1805280e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1805280f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180528109`
- `OLEAUT32!__imp_SysFreeString` at `0x18052812b`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x180527e8f`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x180527e8f`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180527e2d`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180527f87`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180527e2d`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180527f87`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180527e59`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180527e59`
- `urlmon!__imp_IsProtectedModeURL` at `0x180527fa0`
- `urlmon!__imp_IsProtectedModeURL` at `0x180527fa0`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x180527fec`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x180527fec`

## pseudocode

```c

```
