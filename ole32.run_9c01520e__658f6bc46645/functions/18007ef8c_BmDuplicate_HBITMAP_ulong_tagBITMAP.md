# BmDuplicate(HBITMAP__ *,ulong *,tagBITMAP *)

- ea: `0x18007ef8c`
- end: `0x18007f118`
- name: `?BmDuplicate@@YAPEAUHBITMAP__@@PEAU1@PEAKPEAUtagBITMAP@@@Z`
- size: `396`
- prototype: `HBITMAP__ *__fastcall(HBITMAP__ *hold, unsigned int *hold, tagBITMAP *lpdwSize)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017a10`

## callees

- `0x18007ef8c`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18007f004`
- `KERNELBASE!GlobalAlloc` at `0x18007f004`
- `KERNELBASE!GlobalFree` at `0x18007f0ea`
- `KERNELBASE!GlobalFree` at `0x18007f0ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f03a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f03a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f01f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f01f`
- `GDI32!DeleteObject` at `0x18007f09e`
- `GDI32!DeleteObject` at `0x18007f09e`
- `GDI32!CreateBitmap` at `0x18007f06f`
- `GDI32!CreateBitmap` at `0x18007f06f`
- `GDI32!GetObjectW` at `0x18007efc8`
- `GDI32!GetObjectW` at `0x18007efc8`
- `GDI32!SetBitmapBits` at `0x18007f08b`
- `GDI32!SetBitmapBits` at `0x18007f08b`
- `GDI32!GetBitmapBits` at `0x18007f04e`
- `GDI32!GetBitmapBits` at `0x18007f04e`
- `GDI32!GetBitmapDimensionEx` at `0x18007f0b5`
- `GDI32!GetBitmapDimensionEx` at `0x18007f0b5`
- `GDI32!SetBitmapDimensionEx` at `0x18007f0db`
- `GDI32!SetBitmapDimensionEx` at `0x18007f0db`

## pseudocode

```c
HBITMAP __fastcall BmDuplicate(HBITMAP hold, unsigned int *a2, tagBITMAP *lpdwSize)
{
  HBITMAP v3; // rbx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rdi
  HGLOBAL v7; // rax
  void *v8; // rsi
  void *v9; // r14
  HBITMAP Bitmap; // rax
  tagBITMAP bm; // [rsp+30h] [rbp-20h] BYREF
  tagSIZE extents; // [rsp+80h] [rbp+30h] BYREF

  v3 = 0;
  extents.cy = 0;
  extents.cx = 0;
  memset(&bm, 0, sizeof(bm));
  GetObjectW(hold, 32, &bm);
  v5 = (unsigned int)bm.bmWidthBytes * (unsigned __int64)(unsigned int)bm.bmHeight;
  if ( v5 > 0xFFFFFFFF )
    return 0;
  v6 = (unsigned int)v5 * (unsigned __int64)bm.bmPlanes;
  if ( v6 > 0xFFFFFFFF )
    return 0;
  v7 = GlobalAlloc(2u, (unsigned int)v6);
  v8 = v7;
  if ( !v7 )
    return 0;
  v9 = GlobalLock(v7);
  if ( v9 )
  {
    GlobalUnlock(v8);
    GetBitmapBits(hold, v6, v9);
    Bitmap = CreateBitmap(bm.bmWidth, bm.bmHeight, bm.bmPlanes, bm.bmBitsPixel, 0);
    v3 = Bitmap;
    if ( Bitmap )
    {
      if ( SetBitmapBits(Bitmap, v6, v9) )
      {
        if ( GetBitmapDimensionEx(hold, &extents) && extents.cx )
        {
          if ( extents.cy )
            SetBitmapDimensionEx(v3, extents.cx, extents.cy, 0);
        }
      }
      else
      {
        DeleteObject(v3);
        v3 = 0;
      }
    }
  }
  GlobalFree(v8);
  return v3;
}

