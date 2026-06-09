# _guard_dispatch_icall

- ea: `0x140005fb0`
- end: `0x140005fb6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `59`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400015c0`
- `0x14000219c`
- `0x140002340`
- `0x140002570`
- `0x1400025a0`
- `0x1400025f4`
- `0x140002638`
- `0x1400026a4`
- `0x140002740`
- `0x1400027f8`
- `0x14000283c`
- `0x1400028f4`
- `0x140002990`
- `0x140002aa0`
- `0x140002b18`
- `0x140002bd8`
- `0x140002fcc`
- `0x14000328c`
- `0x1400033d4`
- `0x140003438`
- `0x140003568`
- `0x1400035dc`
- `0x1400036a0`
- `0x1400037b8`
- `0x1400038ac`
- `0x140003904`
- `0x1400039f0`
- `0x140003fa0`
- `0x140004030`
- `0x1400040c8`
- `0x1400041b8`
- `0x1400042c8`
- `0x140004554`
- `0x1400045ec`
- `0x1400046bc`
- `0x140004718`
- `0x1400047a8`
- `0x140004800`
- `0x140004864`
- `0x1400048b4`
- `0x140004a24`
- `0x140004b18`
- `0x140004bd4`
- `0x140004c88`
- `0x140004d5c`
- `0x140004dc8`
- `0x140004e30`
- `0x140004ea4`
- `0x140004f74`
- `0x14000500c`

## callees

- `0x140005fe0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x140005fb0  jmp     cs:__guard_dispatch_icall_fptr
```
