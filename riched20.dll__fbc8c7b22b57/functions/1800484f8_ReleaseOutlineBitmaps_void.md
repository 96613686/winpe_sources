# ReleaseOutlineBitmaps(void)

- ea: `0x1800484f8`
- end: `0x18004858e`
- name: `?ReleaseOutlineBitmaps@@YAXXZ`
- size: `150`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026f28`

## callees

- `0x1800484f8`

## import_xrefs

- `GDI32!DeleteObject` at `0x180048508`
- `GDI32!DeleteObject` at `0x18004852b`
- `GDI32!DeleteObject` at `0x18004854e`
- `GDI32!DeleteObject` at `0x180048571`
- `GDI32!DeleteObject` at `0x180048508`
- `GDI32!DeleteObject` at `0x18004852b`
- `GDI32!DeleteObject` at `0x18004854e`
- `GDI32!DeleteObject` at `0x180048571`

## pseudocode

```c
void ReleaseOutlineBitmaps(void)
{
  if ( h )
  {
    DeleteObject(h);
    h = 0;
  }
  if ( qword_1800A7320 )
  {
    DeleteObject(qword_1800A7320);
    qword_1800A7320 = 0;
  }
  if ( qword_1800A7318 )
  {
    DeleteObject(qword_1800A7318);
    qword_1800A7318 = 0;
  }
  if ( qword_1800A7310 )
  {
    DeleteObject(qword_1800A7310);
    qword_1800A7310 = 0;
  }
}

```

## disassembly

```asm
0x1800484f8  sub     rsp, 28h
0x1800484fc  mov     rcx, cs:h; ho
0x180048503  test    rcx, rcx
0x180048506  jz      short loc_18004851F
0x180048508  call    cs:__imp_DeleteObject
0x18004850f  nop     dword ptr [rax+rax+00h]
0x180048514  mov     cs:h, 0
0x18004851f  mov     rcx, cs:qword_1800A7320; ho
0x180048526  test    rcx, rcx
0x180048529  jz      short loc_180048542
0x18004852b  call    cs:__imp_DeleteObject
0x180048532  nop     dword ptr [rax+rax+00h]
0x180048537  mov     cs:qword_1800A7320, 0
0x180048542  mov     rcx, cs:qword_1800A7318; ho
0x180048549  test    rcx, rcx
0x18004854c  jz      short loc_180048565
0x18004854e  call    cs:__imp_DeleteObject
0x180048555  nop     dword ptr [rax+rax+00h]
0x18004855a  mov     cs:qword_1800A7318, 0
0x180048565  mov     rcx, cs:qword_1800A7310; ho
0x18004856c  test    rcx, rcx
0x18004856f  jz      short loc_180048588
0x180048571  call    cs:__imp_DeleteObject
0x180048578  nop     dword ptr [rax+rax+00h]
0x18004857d  mov     cs:qword_1800A7310, 0
0x180048588  add     rsp, 28h
0x18004858c  retn
```
