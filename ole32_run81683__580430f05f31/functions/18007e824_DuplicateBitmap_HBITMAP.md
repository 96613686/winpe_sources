# DuplicateBitmap(HBITMAP__ *)

- ea: `0x18007e824`
- end: `0x18007e943`
- name: `?DuplicateBitmap@@YAPEAUHBITMAP__@@PEAU1@@Z`
- size: `287`
- prototype: `HBITMAP__ *__fastcall(HBITMAP__ *hold)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007ee34`

## callees

- `0x18007e824`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18007e88f`
- `KERNELBASE!GlobalAlloc` at `0x18007e88f`
- `KERNELBASE!GlobalFree` at `0x18007e8b1`
- `KERNELBASE!GlobalFree` at `0x18007e920`
- `KERNELBASE!GlobalFree` at `0x18007e8b1`
- `KERNELBASE!GlobalFree` at `0x18007e920`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007e917`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007e917`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007e8a0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007e8a0`
- `GDI32!DeleteObject` at `0x18007e933`
- `GDI32!DeleteObject` at `0x18007e933`
- `GDI32!CreateBitmap` at `0x18007e8f5`
- `GDI32!CreateBitmap` at `0x18007e8f5`
- `GDI32!GetObjectW` at `0x18007e849`
- `GDI32!GetObjectW` at `0x18007e849`
- `GDI32!SetBitmapBits` at `0x18007e90b`
- `GDI32!SetBitmapBits` at `0x18007e90b`
- `GDI32!GetBitmapBits` at `0x18007e8d2`
- `GDI32!GetBitmapBits` at `0x18007e8d2`

## pseudocode

