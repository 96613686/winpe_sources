# CHttpIoRequestWinHttp::SendStreamModeRequestAsync(bool,bool)

- ea: `0x180320770`
- end: `0x180320b2c`
- name: `?SendStreamModeRequestAsync@CHttpIoRequestWinHttp@@UEAAJ_N0@Z`
- size: `956`
- prototype: `__int64 __fastcall(CHttpIoRequestWinHttp *__hidden this, bool, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x1800011f4`
- `0x1800054f4`
- `0x180082ad8`
- `0x1800922b8`
- `0x180096c68`
- `0x1800dcfa0`
- `0x180123a58`
- `0x18012962c`
- `0x180320770`
- `0x18068c010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1803207cc`
- `KERNEL32!LoadLibraryW` at `0x1803207cc`
- `KERNEL32!GetLastError` at `0x180320860`
- `KERNEL32!GetLastError` at `0x180320871`
- `KERNEL32!GetLastError` at `0x18032091c`
- `KERNEL32!GetLastError` at `0x180320a85`
- `KERNEL32!GetLastError` at `0x180320860`
- `KERNEL32!GetLastError` at `0x180320871`
- `KERNEL32!GetLastError` at `0x18032091c`
- `KERNEL32!GetLastError` at `0x180320a85`
- `KERNEL32!GetProcAddress` at `0x1803207e8`
- `KERNEL32!GetProcAddress` at `0x1803207e8`
- `KERNEL32!FreeLibrary` at `0x18032082e`
- `KERNEL32!FreeLibrary` at `0x18032082e`
- `WINHTTP!WinHttpSendRequest` at `0x180320a6d`
- `WINHTTP!WinHttpSendRequest` at `0x180320a6d`
- `WINHTTP!WinHttpSetOption` at `0x180320852`
- `WINHTTP!WinHttpSetOption` at `0x180320852`

## string_xrefs

- `0x180320938`: `LoadLibrary for WinHttp.dll failed`
- `0x1803207c5`: `WinHttp.dll`

## pseudocode

```c

```
