# CreateBitmap

- ea: `0x180048720`
- end: `0x18004878e`
- name: `CreateBitmap`
- size: `110`
- prototype: `HBITMAP __stdcall(int nWidth, int nHeight, UINT nPlanes, UINT nBitCount, const void *lpBits)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18003bd30`
- `0x1800485c0`
- `0x18008e84c`

## callees

- `0x180026cf0`
- `0x180048720`

## import_xrefs

- `GDI32!pGdiSharedMemory` at `0x180048778`
- `GDI32!GdiSetLastError` at `0x180048757`
- `GDI32!GdiSetLastError` at `0x180048757`
- `win32u!NtGdiCreateBitmap` at `0x180048766`
- `win32u!NtGdiCreateBitmap` at `0x180048766`

## pseudocode

```c
HBITMAP __stdcall CreateBitmap(int nWidth, int nHeight, UINT nPlanes, UINT nBitCount, const void *lpBits)
{
  HDC Bitmap; // rax
  const BITMAPINFOHEADER *v7; // rdx
  DWORD v8; // r8d
  const void *v9; // r9

  if ( !nWidth || !nHeight )
    return *(HBITMAP *)(pGdiSharedMemory + 1573208LL);
  if ( lpBits && ((nHeight * (((nBitCount * nPlanes * nWidth + 15) >> 3) & 0x1FFFFFFE)) & 0x80000000) != 0 )
  {
    GdiSetLastError(87);
    return 0;
  }
  else
  {
    Bitmap = (HDC)NtGdiCreateBitmap(nWidth, nHeight, nPlanes, nBitCount, lpBits);
    return GdiTrackHCreate(Bitmap, v7, v8, v9);
  }
}

```

## disassembly

```asm
0x180048720  sub     rsp, 38h
0x180048724  test    ecx, ecx
0x180048726  jz      short loc_180048778
0x180048728  test    edx, edx
0x18004872a  jz      short loc_180048778
0x18004872c  mov     r10, [rsp+38h+lpBits]
0x180048731  test    r10, r10
0x180048734  jz      short loc_180048761
0x180048736  mov     eax, ecx
0x180048738  imul    eax, r8d
0x18004873c  imul    eax, r9d
0x180048740  add     eax, 0Fh
0x180048743  shr     eax, 3
0x180048746  and     eax, 1FFFFFFEh
0x18004874b  imul    eax, edx
0x18004874e  test    eax, eax
0x180048750  jns     short loc_180048761
0x180048752  mov     ecx, 57h ; 'W'
0x180048757  call    cs:__imp_GdiSetLastError
0x18004875d  xor     eax, eax
0x18004875f  jmp     short loc_180048789
0x180048761  mov     [rsp+38h+var_18], r10
0x180048766  call    cs:__imp_NtGdiCreateBitmap
0x18004876c  mov     rcx, rax
0x18004876f  add     rsp, 38h
0x180048773  jmp     GdiTrackHCreate
0x180048778  mov     rax, cs:__imp_pGdiSharedMemory
0x18004877f  mov     rax, [rax]
0x180048782  mov     rax, [rax+180158h]
0x180048789  add     rsp, 38h
0x18004878d  retn
```
