# RunShadow(CommandLineData *,HINSTANCE__ *)

- ea: `0x140064090`
- end: `0x14006424f`
- name: `?RunShadow@@YAJPEAVCommandLineData@@PEAUHINSTANCE__@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(struct CommandLineData *, HINSTANCE)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400647f0`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x140064090`
- `0x1400b2d10`
- `0x140114010`

## import_xrefs

- `USER32!DispatchMessageW` at `0x1400641b5`
- `USER32!DispatchMessageW` at `0x1400641b5`
- `USER32!TranslateMessage` at `0x1400641aa`
- `USER32!TranslateMessage` at `0x1400641aa`
- `USER32!GetMessageW` at `0x140064192`
- `USER32!GetMessageW` at `0x140064192`
- `msvcrt!_wtoi` at `0x1400640c3`
- `msvcrt!_wtoi` at `0x1400640c3`
- `KERNEL32!GetLastError` at `0x1400641bd`
- `KERNEL32!GetLastError` at `0x1400641bd`

## pseudocode

```c

```
