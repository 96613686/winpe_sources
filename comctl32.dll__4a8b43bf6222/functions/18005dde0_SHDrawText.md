# SHDrawText

- ea: `0x18005dde0`
- end: `0x18005e2bb`
- name: `SHDrawText`
- size: `1243`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, LPCWSTR lpString@<rdx>, RECT *lprc@<r8>, int, int, int, COLORREF color, COLORREF)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18005a9e4`
- `0x18005ec54`
- `0x1800743e0`
- `0x1800784c0`
- `0x18007a350`

## callees

- `0x1800115f0`
- `0x180017a0c`
- `0x18005dde0`
- `0x180077b7c`
- `0x18008e3b0`

## import_xrefs

- `GDI32!GetTextExtentPointW` at `0x18005e1cc`
- `GDI32!GetTextExtentPointW` at `0x18005e1cc`
- `GDI32!DeleteObject` at `0x18005e12a`
- `GDI32!DeleteObject` at `0x18005e12a`
- `GDI32!GetStockObject` at `0x18005e0e0`
- `GDI32!GetStockObject` at `0x18005e0e0`
- `GDI32!ExtTextOutW` at `0x18005e256`
- `GDI32!ExtTextOutW` at `0x18005e256`
- `GDI32!SetBkColor` at `0x18005e0fc`
- `GDI32!SetBkColor` at `0x18005e277`
- `GDI32!SetBkColor` at `0x18005e0fc`
- `GDI32!SetBkColor` at `0x18005e277`
- `GDI32!SetTextColor` at `0x18005dfa1`
- `GDI32!SetTextColor` at `0x18005e0ee`
- `GDI32!SetTextColor` at `0x18005e267`
- `GDI32!SetTextColor` at `0x18005dfa1`
- `GDI32!SetTextColor` at `0x18005e0ee`
- `GDI32!SetTextColor` at `0x18005e267`
- `GDI32!GetTextAlign` at `0x18005de70`
- `GDI32!GetTextAlign` at `0x18005de70`
- `GDI32!SetTextAlign` at `0x18005de83`
- `GDI32!SetTextAlign` at `0x18005e28b`
- `GDI32!SetTextAlign` at `0x18005de83`
- `GDI32!SetTextAlign` at `0x18005e28b`
- `GDI32!GetNearestColor` at `0x18005e0c1`
- `GDI32!GetNearestColor` at `0x18005e0c1`
- `GDI32!CreateSolidBrush` at `0x18005e0c9`
- `GDI32!CreateSolidBrush` at `0x18005e0c9`
- `KERNEL32!lstrlenW` at `0x18005df5a`
- `KERNEL32!lstrlenW` at `0x18005df5a`
- `USER32!GetSysColor` at `0x18005dfe6`
- `USER32!GetSysColor` at `0x18005dfe6`
- `USER32!GetSysColorBrush` at `0x18005e00b`
- `USER32!GetSysColorBrush` at `0x18005e00b`
- `USER32!DrawTextW` at `0x18005e1a1`
- `USER32!DrawTextW` at `0x18005e1a1`
- `USER32!FillRect` at `0x18005e117`
- `USER32!FillRect` at `0x18005e117`
- `USER32!IsRectEmpty` at `0x18005de46`
- `USER32!IsRectEmpty` at `0x18005de46`
- `USER32!OffsetRect` at `0x18005e154`
- `USER32!OffsetRect` at `0x18005e154`

## pseudocode

```c
void __fastcall SHDrawText(
        HDC hdc,
        WCHAR *lpString,
        RECT *lprc,
        int a4,
        __int16 a5,
        int a6,
        int a7,
        COLORREF color,
        COLORREF a9)
{
  DWORD SysColor; // r15d
  WCHAR *v11; // r13
  LONG v13; // ecx
  LONG v14; // edx
  int v15; // eax
  int v16; // ecx
  COLORREF v17; // edi
  COLORREF v18; // edx
  int v19; // r15d
  RECT *v20; // rbx
  COLORREF v21; // esi
  HBRUSH v22; // rbx
  COLORREF v23; // edi
  HBRUSH SysColorBrush; // rax
  DWORD v25; // eax
  COLORREF NearestColor; // eax
  HBRUSH SolidBrush; // rax
  HBRUSH v28; // r8
  int v29; // edx
  UINT format; // ecx
  LONG left; // ecx
  UINT v32; // r9d
  int v33; // kr00_4
  int v34; // r8d
  int cchText; // [rsp+44h] [rbp-BCh]
  RECT *lprca; // [rsp+50h] [rbp-B0h] BYREF
  UINT options; // [rsp+58h] [rbp-A8h]
  UINT align; // [rsp+5Ch] [rbp-A4h]
  int v40; // [rsp+60h] [rbp-A0h]
  HGDIOBJ ho; // [rsp+68h] [rbp-98h]
  struct tagRECT rc; // [rsp+70h] [rbp-90h] BYREF
  WCHAR chText[264]; // [rsp+80h] [rbp-80h] BYREF

  SysColor = a9;
  lprca = lprc;
  v11 = lpString;
  rc = 0;
  if ( lpString && !IsRectEmpty(lprc) )
  {
    align = 0;
    v40 = a5 & 0x800;
    if ( (a5 & 0x800) != 0 )
    {
      align = GetTextAlign(hdc);
      SetTextAlign(hdc, align | 0x100);
    }
    rc = *lprc;
    if ( (a5 & 0x40) != 0 )
    {
      v13 = 3 * g_cxLabelMargin + rc.left;
      v14 = rc.right - 3 * g_cxLabelMargin;
    }
    else
    {
      v13 = g_cxLabelMargin + rc.left;
      v14 = rc.right - g_cxLabelMargin;
    }
    rc.right = v14;
    rc.left = v13;
    if ( v13 < v14 || (a5 & 0x118) != 0 )
    {
      if ( (a5 & 2) != 0 && (unsigned int)ListView_NeedsEllipses(hdc, v11, a7) )
      {
        memmove(chText, v11, 0);
        StringCchCopyW(chText, 0x107u, L"...");
        v15 = 3;
        a4 = 0;
        v11 = chText;
      }
      else
      {
        v15 = lstrlenW(v11);
      }
      cchText = v15;
      if ( a9 == -1 && (a5 & 0x108) == 0 )
      {
        v16 = a5 & 0x80;
LABEL_18:
        v17 = 0;
        v18 = 0;
        options = 0;
        if ( !v16 )
          v18 = color;
        v19 = 1;
        v20 = lprca;
        v21 = SetTextColor(hdc, v18);
LABEL_52:
        if ( (a5 & 0x20) != 0 )
          OffsetRect(&rc, g_cxBorder, g_cyBorder);
        if ( (a5 & 1) != 0 )
        {
          v29 = ((a5 & 0x400) << 8) | 0xA911;
          if ( (a5 & 4) != 0 )
            v29 = ((a5 & 0x400) << 8) | 0xA811;
          format = v29 | 0x80000;
          if ( (a5 & 0x1000) == 0 )
            format = v29;
          DrawTextW(hdc, v11, cchText, &rc, format);
        }
        else
        {
          if ( a4 )
          {
            lprca = 0;
            GetTextExtentPointW(hdc, v11, cchText, (LPSIZE)&lprca);
            if ( a4 == 2 )
            {
              left = (rc.left + rc.right - (int)lprca) / 2;
              rc.left = left;
            }
            else
            {
              left = rc.right - (_DWORD)lprca;
              rc.left = rc.right - (_DWORD)lprca;
            }
          }
          else
          {
            left = rc.left;
          }
          v32 = options | 4;
          v33 = rc.bottom - rc.top - a6;
          v34 = v33 / 2 + rc.top;
          if ( (a5 & 4) == 0 )
            v32 = options;
          rc.top += v33 / 2;
          ExtTextOutW(hdc, left, v34, v32, v20, v11, cchText, 0);
        }
        if ( (a5 & 0x98) != 0 )
        {
          SetTextColor(hdc, v21);
          if ( !v19 )
            SetBkColor(hdc, v17);
        }
        if ( v40 )
          SetTextAlign(hdc, align);
        return;
      }
      v16 = a5 & 0x80;
      if ( (a5 & 0x80) != 0 )
        goto LABEL_18;
      v22 = 0;
      ho = 0;
      options = 2;
      if ( (a5 & 8) != 0 )
      {
        v23 = g_clrHighlightText;
        if ( (a5 & 0x200) != 0 )
          SysColor = GetSysColor(26);
        else
          SysColor = g_clrHighlight;
        if ( (a5 & 1) == 0 )
          goto LABEL_47;
        if ( (a5 & 0x200) != 0 )
        {
          SysColorBrush = GetSysColorBrush(26);
LABEL_46:
          v22 = SysColorBrush;
          goto LABEL_47;
        }
        goto LABEL_33;
      }
      if ( (a5 & 0x100) != 0 )
      {
        if ( a9 == -16777216 )
          SysColor = g_clrWindow;
        v25 = SysColor;
        SysColor = g_clrBtnFace;
        if ( v25 != g_clrBtnFace )
        {
          v23 = g_clrBtnText;
          if ( (a5 & 1) != 0 )
            v22 = g_hbrBtnFace;
          goto LABEL_47;
        }
        v23 = g_clrHighlightText;
        SysColor = g_clrHighlight;
        if ( (a5 & 1) != 0 )
LABEL_33:
          v22 = g_hbrHighlight;
      }
      else
      {
        v23 = color;
        if ( color == -16777216 )
        {
          v23 = g_clrWindowText;
          if ( a9 == -16777216 )
          {
            SysColor = g_clrWindow;
            if ( (a5 & 0x11) == 0x11 )
              v22 = g_hbrWindow;
            goto LABEL_47;
          }
        }
        else if ( a9 == -16777216 )
        {
          SysColor = g_clrWindow;
        }
        if ( (a5 & 0x11) == 0x11 )
        {
          NearestColor = GetNearestColor(hdc, SysColor);
          SolidBrush = CreateSolidBrush(NearestColor);
          v22 = SolidBrush;
          if ( !SolidBrush )
          {
            SysColorBrush = (HBRUSH)GetStockObject(0);
            goto LABEL_46;
          }
          ho = SolidBrush;
        }
      }
LABEL_47:
      v21 = SetTextColor(hdc, v23);
      v17 = SetBkColor(hdc, SysColor);
      if ( v22 )
      {
        v28 = v22;
        v20 = lprca;
        FillRect(hdc, lprca, v28);
        if ( ho )
          DeleteObject(ho);
      }
      else
      {
        v20 = lprca;
      }
      v19 = 0;
      goto LABEL_52;
    }
  }
}

