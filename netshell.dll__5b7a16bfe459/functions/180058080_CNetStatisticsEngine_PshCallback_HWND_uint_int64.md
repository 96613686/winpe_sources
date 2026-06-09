# CNetStatisticsEngine::PshCallback(HWND__ *,uint,__int64)

- ea: `0x180058080`
- end: `0x180058173`
- name: `?PshCallback@CNetStatisticsEngine@@SAHPEAUHWND__@@I_J@Z`
- size: `243`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180017674`
- `0x180058080`

## import_xrefs

- `SHELL32!__imp_SetWindowRelaunchProperties` at `0x1800580d3`
- `SHELL32!__imp_SetWindowRelaunchProperties` at `0x180058107`
- `SHELL32!__imp_SetWindowRelaunchProperties` at `0x1800580d3`
- `SHELL32!__imp_SetWindowRelaunchProperties` at `0x180058107`
- `USER32!SendMessageW` at `0x180058146`
- `USER32!SendMessageW` at `0x180058160`
- `USER32!SendMessageW` at `0x180058146`
- `USER32!SendMessageW` at `0x180058160`
- `USER32!GetDlgItem` at `0x180058115`
- `USER32!GetDlgItem` at `0x180058115`
- `USER32!SetWindowTextW` at `0x180058133`
- `USER32!SetWindowTextW` at `0x180058133`

## string_xrefs

- `0x1800580de`: `@%SystemRoot%\system32\shell32.dll,-4161`
- `0x1800580ed`: `%SystemRoot%\system32\shell32.dll,-22`
- `0x1800580f9`: `%SystemRoot%\system32\control.exe`

## pseudocode

```c

```