```

## disassembly

```asm
0x18007ef8c  mov     rax, rsp
0x18007ef8f  mov     [rax+8], rbx
0x18007ef93  mov     [rax+10h], rsi
0x18007ef97  mov     [rax+20h], rdi
0x18007ef9b  mov     [rax+18h], r8
0x18007ef9f  push    rbp
0x18007efa0  push    r14
0x18007efa2  push    r15
0x18007efa4  mov     rbp, rsp
0x18007efa7  sub     rsp, 50h
0x18007efab  xor     ebx, ebx
0x18007efad  lea     r8, [rbp+bm]; pv
0x18007efb1  and     [rbp+extents.cy], ebx
0x18007efb4  xorps   xmm0, xmm0
0x18007efb7  and     [rbp+extents.cx], ebx
0x18007efba  mov     r15, hold
0x18007efbd  movups  xmmword ptr [rbp+bm.bmType], xmm0
0x18007efc1  lea     edx, [rbx+20h]; c
0x18007efc4  movups  xmmword ptr [rbp+bm.bmPlanes], xmm0
0x18007efc8  call    cs:__imp_GetObjectW
0x18007efcf  nop     dword ptr [rax+rax+00h]
0x18007efd4  mov     edx, [rbp+bm.bmHeight]
0x18007efd7  mov     ecx, 0FFFFFFFFh
0x18007efdc  mov     eax, [rbp+bm.bmWidthBytes]
0x18007efdf  imul    rdx, rax
0x18007efe3  cmp     rdx, hold
0x18007efe6  ja      loc_18007F0FB
0x18007efec  movzx   edi, [rbp+bm.bmPlanes]
0x18007eff0  mov     eax, edx
0x18007eff2  imul    rdi, rax
0x18007eff6  cmp     rdi, hold
0x18007eff9  ja      loc_18007F0FB
0x18007efff  mov     edx, edi; dwBytes
0x18007f001  lea     ecx, [rbx+2]; uFlags
0x18007f004  call    cs:__imp_GlobalAlloc
0x18007f00b  nop     dword ptr [rax+rax+00h]
0x18007f010  mov     rsi, rax
0x18007f013  test    rax, rax
0x18007f016  jz      loc_18007F0FB
0x18007f01c  mov     hold, rax; hMem
0x18007f01f  call    cs:__imp_GlobalLock
0x18007f026  nop     dword ptr [rax+rax+00h]
0x18007f02b  mov     r14, rax
0x18007f02e  test    rax, rax
0x18007f031  jz      $errRtn_88
0x18007f037  mov     hold, rsi; hMem
0x18007f03a  call    cs:__imp_GlobalUnlock
0x18007f041  nop     dword ptr [rax+rax+00h]
0x18007f046  mov     r8, r14; lpvBits
0x18007f049  mov     edx, edi; cb
0x18007f04b  mov     hold, r15; hbit
0x18007f04e  call    cs:__imp_GetBitmapBits
0x18007f055  nop     dword ptr [rax+rax+00h]
0x18007f05a  movzx   r9d, [rbp+bm.bmBitsPixel]; nBitCount
0x18007f05f  movzx   r8d, [rbp+bm.bmPlanes]; nPlanes
0x18007f064  mov     edx, [rbp+bm.bmHeight]; nHeight
0x18007f067  mov     ecx, [rbp+bm.bmWidth]; nWidth
0x18007f06a  and     [rsp+50h+var_30], rbx
0x18007f06f  call    cs:__imp_CreateBitmap
0x18007f076  nop     dword ptr [rax+rax+00h]
0x18007f07b  mov     rbx, rax
0x18007f07e  test    rax, rax
0x18007f081  jz      short $errRtn_88
0x18007f083  mov     r8, r14; pvBits
0x18007f086  mov     edx, edi; cb
0x18007f088  mov     hold, rax; hbm
0x18007f08b  call    cs:__imp_SetBitmapBits
0x18007f092  nop     dword ptr [rax+rax+00h]
0x18007f097  test    eax, eax
0x18007f099  jnz     short loc_18007F0AE
0x18007f09b  mov     hold, rbx; ho
0x18007f09e  call    cs:__imp_DeleteObject
0x18007f0a5  nop     dword ptr [rax+rax+00h]
0x18007f0aa  xor     ebx, ebx
0x18007f0ac  jmp     short $errRtn_88
0x18007f0ae  lea     rdx, [rbp+extents]; lpsize
0x18007f0b2  mov     hold, r15; hbit
0x18007f0b5  call    cs:__imp_GetBitmapDimensionEx
0x18007f0bc  nop     dword ptr [rax+rax+00h]
0x18007f0c1  test    eax, eax
0x18007f0c3  jz      short $errRtn_88
0x18007f0c5  mov     edx, [rbp+extents.cx]; w
0x18007f0c8  test    edx, edx
0x18007f0ca  jz      short $errRtn_88
0x18007f0cc  mov     r8d, [rbp+extents.cy]; h
0x18007f0d0  test    r8d, r8d
0x18007f0d3  jz      short $errRtn_88
0x18007f0d5  xor     r9d, r9d; lpsz
0x18007f0d8  mov     hold, rbx; hbm
0x18007f0db  call    cs:__imp_SetBitmapDimensionEx
0x18007f0e2  nop     dword ptr [rax+rax+00h]
0x18007f0e7  mov     hold, rsi; hMem
0x18007f0ea  call    cs:__imp_GlobalFree
0x18007f0f1  nop     dword ptr [rax+rax+00h]
0x18007f0f6  mov     rax, rbx
0x18007f0f9  jmp     short loc_18007F0FD
0x18007f0fb  xor     eax, eax
0x18007f0fd  lea     r11, [rsp+50h+var_s0]
0x18007f102  mov     rbx, [r11+20h]
0x18007f106  mov     rsi, [r11+28h]
0x18007f10a  mov     rdi, [r11+38h]
0x18007f10e  mov     rsp, r11
0x18007f111  pop     r15
0x18007f113  pop     r14
0x18007f115  pop     rbp
0x18007f116  retn
```
