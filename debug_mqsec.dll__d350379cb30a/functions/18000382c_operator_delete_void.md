# operator delete(void *)

- ea: `0x18000382c`
- end: `0x18000383c`
- name: `??3@YAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `17`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001864`
- `0x1800018b4`
- `0x180001a20`
- `0x180001bd0`
- `0x180002010`
- `0x180002d70`
- `0x18002fcb1`
- `0x18002fdab`
- `0x180030084`
- `0x180030096`
- `0x1800302a2`
- `0x1800303a5`
- `0x1800303c9`
- `0x180030411`
- `0x18003070a`
- `0x1800307f4`
- `0x180030862`

## import_xrefs

- `msvcrt!free` at `0x180003830`
- `msvcrt!free` at `0x180003830`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  free(a1);
}

```

## disassembly

```asm
0x18000382c  sub     rsp, 28h
0x180003830  call    cs:__imp_free
0x180003836  nop
0x180003837  add     rsp, 28h
0x18000383b  retn
```
