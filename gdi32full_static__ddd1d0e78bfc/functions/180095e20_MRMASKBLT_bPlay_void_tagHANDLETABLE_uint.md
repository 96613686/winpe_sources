# MRMASKBLT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180095e20`
- end: `0x18009615a`
- name: `?bPlay@MRMASKBLT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `826`
- prototype: `__int64 __fastcall(MRMASKBLT *__hidden this, HDC hdcDest, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016350`

## callees

- `0x18001e920`
- `0x180028bd0`
- `0x18002b344`
- `0x18002e040`
- `0x180034210`
- `0x180034f78`
- `0x180035af0`
- `0x18007d0ac`
- `0x180094db0`
- `0x180095e20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095ef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095f36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095f56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096135`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095ef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095f36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095f56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096135`
- `GDI32!DeleteDC` at `0x180096106`
- `GDI32!DeleteDC` at `0x180096106`
- `GDI32!SelectObject` at `0x180096073`
- `GDI32!SelectObject` at `0x1800960e8`
- `GDI32!SelectObject` at `0x180096073`
- `GDI32!SelectObject` at `0x1800960e8`
- `GDI32!SetWorldTransform` at `0x180095f7e`
- `GDI32!SetWorldTransform` at `0x180095f7e`
- `GDI32!DeleteObject` at `0x1800960f7`
- `GDI32!DeleteObject` at `0x18009611a`
- `GDI32!DeleteObject` at `0x1800960f7`
- `GDI32!DeleteObject` at `0x18009611a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MRMASKBLT::bPlay(MRMASKBLT *this, HDC hdcDest, struct tagHANDLETABLE *a3)
{
  unsigned int v6; // r13d
  BITMAPINFOHEADER *v7; // r14
  MF *v8; // rdi
  HBITMAP hbmMask; // rsi
  HLOCAL v11; // rdi
  HDC CompatibleDCAdvanced; // rax
  HDC hdcSrc; // rdi
  DWORD rop; // eax
  int v15; // eax
  HBITMAP DIBitmap; // rax
  HBITMAP v17; // r12
  HGDIOBJ v18; // r15
  HLOCAL hMem; // [rsp+60h] [rbp-9h] BYREF
  char v20; // [rsp+68h] [rbp-1h]
  BITMAPINFOHEADER *pbmih; // [rsp+70h] [rbp+7h] BYREF
  char v22; // [rsp+78h] [rbp+Fh]

  v6 = 0;
  v7 = 0;
  pbmih = 0;
  v22 = 0;
  v8 = (MF *)pvClientObjGet(a3->objectHandle[0], 4587520);
  if ( !v8 || !MRMASKBLT::bCheckRecord(this, a3) )
    return 0;
  if ( MF::bClipped(v8, (MRMASKBLT *)((char *)this + 8)) )
    return 1;
  hbmMask = 0;
  if ( *((_DWORD *)this + 29) )
  {
    hMem = 0;
    v20 = 0;
    if ( !(unsigned int)bCheckBitmap(
                          a3,
                          this,
                          *((_DWORD *)this + 30),
                          *((_DWORD *)this + 31),
                          *((_DWORD *)this + 27),
                          0,
                          (BitmapInfoPtr *)&hMem) )
    {
      if ( hMem )
      {
        if ( v20 )
          LocalFree(hMem);
      }
      return 0;
    }
    v11 = hMem;
    hbmMask = (HBITMAP)CreateMonoDib(
                         (BITMAPINFO *)hMem,
                         (char *)this + *((unsigned int *)this + 30),
                         *((_DWORD *)this + 27));
    if ( !hbmMask )
    {
      if ( v11 && v20 )
        LocalFree(v11);
      return 0;
    }
    if ( v11 && v20 )
      LocalFree(v11);
  }
  CompatibleDCAdvanced = (HDC)CreateCompatibleDCAdvanced(hdcDest);
  hdcSrc = CompatibleDCAdvanced;
  if ( CompatibleDCAdvanced )
  {
    if ( SetWorldTransform(CompatibleDCAdvanced, (const XFORM *)((char *)this + 52)) )
    {
      rop = *((_DWORD *)this + 10);
      if ( ((rop ^ (4 * rop)) & 0xCCCC0000) != 0 )
      {
        v15 = bCheckBitmap(
                a3,
                this,
                *((_DWORD *)this + 23),
                *((_DWORD *)this + 24),
                *((_DWORD *)this + 20),
                0,
                (BitmapInfoPtr *)&pbmih);
        v7 = pbmih;
        if ( v15 )
        {
          DIBitmap = CreateDIBitmap(
                       hdcSrc,
                       pbmih,
                       6u,
                       (char *)this + *((unsigned int *)this + 23),
                       (const BITMAPINFO *)((char *)this + *((unsigned int *)this + 21)),
                       *((_DWORD *)this + 20));
          v17 = DIBitmap;
          if ( DIBitmap )
          {
            v18 = SelectObject(hdcSrc, DIBitmap);
            if ( v18 )
            {
              if ( SetBkColor(hdcSrc, *((_DWORD *)this + 19)) != -1 )
                v6 = MaskBlt(
                       hdcDest,
                       *((_DWORD *)this + 6),
                       *((_DWORD *)this + 7),
                       *((_DWORD *)this + 8),
                       *((_DWORD *)this + 9),
                       hdcSrc,
                       *((_DWORD *)this + 11),
                       *((_DWORD *)this + 12),
                       hbmMask,
                       *((_DWORD *)this + 25),
                       *((_DWORD *)this + 26),
                       *((_DWORD *)this + 10));
              SelectObject(hdcSrc, v18);
            }
            DeleteObject(v17);
          }
        }
      }
      else
      {
        v6 = MaskBlt(
               hdcDest,
               *((_DWORD *)this + 6),
               *((_DWORD *)this + 7),
               *((_DWORD *)this + 8),
               *((_DWORD *)this + 9),
               hdcSrc,
               *((_DWORD *)this + 11),
               *((_DWORD *)this + 12),
               hbmMask,
               *((_DWORD *)this + 25),
               *((_DWORD *)this + 26),
               rop);
      }
    }
    DeleteDC(hdcSrc);
  }
  if ( hbmMask )
    DeleteObject(hbmMask);
  if ( v7 && v22 )
    LocalFree(v7);
  return v6;
}

```

## disassembly

```asm
0x180095e20  mov     [rsp-8+hdcDest], rdx
0x180095e25  push    rbp
0x180095e26  push    rbx
0x180095e27  push    rsi
0x180095e28  push    rdi
0x180095e29  push    r12
0x180095e2b  push    r13
0x180095e2d  push    r14
0x180095e2f  push    r15
0x180095e31  lea     rbp, [rsp-1Fh]
0x180095e36  sub     rsp, 88h
0x180095e3d  mov     r15, r8
0x180095e40  mov     r12, rdx
0x180095e43  mov     rbx, rcx
0x180095e46  xor     r13d, r13d
0x180095e49  mov     r14d, r13d
0x180095e4c  mov     [rbp+57h+pbmih], r13
0x180095e50  mov     [rbp+57h+var_48], r13b
0x180095e54  mov     edx, 460000h
0x180095e59  mov     rcx, [r8]
0x180095e5c  call    pvClientObjGet
0x180095e61  mov     rdi, rax
0x180095e64  test    rax, rax
0x180095e67  jnz     short loc_180095E70
0x180095e69  xor     eax, eax
0x180095e6b  jmp     loc_180096145
0x180095e70  mov     rdx, r15; struct tagHANDLETABLE *
0x180095e73  mov     rcx, rbx; this
0x180095e76  call    ?bCheckRecord@MRMASKBLT@@QEAAHPEAUtagHANDLETABLE@@@Z; MRMASKBLT::bCheckRecord(tagHANDLETABLE *)
0x180095e7b  test    eax, eax
0x180095e7d  jnz     short loc_180095E81
0x180095e7f  jmp     short loc_180095E69
0x180095e81  lea     rdx, [rbx+8]; struct ERECTL *
0x180095e85  mov     rcx, rdi; this
0x180095e88  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x180095e8d  test    eax, eax
0x180095e8f  jz      short loc_180095E9B
0x180095e91  mov     eax, 1
0x180095e96  jmp     loc_180096145
0x180095e9b  mov     rsi, r13
0x180095e9e  mov     r9d, [rbx+74h]
0x180095ea2  test    r9d, r9d
0x180095ea5  jz      loc_180095F63
0x180095eab  mov     [rbp+57h+hMem], r13
0x180095eaf  mov     [rbp+57h+var_58], r13b
0x180095eb3  lea     rax, [rbp+57h+hMem]
0x180095eb7  mov     [rsp+0C0h+hbmMask], rax; BitmapInfoPtr *
0x180095ebc  mov     [rsp+0C0h+ySrc], r13d; int
0x180095ec1  mov     eax, [rbx+6Ch]
0x180095ec4  mov     [rsp+0C0h+xSrc], eax; int
0x180095ec8  mov     eax, [rbx+7Ch]
0x180095ecb  mov     dword ptr [rsp+0C0h+hdcSrc], eax; int
0x180095ecf  mov     eax, [rbx+78h]
0x180095ed2  mov     [rsp+0C0h+height], eax; int
0x180095ed6  mov     r8d, [rbx+70h]
0x180095eda  mov     rdx, rbx; this
0x180095edd  mov     rcx, r15; struct tagHANDLETABLE *
0x180095ee0  call    bCheckBitmap
0x180095ee5  test    eax, eax
0x180095ee7  jnz     short loc_180095F0A
0x180095ee9  mov     rcx, [rbp+57h+hMem]; hMem
0x180095eed  test    rcx, rcx
0x180095ef0  jz      short loc_180095F05
0x180095ef2  cmp     [rbp+57h+var_58], r13b
0x180095ef6  jz      short loc_180095F05
0x180095ef8  call    cs:__imp_LocalFree
0x180095eff  nop     dword ptr [rax+rax+00h]
0x180095f04  nop
0x180095f05  jmp     loc_180095E69
0x180095f0a  mov     edx, [rbx+78h]
0x180095f0d  add     rdx, rbx; lpBits
0x180095f10  mov     r8d, [rbx+6Ch]; ColorUse
0x180095f14  mov     rdi, [rbp+57h+hMem]
0x180095f18  mov     rcx, rdi; lpbmi
0x180095f1b  call    CreateMonoDib
0x180095f20  mov     rsi, rax
0x180095f23  test    rax, rax
0x180095f26  jnz     short loc_180095F48
0x180095f28  test    rdi, rdi
0x180095f2b  jz      short loc_180095F43
0x180095f2d  cmp     [rbp+57h+var_58], r13b
0x180095f31  jz      short loc_180095F43
0x180095f33  mov     rcx, rdi; hMem
0x180095f36  call    cs:__imp_LocalFree
0x180095f3d  nop     dword ptr [rax+rax+00h]
0x180095f42  nop
0x180095f43  jmp     loc_180095E69
0x180095f48  test    rdi, rdi
0x180095f4b  jz      short loc_180095F63
0x180095f4d  cmp     [rbp+57h+var_58], r13b
0x180095f51  jz      short loc_180095F63
0x180095f53  mov     rcx, rdi; hMem
0x180095f56  call    cs:__imp_LocalFree
0x180095f5d  nop     dword ptr [rax+rax+00h]
0x180095f62  nop
0x180095f63  mov     rcx, r12
0x180095f66  call    CreateCompatibleDCAdvanced
0x180095f6b  mov     rdi, rax
0x180095f6e  test    rax, rax
0x180095f71  jz      loc_180096112
0x180095f77  lea     rdx, [rbx+34h]; lpxf
0x180095f7b  mov     rcx, rax; hdc
0x180095f7e  call    cs:__imp_SetWorldTransform
0x180095f85  nop     dword ptr [rax+rax+00h]
0x180095f8a  test    eax, eax
0x180095f8c  jz      loc_180096103
0x180095f92  mov     eax, [rbx+28h]
0x180095f95  lea     ecx, ds:0[rax*4]
0x180095f9c  xor     ecx, eax
0x180095f9e  test    ecx, 0CCCC0000h
0x180095fa4  jnz     short loc_180095FF2
0x180095fa6  mov     [rsp+0C0h+rop], eax; rop
0x180095faa  mov     eax, [rbx+68h]
0x180095fad  mov     [rsp+0C0h+yMask], eax; yMask
0x180095fb1  mov     eax, [rbx+64h]
0x180095fb4  mov     [rsp+0C0h+xMask], eax; xMask
0x180095fb8  mov     [rsp+0C0h+hbmMask], rsi; hbmMask
0x180095fbd  mov     eax, [rbx+30h]
0x180095fc0  mov     [rsp+0C0h+ySrc], eax; ySrc
0x180095fc4  mov     eax, [rbx+2Ch]
0x180095fc7  mov     [rsp+0C0h+xSrc], eax; xSrc
0x180095fcb  mov     [rsp+0C0h+hdcSrc], rdi; hdcSrc
0x180095fd0  mov     eax, [rbx+24h]
0x180095fd3  mov     [rsp+0C0h+height], eax; height
0x180095fd7  mov     r9d, [rbx+20h]; width
0x180095fdb  mov     r8d, [rbx+1Ch]; yDest
0x180095fdf  mov     edx, [rbx+18h]; xDest
0x180095fe2  mov     rcx, r12; hdcDest
0x180095fe5  call    MaskBlt
0x180095fea  mov     r13d, eax
0x180095fed  jmp     loc_180096103
0x180095ff2  lea     rax, [rbp+57h+pbmih]
0x180095ff6  mov     [rsp+0C0h+hbmMask], rax; BitmapInfoPtr *
0x180095ffb  mov     [rsp+0C0h+ySrc], 0; int
0x180096003  mov     eax, [rbx+50h]
0x180096006  mov     [rsp+0C0h+xSrc], eax; int
0x18009600a  mov     eax, [rbx+60h]
0x18009600d  mov     dword ptr [rsp+0C0h+hdcSrc], eax; int
0x180096011  mov     eax, [rbx+5Ch]
0x180096014  mov     [rsp+0C0h+height], eax; int
0x180096018  mov     r9d, [rbx+58h]
0x18009601c  mov     r8d, [rbx+54h]
0x180096020  mov     rdx, rbx; this
0x180096023  mov     rcx, r15; struct tagHANDLETABLE *
0x180096026  call    bCheckBitmap
0x18009602b  mov     r14, [rbp+57h+pbmih]
0x18009602f  test    eax, eax
0x180096031  jz      loc_180096103
0x180096037  mov     ecx, [rbx+54h]
0x18009603a  add     rcx, rbx
0x18009603d  mov     r9d, [rbx+5Ch]
0x180096041  add     r9, rbx; pjBits
0x180096044  mov     eax, [rbx+50h]
0x180096047  mov     dword ptr [rsp+0C0h+hdcSrc], eax; iUsage
0x18009604b  mov     qword ptr [rsp+0C0h+height], rcx; pbmi
0x180096050  mov     r8d, 6; flInit
0x180096056  mov     rdx, r14; pbmih
0x180096059  mov     rcx, rdi; hdc
0x18009605c  call    CreateDIBitmap
0x180096061  mov     r12, rax
0x180096064  test    rax, rax
0x180096067  jz      loc_180096103
0x18009606d  mov     rdx, rax; h
0x180096070  mov     rcx, rdi; hdc
0x180096073  call    cs:__imp_SelectObject
0x18009607a  nop     dword ptr [rax+rax+00h]
0x18009607f  mov     r15, rax
0x180096082  test    rax, rax
0x180096085  jz      short loc_1800960F4
0x180096087  mov     edx, [rbx+4Ch]; color
0x18009608a  mov     rcx, rdi; hdc
0x18009608d  call    SetBkColor
0x180096092  cmp     eax, 0FFFFFFFFh
0x180096095  jz      short loc_1800960E2
0x180096097  mov     ecx, [rbx+28h]
0x18009609a  mov     [rsp+0C0h+rop], ecx; rop
0x18009609e  mov     ecx, [rbx+68h]
0x1800960a1  mov     [rsp+0C0h+yMask], ecx; yMask
0x1800960a5  mov     eax, [rbx+64h]
0x1800960a8  mov     [rsp+0C0h+xMask], eax; xMask
0x1800960ac  mov     [rsp+0C0h+hbmMask], rsi; hbmMask
0x1800960b1  mov     eax, [rbx+30h]
0x1800960b4  mov     [rsp+0C0h+ySrc], eax; ySrc
0x1800960b8  mov     eax, [rbx+2Ch]
0x1800960bb  mov     [rsp+0C0h+xSrc], eax; xSrc
0x1800960bf  mov     [rsp+0C0h+hdcSrc], rdi; hdcSrc
0x1800960c4  mov     eax, [rbx+24h]
0x1800960c7  mov     [rsp+0C0h+height], eax; height
0x1800960cb  mov     r9d, [rbx+20h]; width
0x1800960cf  mov     r8d, [rbx+1Ch]; yDest
0x1800960d3  mov     edx, [rbx+18h]; xDest
0x1800960d6  mov     rcx, [rbp+57h+hdcDest]; hdcDest
0x1800960da  call    MaskBlt
0x1800960df  mov     r13d, eax
0x1800960e2  mov     rdx, r15; h
0x1800960e5  mov     rcx, rdi; hdc
0x1800960e8  call    cs:__imp_SelectObject
0x1800960ef  nop     dword ptr [rax+rax+00h]
0x1800960f4  mov     rcx, r12; ho
0x1800960f7  call    cs:__imp_DeleteObject
0x1800960fe  nop     dword ptr [rax+rax+00h]
0x180096103  mov     rcx, rdi; hdc
0x180096106  call    cs:__imp_DeleteDC
0x18009610d  nop     dword ptr [rax+rax+00h]
0x180096112  test    rsi, rsi
0x180096115  jz      short loc_180096127
0x180096117  mov     rcx, rsi; ho
0x18009611a  call    cs:__imp_DeleteObject
0x180096121  nop     dword ptr [rax+rax+00h]
0x180096126  nop
0x180096127  test    r14, r14
0x18009612a  jz      short loc_180096142
0x18009612c  cmp     [rbp+57h+var_48], 0
0x180096130  jz      short loc_180096142
0x180096132  mov     rcx, r14; hMem
0x180096135  call    cs:__imp_LocalFree
0x18009613c  nop     dword ptr [rax+rax+00h]
0x180096141  nop
0x180096142  mov     eax, r13d
0x180096145  add     rsp, 88h
0x18009614c  pop     r15
0x18009614e  pop     r14
0x180096150  pop     r13
0x180096152  pop     r12
0x180096154  pop     rdi
0x180096155  pop     rsi
0x180096156  pop     rbx
0x180096157  pop     rbp
0x180096158  retn
```
