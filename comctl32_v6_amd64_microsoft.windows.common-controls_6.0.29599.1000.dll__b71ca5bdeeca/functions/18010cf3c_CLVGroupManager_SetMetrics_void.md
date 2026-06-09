# CLVGroupManager::SetMetrics(void)

- ea: `0x18010cf3c`
- end: `0x18010d29c`
- name: `?SetMetrics@CLVGroupManager@@QEAAXXZ`
- size: `864`
- prototype: `void __fastcall(CLVGroupManager *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18005f260`
- `0x180077618`
- `0x18010ceb4`

## callees

- `0x18010cf3c`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `GDI32!DeleteObject` at `0x18010d13c`
- `GDI32!DeleteObject` at `0x18010d1be`
- `GDI32!DeleteObject` at `0x18010d240`
- `GDI32!DeleteObject` at `0x18010d13c`
- `GDI32!DeleteObject` at `0x18010d1be`
- `GDI32!DeleteObject` at `0x18010d240`
- `GDI32!GetTextMetricsW` at `0x18010d120`
- `GDI32!GetTextMetricsW` at `0x18010d1a2`
- `GDI32!GetTextMetricsW` at `0x18010d224`
- `GDI32!GetTextMetricsW` at `0x18010d120`
- `GDI32!GetTextMetricsW` at `0x18010d1a2`
- `GDI32!GetTextMetricsW` at `0x18010d224`
- `GDI32!SelectObject` at `0x18010d10f`
- `GDI32!SelectObject` at `0x18010d133`
- `GDI32!SelectObject` at `0x18010d191`
- `GDI32!SelectObject` at `0x18010d1b5`
- `GDI32!SelectObject` at `0x18010d213`
- `GDI32!SelectObject` at `0x18010d237`
- `GDI32!SelectObject` at `0x18010d10f`
- `GDI32!SelectObject` at `0x18010d133`
- `GDI32!SelectObject` at `0x18010d191`
- `GDI32!SelectObject` at `0x18010d1b5`
- `GDI32!SelectObject` at `0x18010d213`
- `GDI32!SelectObject` at `0x18010d237`
- `GDI32!CreateFontIndirectW` at `0x18010d0fb`
- `GDI32!CreateFontIndirectW` at `0x18010d17d`
- `GDI32!CreateFontIndirectW` at `0x18010d1ff`
- `GDI32!CreateFontIndirectW` at `0x18010d0fb`
- `GDI32!CreateFontIndirectW` at `0x18010d17d`
- `GDI32!CreateFontIndirectW` at `0x18010d1ff`
- `USER32!GetDC` at `0x18010cfb1`
- `USER32!GetDC` at `0x18010cfb1`
- `USER32!ReleaseDC` at `0x18010d254`
- `USER32!ReleaseDC` at `0x18010d254`
- `UxTheme!GetThemeMargins` at `0x18010cfec`
- `UxTheme!GetThemeMargins` at `0x18010cfec`
- `UxTheme!GetThemePartSize` at `0x18010d033`
- `UxTheme!GetThemePartSize` at `0x18010d079`
- `UxTheme!GetThemePartSize` at `0x18010d033`
- `UxTheme!GetThemePartSize` at `0x18010d079`
- `UxTheme!GetThemeFont` at `0x18010d0ed`
- `UxTheme!GetThemeFont` at `0x18010d16f`
- `UxTheme!GetThemeFont` at `0x18010d1f1`
- `UxTheme!GetThemeFont` at `0x18010d0ed`
- `UxTheme!GetThemeFont` at `0x18010d16f`
- `UxTheme!GetThemeFont` at `0x18010d1f1`

## pseudocode

