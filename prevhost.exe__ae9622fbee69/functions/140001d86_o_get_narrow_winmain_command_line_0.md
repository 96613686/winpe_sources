# _o__get_narrow_winmain_command_line_0

- ea: `0x140001d86`
- end: `0x140001d8c`
- name: `_o__get_narrow_winmain_command_line_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400012c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_narrow_winmain_command_line` at `0x140001d86`

## pseudocode

```c
// attributes: thunk
__int64 o__get_narrow_winmain_command_line_0()
{
  return _o__get_narrow_winmain_command_line();
}

```

## disassembly

```asm
0x140001d86  jmp     cs:__imp__o__get_narrow_winmain_command_line
```