```c
HBITMAP __fastcall DuplicateBitmap(HBITMAP hold)
{
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdx
  int v5; // ebp
  HGLOBAL v6; // rax
  void *v7; // rdi
  void *v8; // rax
  const void *v9; // rsi
  LONG v11; // r14d
  HBITMAP Bitmap; // rax
  HBITMAP v13; // rbx
  tagBITMAP bm; // [rsp+30h] [rbp-48h] BYREF

  memset(&bm, 0, sizeof(bm));
  GetObjectW(hold, 32, &bm);
  v2 = (unsigned int)bm.bmWidthBytes * (unsigned __int64)(unsigned int)bm.bmHeight;
  if ( v2 > 0xFFFFFFFF )
    return 0;
  v3 = bm.bmPlanes * (unsigned __int64)(unsigned int)v2;
  if ( v3 > 0xFFFFFFFF )
    return 0;
  v4 = bm.bmBitsPixel * (unsigned __int64)(unsigned int)v3;
  if ( v4 > 0xFFFFFFFF )
    return 0;
  v5 = bm.bmBitsPixel * (_DWORD)v3;
  v6 = GlobalAlloc(0x42u, (unsigned int)v4);
  v7 = v6;
  if ( !v6 )
    return 0;
  v8 = GlobalLock(v6);
  v9 = v8;
  if ( !v8 )
  {
    GlobalFree(v7);
    return 0;
  }
  v11 = 1;
  GetBitmapBits(hold, v5, v8);
  Bitmap = CreateBitmap(bm.bmWidth, bm.bmHeight, bm.bmPlanes, bm.bmBitsPixel, 0);
  v13 = Bitmap;
  if ( Bitmap )
    v11 = SetBitmapBits(Bitmap, v5, v9);
  GlobalUnlock(v7);
  GlobalFree(v7);
  if ( v13 )
  {
    if ( !v11 )
    {
      DeleteObject(v13);
      return 0;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18007e824  push    rbx
0x18007e826  push    rbp
0x18007e827  push    rsi
0x18007e828  push    rdi
0x18007e829  push    r14
0x18007e82b  sub     rsp, 50h
0x18007e82f  xorps   xmm0, xmm0
0x18007e832  lea     r8, [rsp+78h+bm]; pv
0x18007e837  mov     edx, 20h ; ' '; c
0x18007e83c  mov     rbx, hold
0x18007e83f  movups  xmmword ptr [rsp+78h+bm.bmType], xmm0
0x18007e844  movups  xmmword ptr [rsp+78h+bm.bmPlanes], xmm0
0x18007e849  call    cs:__imp_GetObjectW
0x18007e84f  mov     edx, [rsp+78h+bm.bmHeight]
0x18007e853  mov     r8d, 0FFFFFFFFh
0x18007e859  mov     eax, [rsp+78h+bm.bmWidthBytes]
0x18007e85d  imul    rdx, rax
0x18007e861  cmp     rdx, r8
0x18007e864  ja      short loc_18007E8B7
0x18007e866  movzx   eax, [rsp+78h+bm.bmPlanes]
0x18007e86b  mov     ecx, edx
0x18007e86d  imul    hold, rax
0x18007e871  cmp     hold, r8
0x18007e874  ja      short loc_18007E8B7
0x18007e876  movzx   eax, [rsp+78h+bm.bmBitsPixel]
0x18007e87b  mov     edx, ecx
0x18007e87d  imul    rdx, rax
0x18007e881  cmp     rdx, r8
0x18007e884  ja      short loc_18007E8B7
0x18007e886  mov     ebp, edx
0x18007e888  mov     ecx, 42h ; 'B'; uFlags
0x18007e88d  mov     edx, edx; dwBytes
0x18007e88f  call    cs:__imp_GlobalAlloc
0x18007e895  mov     rdi, rax
0x18007e898  test    rax, rax
0x18007e89b  jz      short loc_18007E8B7
0x18007e89d  mov     hold, rax; hMem
0x18007e8a0  call    cs:__imp_GlobalLock
0x18007e8a6  mov     rsi, rax
0x18007e8a9  test    rax, rax
0x18007e8ac  jnz     short loc_18007E8C4
0x18007e8ae  mov     hold, rdi; hMem
0x18007e8b1  call    cs:__imp_GlobalFree
0x18007e8b7  xor     eax, eax
0x18007e8b9  add     rsp, 50h
0x18007e8bd  pop     r14
0x18007e8bf  pop     rdi
0x18007e8c0  pop     rsi
0x18007e8c1  pop     rbp
0x18007e8c2  pop     rbx
0x18007e8c3  retn
0x18007e8c4  mov     r8, rsi; lpvBits
0x18007e8c7  mov     edx, ebp; cb
0x18007e8c9  mov     hold, rbx; hbit
0x18007e8cc  mov     r14d, 1
0x18007e8d2  call    cs:__imp_GetBitmapBits
0x18007e8d8  movzx   r9d, [rsp+78h+bm.bmBitsPixel]; nBitCount
0x18007e8de  movzx   r8d, [rsp+78h+bm.bmPlanes]; nPlanes
0x18007e8e4  mov     edx, [rsp+78h+bm.bmHeight]; nHeight
0x18007e8e8  mov     ecx, [rsp+78h+bm.bmWidth]; nWidth
0x18007e8ec  mov     [rsp+78h+lpBits], 0; lpBits
0x18007e8f5  call    cs:__imp_CreateBitmap
0x18007e8fb  mov     rbx, rax
0x18007e8fe  test    rax, rax
0x18007e901  jz      short loc_18007E914
0x18007e903  mov     r8, rsi; pvBits
0x18007e906  mov     edx, ebp; cb
0x18007e908  mov     hold, rax; hbm
0x18007e90b  call    cs:__imp_SetBitmapBits
0x18007e911  mov     r14d, eax
0x18007e914  mov     hold, rdi; hMem
0x18007e917  call    cs:__imp_GlobalUnlock
0x18007e91d  mov     hold, rdi; hMem
0x18007e920  call    cs:__imp_GlobalFree
0x18007e926  test    rbx, rbx
0x18007e929  jz      short loc_18007E93B
0x18007e92b  test    r14d, r14d
0x18007e92e  jnz     short loc_18007E93B
0x18007e930  mov     hold, rbx; ho
0x18007e933  call    cs:__imp_DeleteObject
0x18007e939  xor     ebx, ebx
0x18007e93b  mov     rax, rbx
0x18007e93e  jmp     loc_18007E8B9
```
