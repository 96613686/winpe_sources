# BmDuplicate(HBITMAP__ *,ulong *,tagBITMAP *)

- ea: `0x1800848f4`
- end: `0x180084a31`
- name: `?BmDuplicate@@YAPEAUHBITMAP__@@PEAU1@PEAKPEAUtagBITMAP@@@Z`
- size: `317`
- prototype: `HBITMAP__ *__fastcall(HBITMAP__ *hold, unsigned int *hold, tagBITMAP *lpdwSize)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c3c0`

## callees

- `0x1800848f4`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180084963`
- `KERNELBASE!GlobalAlloc` at `0x180084963`
- `KERNELBASE!GlobalFree` at `0x180084a17`
- `KERNELBASE!GlobalFree` at `0x180084a17`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008498f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008498f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008497a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008497a`
- `GDI32!DeleteObject` at `0x1800849dd`
- `GDI32!DeleteObject` at `0x1800849dd`
- `GDI32!CreateBitmap` at `0x1800849b9`
- `GDI32!CreateBitmap` at `0x1800849b9`
- `GDI32!GetObjectW` at `0x180084927`
- `GDI32!GetObjectW` at `0x180084927`
- `GDI32!SetBitmapBits` at `0x1800849d0`
- `GDI32!SetBitmapBits` at `0x1800849d0`
- `GDI32!GetBitmapBits` at `0x18008499e`
- `GDI32!GetBitmapBits` at `0x18008499e`
- `GDI32!GetBitmapDimensionEx` at `0x1800849ee`
- `GDI32!GetBitmapDimensionEx` at `0x1800849ee`
- `GDI32!SetBitmapDimensionEx` at `0x180084a0e`
- `GDI32!SetBitmapDimensionEx` at `0x180084a0e`

## pseudocode

```c
HBITMAP __fastcall BmDuplicate(HBITMAP hold, unsigned int *a2, tagBITMAP *lpdwSize)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  int v6; // r14d
  HGLOBAL v7; // rax
  void *v8; // rdi
  HBITMAP v9; // rbx
  void *v10; // rsi
  HBITMAP Bitmap; // rax
  tagBITMAP bm; // [rsp+30h] [rbp-28h] BYREF
  tagSIZE extents; // [rsp+A0h] [rbp+48h] BYREF

  extents = 0;
  memset(&bm, 0, sizeof(bm));
  GetObjectW(hold, 32, &bm);
  v4 = (unsigned int)bm.bmWidthBytes * (unsigned __int64)(unsigned int)bm.bmHeight;
  if ( v4 > 0xFFFFFFFF )
    return 0;
  v5 = bm.bmPlanes * (unsigned __int64)(unsigned int)v4;
  if ( v5 > 0xFFFFFFFF )
    return 0;
  v6 = bm.bmPlanes * (_DWORD)v4;
  v7 = GlobalAlloc(2u, (unsigned int)v5);
  v8 = v7;
  if ( !v7 )
    return 0;
  v9 = 0;
  v10 = GlobalLock(v7);
  if ( v10 )
  {
    GlobalUnlock(v8);
    GetBitmapBits(hold, v6, v10);
    Bitmap = CreateBitmap(bm.bmWidth, bm.bmHeight, bm.bmPlanes, bm.bmBitsPixel, 0);
    v9 = Bitmap;
    if ( Bitmap )
    {
      if ( SetBitmapBits(Bitmap, v6, v10) )
      {
        if ( GetBitmapDimensionEx(hold, &extents) && extents.cx )
        {
          if ( extents.cy )
            SetBitmapDimensionEx(v9, extents.cx, extents.cy, 0);
        }
      }
      else
      {
        DeleteObject(v9);
        v9 = 0;
      }
    }
  }
  GlobalFree(v8);
  return v9;
}

```

## disassembly

