# CRdpClipMainWnd::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140004fb0`
- end: `0x140005678`
- name: `?WndProc@CRdpClipMainWnd@@MEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1736`
- prototype: `__int64 __fastcall(CRdpClipMainWnd *__hidden this, HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000429c`
- `0x140004b1c`
- `0x140004e60`
- `0x140004fb0`
- `0x1400056c4`
- `0x140005750`
- `0x14000a150`
- `0x14000a798`
- `0x14000f824`
- `0x14000fe28`
- `0x1400103e8`
- `0x140013cd0`
- `0x140013fd0`
- `0x1400177b0`
- `0x140027de0`
- `0x140027ea4`
- `0x1400365d0`
- `0x14006b010`

## import_xrefs

- `USER32!DefWindowProcW` at `0x140005001`
- `USER32!DefWindowProcW` at `0x140005001`
- `USER32!PostMessageW` at `0x14000565b`
- `USER32!PostMessageW` at `0x14000565b`
- `USER32!PostQuitMessage` at `0x140005665`
- `USER32!PostQuitMessage` at `0x140005665`
- `WINSTA!WinStationIsSessionRemoteable` at `0x14000539b`
- `WINSTA!WinStationIsSessionRemoteable` at `0x14000539b`

## string_xrefs

- `0x1400055d0`: `RdpDisplayControlHandler::OnDisplayChangeCompleted failed. Non Fatal`

## pseudocode

```c

```
