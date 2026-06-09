# CopyBitmapInfoHeader

- ea: `0x1800070c4`
- end: `0x1800070e8`
- name: `CopyBitmapInfoHeader`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800076c4`

## callees

- `0x180007034`
- `0x180017010`

## pseudocode

```c
HLOCAL __fastcall CopyBitmapInfoHeader(__int64 a1)
{
  unsigned int *v1; // rax

  v1 = (unsigned int *)((__int64 (__fastcall *)(__int64, _QWORD, __int64))GetVDMPointer)(a1, 0, 1);
  return CopyAlloc(v1, *v1);
}

```

## disassembly

```asm
0x1800070c4  sub     rsp, 28h
0x1800070c8  mov     rax, cs:GetVDMPointer
0x1800070cf  xor     edx, edx
0x1800070d1  lea     r8d, [rdx+1]
0x1800070d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070da  mov     rcx, rax; Src
0x1800070dd  mov     edx, [rax]; Size
0x1800070df  add     rsp, 28h
0x1800070e3  jmp     CopyAlloc
```
