# _guard_dispatch_icall

- ea: `0x14001fc70`
- end: `0x14001fc76`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `110`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001b30`
- `0x140002ec8`
- `0x140003bf4`
- `0x140003cb4`
- `0x140003d98`
- `0x140003ed4`
- `0x140004080`
- `0x1400041f8`
- `0x140004364`
- `0x140004434`
- `0x140004550`
- `0x140004684`
- `0x140004788`
- `0x1400048b0`
- `0x1400049c0`
- `0x140004a68`
- `0x140004b4c`
- `0x140004c5c`
- `0x140004d30`
- `0x140004e58`
- `0x140004f5c`
- `0x140005050`
- `0x1400051b4`
- `0x140006bc0`
- `0x14000877c`
- `0x140008cdc`
- `0x1400097f4`
- `0x14000b888`
- `0x14000b974`
- `0x14000ba7c`
- `0x14000bb4c`
- `0x14000bbfc`
- `0x14000bcd8`
- `0x14000bd80`
- `0x14000be58`
- `0x14000bf00`
- `0x14000c004`
- `0x14000c0d4`
- `0x14000c1cc`
- `0x14000c2e0`
- `0x14000c3b4`
- `0x14000c4ac`
- `0x14000c5e0`
- `0x14000c704`
- `0x14000c838`
- `0x14000c92c`
- `0x14000ca20`
- `0x14000cba8`
- `0x14000cd4c`
- `0x14000ce70`

## callees

- `0x14001fca0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x14001fc70  jmp     cs:__guard_dispatch_icall_fptr
```
