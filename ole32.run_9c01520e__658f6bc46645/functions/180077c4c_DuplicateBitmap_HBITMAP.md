# DuplicateBitmap(HBITMAP__ *)

- ea: `0x180077c4c`
- end: `0x180077dbc`
- name: `?DuplicateBitmap@@YAPEAUHBITMAP__@@PEAU1@@Z`
- size: `368`
- prototype: `HBITMAP__ *__fastcall(HBITMAP__ *hold)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800783a0`

## callees

- `0x180077c4c`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180077cca`
- `KERNELBASE!GlobalAlloc` at `0x180077cca`
- `KERNELBASE!GlobalFree` at `0x180077cf8`
- `KERNELBASE!GlobalFree` at `0x180077d8d`
- `KERNELBASE!GlobalFree` at `0x180077cf8`
- `KERNELBASE!GlobalFree` at `0x180077d8d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180077d7e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180077d7e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180077ce1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180077ce1`
- `GDI32!DeleteObject` at `0x180077da6`
- `GDI32!DeleteObject` at `0x180077da6`
- `GDI32!CreateBitmap` at `0x180077d50`
- `GDI32!CreateBitmap` at `0x180077d50`
- `GDI32!GetObjectW` at `0x180077c81`
- `GDI32!GetObjectW` at `0x180077c81`
- `GDI32!SetBitmapBits` at `0x180077d6c`
- `GDI32!SetBitmapBits` at `0x180077d6c`
- `GDI32!GetBitmapBits` at `0x180077d2a`
- `GDI32!GetBitmapBits` at `0x180077d2a`

## pseudocode

```c
HBITMAP __fastcall DuplicateBitmap(HBITMAP hold)
{
  LONG v1; // r14d
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rsi
  HGLOBAL v6; // rax
  void *v7; // rdi
  void *v8; // rax
  const void *v9; // rbp
  HBITMAP Bitmap; // rax
  HBITMAP v12; // rbx
  tagBITMAP bm; // [rsp+30h] [rbp-28h] BYREF

  v1 = 1;
  memset(&bm, 0, sizeof(bm));
  GetObjectW(hold, 32, &bm);
  v3 = (unsigned int)bm.bmWidthBytes * (unsigned __int64)(unsigned int)bm.bmHeight;
  if ( v3 > 0xFFFFFFFF )
    return 0;
  v4 = (unsigned int)v3 * (unsigned __int64)bm.bmPlanes;
  if ( v4 > 0xFFFFFFFF )
    return 0;
  v5 = (unsigned int)v4 * (unsigned __int64)bm.bmBitsPixel;
  if ( v5 > 0xFFFFFFFF )
    return 0;
  v6 = GlobalAlloc(0x42u, (unsigned int)v5);
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
  GetBitmapBits(hold, v5, v8);
  Bitmap = CreateBitmap(bm.bmWidth, bm.bmHeight, bm.bmPlanes, bm.bmBitsPixel, 0);
  v12 = Bitmap;
  if ( Bitmap )
    v1 = SetBitmapBits(Bitmap, v5, v9);
  GlobalUnlock(v7);
  GlobalFree(v7);
  if ( v12 )
  {
    if ( !v1 )
    {
      DeleteObject(v12);
      return 0;
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180077c4c  mov     rax, rsp
0x180077c4f  mov     [rax+8], rbx
0x180077c53  mov     [rax+10h], rbp
0x180077c57  mov     [rax+18h], rsi
0x180077c5b  mov     [rax+20h], rdi
0x180077c5f  push    r14
0x180077c61  sub     rsp, 50h
0x180077c65  xorps   xmm0, xmm0
0x180077c68  lea     r8, [rax-28h]; pv
0x180077c6c  mov     r14d, 1
0x180077c72  mov     rbx, hold
0x180077c75  movups  xmmword ptr [rax-28h], xmm0
0x180077c79  movups  xmmword ptr [rax-18h], xmm0
0x180077c7d  lea     edx, [r14+1Fh]; c
0x180077c81  call    cs:__imp_GetObjectW
0x180077c88  nop     dword ptr [rax+rax+00h]
0x180077c8d  mov     edx, [rsp+58h+bm.bmHeight]
0x180077c91  mov     r8d, 0FFFFFFFFh
0x180077c97  mov     eax, [rsp+58h+bm.bmWidthBytes]
0x180077c9b  imul    rdx, rax
0x180077c9f  cmp     rdx, r8
0x180077ca2  ja      short loc_180077D04
0x180077ca4  movzx   ecx, [rsp+58h+bm.bmPlanes]
0x180077ca9  mov     eax, edx
0x180077cab  imul    hold, rax
0x180077caf  cmp     hold, r8
0x180077cb2  ja      short loc_180077D04
0x180077cb4  movzx   esi, [rsp+58h+bm.bmBitsPixel]
0x180077cb9  mov     eax, ecx
0x180077cbb  imul    rsi, rax
0x180077cbf  cmp     rsi, r8
0x180077cc2  ja      short loc_180077D04
0x180077cc4  mov     edx, esi; dwBytes
0x180077cc6  lea     ecx, [r14+41h]; uFlags
0x180077cca  call    cs:__imp_GlobalAlloc
0x180077cd1  nop     dword ptr [rax+rax+00h]
0x180077cd6  mov     rdi, rax
0x180077cd9  test    rax, rax
0x180077cdc  jz      short loc_180077D04
0x180077cde  mov     hold, rax; hMem
0x180077ce1  call    cs:__imp_GlobalLock
0x180077ce8  nop     dword ptr [rax+rax+00h]
0x180077ced  mov     rbp, rax
0x180077cf0  test    rax, rax
0x180077cf3  jnz     short loc_180077D22
0x180077cf5  mov     hold, rdi; hMem
0x180077cf8  call    cs:__imp_GlobalFree
0x180077cff  nop     dword ptr [rax+rax+00h]
0x180077d04  xor     eax, eax
0x180077d06  mov     rbx, [rsp+58h+arg_0]
0x180077d0b  mov     rbp, [rsp+58h+arg_8]
0x180077d10  mov     rsi, [rsp+58h+arg_10]
0x180077d15  mov     rdi, [rsp+58h+arg_18]
0x180077d1a  add     rsp, 50h
0x180077d1e  pop     r14
0x180077d20  retn
0x180077d22  mov     r8, rbp; lpvBits
0x180077d25  mov     edx, esi; cb
0x180077d27  mov     hold, rbx; hbit
0x180077d2a  call    cs:__imp_GetBitmapBits
0x180077d31  nop     dword ptr [rax+rax+00h]
0x180077d36  movzx   r9d, [rsp+58h+bm.bmBitsPixel]; nBitCount
0x180077d3c  movzx   r8d, [rsp+58h+bm.bmPlanes]; nPlanes
0x180077d42  mov     edx, [rsp+58h+bm.bmHeight]; nHeight
0x180077d46  mov     ecx, [rsp+58h+bm.bmWidth]; nWidth
0x180077d4a  and     [rsp+58h+var_38], 0
0x180077d50  call    cs:__imp_CreateBitmap
0x180077d57  nop     dword ptr [rax+rax+00h]
0x180077d5c  mov     rbx, rax
0x180077d5f  test    rax, rax
0x180077d62  jz      short loc_180077D7B
0x180077d64  mov     r8, rbp; pvBits
0x180077d67  mov     edx, esi; cb
0x180077d69  mov     hold, rax; hbm
0x180077d6c  call    cs:__imp_SetBitmapBits
0x180077d73  nop     dword ptr [rax+rax+00h]
0x180077d78  mov     r14d, eax
0x180077d7b  mov     hold, rdi; hMem
0x180077d7e  call    cs:__imp_GlobalUnlock
0x180077d85  nop     dword ptr [rax+rax+00h]
0x180077d8a  mov     hold, rdi; hMem
0x180077d8d  call    cs:__imp_GlobalFree
0x180077d94  nop     dword ptr [rax+rax+00h]
0x180077d99  test    rbx, rbx
0x180077d9c  jz      short loc_180077DB4
0x180077d9e  test    r14d, r14d
0x180077da1  jnz     short loc_180077DB4
0x180077da3  mov     hold, rbx; ho
0x180077da6  call    cs:__imp_DeleteObject
0x180077dad  nop     dword ptr [rax+rax+00h]
0x180077db2  xor     ebx, ebx
0x180077db4  mov     rax, rbx
0x180077db7  jmp     loc_180077D06
```
