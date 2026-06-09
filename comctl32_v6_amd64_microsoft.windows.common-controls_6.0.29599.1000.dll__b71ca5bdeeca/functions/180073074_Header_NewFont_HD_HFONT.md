# Header_NewFont(HD *,HFONT__ *)

- ea: `0x180073074`
- end: `0x1800732b6`
- name: `?Header_NewFont@@YAXPEAUHD@@PEAUHFONT__@@@Z`
- size: `578`
- prototype: `void(struct HD *, HFONT)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800089d0`
- `0x180054470`

## callees

- `0x18004f420`
- `0x180072398`
- `0x180073074`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x180073296`
- `GDI32!DeleteObject` at `0x180073296`
- `GDI32!GetTextMetricsW` at `0x180073179`
- `GDI32!GetTextMetricsW` at `0x180073179`
- `GDI32!SelectObject` at `0x180073169`
- `GDI32!SelectObject` at `0x180073282`
- `GDI32!SelectObject` at `0x1800732ab`
- `GDI32!SelectObject` at `0x180073169`
- `GDI32!SelectObject` at `0x180073282`
- `GDI32!SelectObject` at `0x1800732ab`
- `GDI32!GetTextExtentPointW` at `0x180073157`
- `GDI32!GetTextExtentPointW` at `0x180073157`
- `GDI32!CreateFontW` at `0x1800731ff`
- `GDI32!CreateFontW` at `0x1800731ff`
- `USER32!GetDC` at `0x1800730c1`
- `USER32!GetDC` at `0x1800730c1`
- `USER32!GetSystemMetrics` at `0x18007318d`
- `USER32!GetSystemMetrics` at `0x18007318d`
- `USER32!ReleaseDC` at `0x18007322d`
- `USER32!ReleaseDC` at `0x18007322d`
- `UxTheme!GetThemeTextExtent` at `0x180073125`
- `UxTheme!GetThemeTextExtent` at `0x180073125`

## pseudocode

```c
void __fastcall Header_NewFont(struct HD *a1, HFONT a2)
{
  HGDIOBJ v4; // rsi
  HDC DC; // rax
  HDC v6; // rdi
  void *v7; // rcx
  HRESULT ThemeTextExtent; // eax
  void *v9; // rdx
  __int16 SystemMetrics; // ax
  HFONT FontW; // rsi
  __int64 v12; // rcx
  void *v13; // rcx
  struct tagSIZE sz; // [rsp+70h] [rbp-29h] BYREF
  struct tagRECT pExtentRect; // [rsp+78h] [rbp-21h] BYREF
  RECT pBoundingRect; // [rsp+88h] [rbp-11h] BYREF
  struct tagTEXTMETRICW tm; // [rsp+98h] [rbp-1h] BYREF

  sz = 0;
  v4 = 0;
  memset(&tm, 0, sizeof(tm));
  DC = GetDC(0);
  v6 = DC;
  if ( a2 )
    SelectObject(DC, a2);
  v7 = (void *)*((_QWORD *)a1 + 38);
  if ( !v7
    || (pExtentRect = 0,
        pBoundingRect = 0,
        ThemeTextExtent = GetThemeTextExtent(v7, v6, 1, 0, L"M", -1, 0x800u, &pBoundingRect, &pExtentRect),
        sz.cx = pExtentRect.right - pExtentRect.left,
        sz.cy = pExtentRect.bottom - pExtentRect.top,
        ThemeTextExtent < 0) )
  {
    GetTextExtentPointW(v6, L"...", 3, &sz);
  }
  v9 = (void *)*((_QWORD *)a1 + 11);
  if ( v9 )
    v4 = SelectObject(v6, v9);
  GetTextMetricsW(v6, &tm);
  if ( v4 )
    SelectObject(v6, v4);
  SystemMetrics = GetSystemMetrics(6);
  FontW = CreateFontW(
            ((LOWORD(tm.tmHeight) + SystemMetrics + LOWORD(tm.tmExternalLeading)) & 0xFFFEu) - 1,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            1u,
            0,
            0,
            0,
            0,
            L"Marlett");
  *((_DWORD *)a1 + 17) = sz.cx;
  *((_DWORD *)a1 + 19) = sz.cy;
  *((_QWORD *)a1 + 11) = a2;
  if ( FontW )
  {
    v13 = (void *)*((_QWORD *)a1 + 12);
    if ( v13 )
      DeleteObject(v13);
    *((_QWORD *)a1 + 12) = FontW;
  }
  *((_DWORD *)a1 + 7) = GetCodePageForFont(a2);
  ReleaseDC(0, v6);
  v12 = *((_QWORD *)a1 + 36);
  if ( v12 )
    SendNotifyEx(v12, *(_QWORD *)a1, 4294967273LL, 0, *((_DWORD *)a1 + 6) & 1);
}