```c
void __fastcall CLVGroupManager::SetMetrics(CLVGroupManager *this)
{
  __int64 v2; // rcx
  int v3; // eax
  HDC DC; // rsi
  __int64 v5; // rcx
  __int64 v6; // rax
  HFONT v7; // rax
  HFONT v8; // r14
  HGDIOBJ v9; // rbx
  HFONT v10; // rax
  HFONT v11; // r14
  HGDIOBJ v12; // rbx
  HFONT v13; // rax
  HFONT v14; // r14
  HGDIOBJ v15; // rbx
  int v16; // eax
  int v17; // edx
  int v18; // ecx
  int v19; // r8d
  SIZE psz; // [rsp+40h] [rbp-C0h] BYREF
  struct tagTEXTMETRICW tm; // [rsp+48h] [rbp-B8h] BYREF
  LOGFONTW pFont; // [rsp+90h] [rbp-70h] BYREF

  v2 = *((_QWORD *)this + 17);
  v3 = *(_DWORD *)(v2 + 260);
  *((_DWORD *)this + 26) = v3;
  *((_DWORD *)this + 25) = v3;
  *((_DWORD *)this + 24) = v3;
  *((_DWORD *)this + 22) = 10;
  *((_DWORD *)this + 23) = 10;
  *((_DWORD *)this + 27) = 10;
  *((_DWORD *)this + 28) = 10;
  *(_QWORD *)((char *)this + 116) = 2;
  *((_DWORD *)this + 31) = 0;
  if ( *(_QWORD *)(*(_QWORD *)(v2 + 472) + 24LL) )
  {
    DC = GetDC(*(HWND *)(v2 + 96));
    GetThemeMargins(
      *(HTHEME *)(*(_QWORD *)(*((_QWORD *)this + 17) + 472LL) + 24LL),
      DC,
      6,
      0,
      3602,
      0,
      (MARGINS *)((char *)this + 108));
    v5 = *((_QWORD *)this + 17);
    psz = 0;
    if ( GetThemePartSize(*(HTHEME *)(*(_QWORD *)(v5 + 472) + 24LL), DC, 7, 1, 0, TS_TRUE, &psz) >= 0 )
      *((_DWORD *)this + 31) = psz.cy;
    if ( GetThemePartSize(*(HTHEME *)(*(_QWORD *)(*((_QWORD *)this + 17) + 472LL) + 24LL), DC, 9, 1, 0, TS_DRAW, &psz) >= 0 )
      *((SIZE *)this + 11) = psz;
    if ( DC )
    {
      memset_0(&pFont, 0, sizeof(pFont));
      v6 = *((_QWORD *)this + 17);
      memset(&tm, 0, sizeof(tm));
      if ( GetThemeFont(*(HTHEME *)(*(_QWORD *)(v6 + 472) + 24LL), DC, 6, 0, 210, &pFont) >= 0 )
      {
        v7 = CreateFontIndirectW(&pFont);
        v8 = v7;
        if ( v7 )
        {
          v9 = SelectObject(DC, v7);
          GetTextMetricsW(DC, &tm);
          *((_DWORD *)this + 24) = tm.tmHeight;
          SelectObject(DC, v9);
          DeleteObject(v8);
        }
      }
      if ( GetThemeFont(*(HTHEME *)(*(_QWORD *)(*((_QWORD *)this + 17) + 472LL) + 24LL), DC, 6, 0, 808, &pFont) >= 0 )
      {
        v10 = CreateFontIndirectW(&pFont);
        v11 = v10;
        if ( v10 )
        {
          v12 = SelectObject(DC, v10);
          GetTextMetricsW(DC, &tm);
          *((_DWORD *)this + 25) = tm.tmHeight;
          SelectObject(DC, v12);
          DeleteObject(v11);
        }
      }
      if ( GetThemeFont(*(HTHEME *)(*(_QWORD *)(*((_QWORD *)this + 17) + 472LL) + 24LL), DC, 6, 0, 809, &pFont) >= 0 )
      {
        v13 = CreateFontIndirectW(&pFont);
        v14 = v13;
        if ( v13 )
        {
          v15 = SelectObject(DC, v13);
          GetTextMetricsW(DC, &tm);
          *((_DWORD *)this + 26) = tm.tmHeight;
          SelectObject(DC, v15);
          DeleteObject(v14);
        }
      }
    }
    ReleaseDC(*(HWND *)(*((_QWORD *)this + 17) + 96LL), DC);
    v16 = *((_DWORD *)this + 30);
    v17 = 0;
    v18 = *((_DWORD *)this + 28);
    v19 = *((_DWORD *)this + 27);
  }
  else
  {
    v16 = 12;
    v18 = 0;
    v17 = 12;
    v19 = 12;
  }
  *((_DWORD *)this + 12) = v19;
  *((_DWORD *)this + 13) = v17;
  *((_DWORD *)this + 14) = v18;
  *((_DWORD *)this + 15) = v16;
}

```

