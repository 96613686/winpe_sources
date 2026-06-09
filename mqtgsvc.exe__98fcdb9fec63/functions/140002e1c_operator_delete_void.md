# operator delete(void *)

- ea: `0x140002e1c`
- end: `0x140002e2c`
- name: `??3@YAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `18`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1400018b0`
- `0x1400020f8`
- `0x140002148`
- `0x1400021f8`
- `0x1400023b0`
- `0x1400027f0`
- `0x14001d0ba`
- `0x14001d1be`
- `0x14001d540`
- `0x14001de06`
- `0x14001de47`
- `0x14001de7d`
- `0x14001dfb4`
- `0x14001e031`
- `0x14001e3a0`
- `0x14001e54c`
- `0x14001e978`
- `0x14001ebcf`

## import_xrefs

- `msvcrt!free` at `0x140002e20`
- `msvcrt!free` at `0x140002e20`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  free(a1);
}

```

## disassembly

```asm
0x140002e1c  sub     rsp, 28h
0x140002e20  call    cs:__imp_free
0x140002e26  nop
0x140002e27  add     rsp, 28h
0x140002e2b  retn
```
