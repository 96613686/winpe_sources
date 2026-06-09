# MRPLGBLT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x1800908c0`
- end: `0x180090b55`
- name: `?bPlay@MRPLGBLT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `661`
- prototype: `__int64 __fastcall(MRPLGBLT *__hidden this, void *, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800305e0`

## callees

- `0x18001dc40`
- `0x18001e870`
- `0x18001eb5c`
- `0x18001ec70`
- `0x180022504`
- `0x180024fb8`
- `0x1800785d4`
- `0x18008f4f0`
- `0x1800908c0`
- `0x180093580`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009099c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800909d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800909f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090b3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009099c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800909d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800909f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090b3a`
- `GDI32!DeleteDC` at `0x180090b14`
- `GDI32!DeleteDC` at `0x180090b14`
- `GDI32!SelectObject` at `0x180090a8e`
- `GDI32!SelectObject` at `0x180090b02`
- `GDI32!SelectObject` at `0x180090a8e`
- `GDI32!SelectObject` at `0x180090b02`
- `GDI32!SetWorldTransform` at `0x180090aa3`
- `GDI32!SetWorldTransform` at `0x180090aa3`
- `GDI32!DeleteObject` at `0x180090b0b`
- `GDI32!DeleteObject` at `0x180090b26`
- `GDI32!DeleteObject` at `0x180090b0b`
- `GDI32!DeleteObject` at `0x180090b26`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MRPLGBLT::bPlay(MRPLGBLT *this, HDC a2, struct tagHANDLETABLE *a3)
{
  unsigned int v5; // r13d
  BITMAPINFOHEADER *v6; // r14
  char v7; // r15
  MF *v8; // rdi
  HBITMAP hbmMask; // rsi
  unsigned int v11; // r9d
  HLOCAL v12; // rdi
  HDC CompatibleDCAdvanced; // rdi
  int v14; // eax
  HBITMAP DIBitmap; // rax
  HBITMAP v16; // r12
  HGDIOBJ v17; // r15
  HLOCAL hMem; // [rsp+50h] [rbp-28h] BYREF
  char v19; // [rsp+58h] [rbp-20h]
  BITMAPINFOHEADER *pbmih; // [rsp+60h] [rbp-18h] BYREF
  char v21; // [rsp+68h] [rbp-10h]

  v5 = 0;
  v6 = 0;
  pbmih = 0;
  v7 = 0;
  v21 = 0;
  v8 = (MF *)pvClientObjGet(a3->objectHandle[0], 4587520);
  if ( !v8 || !MRPLGBLT::bCheckRecord(this, a3) )
    return 0;
  if ( MF::bClipped(v8, (MRPLGBLT *)((char *)this + 8)) )
    return 1;
  hbmMask = 0;
  v11 = *((_DWORD *)this + 32);
  if ( v11 )
  {
    hMem = 0;
    v19 = 0;
    if ( !(unsigned int)bCheckBitmap(
                          a3,
                          this,
                          *((_DWORD *)this + 31),
                          v11,
                          *((_DWORD *)this + 33),
                          *((_DWORD *)this + 34),
                          *((_DWORD *)this + 30),
                          0,
                          (BitmapInfoPtr *)&hMem) )
    {
      if ( hMem )
      {
        if ( v19 )
          LocalFree(hMem);
      }
      return 0;
    }
    v12 = hMem;
    hbmMask = (HBITMAP)CreateMonoDib(
                         (BITMAPINFO *)hMem,
                         (char *)this + *((unsigned int *)this + 33),
                         *((_DWORD *)this + 30));
    if ( !hbmMask )
    {
      if ( v12 && v19 )
        LocalFree(v12);
      return 0;
    }
    if ( v12 && v19 )
      LocalFree(v12);
  }
  CompatibleDCAdvanced = (HDC)CreateCompatibleDCAdvanced(a2);
  if ( CompatibleDCAdvanced )
  {
    v14 = bCheckBitmap(
            a3,
            this,
            *((_DWORD *)this + 24),
            *((_DWORD *)this + 25),
            *((_DWORD *)this + 26),
            *((_DWORD *)this + 27),
            *((_DWORD *)this + 23),
            0,
            (BitmapInfoPtr *)&pbmih);
    v6 = pbmih;
    if ( v14 )
    {
      DIBitmap = CreateDIBitmap(
                   CompatibleDCAdvanced,
                   pbmih,
                   6u,
                   (char *)this + *((unsigned int *)this + 26),
                   (const BITMAPINFO *)((char *)this + *((unsigned int *)this + 24)),
                   *((_DWORD *)this + 23));
      v16 = DIBitmap;
      if ( DIBitmap )
      {
        v17 = SelectObject(CompatibleDCAdvanced, DIBitmap);
        if ( v17 )
        {
          if ( SetWorldTransform(CompatibleDCAdvanced, (const XFORM *)((char *)this + 64))
            && SetBkColor(CompatibleDCAdvanced, *((_DWORD *)this + 22)) != -1 )
          {
            v5 = PlgBlt(
                   a2,
                   (const POINT *)this + 3,
                   CompatibleDCAdvanced,
                   *((_DWORD *)this + 12),
                   *((_DWORD *)this + 13),
                   *((_DWORD *)this + 14),
                   *((_DWORD *)this + 15),
                   hbmMask,
                   *((_DWORD *)this + 28),
                   *((_DWORD *)this + 29));
          }
          SelectObject(CompatibleDCAdvanced, v17);
        }
        DeleteObject(v16);
      }
    }
    DeleteDC(CompatibleDCAdvanced);
    v7 = v21;
  }
  if ( hbmMask )
    DeleteObject(hbmMask);
  if ( v6 && v7 )
    LocalFree(v6);
  return v5;
}

```

## disassembly

```asm
0x1800908c0  mov     [rsp-40h+hdcDest], rdx
0x1800908c5  push    rbp
0x1800908c6  push    rbx
0x1800908c7  push    rsi
0x1800908c8  push    rdi
0x1800908c9  push    r12
0x1800908cb  push    r13
0x1800908cd  push    r14
0x1800908cf  push    r15
0x1800908d1  mov     rbp, rsp
0x1800908d4  sub     rsp, 78h
0x1800908d8  mov     r12, r8
0x1800908db  mov     rbx, rcx
0x1800908de  xor     r13d, r13d
0x1800908e1  mov     r14d, r13d
0x1800908e4  mov     [rbp+pbmih], r13
0x1800908e8  mov     r15b, r13b
0x1800908eb  mov     [rbp+var_10], r13b
0x1800908ef  mov     edx, 460000h
0x1800908f4  mov     rcx, [r8]
0x1800908f7  call    pvClientObjGet
0x1800908fc  mov     rdi, rax
0x1800908ff  test    rax, rax
0x180090902  jnz     short loc_18009090B
0x180090904  xor     eax, eax
0x180090906  jmp     loc_180090B44
0x18009090b  mov     rdx, r12; struct tagHANDLETABLE *
0x18009090e  mov     rcx, rbx; this
0x180090911  call    ?bCheckRecord@MRPLGBLT@@QEAAHPEAUtagHANDLETABLE@@@Z; MRPLGBLT::bCheckRecord(tagHANDLETABLE *)
0x180090916  test    eax, eax
0x180090918  jnz     short loc_18009091C
0x18009091a  jmp     short loc_180090904
0x18009091c  lea     rdx, [rbx+8]; struct ERECTL *
0x180090920  mov     rcx, rdi; this
0x180090923  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x180090928  test    eax, eax
0x18009092a  jz      short loc_180090936
0x18009092c  mov     eax, 1
0x180090931  jmp     loc_180090B44
0x180090936  mov     rsi, r13
0x180090939  mov     r9d, [rbx+80h]
0x180090940  test    r9d, r9d
0x180090943  jz      loc_1800909F8
0x180090949  mov     [rbp+hMem], r13
0x18009094d  mov     [rbp+var_20], r13b
0x180090951  lea     rax, [rbp+hMem]
0x180090955  mov     qword ptr [rsp+78h+xMask], rax; BitmapInfoPtr *
0x18009095a  mov     dword ptr [rsp+78h+hbmMask], r13d; int
0x18009095f  mov     eax, [rbx+78h]
0x180090962  mov     [rsp+78h+height], eax; int
0x180090966  mov     eax, [rbx+88h]
0x18009096c  mov     [rsp+78h+iUsage], eax; int
0x180090970  mov     eax, [rbx+84h]
0x180090976  mov     dword ptr [rsp+78h+pbmi], eax; int
0x18009097a  mov     r8d, [rbx+7Ch]
0x18009097e  mov     rdx, rbx; this
0x180090981  mov     rcx, r12; struct tagHANDLETABLE *
0x180090984  call    bCheckBitmap
0x180090989  test    eax, eax
0x18009098b  jnz     short loc_1800909A8
0x18009098d  mov     rcx, [rbp+hMem]; hMem
0x180090991  test    rcx, rcx
0x180090994  jz      short loc_1800909A3
0x180090996  cmp     [rbp+var_20], r13b
0x18009099a  jz      short loc_1800909A3
0x18009099c  call    cs:__imp_LocalFree
0x1800909a2  nop
0x1800909a3  jmp     loc_180090904
0x1800909a8  mov     edx, [rbx+84h]
0x1800909ae  add     rdx, rbx; lpBits
0x1800909b1  mov     r8d, [rbx+78h]; ColorUse
0x1800909b5  mov     rdi, [rbp+hMem]
0x1800909b9  mov     rcx, rdi; lpbmi
0x1800909bc  call    CreateMonoDib
0x1800909c1  mov     rsi, rax
0x1800909c4  test    rax, rax
0x1800909c7  jnz     short loc_1800909E3
0x1800909c9  test    rdi, rdi
0x1800909cc  jz      short loc_1800909DE
0x1800909ce  cmp     [rbp+var_20], r13b
0x1800909d2  jz      short loc_1800909DE
0x1800909d4  mov     rcx, rdi; hMem
0x1800909d7  call    cs:__imp_LocalFree
0x1800909dd  nop
0x1800909de  jmp     loc_180090904
0x1800909e3  test    rdi, rdi
0x1800909e6  jz      short loc_1800909F8
0x1800909e8  cmp     [rbp+var_20], r13b
0x1800909ec  jz      short loc_1800909F8
0x1800909ee  mov     rcx, rdi; hMem
0x1800909f1  call    cs:__imp_LocalFree
0x1800909f7  nop
0x1800909f8  mov     rcx, [rbp+hdcDest]
0x1800909fc  call    CreateCompatibleDCAdvanced
0x180090a01  mov     rdi, rax
0x180090a04  test    rax, rax
0x180090a07  jz      loc_180090B1E
0x180090a0d  lea     rax, [rbp+pbmih]
0x180090a11  mov     qword ptr [rsp+78h+xMask], rax; BitmapInfoPtr *
0x180090a16  mov     dword ptr [rsp+78h+hbmMask], 0; int
0x180090a1e  mov     ecx, [rbx+5Ch]
0x180090a21  mov     [rsp+78h+height], ecx; int
0x180090a25  mov     ecx, [rbx+6Ch]
0x180090a28  mov     [rsp+78h+iUsage], ecx; int
0x180090a2c  mov     ecx, [rbx+68h]
0x180090a2f  mov     dword ptr [rsp+78h+pbmi], ecx; int
0x180090a33  mov     r9d, [rbx+64h]
0x180090a37  mov     r8d, [rbx+60h]
0x180090a3b  mov     rdx, rbx; this
0x180090a3e  mov     rcx, r12; struct tagHANDLETABLE *
0x180090a41  call    bCheckBitmap
0x180090a46  mov     r14, [rbp+pbmih]
0x180090a4a  test    eax, eax
0x180090a4c  jz      loc_180090B11
0x180090a52  mov     ecx, [rbx+60h]
0x180090a55  add     rcx, rbx
0x180090a58  mov     r9d, [rbx+68h]
0x180090a5c  add     r9, rbx; pjBits
0x180090a5f  mov     eax, [rbx+5Ch]
0x180090a62  mov     [rsp+78h+iUsage], eax; iUsage
0x180090a66  mov     [rsp+78h+pbmi], rcx; pbmi
0x180090a6b  mov     r8d, 6; flInit
0x180090a71  mov     rdx, r14; pbmih
0x180090a74  mov     rcx, rdi; hdc
0x180090a77  call    CreateDIBitmap
0x180090a7c  mov     r12, rax
0x180090a7f  test    rax, rax
0x180090a82  jz      loc_180090B11
0x180090a88  mov     rdx, rax; h
0x180090a8b  mov     rcx, rdi; hdc
0x180090a8e  call    cs:__imp_SelectObject
0x180090a94  mov     r15, rax
0x180090a97  test    rax, rax
0x180090a9a  jz      short loc_180090B08
0x180090a9c  lea     rdx, [rbx+40h]; lpxf
0x180090aa0  mov     rcx, rdi; hdc
0x180090aa3  call    cs:__imp_SetWorldTransform
0x180090aa9  test    eax, eax
0x180090aab  jz      short loc_180090AFC
0x180090aad  mov     edx, [rbx+58h]; color
0x180090ab0  mov     rcx, rdi; hdc
0x180090ab3  call    SetBkColor
0x180090ab8  cmp     eax, 0FFFFFFFFh
0x180090abb  jz      short loc_180090AFC
0x180090abd  lea     rdx, [rbx+18h]; lpPoint
0x180090ac1  mov     eax, [rbx+74h]
0x180090ac4  mov     [rsp+78h+yMask], eax; yMask
0x180090ac8  mov     eax, [rbx+70h]
0x180090acb  mov     [rsp+78h+xMask], eax; xMask
0x180090acf  mov     [rsp+78h+hbmMask], rsi; hbmMask
0x180090ad4  mov     eax, [rbx+3Ch]
0x180090ad7  mov     [rsp+78h+height], eax; height
0x180090adb  mov     eax, [rbx+38h]
0x180090ade  mov     [rsp+78h+iUsage], eax; width
0x180090ae2  mov     eax, [rbx+34h]
0x180090ae5  mov     dword ptr [rsp+78h+pbmi], eax; ySrc
0x180090ae9  mov     r9d, [rbx+30h]; xSrc
0x180090aed  mov     r8, rdi; hdcSrc
0x180090af0  mov     rcx, [rbp+hdcDest]; hdcDest
0x180090af4  call    PlgBlt
0x180090af9  mov     r13d, eax
0x180090afc  mov     rdx, r15; h
0x180090aff  mov     rcx, rdi; hdc
0x180090b02  call    cs:__imp_SelectObject
0x180090b08  mov     rcx, r12; ho
0x180090b0b  call    cs:__imp_DeleteObject
0x180090b11  mov     rcx, rdi; hdc
0x180090b14  call    cs:__imp_DeleteDC
0x180090b1a  mov     r15b, [rbp+var_10]
0x180090b1e  test    rsi, rsi
0x180090b21  jz      short loc_180090B2D
0x180090b23  mov     rcx, rsi; ho
0x180090b26  call    cs:__imp_DeleteObject
0x180090b2c  nop
0x180090b2d  test    r14, r14
0x180090b30  jz      short loc_180090B41
0x180090b32  test    r15b, r15b
0x180090b35  jz      short loc_180090B41
0x180090b37  mov     rcx, r14; hMem
0x180090b3a  call    cs:__imp_LocalFree
0x180090b40  nop
0x180090b41  mov     eax, r13d
0x180090b44  add     rsp, 78h
0x180090b48  pop     r15
0x180090b4a  pop     r14
0x180090b4c  pop     r13
0x180090b4e  pop     r12
0x180090b50  pop     rdi
0x180090b51  pop     rsi
0x180090b52  pop     rbx
0x180090b53  pop     rbp
0x180090b54  retn
```
