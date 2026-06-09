# CreateBitmap

- ea: `0x18004ded0`
- end: `0x18004df4b`
- name: `CreateBitmap`
- size: `123`
- prototype: `HBITMAP __stdcall(int nWidth, int nHeight, UINT nPlanes, UINT nBitCount, const void *lpBits)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800479b0`
- `0x18004dd60`
- `0x180094210`

## callees

- `0x18002fda0`
- `0x18004ded0`

## import_xrefs

- `GDI32!pGdiSharedMemory` at `0x18004df34`
- `GDI32!GdiSetLastError` at `0x18004df07`
- `GDI32!GdiSetLastError` at `0x18004df07`
- `win32u!NtGdiCreateBitmap` at `0x18004df1c`
- `win32u!NtGdiCreateBitmap` at `0x18004df1c`

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
0x18004ded0  sub     rsp, 38h
0x18004ded4  test    ecx, ecx
0x18004ded6  jz      short loc_18004DF34
0x18004ded8  test    edx, edx
0x18004deda  jz      short loc_18004DF34
0x18004dedc  mov     r10, [rsp+38h+lpBits]
0x18004dee1  test    r10, r10
0x18004dee4  jz      short loc_18004DF17
0x18004dee6  mov     eax, ecx
0x18004dee8  imul    eax, r8d
0x18004deec  imul    eax, r9d
0x18004def0  add     eax, 0Fh
0x18004def3  shr     eax, 3
0x18004def6  and     eax, 1FFFFFFEh
0x18004defb  imul    eax, edx
0x18004defe  test    eax, eax
0x18004df00  jns     short loc_18004DF17
0x18004df02  mov     ecx, 57h ; 'W'
0x18004df07  call    cs:__imp_GdiSetLastError
0x18004df0e  nop     dword ptr [rax+rax+00h]
0x18004df13  xor     eax, eax
0x18004df15  jmp     short loc_18004DF45
0x18004df17  mov     [rsp+38h+var_18], r10
0x18004df1c  call    cs:__imp_NtGdiCreateBitmap
0x18004df23  nop     dword ptr [rax+rax+00h]
0x18004df28  mov     rcx, rax
0x18004df2b  add     rsp, 38h
0x18004df2f  jmp     GdiTrackHCreate
0x18004df34  mov     rax, cs:__imp_pGdiSharedMemory
0x18004df3b  mov     rax, [rax]
0x18004df3e  mov     rax, [rax+180158h]
0x18004df45  add     rsp, 38h
0x18004df49  retn
```
