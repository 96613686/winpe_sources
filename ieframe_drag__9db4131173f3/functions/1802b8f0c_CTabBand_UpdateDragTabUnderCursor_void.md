# CTabBand::UpdateDragTabUnderCursor(void)

- ea: `0x1802b8f0c`
- end: `0x1802b9172`
- name: `?UpdateDragTabUnderCursor@CTabBand@@QEAAXXZ`
- size: `614`
- prototype: `void __fastcall(CTabBand *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1802b9178`
- `0x1802b9400`
- `0x1802b9c84`

## callees

- `0x1802b8f0c`
- `0x1802b9d54`
- `0x1802b9e48`
- `0x1802b9fb8`
- `0x1802ba0fc`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x1802b8fea`
- `GDI32!CreateDIBSection` at `0x1802b8fea`
- `GDI32!GdiFlush` at `0x1802b905b`
- `GDI32!GdiFlush` at `0x1802b905b`
- `GDI32!DeleteObject` at `0x1802b9138`
- `GDI32!DeleteObject` at `0x1802b9138`
- `GDI32!SelectObject` at `0x1802b9002`
- `GDI32!SelectObject` at `0x1802b9055`
- `GDI32!SelectObject` at `0x1802b909f`
- `GDI32!SelectObject` at `0x1802b912f`
- `GDI32!SelectObject` at `0x1802b9002`
- `GDI32!SelectObject` at `0x1802b9055`
- `GDI32!SelectObject` at `0x1802b909f`
- `GDI32!SelectObject` at `0x1802b912f`
- `GDI32!DeleteDC` at `0x1802b9141`
- `GDI32!DeleteDC` at `0x1802b9141`
- `GDI32!CreateCompatibleDC` at `0x1802b8f62`
- `GDI32!CreateCompatibleDC` at `0x1802b8f62`
- `USER32!UpdateLayeredWindow` at `0x1802b9111`
- `USER32!UpdateLayeredWindow` at `0x1802b9111`
- `USER32!ReleaseDC` at `0x1802b9121`
- `USER32!ReleaseDC` at `0x1802b914c`
- `USER32!ReleaseDC` at `0x1802b9121`
- `USER32!ReleaseDC` at `0x1802b914c`
- `USER32!GetDC` at `0x1802b8f48`
- `USER32!GetDC` at `0x1802b90c8`
- `USER32!GetDC` at `0x1802b8f48`
- `USER32!GetDC` at `0x1802b90c8`

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
0x1802b8f0c  push    rbp
0x1802b8f0e  push    rbx
0x1802b8f0f  push    rsi
0x1802b8f10  push    rdi
0x1802b8f11  push    r12
0x1802b8f13  push    r13
0x1802b8f15  push    r14
0x1802b8f17  push    r15
0x1802b8f19  lea     rbp, [rsp-28h]
0x1802b8f1e  sub     rsp, 128h
0x1802b8f25  mov     rax, cs:__security_cookie
0x1802b8f2c  xor     rax, rsp
0x1802b8f2f  mov     [rbp+60h+var_50], rax
0x1802b8f33  xor     r13d, r13d
0x1802b8f36  mov     rsi, rcx
0x1802b8f39  cmp     [rcx+108h], r13
0x1802b8f40  jz      loc_1802B9152
0x1802b8f46  xor     ecx, ecx; hWnd
0x1802b8f48  call    cs:__imp_GetDC
0x1802b8f4e  mov     [rsp+160h+h], rax
0x1802b8f53  mov     r14, rax
0x1802b8f56  test    rax, rax
0x1802b8f59  jz      loc_1802B9152
0x1802b8f5f  mov     rcx, rax; hdc
0x1802b8f62  call    cs:__imp_CreateCompatibleDC
0x1802b8f68  mov     rdi, rax
0x1802b8f6b  test    rax, rax
0x1802b8f6e  jz      loc_1802B9147
0x1802b8f74  mov     r15d, [rsi+114h]
0x1802b8f7b  lea     ebx, [r13+7Ch]
0x1802b8f7f  mov     r12d, [rsi+110h]
0x1802b8f86  lea     rcx, [rbp+60h+pbmi]; void *
0x1802b8f8a  mov     r8d, ebx; Size
0x1802b8f8d  mov     [rsp+160h+ppvBits], r13
0x1802b8f92  xor     edx, edx; Val
0x1802b8f94  inc     r15d
0x1802b8f97  call    memset_0
0x1802b8f9c  lea     r9, [rsp+160h+ppvBits]; ppvBits
0x1802b8fa1  mov     [rsp+160h+offset], r13d; offset
0x1802b8fa6  xor     r8d, r8d; usage
0x1802b8fa9  mov     [rbp+60h+pbmi.bmiHeader.biSize], ebx
0x1802b8fac  lea     rdx, [rbp+60h+pbmi]; pbmi
0x1802b8fb0  mov     [rbp+60h+pbmi.bmiHeader.biWidth], r12d
0x1802b8fb4  mov     rcx, rdi; hdc
0x1802b8fb7  mov     [rbp+60h+pbmi.bmiHeader.biHeight], r15d
0x1802b8fbb  mov     dword ptr [rbp+60h+pbmi.bmiHeader.biPlanes], 200001h
0x1802b8fc2  mov     [rbp+60h+pbmi.bmiHeader.biCompression], 3
0x1802b8fc9  mov     [rbp+60h+var_9C], 0FF000000h
0x1802b8fd0  mov     dword ptr [rbp+60h+pbmi.bmiColors.rgbBlue], 0FF0000h
0x1802b8fd7  mov     [rbp+60h+var_A4], 0FF00h
0x1802b8fde  mov     [rbp+60h+var_A0], 0FFh
0x1802b8fe5  mov     [rsp+160h+hSection], r13; hSection
0x1802b8fea  call    cs:__imp_CreateDIBSection
0x1802b8ff0  mov     r13, rax
0x1802b8ff3  test    rax, rax
0x1802b8ff6  jz      loc_1802B913E
0x1802b8ffc  mov     rdx, rax; h
0x1802b8fff  mov     rcx, rdi; hdc
0x1802b9002  call    cs:__imp_SelectObject
0x1802b9008  lea     r8, [rsp+160h+var_E8]; struct tagRECT *
0x1802b900d  mov     qword ptr [rsp+160h+var_E8.left], 0
0x1802b9016  mov     rdx, rdi; HDC
0x1802b9019  mov     [rbp+60h+var_E8.right], r12d
0x1802b901d  mov     rbx, rax
0x1802b9020  mov     [rbp+60h+var_E8.bottom], r15d
0x1802b9024  call    ?_DrawDragTabBorder@CTabBand@@IEAAXPEAUHDC__@@PEAUtagRECT@@@Z; CTabBand::_DrawDragTabBorder(HDC__ *,tagRECT *)
0x1802b9029  lea     r8, [rsp+160h+var_E8]; struct tagRECT *
0x1802b902e  mov     rdx, rdi; HDC
0x1802b9031  mov     rcx, rsi; this
0x1802b9034  call    ?_DrawDragTabGradient@CTabBand@@IEAAXPEAUHDC__@@PEAUtagRECT@@@Z; CTabBand::_DrawDragTabGradient(HDC__ *,tagRECT *)
0x1802b9039  mov     rdx, rdi; HDC
0x1802b903c  mov     rcx, rsi; this
0x1802b903f  call    ?_DrawDragTabFavicon@CTabBand@@IEAAXPEAUHDC__@@PEAUtagRECT@@@Z; CTabBand::_DrawDragTabFavicon(HDC__ *,tagRECT *)
0x1802b9044  mov     rdx, rdi; HDC
0x1802b9047  mov     rcx, rsi; this
0x1802b904a  call    ?_DrawDragTabTitle@CTabBand@@IEAAXPEAUHDC__@@PEAUtagRECT@@@Z; CTabBand::_DrawDragTabTitle(HDC__ *,tagRECT *)
0x1802b904f  mov     rdx, rbx; h
0x1802b9052  mov     rcx, rdi; hdc
0x1802b9055  call    cs:__imp_SelectObject
0x1802b905b  call    cs:__imp_GdiFlush
0x1802b9061  mov     rcx, [rsp+160h+ppvBits]
0x1802b9066  xor     ebx, ebx
0x1802b9068  mov     edx, ebx
0x1802b906a  test    r15d, r15d
0x1802b906d  jle     short loc_1802B9099
0x1802b906f  lea     r14d, [rbx+1]
0x1802b9073  mov     eax, ebx
0x1802b9075  test    r12d, r12d
0x1802b9078  jle     short loc_1802B908C
0x1802b907a  or      dword ptr [rcx], 0FF000000h
0x1802b9080  add     eax, r14d
0x1802b9083  add     rcx, 4
0x1802b9087  cmp     eax, r12d
0x1802b908a  jl      short loc_1802B907A
0x1802b908c  add     edx, r14d
0x1802b908f  cmp     edx, r15d
0x1802b9092  jl      short loc_1802B9073
0x1802b9094  mov     r14, [rsp+160h+h]
0x1802b9099  mov     rdx, r13; h
0x1802b909c  mov     rcx, rdi; hdc
0x1802b909f  call    cs:__imp_SelectObject
0x1802b90a5  mov     rcx, [rsi+108h]; hWnd
0x1802b90ac  mov     [rsp+160h+h], rax
0x1802b90b1  mov     dword ptr [rsp+160h+var_110.BlendOp], 1FF0000h
0x1802b90b9  mov     [rsp+160h+psize.cx], r12d
0x1802b90be  mov     [rsp+160h+psize.cy], r15d
0x1802b90c3  mov     qword ptr [rsp+160h+pptSrc.x], rbx
0x1802b90c8  call    cs:__imp_GetDC
0x1802b90ce  mov     rbx, rax
0x1802b90d1  test    rax, rax
0x1802b90d4  jz      short loc_1802B9127
0x1802b90d6  mov     rcx, [rsi+108h]; hWnd
0x1802b90dd  lea     rax, [rsp+160h+var_110]
0x1802b90e2  mov     [rsp+160h+dwFlags], 2; dwFlags
0x1802b90ea  lea     r9, [rsp+160h+psize]; psize
0x1802b90ef  mov     [rsp+160h+pblend], rax; pblend
0x1802b90f4  xor     r8d, r8d; pptDst
0x1802b90f7  lea     rax, [rsp+160h+pptSrc]
0x1802b90fc  mov     [rsp+160h+crKey], 0FFFFFFFFh; crKey
0x1802b9104  mov     qword ptr [rsp+160h+offset], rax; pptSrc
0x1802b9109  mov     rdx, rbx; hdcDst
0x1802b910c  mov     [rsp+160h+hSection], rdi; hdcSrc
0x1802b9111  call    cs:__imp_UpdateLayeredWindow
0x1802b9117  mov     rcx, [rsi+108h]; hWnd
0x1802b911e  mov     rdx, rbx; hDC
0x1802b9121  call    cs:__imp_ReleaseDC
0x1802b9127  mov     rdx, [rsp+160h+h]; h
0x1802b912c  mov     rcx, rdi; hdc
0x1802b912f  call    cs:__imp_SelectObject
0x1802b9135  mov     rcx, r13; ho
0x1802b9138  call    cs:__imp_DeleteObject
0x1802b913e  mov     rcx, rdi; hdc
0x1802b9141  call    cs:__imp_DeleteDC
0x1802b9147  mov     rdx, r14; hDC
0x1802b914a  xor     ecx, ecx; hWnd
0x1802b914c  call    cs:__imp_ReleaseDC
0x1802b9152  mov     rcx, [rbp+60h+var_50]
0x1802b9156  xor     rcx, rsp; StackCookie
0x1802b9159  call    __security_check_cookie
0x1802b915e  add     rsp, 128h
0x1802b9165  pop     r15
0x1802b9167  pop     r14
0x1802b9169  pop     r13
0x1802b916b  pop     r12
0x1802b916d  pop     rdi
0x1802b916e  pop     rsi
0x1802b916f  pop     rbx
0x1802b9170  pop     rbp
0x1802b9171  retn
```
