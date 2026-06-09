# sandbox::SandboxConnection::ValidateInternalPointer(IPrintSandbox * *)

- ea: `0x1800d94ec`
- end: `0x1800d9887`
- name: `?ValidateInternalPointer@SandboxConnection@sandbox@@AEAAJPEAPEAUIPrintSandbox@@@Z`
- size: `923`
- prototype: `__int64 __fastcall(sandbox::SandboxConnection *__hidden this, struct IPrintSandbox **)`
- caller_count: `9`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ff40`
- `0x180020060`
- `0x180034cc0`
- `0x1800d8e00`
- `0x1800d8ec0`
- `0x1800d8fc0`
- `0x1800d9080`
- `0x1800d92a0`
- `0x1800d93c0`

## callees

- `0x180011f74`
- `0x180015e28`
- `0x1800166b4`
- `0x18001683c`
- `0x180020184`
- `0x180022e64`
- `0x1800d78a4`
- `0x1800d794c`
- `0x1800d94ec`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9604`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9617`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9604`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9617`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d95c9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d95c9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d96ad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d96ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d951f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d97b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d951f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d97b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d9556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d9854`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d9556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d9854`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800d9534`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800d97e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800d9534`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800d97e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d959a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d959a`

## string_xrefs

- `0x1800d95c2`: `ole32.dll`
- `0x1800d95fa`: `CreateBindCtx`
- `0x1800d981c`: `A sandbox host is going to be recycled because of policies. m_dwObjectsCreated %u m_dwTimeBeforeRecycle %u`
- `0x1800d979c`: `SetComSecurityBlanket failed: hr: 0x%x`
- `0x1800d9660`: `Session:%u!clsid:E7B3C0E0-FB47-49F6-A66B-8A7C2E4E7B9C`

## pseudocode

```c

```
