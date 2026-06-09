# operator delete(void *)

- ea: `0x14000181c`
- end: `0x14000182c`
- name: `??3@YAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1400017d0`

## import_xrefs

- `msvcrt!free` at `0x140001820`
- `msvcrt!free` at `0x140001820`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall operator delete(void *a1)
{
  free(a1);
}

```

## disassembly

```asm
0x14000181c  sub     rsp, 28h
0x140001820  call    cs:__imp_free
0x140001826  nop
0x140001827  add     rsp, 28h
0x14000182b  retn
```