## disassembly

```asm
0x18010cf3c  push    rbp
0x18010cf3e  push    rbx
0x18010cf3f  push    rsi
0x18010cf40  push    rdi
0x18010cf41  push    r14
0x18010cf43  push    r15
0x18010cf45  lea     rbp, [rsp-8]
0x18010cf4a  sub     rsp, 108h
0x18010cf51  mov     rax, cs:__security_cookie
0x18010cf58  xor     rax, rsp
0x18010cf5b  mov     [rbp+30h+var_40], rax
0x18010cf5f  mov     rdi, rcx
0x18010cf62  mov     rcx, [rcx+88h]
0x18010cf69  mov     eax, [rcx+104h]
0x18010cf6f  lea     r15, [rdi+6Ch]
0x18010cf73  mov     [rdi+68h], eax
0x18010cf76  mov     [rdi+64h], eax
0x18010cf79  mov     [rdi+60h], eax
0x18010cf7c  mov     eax, 0Ah
0x18010cf81  mov     [rdi+58h], eax
0x18010cf84  mov     [rdi+5Ch], eax
0x18010cf87  mov     [r15], eax
0x18010cf8a  lea     ebx, [rax-8]
0x18010cf8d  mov     [rdi+70h], eax
0x18010cf90  mov     [rdi+74h], rbx
0x18010cf94  mov     dword ptr [rdi+7Ch], 0
0x18010cf9b  mov     rax, [rcx+1D8h]
0x18010cfa2  cmp     qword ptr [rax+18h], 0
0x18010cfa7  jz      loc_18010D267
0x18010cfad  mov     rcx, [rcx+60h]; hWnd
0x18010cfb1  call    cs:__imp_GetDC
0x18010cfb7  mov     rcx, [rdi+88h]
0x18010cfbe  lea     r8d, [rbx+4]; iPartId
0x18010cfc2  mov     [rsp+130h+pMargins], r15; pMargins
0x18010cfc7  xor     r9d, r9d; iStateId
0x18010cfca  mov     [rsp+130h+prc], 0; prc
0x18010cfd3  mov     rdx, rax; hdc
0x18010cfd6  mov     rsi, rax
0x18010cfd9  mov     [rsp+130h+iPropId], 0E12h; iPropId
0x18010cfe1  mov     rcx, [rcx+1D8h]
0x18010cfe8  mov     rcx, [rcx+18h]; hTheme
0x18010cfec  call    cs:__imp_GetThemeMargins
0x18010cff2  mov     rcx, [rdi+88h]
0x18010cff9  lea     rax, [rsp+130h+psz]
0x18010cffe  mov     qword ptr [rsp+130h+psz.cx], 0
0x18010d007  lea     r14d, [rbx-1]
0x18010d00b  mov     [rsp+130h+pMargins], rax; psz
0x18010d010  lea     r8d, [rbx+5]; iPartId
0x18010d014  mov     dword ptr [rsp+130h+prc], r14d; eSize
0x18010d019  mov     r9d, r14d; iStateId
0x18010d01c  mov     rcx, [rcx+1D8h]
0x18010d023  mov     rdx, rsi; hdc
0x18010d026  mov     qword ptr [rsp+130h+iPropId], 0; prc
0x18010d02f  mov     rcx, [rcx+18h]; hTheme
0x18010d033  call    cs:__imp_GetThemePartSize
0x18010d039  test    eax, eax
0x18010d03b  js      short loc_18010D044
0x18010d03d  mov     eax, [rsp+130h+psz.cy]
0x18010d041  mov     [rdi+7Ch], eax
0x18010d044  mov     rax, [rdi+88h]
0x18010d04b  mov     r9d, r14d; iStateId
0x18010d04e  mov     r8d, 9; iPartId
0x18010d054  mov     rdx, rsi; hdc
0x18010d057  mov     rcx, [rax+1D8h]
0x18010d05e  lea     rax, [rsp+130h+psz]
0x18010d063  mov     [rsp+130h+pMargins], rax; psz
0x18010d068  mov     dword ptr [rsp+130h+prc], ebx; eSize
0x18010d06c  mov     qword ptr [rsp+130h+iPropId], 0; prc
0x18010d075  mov     rcx, [rcx+18h]; hTheme
0x18010d079  call    cs:__imp_GetThemePartSize
0x18010d07f  test    eax, eax
0x18010d081  js      short loc_18010D091
0x18010d083  mov     eax, [rsp+130h+psz.cx]
0x18010d087  mov     [rdi+58h], eax
0x18010d08a  mov     eax, [rsp+130h+psz.cy]
0x18010d08e  mov     [rdi+5Ch], eax
0x18010d091  test    rsi, rsi
0x18010d094  jz      loc_18010D246
0x18010d09a  xor     edx, edx; Val
0x18010d09c  lea     rcx, [rbp+30h+pFont]; void *
0x18010d0a0  lea     r8d, [rdx+5Ch]; Size
0x18010d0a4  call    memset_0
0x18010d0a9  mov     rax, [rdi+88h]
0x18010d0b0  xorps   xmm0, xmm0
0x18010d0b3  movups  xmmword ptr [rsp+130h+tm.tmOverhang], xmm0
0x18010d0b8  xor     r9d, r9d; iStateId
0x18010d0bb  mov     rdx, rsi; hdc
0x18010d0be  movups  xmmword ptr [rsp+130h+tm.tmHeight], xmm0
0x18010d0c3  movups  xmmword ptr [rsp+130h+tm.tmExternalLeading], xmm0
0x18010d0c8  lea     r8d, [r9+6]; iPartId
0x18010d0cc  movups  xmmword ptr [rsp+130h+tm.tmFirstChar], xmm0
0x18010d0d1  mov     rcx, [rax+1D8h]
0x18010d0d8  lea     rax, [rbp+30h+pFont]
0x18010d0dc  mov     [rsp+130h+prc], rax; pFont
0x18010d0e1  mov     [rsp+130h+iPropId], 0D2h; iPropId
0x18010d0e9  mov     rcx, [rcx+18h]; hTheme
0x18010d0ed  call    cs:__imp_GetThemeFont
0x18010d0f3  test    eax, eax
0x18010d0f5  js      short loc_18010D142
0x18010d0f7  lea     rcx, [rbp+30h+pFont]; lplf
0x18010d0fb  call    cs:__imp_CreateFontIndirectW
0x18010d101  mov     r14, rax
0x18010d104  test    rax, rax
0x18010d107  jz      short loc_18010D142
0x18010d109  mov     rdx, rax; h
0x18010d10c  mov     rcx, rsi; hdc
0x18010d10f  call    cs:__imp_SelectObject
0x18010d115  lea     rdx, [rsp+130h+tm]; lptm
0x18010d11a  mov     rcx, rsi; hdc
0x18010d11d  mov     rbx, rax
0x18010d120  call    cs:__imp_GetTextMetricsW
0x18010d126  mov     ecx, [rsp+130h+tm.tmHeight]
0x18010d12a  mov     rdx, rbx; h
0x18010d12d  mov     [rdi+60h], ecx
0x18010d130  mov     rcx, rsi; hdc
0x18010d133  call    cs:__imp_SelectObject
0x18010d139  mov     rcx, r14; ho
0x18010d13c  call    cs:__imp_DeleteObject
0x18010d142  mov     rax, [rdi+88h]
0x18010d149  xor     r9d, r9d; iStateId
0x18010d14c  mov     rdx, rsi; hdc
0x18010d14f  mov     rcx, [rax+1D8h]
0x18010d156  lea     r8d, [r9+6]; iPartId
0x18010d15a  lea     rax, [rbp+30h+pFont]
0x18010d15e  mov     [rsp+130h+prc], rax; pFont
0x18010d163  mov     [rsp+130h+iPropId], 328h; iPropId
0x18010d16b  mov     rcx, [rcx+18h]; hTheme
0x18010d16f  call    cs:__imp_GetThemeFont
0x18010d175  test    eax, eax
0x18010d177  js      short loc_18010D1C4
0x18010d179  lea     rcx, [rbp+30h+pFont]; lplf
0x18010d17d  call    cs:__imp_CreateFontIndirectW
0x18010d183  mov     r14, rax
0x18010d186  test    rax, rax
0x18010d189  jz      short loc_18010D1C4
0x18010d18b  mov     rdx, rax; h
0x18010d18e  mov     rcx, rsi; hdc
0x18010d191  call    cs:__imp_SelectObject
0x18010d197  lea     rdx, [rsp+130h+tm]; lptm
0x18010d19c  mov     rcx, rsi; hdc
0x18010d19f  mov     rbx, rax
0x18010d1a2  call    cs:__imp_GetTextMetricsW
0x18010d1a8  mov     ecx, [rsp+130h+tm.tmHeight]
0x18010d1ac  mov     rdx, rbx; h
0x18010d1af  mov     [rdi+64h], ecx
0x18010d1b2  mov     rcx, rsi; hdc
0x18010d1b5  call    cs:__imp_SelectObject
0x18010d1bb  mov     rcx, r14; ho
0x18010d1be  call    cs:__imp_DeleteObject
0x18010d1c4  mov     rax, [rdi+88h]
0x18010d1cb  xor     r9d, r9d; iStateId
0x18010d1ce  mov     rdx, rsi; hdc
0x18010d1d1  mov     rcx, [rax+1D8h]
0x18010d1d8  lea     r8d, [r9+6]; iPartId
0x18010d1dc  lea     rax, [rbp+30h+pFont]
0x18010d1e0  mov     [rsp+130h+prc], rax; pFont
0x18010d1e5  mov     [rsp+130h+iPropId], 329h; iPropId
0x18010d1ed  mov     rcx, [rcx+18h]; hTheme
0x18010d1f1  call    cs:__imp_GetThemeFont
0x18010d1f7  test    eax, eax
0x18010d1f9  js      short loc_18010D246
0x18010d1fb  lea     rcx, [rbp+30h+pFont]; lplf
0x18010d1ff  call    cs:__imp_CreateFontIndirectW
0x18010d205  mov     r14, rax
0x18010d208  test    rax, rax
0x18010d20b  jz      short loc_18010D246
0x18010d20d  mov     rdx, rax; h
0x18010d210  mov     rcx, rsi; hdc
0x18010d213  call    cs:__imp_SelectObject
0x18010d219  lea     rdx, [rsp+130h+tm]; lptm
0x18010d21e  mov     rcx, rsi; hdc
0x18010d221  mov     rbx, rax
0x18010d224  call    cs:__imp_GetTextMetricsW
0x18010d22a  mov     ecx, [rsp+130h+tm.tmHeight]
0x18010d22e  mov     rdx, rbx; h
0x18010d231  mov     [rdi+68h], ecx
0x18010d234  mov     rcx, rsi; hdc
0x18010d237  call    cs:__imp_SelectObject
0x18010d23d  mov     rcx, r14; ho
0x18010d240  call    cs:__imp_DeleteObject
0x18010d246  mov     rcx, [rdi+88h]
0x18010d24d  mov     rdx, rsi; hDC
0x18010d250  mov     rcx, [rcx+60h]; hWnd
0x18010d254  call    cs:__imp_ReleaseDC
0x18010d25a  mov     eax, [rdi+78h]
0x18010d25d  xor     edx, edx
0x18010d25f  mov     ecx, [rdi+70h]
0x18010d262  mov     r8d, [r15]
0x18010d265  jmp     short loc_18010D273
0x18010d267  mov     eax, 0Ch
0x18010d26c  xor     ecx, ecx
0x18010d26e  mov     edx, eax
0x18010d270  mov     r8d, eax
0x18010d273  mov     [rdi+30h], r8d
0x18010d277  mov     [rdi+34h], edx
0x18010d27a  mov     [rdi+38h], ecx
0x18010d27d  mov     [rdi+3Ch], eax
0x18010d280  mov     rcx, [rbp+30h+var_40]
0x18010d284  xor     rcx, rsp; StackCookie
0x18010d287  call    __security_check_cookie
0x18010d28c  add     rsp, 108h
0x18010d293  pop     r15
0x18010d295  pop     r14
0x18010d297  pop     rdi
0x18010d298  pop     rsi
0x18010d299  pop     rbx
0x18010d29a  pop     rbp
0x18010d29b  retn
```
