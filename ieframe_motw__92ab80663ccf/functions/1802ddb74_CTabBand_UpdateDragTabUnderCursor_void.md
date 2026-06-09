# CTabBand::UpdateDragTabUnderCursor(void)

- ea: `0x1802ddb74`
- end: `0x1802dde2f`
- name: `?UpdateDragTabUnderCursor@CTabBand@@QEAAXXZ`
- size: `699`
- prototype: `void __fastcall(CTabBand *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1802dde38`
- `0x1802de0f4`
- `0x1802de988`

## callees

- `0x1802ddb74`
- `0x1802dea5c`
- `0x1802deb88`
- `0x1802ded0c`
- `0x1802dee88`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x1802ddc5e`
- `GDI32!CreateDIBSection` at `0x1802ddc5e`
- `GDI32!GdiFlush` at `0x1802ddce1`
- `GDI32!GdiFlush` at `0x1802ddce1`
- `GDI32!DeleteObject` at `0x1802ddde2`
- `GDI32!DeleteObject` at `0x1802ddde2`
- `GDI32!SelectObject` at `0x1802ddc7c`
- `GDI32!SelectObject` at `0x1802ddcd5`
- `GDI32!SelectObject` at `0x1802ddd2b`
- `GDI32!SelectObject` at `0x1802dddd3`
- `GDI32!SelectObject` at `0x1802ddc7c`
- `GDI32!SelectObject` at `0x1802ddcd5`
- `GDI32!SelectObject` at `0x1802ddd2b`
- `GDI32!SelectObject` at `0x1802dddd3`
- `GDI32!DeleteDC` at `0x1802dddf1`
- `GDI32!DeleteDC` at `0x1802dddf1`
- `GDI32!CreateCompatibleDC` at `0x1802ddbd0`
- `GDI32!CreateCompatibleDC` at `0x1802ddbd0`
- `USER32!UpdateLayeredWindow` at `0x1802ddda9`
- `USER32!UpdateLayeredWindow` at `0x1802ddda9`
- `USER32!ReleaseDC` at `0x1802dddbf`
- `USER32!ReleaseDC` at `0x1802dde02`
- `USER32!ReleaseDC` at `0x1802dddbf`
- `USER32!ReleaseDC` at `0x1802dde02`
- `USER32!GetDC` at `0x1802ddbb0`
- `USER32!GetDC` at `0x1802ddd5a`
- `USER32!GetDC` at `0x1802ddbb0`
- `USER32!GetDC` at `0x1802ddd5a`

## pseudocode

```c
void __fastcall CTabBand::UpdateDragTabUnderCursor(CTabBand *this)
{
  HDC DC; // rax
  HDC v3; // r14
  HDC CompatibleDC; // rdi
  int v5; // r15d
  LONG v6; // r12d
  LONG v7; // r15d
  HBITMAP v8; // rax
  HBITMAP v9; // r13
  HGDIOBJ v10; // rax
  void *v11; // rbx
  CTabBand *v12; // rcx
  struct tagRECT *v13; // r8
  struct tagRECT *v14; // r8
  _DWORD *v15; // rcx
  LONG v16; // edx
  LONG i; // eax
  HGDIOBJ v18; // rax
  HWND v19; // rcx
  HDC v20; // rbx
  BLENDFUNCTION pblend; // [rsp+50h] [rbp-B0h] BYREF
  HGDIOBJ h; // [rsp+58h] [rbp-A8h]
  void *ppvBits; // [rsp+60h] [rbp-A0h] BYREF
  POINT pptSrc; // [rsp+68h] [rbp-98h] BYREF
  SIZE psize; // [rsp+70h] [rbp-90h] BYREF
  struct tagRECT v26; // [rsp+78h] [rbp-88h] BYREF
  BITMAPINFO pbmi; // [rsp+90h] [rbp-70h] BYREF
  int v28; // [rsp+BCh] [rbp-44h]
  int v29; // [rsp+C0h] [rbp-40h]
  int v30; // [rsp+C4h] [rbp-3Ch]

  if ( *((_QWORD *)this + 33) )
  {
    DC = GetDC(0);
    h = DC;
    v3 = DC;
    if ( DC )
    {
      CompatibleDC = CreateCompatibleDC(DC);
      if ( CompatibleDC )
      {
        v5 = *((_DWORD *)this + 69);
        v6 = *((_DWORD *)this + 68);
        ppvBits = 0;
        v7 = v5 + 1;
        memset_0(&pbmi, 0, 0x7Cu);
        pbmi.bmiHeader.biSize = 124;
        pbmi.bmiHeader.biWidth = v6;
        pbmi.bmiHeader.biHeight = v7;
        *(_DWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
        pbmi.bmiHeader.biCompression = 3;
        v30 = -16777216;
        pbmi.bmiColors[0] = (RGBQUAD)16711680;
        v28 = 65280;
        v29 = 255;
        v8 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
        v9 = v8;
        if ( v8 )
        {
          v10 = SelectObject(CompatibleDC, v8);
          *(_QWORD *)&v26.left = 0;
          v26.right = v6;
          v11 = v10;
          v26.bottom = v7;
          CTabBand::_DrawDragTabBorder(v12, CompatibleDC, &v26);
          CTabBand::_DrawDragTabGradient(this, CompatibleDC, &v26);
          CTabBand::_DrawDragTabFavicon(this, CompatibleDC, v13);
          CTabBand::_DrawDragTabTitle(this, CompatibleDC, v14);
          SelectObject(CompatibleDC, v11);
          GdiFlush();
          v15 = ppvBits;
          v16 = 0;
          if ( v7 > 0 )
          {
            do
            {
              for ( i = 0; i < v6; ++v15 )
              {
                *v15 |= 0xFF000000;
                ++i;
              }
              ++v16;
            }
            while ( v16 < v7 );
            v3 = (HDC)h;
          }
          v18 = SelectObject(CompatibleDC, v9);
          v19 = (HWND)*((_QWORD *)this + 33);
          h = v18;
          pblend = (BLENDFUNCTION)33488896;
          psize.cx = v6;
          psize.cy = v7;
          pptSrc = 0;
          v20 = GetDC(v19);
          if ( v20 )
          {
            UpdateLayeredWindow(*((HWND *)this + 33), v20, 0, &psize, CompatibleDC, &pptSrc, 0xFFFFFFFF, &pblend, 2u);
            ReleaseDC(*((HWND *)this + 33), v20);
          }
          SelectObject(CompatibleDC, h);
          DeleteObject(v9);
        }
        DeleteDC(CompatibleDC);
      }
      ReleaseDC(0, v3);
    }
  }
}

```

## disassembly

```asm
0x1802ddb74  push    rbp
0x1802ddb76  push    rbx
0x1802ddb77  push    rsi
0x1802ddb78  push    rdi
0x1802ddb79  push    r12
0x1802ddb7b  push    r13
0x1802ddb7d  push    r14
0x1802ddb7f  push    r15
0x1802ddb81  lea     rbp, [rsp-28h]
0x1802ddb86  sub     rsp, 128h
0x1802ddb8d  mov     rax, cs:__security_cookie
0x1802ddb94  xor     rax, rsp
0x1802ddb97  mov     [rbp+60h+var_50], rax
0x1802ddb9b  xor     r13d, r13d
0x1802ddb9e  mov     rsi, rcx
0x1802ddba1  cmp     [rcx+108h], r13
0x1802ddba8  jz      loc_1802DDE0E
0x1802ddbae  xor     ecx, ecx; hWnd
0x1802ddbb0  call    cs:__imp_GetDC
0x1802ddbb7  nop     dword ptr [rax+rax+00h]
0x1802ddbbc  mov     [rsp+160h+h], rax
0x1802ddbc1  mov     r14, rax
0x1802ddbc4  test    rax, rax
0x1802ddbc7  jz      loc_1802DDE0E
0x1802ddbcd  mov     rcx, rax; hdc
0x1802ddbd0  call    cs:__imp_CreateCompatibleDC
0x1802ddbd7  nop     dword ptr [rax+rax+00h]
0x1802ddbdc  mov     rdi, rax
0x1802ddbdf  test    rax, rax
0x1802ddbe2  jz      loc_1802DDDFD
0x1802ddbe8  mov     r15d, [rsi+114h]
0x1802ddbef  lea     ebx, [r13+7Ch]
0x1802ddbf3  mov     r12d, [rsi+110h]
0x1802ddbfa  lea     rcx, [rbp+60h+pbmi]; void *
0x1802ddbfe  mov     r8d, ebx; Size
0x1802ddc01  mov     [rsp+160h+ppvBits], r13
0x1802ddc06  xor     edx, edx; Val
0x1802ddc08  inc     r15d
0x1802ddc0b  call    memset_0
0x1802ddc10  lea     r9, [rsp+160h+ppvBits]; ppvBits
0x1802ddc15  mov     [rsp+160h+offset], r13d; offset
0x1802ddc1a  xor     r8d, r8d; usage
0x1802ddc1d  mov     [rbp+60h+pbmi.bmiHeader.biSize], ebx
0x1802ddc20  lea     rdx, [rbp+60h+pbmi]; pbmi
0x1802ddc24  mov     [rbp+60h+pbmi.bmiHeader.biWidth], r12d
0x1802ddc28  mov     rcx, rdi; hdc
0x1802ddc2b  mov     [rbp+60h+pbmi.bmiHeader.biHeight], r15d
0x1802ddc2f  mov     dword ptr [rbp+60h+pbmi.bmiHeader.biPlanes], 200001h
0x1802ddc36  mov     [rbp+60h+pbmi.bmiHeader.biCompression], 3
0x1802ddc3d  mov     [rbp+60h+var_9C], 0FF000000h
0x1802ddc44  mov     dword ptr [rbp+60h+pbmi.bmiColors.rgbBlue], 0FF0000h
0x1802ddc4b  mov     [rbp+60h+var_A4], 0FF00h
0x1802ddc52  mov     [rbp+60h+var_A0], 0FFh
0x1802ddc59  mov     [rsp+160h+hSection], r13; hSection
0x1802ddc5e  call    cs:__imp_CreateDIBSection
0x1802ddc65  nop     dword ptr [rax+rax+00h]
0x1802ddc6a  mov     r13, rax
0x1802ddc6d  test    rax, rax
0x1802ddc70  jz      loc_1802DDDEE
0x1802ddc76  mov     rdx, rax; h
0x1802ddc79  mov     rcx, rdi; hdc
0x1802ddc7c  call    cs:__imp_SelectObject
0x1802ddc83  nop     dword ptr [rax+rax+00h]
0x1802ddc88  lea     r8, [rsp+160h+var_E8]; struct tagRECT *
0x1802ddc8d  mov     qword ptr [rsp+160h+var_E8.left], 0
0x1802ddc96  mov     rdx, rdi; HDC
0x1802ddc99  mov     [rbp+60h+var_E8.right], r12d
0x1802ddc9d  mov     rbx, rax
0x1802ddca0  mov     [rbp+60h+var_E8.bottom], r15d
0x1802ddca4  call    ?_DrawDragTabBorder@CTabBand@@IEAAXPEAUHDC__@@PEAUtagRECT@@@Z; CTabBand::_DrawDragTabBorder(HDC__ *,tagRECT *)
0x1802ddca9  lea     r8, [rsp+160h+var_E8]; struct tagRECT *
0x1802ddcae  mov     rdx, rdi; HDC
0x1802ddcb1  mov     rcx, rsi; this
0x1802ddcb4  call    ?_DrawDragTabGradient@CTabBand@@IEAAXPEAUHDC__@@PEAUtagRECT@@@Z; CTabBand::_DrawDragTabGradient(HDC__ *,tagRECT *)
0x1802ddcb9  mov     rdx, rdi; HDC
0x1802ddcbc  mov     rcx, rsi; this
0x1802ddcbf  call    ?_DrawDragTabFavicon@CTabBand@@IEAAXPEAUHDC__@@PEAUtagRECT@@@Z; CTabBand::_DrawDragTabFavicon(HDC__ *,tagRECT *)
0x1802ddcc4  mov     rdx, rdi; HDC
0x1802ddcc7  mov     rcx, rsi; this
0x1802ddcca  call    ?_DrawDragTabTitle@CTabBand@@IEAAXPEAUHDC__@@PEAUtagRECT@@@Z; CTabBand::_DrawDragTabTitle(HDC__ *,tagRECT *)
0x1802ddccf  mov     rdx, rbx; h
0x1802ddcd2  mov     rcx, rdi; hdc
0x1802ddcd5  call    cs:__imp_SelectObject
0x1802ddcdc  nop     dword ptr [rax+rax+00h]
0x1802ddce1  call    cs:__imp_GdiFlush
0x1802ddce8  nop     dword ptr [rax+rax+00h]
0x1802ddced  mov     rcx, [rsp+160h+ppvBits]
0x1802ddcf2  xor     ebx, ebx
0x1802ddcf4  mov     edx, ebx
0x1802ddcf6  test    r15d, r15d
0x1802ddcf9  jle     short loc_1802DDD25
0x1802ddcfb  lea     r14d, [rbx+1]
0x1802ddcff  mov     eax, ebx
0x1802ddd01  test    r12d, r12d
0x1802ddd04  jle     short loc_1802DDD18
0x1802ddd06  or      dword ptr [rcx], 0FF000000h
0x1802ddd0c  add     eax, r14d
0x1802ddd0f  add     rcx, 4
0x1802ddd13  cmp     eax, r12d
0x1802ddd16  jl      short loc_1802DDD06
0x1802ddd18  add     edx, r14d
0x1802ddd1b  cmp     edx, r15d
0x1802ddd1e  jl      short loc_1802DDCFF
0x1802ddd20  mov     r14, [rsp+160h+h]
0x1802ddd25  mov     rdx, r13; h
0x1802ddd28  mov     rcx, rdi; hdc
0x1802ddd2b  call    cs:__imp_SelectObject
0x1802ddd32  nop     dword ptr [rax+rax+00h]
0x1802ddd37  mov     rcx, [rsi+108h]; hWnd
0x1802ddd3e  mov     [rsp+160h+h], rax
0x1802ddd43  mov     dword ptr [rsp+160h+var_110.BlendOp], 1FF0000h
0x1802ddd4b  mov     [rsp+160h+psize.cx], r12d
0x1802ddd50  mov     [rsp+160h+psize.cy], r15d
0x1802ddd55  mov     qword ptr [rsp+160h+pptSrc.x], rbx
0x1802ddd5a  call    cs:__imp_GetDC
0x1802ddd61  nop     dword ptr [rax+rax+00h]
0x1802ddd66  mov     rbx, rax
0x1802ddd69  test    rax, rax
0x1802ddd6c  jz      short loc_1802DDDCB
0x1802ddd6e  mov     rcx, [rsi+108h]; hWnd
0x1802ddd75  lea     rax, [rsp+160h+var_110]
0x1802ddd7a  mov     [rsp+160h+dwFlags], 2; dwFlags
0x1802ddd82  lea     r9, [rsp+160h+psize]; psize
0x1802ddd87  mov     [rsp+160h+pblend], rax; pblend
0x1802ddd8c  xor     r8d, r8d; pptDst
0x1802ddd8f  lea     rax, [rsp+160h+pptSrc]
0x1802ddd94  mov     [rsp+160h+crKey], 0FFFFFFFFh; crKey
0x1802ddd9c  mov     qword ptr [rsp+160h+offset], rax; pptSrc
0x1802ddda1  mov     rdx, rbx; hdcDst
0x1802ddda4  mov     [rsp+160h+hSection], rdi; hdcSrc
0x1802ddda9  call    cs:__imp_UpdateLayeredWindow
0x1802dddb0  nop     dword ptr [rax+rax+00h]
0x1802dddb5  mov     rcx, [rsi+108h]; hWnd
0x1802dddbc  mov     rdx, rbx; hDC
0x1802dddbf  call    cs:__imp_ReleaseDC
0x1802dddc6  nop     dword ptr [rax+rax+00h]
0x1802dddcb  mov     rdx, [rsp+160h+h]; h
0x1802dddd0  mov     rcx, rdi; hdc
0x1802dddd3  call    cs:__imp_SelectObject
0x1802dddda  nop     dword ptr [rax+rax+00h]
0x1802ddddf  mov     rcx, r13; ho
0x1802ddde2  call    cs:__imp_DeleteObject
0x1802ddde9  nop     dword ptr [rax+rax+00h]
0x1802dddee  mov     rcx, rdi; hdc
0x1802dddf1  call    cs:__imp_DeleteDC
0x1802dddf8  nop     dword ptr [rax+rax+00h]
0x1802dddfd  mov     rdx, r14; hDC
0x1802dde00  xor     ecx, ecx; hWnd
0x1802dde02  call    cs:__imp_ReleaseDC
0x1802dde09  nop     dword ptr [rax+rax+00h]
0x1802dde0e  mov     rcx, [rbp+60h+var_50]
0x1802dde12  xor     rcx, rsp; StackCookie
0x1802dde15  call    __security_check_cookie
0x1802dde1a  add     rsp, 128h
0x1802dde21  pop     r15
0x1802dde23  pop     r14
0x1802dde25  pop     r13
0x1802dde27  pop     r12
0x1802dde29  pop     rdi
0x1802dde2a  pop     rsi
0x1802dde2b  pop     rbx
0x1802dde2c  pop     rbp
0x1802dde2d  retn
```
