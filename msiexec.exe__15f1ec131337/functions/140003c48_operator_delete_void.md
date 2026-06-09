# operator delete(void *)

- ea: `0x140003c48`
- end: `0x140003c5c`
- name: `??3@YAXPEAX@Z`
- size: `20`
- prototype: `void __fastcall(void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003b80`
- `0x140003ba0`
- `0x140003bc0`
- `0x1400066d8`

## callees

- `0x140003c48`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140003c51`
- `KERNEL32!GlobalFree` at `0x140003c51`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    GlobalFree(a1);
}

```

## disassembly

```asm
0x140003c48  sub     rsp, 28h
0x140003c4c  test    rcx, rcx
0x140003c4f  jz      short loc_140003C57
0x140003c51  call    cs:__imp_GlobalFree
0x140003c57  add     rsp, 28h
0x140003c5b  retn
```
