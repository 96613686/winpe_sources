# CShellBrowser2::v_OnCommand(unsigned __int64,__int64)

- ea: `0x180205ef0`
- end: `0x18020723f`
- name: `?v_OnCommand@CShellBrowser2@@EEAA_J_K_J@Z`
- size: `4943`
- prototype: `__int64 __fastcall(CShellBrowser2 *__hidden this, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `49`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1801ffac8`
- `0x180207c30`

## callees

- `0x180005030`
- `0x1800144d0`
- `0x1800184f0`
- `0x18004b960`
- `0x18004d964`
- `0x180074e98`
- `0x18007b178`
- `0x180097ff0`
- `0x1800c8c9c`
- `0x1800d1c00`
- `0x1801b6680`
- `0x1801b6dc0`
- `0x1801bdad0`
- `0x1801c07a8`
- `0x1801c0844`
- `0x1801f3be4`
- `0x1801f5ac8`
- `0x1801f626c`
- `0x1801f7b94`
- `0x1801f9f68`
- `0x1801fae60`
- `0x1801fc8c0`
- `0x1801fcafc`
- `0x1801fd32c`
- `0x1801fd8f0`
- `0x1801ffac8`
- `0x1801ffe90`
- `0x180200028`
- `0x180200178`
- `0x180200dbc`
- `0x180201230`
- `0x1802012d8`
- `0x180202d98`
- `0x180203d18`
- `0x180203e30`
- `0x180204920`
- `0x180204f38`
- `0x180205ef0`
- `0x18020782c`
- `0x1802c58e8`
- `0x1803f5428`
- `0x1804211f0`
- `0x1804256a0`
- `0x18051ea84`
- `0x180557a1c`
- `0x180566458`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180206fcc`
- `KERNEL32!IsDebuggerPresent` at `0x180206fcc`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1802062a2`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180206c75`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1802062a2`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180206c75`
- `USER32!GetKeyState` at `0x180206fa5`
- `USER32!GetKeyState` at `0x180206fbb`
- `USER32!GetKeyState` at `0x180206fa5`
- `USER32!GetKeyState` at `0x180206fbb`
- `USER32!AllowSetForegroundWindow` at `0x1802065a3`
- `USER32!AllowSetForegroundWindow` at `0x180206925`
- `USER32!AllowSetForegroundWindow` at `0x180206a63`
- `USER32!AllowSetForegroundWindow` at `0x1802065a3`
- `USER32!AllowSetForegroundWindow` at `0x180206925`
- `USER32!AllowSetForegroundWindow` at `0x180206a63`
- `OLEAUT32!__imp_SysFreeString` at `0x1802067c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18020697f`
- `OLEAUT32!__imp_SysFreeString` at `0x1802067c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18020697f`
- `OLEAUT32!__imp_VariantClear` at `0x1802067af`
- `OLEAUT32!__imp_VariantClear` at `0x1802067af`
- `SHELL32!__imp_ILFree` at `0x18020631a`
- `SHELL32!__imp_ILFree` at `0x18020631a`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802066b9`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802066b9`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180205f7e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18020700e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180205f7e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18020700e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180206049`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1802071d7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180206049`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1802071d7`
- `WININET!InternetFortezzaCommand` at `0x180206151`
- `WININET!InternetFortezzaCommand` at `0x180206151`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18020695a`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18020695a`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180206f85`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x180206f85`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1802068a6`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1802068a6`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18020696e`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18020696e`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180206a6f`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180206f68`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180206a6f`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x180206f68`

## pseudocode

```c

```