```

## disassembly

```asm
0x18005dde0  mov     [rsp-8+arg_18], rbx
0x18005dde5  push    rbp
0x18005dde6  push    rsi
0x18005dde7  push    rdi
0x18005dde8  push    r12
0x18005ddea  push    r13
0x18005ddec  push    r14
0x18005ddee  push    r15
0x18005ddf0  lea     rbp, [rsp-1A0h]
0x18005ddf8  sub     rsp, 2A0h
0x18005ddff  mov     rax, cs:__security_cookie
0x18005de06  xor     rax, rsp
0x18005de09  mov     [rbp+1D0h+var_40], rax
0x18005de10  mov     r15d, [rbp+1D0h+arg_40]
0x18005de17  mov     rbx, r8
0x18005de1a  mov     [rsp+2D0h+lprc], rbx
0x18005de1f  xorps   xmm0, xmm0
0x18005de22  mov     [rsp+2D0h+var_288], r9d
0x18005de27  mov     r13, rdx
0x18005de2a  mov     [rsp+2D0h+var_290], 0
0x18005de32  mov     r12, rcx
0x18005de35  movups  xmmword ptr [rsp+2D0h+rc.left], xmm0
0x18005de3a  test    rdx, rdx
0x18005de3d  jz      loc_18005E291
0x18005de43  mov     rcx, rbx; lprc
0x18005de46  call    cs:__imp_IsRectEmpty
0x18005de4c  test    eax, eax
0x18005de4e  jnz     loc_18005E291
0x18005de54  mov     r14d, dword ptr [rbp+1D0h+arg_20]
0x18005de5b  mov     [rsp+2D0h+align], eax
0x18005de5f  mov     eax, r14d
0x18005de62  and     eax, 800h
0x18005de67  mov     [rsp+2D0h+var_270], eax
0x18005de6b  jz      short loc_18005DE89
0x18005de6d  mov     rcx, r12; hdc
0x18005de70  call    cs:__imp_GetTextAlign
0x18005de76  mov     edx, eax
0x18005de78  mov     [rsp+2D0h+align], eax
0x18005de7c  bts     edx, 8; align
0x18005de80  mov     rcx, r12; hdc
0x18005de83  call    cs:__imp_SetTextAlign
0x18005de89  movups  xmm0, xmmword ptr [rbx]
0x18005de8c  movdqu  xmmword ptr [rsp+2D0h+rc.left], xmm0
0x18005de92  mov     edx, [rsp+2D0h+rc.right]
0x18005de96  test    r14b, 40h
0x18005de9a  jz      short loc_18005DEAF
0x18005de9c  mov     ecx, cs:g_cxLabelMargin
0x18005dea2  lea     eax, [rcx+rcx*2]
0x18005dea5  mov     ecx, [rsp+2D0h+rc.left]
0x18005dea9  add     ecx, eax
0x18005deab  sub     edx, eax
0x18005dead  jmp     short loc_18005DEBF
0x18005deaf  mov     ecx, [rsp+2D0h+rc.left]
0x18005deb3  add     ecx, cs:g_cxLabelMargin
0x18005deb9  sub     edx, cs:g_cxLabelMargin
0x18005debf  mov     [rsp+2D0h+rc.right], edx
0x18005dec3  mov     [rsp+2D0h+rc.left], ecx
0x18005dec7  cmp     ecx, edx
0x18005dec9  jl      short loc_18005DED8
0x18005decb  test    r14d, 118h
0x18005ded2  jz      loc_18005E291
0x18005ded8  test    r14b, 2
0x18005dedc  jz      short loc_18005DF57
0x18005dede  mov     eax, [rbp+1D0h+arg_30]
0x18005dee4  lea     r9, [rsp+2D0h+var_290]
0x18005dee9  lea     r8, [rsp+2D0h+rc]
0x18005deee  mov     [rsp+2D0h+format], eax; int
0x18005def2  mov     rdx, r13; lpString
0x18005def5  mov     rcx, r12; hdc
0x18005def8  call    ListView_NeedsEllipses
0x18005defd  test    eax, eax
0x18005deff  jz      short loc_18005DF57
0x18005df01  movsxd  rsi, [rsp+2D0h+var_290]
0x18005df06  mov     ecx, 103h
0x18005df0b  cmp     rsi, 104h
0x18005df12  mov     rdx, r13; Src
0x18005df15  cmovnb  esi, ecx
0x18005df18  lea     rcx, [rbp+1D0h+chText]; void *
0x18005df1c  movsxd  rbx, esi
0x18005df1f  lea     rdi, [rbx+rbx]
0x18005df23  mov     r8, rdi; Size
0x18005df26  call    memmove
0x18005df2b  mov     edx, 107h
0x18005df30  lea     rcx, [rbp+1D0h+chText]
0x18005df34  sub     rdx, rbx; cchDest
0x18005df37  lea     r8, c_szEllipses; "..."
0x18005df3e  add     rcx, rdi; pszDest
0x18005df41  call    StringCchCopyW
0x18005df46  lea     eax, [rsi+3]
0x18005df49  mov     [rsp+2D0h+var_288], 0
0x18005df51  lea     r13, [rbp+1D0h+chText]
0x18005df55  jmp     short loc_18005DF60
0x18005df57  mov     rcx, r13; lpString
0x18005df5a  call    cs:__imp_lstrlenW
0x18005df60  mov     [rsp+2D0h+cchText], eax
0x18005df64  cmp     r15d, 0FFFFFFFFh
0x18005df68  jnz     short loc_18005DF7E
0x18005df6a  test    r14d, 108h
0x18005df71  jnz     short loc_18005DF7E
0x18005df73  mov     ecx, r14d
0x18005df76  and     ecx, 80h
0x18005df7c  jmp     short loc_18005DF89
0x18005df7e  mov     ecx, r14d
0x18005df81  and     ecx, 80h
0x18005df87  jz      short loc_18005DFB3
0x18005df89  xor     edi, edi
0x18005df8b  xor     edx, edx
0x18005df8d  test    ecx, ecx
0x18005df8f  mov     [rsp+2D0h+options], edi
0x18005df93  mov     rcx, r12; hdc
0x18005df96  cmovz   edx, [rbp+1D0h+color]; color
0x18005df9d  lea     r15d, [rdi+1]
0x18005dfa1  call    cs:__imp_SetTextColor
0x18005dfa7  mov     rbx, [rsp+2D0h+lprc]
0x18005dfac  mov     esi, eax
0x18005dfae  jmp     loc_18005E13C
0x18005dfb3  xor     eax, eax
0x18005dfb5  mov     [rsp+2D0h+var_290], 0
0x18005dfbd  xor     ebx, ebx
0x18005dfbf  mov     [rsp+2D0h+ho], rax
0x18005dfc4  mov     [rsp+2D0h+options], 2
0x18005dfcc  test    r14b, 8
0x18005dfd0  jz      short loc_18005E016
0x18005dfd2  mov     edi, cs:g_clrHighlightText
0x18005dfd8  mov     esi, r14d
0x18005dfdb  and     esi, 200h
0x18005dfe1  jz      short loc_18005DFF1
0x18005dfe3  lea     ecx, [rbx+1Ah]; nIndex
0x18005dfe6  call    cs:__imp_GetSysColor
0x18005dfec  mov     r15d, eax
0x18005dfef  jmp     short loc_18005DFF8
0x18005dff1  mov     r15d, cs:g_clrHighlight
0x18005dff8  test    r14b, 1
0x18005dffc  jz      loc_18005E0E9
0x18005e002  test    esi, esi
0x18005e004  jz      short loc_18005E057
0x18005e006  mov     ecx, 1Ah; nIndex
0x18005e00b  call    cs:__imp_GetSysColorBrush
0x18005e011  jmp     loc_18005E0E6
0x18005e016  mov     eax, 0FF000000h
0x18005e01b  bt      r14d, 8
0x18005e020  jnb     short loc_18005E076
0x18005e022  cmp     r15d, eax
0x18005e025  mov     ecx, r14d
0x18005e028  cmovz   r15d, cs:g_clrWindow
0x18005e030  and     ecx, 1
0x18005e033  mov     eax, r15d
0x18005e036  mov     r15d, cs:g_clrBtnFace
0x18005e03d  cmp     eax, r15d
0x18005e040  jnz     short loc_18005E063
0x18005e042  mov     edi, cs:g_clrHighlightText
0x18005e048  mov     r15d, cs:g_clrHighlight
0x18005e04f  test    ecx, ecx
0x18005e051  jz      loc_18005E0E9
0x18005e057  mov     rbx, cs:g_hbrHighlight
0x18005e05e  jmp     loc_18005E0E9
0x18005e063  mov     edi, cs:g_clrBtnText
0x18005e069  test    ecx, ecx
0x18005e06b  jz      short loc_18005E0E9
0x18005e06d  mov     rbx, cs:g_hbrBtnFace
0x18005e074  jmp     short loc_18005E0E9
0x18005e076  mov     edi, [rbp+1D0h+color]
0x18005e07c  cmp     edi, eax
0x18005e07e  jnz     short loc_18005E0A5
0x18005e080  mov     edi, cs:g_clrWindowText
0x18005e086  cmp     r15d, eax
0x18005e089  jnz     short loc_18005E0B1
0x18005e08b  mov     r15d, cs:g_clrWindow
0x18005e092  mov     eax, r14d
0x18005e095  and     eax, 11h
0x18005e098  cmp     al, 11h
0x18005e09a  jnz     short loc_18005E0E9
0x18005e09c  mov     rbx, cs:g_hbrWindow
0x18005e0a3  jmp     short loc_18005E0E9
0x18005e0a5  cmp     r15d, eax
0x18005e0a8  jnz     short loc_18005E0B1
0x18005e0aa  mov     r15d, cs:g_clrWindow
0x18005e0b1  mov     eax, r14d
0x18005e0b4  and     eax, 11h
0x18005e0b7  cmp     al, 11h
0x18005e0b9  jnz     short loc_18005E0E9
0x18005e0bb  mov     edx, r15d; color
0x18005e0be  mov     rcx, r12; hdc
0x18005e0c1  call    cs:__imp_GetNearestColor
0x18005e0c7  mov     ecx, eax; color
0x18005e0c9  call    cs:__imp_CreateSolidBrush
0x18005e0cf  mov     rbx, rax
0x18005e0d2  test    rax, rax
0x18005e0d5  jz      short loc_18005E0DE
0x18005e0d7  mov     [rsp+2D0h+ho], rax
0x18005e0dc  jmp     short loc_18005E0E9
0x18005e0de  xor     ecx, ecx; i
0x18005e0e0  call    cs:__imp_GetStockObject
0x18005e0e6  mov     rbx, rax
0x18005e0e9  mov     edx, edi; color
0x18005e0eb  mov     rcx, r12; hdc
0x18005e0ee  call    cs:__imp_SetTextColor
0x18005e0f4  mov     edx, r15d; color
0x18005e0f7  mov     rcx, r12; hdc
0x18005e0fa  mov     esi, eax
0x18005e0fc  call    cs:__imp_SetBkColor
0x18005e102  mov     edi, eax
0x18005e104  test    rbx, rbx
0x18005e107  jz      short loc_18005E132
0x18005e109  mov     r8, rbx; hbr
0x18005e10c  mov     rcx, r12; hDC
0x18005e10f  mov     rbx, [rsp+2D0h+lprc]
0x18005e114  mov     rdx, rbx; lprc
0x18005e117  call    cs:__imp_FillRect
0x18005e11d  mov     rax, [rsp+2D0h+ho]
0x18005e122  test    rax, rax
0x18005e125  jz      short loc_18005E137
0x18005e127  mov     rcx, rax; ho
0x18005e12a  call    cs:__imp_DeleteObject
0x18005e130  jmp     short loc_18005E137
0x18005e132  mov     rbx, [rsp+2D0h+lprc]
0x18005e137  mov     r15d, [rsp+2D0h+var_290]
0x18005e13c  test    r14b, 20h
0x18005e140  jz      short loc_18005E15A
0x18005e142  mov     r8d, cs:g_cyBorder; dy
0x18005e149  lea     rcx, [rsp+2D0h+rc]; lprc
0x18005e14e  mov     edx, cs:g_cxBorder; dx
0x18005e154  call    cs:__imp_OffsetRect
0x18005e15a  test    r14b, 1
0x18005e15e  jz      short loc_18005E1AC
0x18005e160  mov     r8d, [rsp+2D0h+cchText]; cchText
0x18005e165  lea     r9, [rsp+2D0h+rc]; lprc
0x18005e16a  mov     ecx, r14d
0x18005e16d  and     ecx, 400h
0x18005e173  shl     ecx, 8
0x18005e176  or      ecx, 0A811h
0x18005e17c  mov     edx, ecx
0x18005e17e  bts     edx, 8
0x18005e182  test    r14b, 4
0x18005e186  cmovnz  edx, ecx
0x18005e189  mov     ecx, edx
0x18005e18b  bts     ecx, 13h
0x18005e18f  bt      r14d, 0Ch
0x18005e194  cmovnb  ecx, edx
0x18005e197  mov     rdx, r13; lpchText
0x18005e19a  mov     [rsp+2D0h+format], ecx; format
0x18005e19e  mov     rcx, r12; hdc
0x18005e1a1  call    cs:__imp_DrawTextW
0x18005e1a7  jmp     loc_18005E25C
0x18005e1ac  cmp     [rsp+2D0h+var_288], 0
0x18005e1b1  jz      short loc_18005E200
0x18005e1b3  mov     r8d, [rsp+2D0h+cchText]; c
0x18005e1b8  lea     r9, [rsp+2D0h+lprc]; lpsz
0x18005e1bd  mov     rdx, r13; lpString
0x18005e1c0  mov     [rsp+2D0h+lprc], 0
0x18005e1c9  mov     rcx, r12; hdc
0x18005e1cc  call    cs:__imp_GetTextExtentPointW
0x18005e1d2  cmp     [rsp+2D0h+var_288], 2
0x18005e1d7  jnz     short loc_18005E1F2
0x18005e1d9  mov     eax, [rsp+2D0h+rc.right]
0x18005e1dd  sub     eax, dword ptr [rsp+2D0h+lprc]
0x18005e1e1  add     eax, [rsp+2D0h+rc.left]
0x18005e1e5  cdq
0x18005e1e6  sub     eax, edx
0x18005e1e8  sar     eax, 1
0x18005e1ea  mov     ecx, eax
0x18005e1ec  mov     [rsp+2D0h+rc.left], eax
0x18005e1f0  jmp     short loc_18005E204
0x18005e1f2  mov     ecx, [rsp+2D0h+rc.right]
0x18005e1f6  sub     ecx, dword ptr [rsp+2D0h+lprc]
0x18005e1fa  mov     [rsp+2D0h+rc.left], ecx
0x18005e1fe  jmp     short loc_18005E204
0x18005e200  mov     ecx, [rsp+2D0h+rc.left]
0x18005e204  mov     r8d, [rsp+2D0h+rc.top]
0x18005e209  mov     eax, [rsp+2D0h+rc.bottom]
0x18005e20d  mov     r9d, [rsp+2D0h+options]
0x18005e212  sub     eax, r8d
0x18005e215  sub     eax, [rbp+1D0h+arg_28]
0x18005e21b  or      r9d, 4
0x18005e21f  cdq
0x18005e220  mov     [rsp+2D0h+lpDx], 0; lpDx
0x18005e229  sub     eax, edx
0x18005e22b  mov     edx, ecx; x
0x18005e22d  sar     eax, 1
0x18005e22f  mov     rcx, r12; hdc
0x18005e232  add     r8d, eax; y
0x18005e235  mov     eax, [rsp+2D0h+cchText]
0x18005e239  mov     [rsp+2D0h+c], eax; c
0x18005e23d  test    r14b, 4
0x18005e241  mov     [rsp+2D0h+lpString], r13; lpString
0x18005e246  cmovz   r9d, [rsp+2D0h+options]; options
0x18005e24c  mov     [rsp+2D0h+rc.top], r8d
0x18005e251  mov     qword ptr [rsp+2D0h+format], rbx; lprect
0x18005e256  call    cs:__imp_ExtTextOutW
0x18005e25c  test    r14b, 98h
0x18005e260  jz      short loc_18005E27D
0x18005e262  mov     edx, esi; color
0x18005e264  mov     rcx, r12; hdc
0x18005e267  call    cs:__imp_SetTextColor
0x18005e26d  test    r15d, r15d
0x18005e270  jnz     short loc_18005E27D
0x18005e272  mov     edx, edi; color
0x18005e274  mov     rcx, r12; hdc
0x18005e277  call    cs:__imp_SetBkColor
0x18005e27d  cmp     [rsp+2D0h+var_270], 0
  ... truncated ...
```