```asm
0x1800848f4  mov     qword ptr [rsp-30h+extents.cx], r8
0x1800848f9  push    rbp
0x1800848fa  push    rbx
0x1800848fb  push    rsi
0x1800848fc  push    rdi
0x1800848fd  push    r14
0x1800848ff  push    r15
0x180084901  mov     rbp, rsp
0x180084904  sub     rsp, 58h
0x180084908  xorps   xmm0, xmm0
0x18008490b  mov     qword ptr [rbp+extents.cx], 0
0x180084913  lea     r8, [rbp+bm]; pv
0x180084917  mov     edx, 20h ; ' '; c
0x18008491c  movups  xmmword ptr [rbp+bm.bmType], xmm0
0x180084920  mov     r15, hold
0x180084923  movups  xmmword ptr [rbp+bm.bmPlanes], xmm0
0x180084927  call    cs:__imp_GetObjectW
0x18008492d  mov     edx, [rbp+bm.bmHeight]
0x180084930  mov     r8d, 0FFFFFFFFh
0x180084936  mov     eax, [rbp+bm.bmWidthBytes]
0x180084939  imul    rdx, rax
0x18008493d  cmp     rdx, r8
0x180084940  ja      loc_180084A22
0x180084946  movzx   eax, [rbp+bm.bmPlanes]
0x18008494a  mov     ecx, edx
0x18008494c  imul    hold, rax
0x180084950  cmp     hold, r8
0x180084953  ja      loc_180084A22
0x180084959  mov     r14d, ecx
0x18008495c  mov     edx, ecx; dwBytes
0x18008495e  mov     ecx, 2; uFlags
0x180084963  call    cs:__imp_GlobalAlloc
0x180084969  mov     rdi, rax
0x18008496c  test    rax, rax
0x18008496f  jz      loc_180084A22
0x180084975  mov     hold, rax; hMem
0x180084978  xor     ebx, ebx
0x18008497a  call    cs:__imp_GlobalLock
0x180084980  mov     rsi, rax
0x180084983  test    rax, rax
0x180084986  jz      $errRtn_115
0x18008498c  mov     hold, rdi; hMem
0x18008498f  call    cs:__imp_GlobalUnlock
0x180084995  mov     r8, rsi; lpvBits
0x180084998  mov     edx, r14d; cb
0x18008499b  mov     hold, r15; hbit
0x18008499e  call    cs:__imp_GetBitmapBits
0x1800849a4  movzx   r9d, [rbp+bm.bmBitsPixel]; nBitCount
0x1800849a9  movzx   r8d, [rbp+bm.bmPlanes]; nPlanes
0x1800849ae  mov     edx, [rbp+bm.bmHeight]; nHeight
0x1800849b1  mov     ecx, [rbp+bm.bmWidth]; nWidth
0x1800849b4  mov     [rsp+58h+lpBits], rbx; lpBits
0x1800849b9  call    cs:__imp_CreateBitmap
0x1800849bf  mov     rbx, rax
0x1800849c2  test    rax, rax
0x1800849c5  jz      short $errRtn_115
0x1800849c7  mov     r8, rsi; pvBits
0x1800849ca  mov     edx, r14d; cb
0x1800849cd  mov     hold, rax; hbm
0x1800849d0  call    cs:__imp_SetBitmapBits
0x1800849d6  test    eax, eax
0x1800849d8  jnz     short loc_1800849E7
0x1800849da  mov     hold, rbx; ho
0x1800849dd  call    cs:__imp_DeleteObject
0x1800849e3  xor     ebx, ebx
0x1800849e5  jmp     short $errRtn_115
0x1800849e7  lea     rdx, [rbp+extents]; lpsize
0x1800849eb  mov     hold, r15; hbit
0x1800849ee  call    cs:__imp_GetBitmapDimensionEx
0x1800849f4  test    eax, eax
0x1800849f6  jz      short $errRtn_115
0x1800849f8  mov     edx, [rbp+extents.cx]; w
0x1800849fb  test    edx, edx
0x1800849fd  jz      short $errRtn_115
0x1800849ff  mov     r8d, [rbp+extents.cy]; h
0x180084a03  test    r8d, r8d
0x180084a06  jz      short $errRtn_115
0x180084a08  xor     r9d, r9d; lpsz
0x180084a0b  mov     hold, rbx; hbm
0x180084a0e  call    cs:__imp_SetBitmapDimensionEx
0x180084a14  mov     hold, rdi; hMem
0x180084a17  call    cs:__imp_GlobalFree
0x180084a1d  mov     rax, rbx
0x180084a20  jmp     short loc_180084A24
0x180084a22  xor     eax, eax
0x180084a24  add     rsp, 58h
0x180084a28  pop     r15
0x180084a2a  pop     r14
0x180084a2c  pop     rdi
0x180084a2d  pop     rsi
0x180084a2e  pop     rbx
0x180084a2f  pop     rbp
0x180084a30  retn
```