```

## disassembly

```asm
0x180073074  mov     [rsp-8+arg_10], rbx
0x180073079  mov     [rsp-8+arg_18], rsi
0x18007307e  push    rbp
0x18007307f  push    rdi
0x180073080  push    r14
0x180073082  lea     rbp, [rsp-47h]
0x180073087  sub     rsp, 0E0h
0x18007308e  mov     rax, cs:__security_cookie
0x180073095  xor     rax, rsp
0x180073098  mov     [rbp+57h+var_18], rax
0x18007309c  xorps   xmm0, xmm0
0x18007309f  mov     qword ptr [rbp+57h+sz.cx], 0
0x1800730a7  mov     rbx, rcx
0x1800730aa  mov     r14, rdx
0x1800730ad  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x1800730b1  xor     ecx, ecx; hWnd
0x1800730b3  xor     esi, esi
0x1800730b5  movups  xmmword ptr [rbp+57h+tm.tmFirstChar], xmm0
0x1800730b9  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x1800730bd  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x1800730c1  call    cs:__imp_GetDC
0x1800730c7  mov     rdi, rax
0x1800730ca  test    r14, r14
0x1800730cd  jnz     loc_18007327C
0x1800730d3  mov     rcx, [rbx+130h]; hTheme
0x1800730da  test    rcx, rcx
0x1800730dd  jz      short loc_180073143
0x1800730df  lea     rax, [rbp+57h+var_78]
0x1800730e3  xor     r9d, r9d; iStateId
0x1800730e6  mov     [rsp+0F0h+pExtentRect], rax; pExtentRect
0x1800730eb  xorps   xmm0, xmm0
0x1800730ee  lea     rax, [rbp+57h+var_68]
0x1800730f2  xorps   xmm1, xmm1
0x1800730f5  mov     [rsp+0F0h+pBoundingRect], rax; pBoundingRect
0x1800730fa  mov     rdx, rdi; hdc
0x1800730fd  mov     [rsp+0F0h+dwTextFlags], 800h; dwTextFlags
0x180073105  lea     rax, pszText; "M"
0x18007310c  mov     [rsp+0F0h+cchCharCount], 0FFFFFFFFh; cchCharCount
0x180073114  lea     r8d, [r9+1]; iPartId
0x180073118  mov     [rsp+0F0h+pszText], rax; pszText
0x18007311d  movups  xmmword ptr [rbp+57h+var_78.left], xmm0
0x180073121  movups  xmmword ptr [rbp+57h+var_68.left], xmm1
0x180073125  call    cs:__imp_GetThemeTextExtent
0x18007312b  mov     ecx, eax
0x18007312d  mov     eax, [rbp+57h+var_78.right]
0x180073130  sub     eax, [rbp+57h+var_78.left]
0x180073133  mov     [rbp+57h+sz.cx], eax
0x180073136  mov     eax, [rbp+57h+var_78.bottom]
0x180073139  sub     eax, [rbp+57h+var_78.top]
0x18007313c  mov     [rbp+57h+sz.cy], eax
0x18007313f  test    ecx, ecx
0x180073141  jns     short loc_18007315D
0x180073143  lea     r9, [rbp+57h+sz]; lpsz
0x180073147  mov     r8d, 3; c
0x18007314d  lea     rdx, c_szEllipses; "..."
0x180073154  mov     rcx, rdi; hdc
0x180073157  call    cs:__imp_GetTextExtentPointW
0x18007315d  mov     rdx, [rbx+58h]; h
0x180073161  test    rdx, rdx
0x180073164  jz      short loc_180073172
0x180073166  mov     rcx, rdi; hdc
0x180073169  call    cs:__imp_SelectObject
0x18007316f  mov     rsi, rax
0x180073172  lea     rdx, [rbp+57h+tm]; lptm
0x180073176  mov     rcx, rdi; hdc
0x180073179  call    cs:__imp_GetTextMetricsW
0x18007317f  test    rsi, rsi
0x180073182  jnz     loc_1800732A5
0x180073188  mov     ecx, 6; nIndex
0x18007318d  call    cs:__imp_GetSystemMetrics
0x180073193  mov     ecx, [rbp+57h+tm.tmExternalLeading]
0x180073196  xor     r9d, r9d; cOrientation
0x180073199  add     ecx, eax
0x18007319b  xor     r8d, r8d; cEscapement
0x18007319e  add     ecx, [rbp+57h+tm.tmHeight]
0x1800731a1  lea     rax, pszFaceName; "Marlett"
0x1800731a8  mov     [rsp+0F0h+pszFaceName], rax; pszFaceName
0x1800731ad  and     ecx, 0FFFEh
0x1800731b3  mov     [rsp+0F0h+iPitchAndFamily], 0; iPitchAndFamily
0x1800731bb  dec     ecx; cHeight
0x1800731bd  mov     [rsp+0F0h+iQuality], 0; iQuality
0x1800731c5  xor     edx, edx; cWidth
0x1800731c7  mov     [rsp+0F0h+iClipPrecision], 0; iClipPrecision
0x1800731cf  mov     [rsp+0F0h+iOutPrecision], 0; iOutPrecision
0x1800731d7  mov     dword ptr [rsp+0F0h+pExtentRect], 1; iCharSet
0x1800731df  mov     dword ptr [rsp+0F0h+pBoundingRect], 0; bStrikeOut
0x1800731e7  mov     [rsp+0F0h+dwTextFlags], 0; bUnderline
0x1800731ef  mov     [rsp+0F0h+cchCharCount], 0; bItalic
0x1800731f7  mov     dword ptr [rsp+0F0h+pszText], 0; cWeight
0x1800731ff  call    cs:__imp_CreateFontW
0x180073205  mov     ecx, [rbp+57h+sz.cx]
0x180073208  mov     rsi, rax
0x18007320b  mov     [rbx+44h], ecx
0x18007320e  mov     ecx, [rbp+57h+sz.cy]
0x180073211  mov     [rbx+4Ch], ecx
0x180073214  mov     [rbx+58h], r14
0x180073218  test    rax, rax
0x18007321b  jnz     short loc_18007328D
0x18007321d  mov     rcx, r14; h
0x180073220  call    GetCodePageForFont
0x180073225  mov     rdx, rdi; hDC
0x180073228  mov     [rbx+1Ch], eax
0x18007322b  xor     ecx, ecx; hWnd
0x18007322d  call    cs:__imp_ReleaseDC
0x180073233  mov     rcx, [rbx+120h]
0x18007323a  test    rcx, rcx
0x18007323d  jz      short loc_180073258
0x18007323f  mov     eax, [rbx+18h]
0x180073242  xor     r9d, r9d
0x180073245  mov     rdx, [rbx]
0x180073248  and     eax, 1
0x18007324b  mov     dword ptr [rsp+0F0h+pszText], eax
0x18007324f  lea     r8d, [r9-17h]
0x180073253  call    SendNotifyEx
0x180073258  mov     rcx, [rbp+57h+var_18]
0x18007325c  xor     rcx, rsp; StackCookie
0x18007325f  call    __security_check_cookie
0x180073264  lea     r11, [rsp+0F0h+var_10]
0x18007326c  mov     rbx, [r11+30h]
0x180073270  mov     rsi, [r11+38h]
0x180073274  mov     rsp, r11
0x180073277  pop     r14
0x180073279  pop     rdi
0x18007327a  pop     rbp
0x18007327b  retn
0x18007327c  mov     rdx, r14; h
0x18007327f  mov     rcx, rdi; hdc
0x180073282  call    cs:__imp_SelectObject
0x180073288  jmp     loc_1800730D3
0x18007328d  mov     rcx, [rbx+60h]; ho
0x180073291  test    rcx, rcx
0x180073294  jz      short loc_18007329C
0x180073296  call    cs:__imp_DeleteObject
0x18007329c  mov     [rbx+60h], rsi
0x1800732a0  jmp     loc_18007321D
0x1800732a5  mov     rdx, rsi; h
0x1800732a8  mov     rcx, rdi; hdc
0x1800732ab  call    cs:__imp_SelectObject
0x1800732b1  jmp     loc_180073188
```
