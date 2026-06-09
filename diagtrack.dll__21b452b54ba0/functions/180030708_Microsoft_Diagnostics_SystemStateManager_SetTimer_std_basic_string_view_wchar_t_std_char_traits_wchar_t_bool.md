# Microsoft::Diagnostics::SystemStateManager::SetTimer(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool)

- ea: `0x180030708`
- end: `0x18003084e`
- name: `?SetTimer@SystemStateManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z`
- size: `326`
- prototype: ``
- caller_count: `10`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800847c4`
- `0x180085984`
- `0x180110c58`
- `0x18013ba90`
- `0x1801460d4`
- `0x18015f3f0`
- `0x18018d348`
- `0x1801e1d70`
- `0x180283210`
- `0x1802835c8`

## callees

- `0x18002df00`
- `0x18002fa34`
- `0x180030708`
- `0x180030e54`
- `0x18003106c`
- `0x1800310d4`
- `0x1801a9494`
- `0x18020aac0`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x180030743`
- `msvcp_win!_Mtx_lock` at `0x180030743`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180030834`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180030847`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180030834`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180030847`
- `msvcp_win!_Mtx_unlock` at `0x1800307d6`
- `msvcp_win!_Mtx_unlock` at `0x18003080f`
- `msvcp_win!_Mtx_unlock` at `0x1800307d6`
- `msvcp_win!_Mtx_unlock` at `0x18003080f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180030795`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180030795`

## string_xrefs

- `0x18003081d`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`

## pseudocode

```c

```
