# operator delete(void *)

- ea: `0x1800027f4`
- end: `0x180002804`
- name: `??3@YAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `9`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001e90`
- `0x180005680`
- `0x180008490`
- `0x180008550`
- `0x18000e200`
- `0x18000f250`
- `0x18002494f`
- `0x180024ed8`
- `0x1800254a3`

## import_xrefs

- `msvcrt!free` at `0x1800027f8`
- `msvcrt!free` at `0x1800027f8`

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
0x1800027f4  sub     rsp, 28h
0x1800027f8  call    cs:__imp_free
0x1800027fe  nop
0x1800027ff  add     rsp, 28h
0x180002803  retn
```
