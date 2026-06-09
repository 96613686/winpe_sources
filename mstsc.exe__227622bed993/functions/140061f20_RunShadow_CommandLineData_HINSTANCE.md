# RunShadow(CommandLineData *,HINSTANCE__ *)

- ea: `0x140061f20`
- end: `0x1400620df`
- name: `?RunShadow@@YAJPEAVCommandLineData@@PEAUHINSTANCE__@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(struct CommandLineData *, HINSTANCE)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140062680`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x140061f20`
- `0x1400b0ba0`
- `0x140112010`

## import_xrefs

- `USER32!DispatchMessageW` at `0x140062045`
- `USER32!DispatchMessageW` at `0x140062045`
- `USER32!TranslateMessage` at `0x14006203a`
- `USER32!TranslateMessage` at `0x14006203a`
- `USER32!GetMessageW` at `0x140062022`
- `USER32!GetMessageW` at `0x140062022`
- `msvcrt!_wtoi` at `0x140061f53`
- `msvcrt!_wtoi` at `0x140061f53`
- `KERNEL32!GetLastError` at `0x14006204d`
- `KERNEL32!GetLastError` at `0x14006204d`

## pseudocode

```c

```
