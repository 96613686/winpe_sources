# InstallAllPortMonitorsFromInf(HWND__ *,void *,ushort *)

- ea: `0x18001706c`
- end: `0x180017186`
- name: `?InstallAllPortMonitorsFromInf@@YAHPEAUHWND__@@PEAXPEAG@Z`
- size: `282`
- prototype: `__int64 __fastcall(HWND hWnd, HINF InfHandle, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180017550`

## callees

- `0x18001706c`
- `0x18001718c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017163`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017171`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017163`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017171`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001709d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800170b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001709d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800170b4`
- `SETUPAPI!SetupGetStringFieldW` at `0x1800170f9`
- `SETUPAPI!SetupGetStringFieldW` at `0x18001711f`
- `SETUPAPI!SetupGetStringFieldW` at `0x1800170f9`
- `SETUPAPI!SetupGetStringFieldW` at `0x18001711f`
- `SETUPAPI!SetupFindNextLine` at `0x180017156`
- `SETUPAPI!SetupFindNextLine` at `0x180017156`
- `SETUPAPI!SetupFindFirstLineW` at `0x1800170d8`
- `SETUPAPI!SetupFindFirstLineW` at `0x1800170d8`

## pseudocode

```c

```
