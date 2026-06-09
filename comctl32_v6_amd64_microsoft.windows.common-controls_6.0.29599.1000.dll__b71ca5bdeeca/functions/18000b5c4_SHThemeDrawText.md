# SHThemeDrawText

- ea: `0x18000b5c4`
- end: `0x18000bad1`
- name: `SHThemeDrawText`
- size: `1293`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009d9c`
- `0x18000b238`
- `0x1800abadc`

## callees

- `0x18000b5c4`
- `0x180092d60`
- `0x1800ad3b0`
- `0x1800ad7d4`
- `0x1800b0280`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000b745`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000b745`
- `GDI32!SetTextAlign` at `0x18000b64e`
- `GDI32!SetTextAlign` at `0x18000baab`
- `GDI32!SetTextAlign` at `0x18000b64e`
- `GDI32!SetTextAlign` at `0x18000baab`
- `GDI32!SetBkColor` at `0x18000b718`
- `GDI32!SetBkColor` at `0x18000ba98`
- `GDI32!SetBkColor` at `0x18000b718`
- `GDI32!SetBkColor` at `0x18000ba98`
- `GDI32!SetTextColor` at `0x18000b705`
- `GDI32!SetTextColor` at `0x18000ba8b`
- `GDI32!SetTextColor` at `0x18000b705`
- `GDI32!SetTextColor` at `0x18000ba8b`
- `GDI32!GetTextAlign` at `0x18000b63b`
- `GDI32!GetTextAlign` at `0x18000b63b`
- `GDI32!GetTextExtentPointW` at `0x18000ba0b`
- `GDI32!GetTextExtentPointW` at `0x18000ba0b`
- `GDI32!GetTextColor` at `0x18000b900`
- `GDI32!GetTextColor` at `0x18000b987`
- `GDI32!GetTextColor` at `0x18000b900`
- `GDI32!GetTextColor` at `0x18000b987`
- `USER32!DrawTextW` at `0x18000b870`
- `USER32!DrawTextW` at `0x18000b9e1`
- `USER32!DrawTextW` at `0x18000b870`
- `USER32!DrawTextW` at `0x18000b9e1`
- `USER32!OffsetRect` at `0x18000b793`
- `USER32!OffsetRect` at `0x18000b793`
- `USER32!CopyRect` at `0x18000b850`
- `USER32!CopyRect` at `0x18000b850`
- `USER32!IsRectEmpty` at `0x18000b61a`
- `USER32!IsRectEmpty` at `0x18000b61a`
- `USER32!GetSystemMetrics` at `0x18000b66b`
- `USER32!GetSystemMetrics` at `0x18000b680`
- `USER32!GetSystemMetrics` at `0x18000b6a4`
- `USER32!GetSystemMetrics` at `0x18000b6b0`
- `USER32!GetSystemMetrics` at `0x18000b776`
- `USER32!GetSystemMetrics` at `0x18000b783`
- `USER32!GetSystemMetrics` at `0x18000b66b`
- `USER32!GetSystemMetrics` at `0x18000b680`
- `USER32!GetSystemMetrics` at `0x18000b6a4`
- `USER32!GetSystemMetrics` at `0x18000b6b0`
- `USER32!GetSystemMetrics` at `0x18000b776`
- `USER32!GetSystemMetrics` at `0x18000b783`
- `UxTheme!DrawThemeTextEx` at `0x18000b9c1`
- `UxTheme!DrawThemeTextEx` at `0x18000b9c1`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x18000b93c`
- `UxTheme!__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z` at `0x18000b93c`

## pseudocode

```c
void __fastcall SHThemeDrawText(
        void *a1,
        HDC a2,
        int a3,
        int a4,
        DTTOPTS *a5,
        const WCHAR *lpString,
        RECT *lprc,
        int a8,
        unsigned int a9,
        int a10,
        __int64 a11,
        COLORREF color,
        COLORREF a13)
{
  const DTTOPTS *pOptions; // r13
  HTHEME v15; // rbx
  unsigned int v16; // esi
  int SystemMetrics; // eax
  int right; // edx
  int v19; // r12d
  int v20; // ebx
  int v21; // eax
  int v22; // r8d
  int v23; // ecx
  int v24; // edx
  int v25; // ecx
  int v26; // edx
  int v27; // ecx
  int v28; // edx
  UINT dwTextFlags; // ebx
  COLORREF TextColor; // eax
  HTHEME v31; // r14
  int *v32; // rax
  LONG left; // ecx
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  UINT align; // [rsp+64h] [rbp-9Ch]
  int iStateId; // [rsp+68h] [rbp-98h]
  int iPartId; // [rsp+6Ch] [rbp-94h]
  COLORREF v38; // [rsp+70h] [rbp-90h]
  COLORREF v39; // [rsp+74h] [rbp-8Ch]
  struct tagRECT rc; // [rsp+78h] [rbp-88h] BYREF
  HTHEME hTheme; // [rsp+88h] [rbp-78h] BYREF
  struct tagRECT rcDst; // [rsp+90h] [rbp-70h] BYREF
  int v43; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v44[76]; // [rsp+A4h] [rbp-5Ch] BYREF

  pOptions = a5;
  v15 = a1;
  iStateId = a4;
  iPartId = a3;
  hTheme = a1;
  if ( !lpString || IsRectEmpty(lprc) )
    return;
  v16 = a9;
  align = 0;
  if ( (a9 & 0x800) != 0 )
  {
    align = GetTextAlign(a2);
    SetTextAlign(a2, align | 0x100);
  }
  rc = *lprc;
  if ( (a9 & 0x40) != 0 )
  {
    SystemMetrics = GetSystemMetrics(45);
    rc.left += SystemMetrics + 2 * SystemMetrics;
    right = -3 * GetSystemMetrics(45) + rc.right;
  }
  else
  {
    if ( (a9 & 0x20000) != 0 )
    {
      right = rc.right;
      goto LABEL_11;
    }
    rc.left += GetSystemMetrics(45);
    right = rc.right - GetSystemMetrics(45);
  }
  v15 = hTheme;
  rc.right = right;
LABEL_11:
  if ( rc.left < right || (a9 & 0x118) != 0 )
  {
    v34 = 0;
    SHThemeComputeTextColors((_DWORD)v15, a9, (unsigned int)&color, (unsigned int)&a13, (__int64)&v34);
    v38 = SetTextColor(a2, color);
    v39 = SetBkColor(a2, a13);
    if ( v34 )
    {
      v16 = a9 & 0xFFFBFFFF;
      SHThemeFillTextRect(a2, lprc, a13);
    }
    v19 = lstrlenW(lpString);
    if ( (v16 & 0x403) != 0 || (v34 = 0, v15) )
      v34 = 1;
    if ( (v16 & 0x20) != 0 )
    {
      v20 = GetSystemMetrics(6);
      v21 = GetSystemMetrics(5);
      OffsetRect(&rc, v21, v20);
    }
    if ( v34 )
    {
      v22 = v16 & 0x80000;
      if ( (v16 & 0x80001) == 1 )
      {
        v23 = 43025;
      }
      else
      {
        v23 = v22 != 0 ? 43024 : 34852;
        if ( (a8 & 2) != 0 )
        {
          v23 |= 1u;
        }
        else if ( (a8 & 1) != 0 )
        {
          v23 |= 2u;
        }
      }
      v24 = v23 | 0x40000;
      if ( (v16 & 0x400) == 0 )
        v24 = v23;
      v25 = v24 | 0x100;
      if ( (v16 & 4) != 0 )
        v25 = v24;
      v26 = v25 | 0x80000;
      if ( (v16 & 0x1000) == 0 )
        v26 = v25;
      v27 = v26 | 0x24;
      if ( (v16 & 0x2000) == 0 )
        v27 = v26;
      v28 = v27 | 0x20;
      if ( (v16 & 0x100000) == 0 )
        v28 = v27;
      dwTextFlags = v28 & 0xFFFFFFFE;
      if ( (v16 & 0x4000) == 0 )
        dwTextFlags = v28;
      if ( v22 )
      {
        rcDst = 0;
        CopyRect(&rcDst, &rc);
        dwTextFlags |= 4u;
        DrawTextW(a2, lpString, v19, &rcDst, dwTextFlags | 0x400);
        if ( rcDst.bottom > rc.bottom )
          dwTextFlags |= 0x20u;
        else
          rc.top += (rc.bottom - rcDst.bottom) / 2;
      }
      if ( a8 )
      {
        if ( a8 == 1 )
        {
          dwTextFlags |= 2u;
        }
        else if ( a8 == 2 )
        {
          dwTextFlags |= 1u;
        }
      }
      if ( (v16 & 0x40000) != 0 )
      {
        DrawShadowTextEx(a2, dwTextFlags, 0xFFFFFFu, 0, 2, 2, 255, 0);
      }
      else if ( (v16 & 0x800000) != 0 )
      {
        TextColor = GetTextColor(a2);
        DrawTextWithGlow(a2, lpString, v19, &rc, dwTextFlags, TextColor, 0, 0, 0, 1, 0, 0);
      }
      else
      {
        v31 = hTheme;
        if ( !hTheme )
          goto LABEL_59;
        v43 = 72;
        memset_0(v44, 0, 0x44u);
        if ( !a5 || (a5->dwFlags & 1) == 0 )
        {
          v32 = &v43;
          if ( a5 )
            v32 = (int *)a5;
          pOptions = (const DTTOPTS *)v32;
          v32[1] |= 1u;
          v32[2] = GetTextColor(a2);
        }
        if ( DrawThemeTextEx(v31, a2, iPartId, iStateId, lpString, -1, dwTextFlags, &rc, pOptions) < 0 )
LABEL_59:
          DrawTextW(a2, lpString, v19, &rc, dwTextFlags);
      }
    }
    else
    {
      if ( a8 )
      {
        hTheme = 0;
        GetTextExtentPointW(a2, lpString, v19, (LPSIZE)&hTheme);
        if ( a8 == 2 )
        {
          left = (rc.left + rc.right - (int)hTheme) / 2;
          rc.left = left;
        }
        else
        {
          left = rc.right - (_DWORD)hTheme;
          rc.left = rc.right - (_DWORD)hTheme;
        }
      }
      else
      {
        left = rc.left;
      }
      rc.top += (rc.bottom - rc.top - a10) / 2;
      SHExtTextOutW(a2, left, rc.top, v16 & 4);
    }
    SetTextColor(a2, v38);
    SetBkColor(a2, v39);
    if ( (v16 & 0x800) != 0 )
      SetTextAlign(a2, align);
  }
}

```

## disassembly

```asm
0x18000b5c4  push    rbp
0x18000b5c6  push    rbx
0x18000b5c7  push    rsi
0x18000b5c8  push    rdi
0x18000b5c9  push    r12
0x18000b5cb  push    r13
0x18000b5cd  push    r14
0x18000b5cf  push    r15
0x18000b5d1  lea     rbp, [rsp-8]
0x18000b5d6  sub     rsp, 108h
0x18000b5dd  mov     rax, cs:__security_cookie
0x18000b5e4  xor     rax, rsp
0x18000b5e7  mov     [rbp+40h+var_50], rax
0x18000b5eb  mov     r15, [rbp+40h+lpString]
0x18000b5ef  mov     rdi, rdx
0x18000b5f2  mov     r13, [rbp+40h+arg_20]
0x18000b5f6  mov     rbx, rcx
0x18000b5f9  mov     r14, [rbp+40h+lprc]
0x18000b600  mov     [rsp+140h+iStateId], r9d
0x18000b605  mov     [rsp+140h+iPartId], r8d
0x18000b60a  mov     [rbp+40h+hTheme], rcx
0x18000b60e  test    r15, r15
0x18000b611  jz      loc_18000BAB1
0x18000b617  mov     rcx, r14; lprc
0x18000b61a  call    cs:__imp_IsRectEmpty
0x18000b620  test    eax, eax
0x18000b622  jnz     loc_18000BAB1
0x18000b628  mov     esi, [rbp+40h+arg_40]
0x18000b62e  mov     [rsp+140h+align], eax
0x18000b632  bt      esi, 0Bh
0x18000b636  jnb     short loc_18000B654
0x18000b638  mov     rcx, rdi; hdc
0x18000b63b  call    cs:__imp_GetTextAlign
0x18000b641  mov     edx, eax
0x18000b643  mov     [rsp+140h+align], eax
0x18000b647  bts     edx, 8; align
0x18000b64b  mov     rcx, rdi; hdc
0x18000b64e  call    cs:__imp_SetTextAlign
0x18000b654  movups  xmm0, xmmword ptr [r14]
0x18000b658  movdqu  xmmword ptr [rsp+140h+rc.left], xmm0
0x18000b65e  test    sil, 40h
0x18000b662  jz      short loc_18000B697
0x18000b664  mov     ebx, 2Dh ; '-'
0x18000b669  mov     ecx, ebx; nIndex
0x18000b66b  call    cs:__imp_GetSystemMetrics
0x18000b671  mov     ecx, eax
0x18000b673  add     ecx, [rsp+140h+rc.left]
0x18000b677  lea     eax, [rcx+rax*2]
0x18000b67a  mov     ecx, ebx; nIndex
0x18000b67c  mov     [rsp+140h+rc.left], eax
0x18000b680  call    cs:__imp_GetSystemMetrics
0x18000b686  mov     edx, [rbp+40h+rc.right]
0x18000b689  imul    ecx, eax, -3
0x18000b68c  add     edx, ecx
0x18000b68e  mov     rbx, [rbp+40h+hTheme]
0x18000b692  mov     [rbp+40h+rc.right], edx
0x18000b695  jmp     short loc_18000B6C0
0x18000b697  bt      esi, 11h
0x18000b69b  jb      short loc_18000B6BD
0x18000b69d  mov     ebx, 2Dh ; '-'
0x18000b6a2  mov     ecx, ebx; nIndex
0x18000b6a4  call    cs:__imp_GetSystemMetrics
0x18000b6aa  add     [rsp+140h+rc.left], eax
0x18000b6ae  mov     ecx, ebx; nIndex
0x18000b6b0  call    cs:__imp_GetSystemMetrics
0x18000b6b6  mov     edx, [rbp+40h+rc.right]
0x18000b6b9  sub     edx, eax
0x18000b6bb  jmp     short loc_18000B68E
0x18000b6bd  mov     edx, [rbp+40h+rc.right]
0x18000b6c0  cmp     [rsp+140h+rc.left], edx
0x18000b6c4  jl      short loc_18000B6D2
0x18000b6c6  test    esi, 118h
0x18000b6cc  jz      loc_18000BAB1
0x18000b6d2  lea     rax, [rsp+140h+var_E0]
0x18000b6d7  mov     [rsp+140h+var_E0], 0
0x18000b6df  lea     r9, [rbp+40h+arg_60]
0x18000b6e6  mov     qword ptr [rsp+140h+format], rax
0x18000b6eb  lea     r8, [rbp+40h+color]
0x18000b6f2  mov     edx, esi
0x18000b6f4  mov     rcx, rbx
0x18000b6f7  call    SHThemeComputeTextColors
0x18000b6fc  mov     edx, [rbp+40h+color]; color
0x18000b702  mov     rcx, rdi; hdc
0x18000b705  call    cs:__imp_SetTextColor
0x18000b70b  mov     edx, [rbp+40h+arg_60]; color
0x18000b711  mov     rcx, rdi; hdc
0x18000b714  mov     [rsp+140h+var_D0], eax
0x18000b718  call    cs:__imp_SetBkColor
0x18000b71e  mov     r9d, [rsp+140h+var_E0]
0x18000b723  mov     [rsp+140h+var_CC], eax
0x18000b727  test    r9d, r9d
0x18000b72a  jz      short loc_18000B742
0x18000b72c  mov     r8d, [rbp+40h+arg_60]; color
0x18000b733  btr     esi, 12h
0x18000b737  mov     rdx, r14; lprc
0x18000b73a  mov     rcx, rdi; hDC
0x18000b73d  call    SHThemeFillTextRect
0x18000b742  mov     rcx, r15; lpString
0x18000b745  call    cs:__imp_lstrlenW
0x18000b74b  mov     r12d, eax
0x18000b74e  test    esi, 403h
0x18000b754  jnz     short loc_18000B763
0x18000b756  mov     [rsp+140h+var_E0], 0
0x18000b75e  test    rbx, rbx
0x18000b761  jz      short loc_18000B76B
0x18000b763  mov     [rsp+140h+var_E0], 1
0x18000b76b  test    sil, 20h
0x18000b76f  jz      short loc_18000B799
0x18000b771  mov     ecx, 6; nIndex
0x18000b776  call    cs:__imp_GetSystemMetrics
0x18000b77c  mov     ecx, 5; nIndex
0x18000b781  mov     ebx, eax
0x18000b783  call    cs:__imp_GetSystemMetrics
0x18000b789  mov     r8d, ebx; dy
0x18000b78c  lea     rcx, [rsp+140h+rc]; lprc
0x18000b791  mov     edx, eax; dx
0x18000b793  call    cs:__imp_OffsetRect
0x18000b799  cmp     [rsp+140h+var_E0], 0
0x18000b79e  jz      loc_18000B9EC
0x18000b7a4  mov     r14d, [rbp+40h+arg_38]
0x18000b7ab  mov     eax, esi
0x18000b7ad  mov     r8d, esi
0x18000b7b0  mov     r9d, 80000h
0x18000b7b6  and     eax, 80001h
0x18000b7bb  and     r8d, r9d
0x18000b7be  cmp     eax, 1
0x18000b7c1  jnz     short loc_18000B7CA
0x18000b7c3  mov     ecx, 0A811h
0x18000b7c8  jmp     short loc_18000B7F1
0x18000b7ca  mov     eax, r8d
0x18000b7cd  neg     eax
0x18000b7cf  sbb     ecx, ecx
0x18000b7d1  and     ecx, 1FECh
0x18000b7d7  add     ecx, 8824h
0x18000b7dd  test    r14b, 2
0x18000b7e1  jz      short loc_18000B7E8
0x18000b7e3  or      ecx, 1
0x18000b7e6  jmp     short loc_18000B7F1
0x18000b7e8  test    r14b, 1
0x18000b7ec  jz      short loc_18000B7F1
0x18000b7ee  or      ecx, 2
0x18000b7f1  mov     edx, ecx
0x18000b7f3  bts     edx, 12h
0x18000b7f7  bt      esi, 0Ah
0x18000b7fb  cmovnb  edx, ecx
0x18000b7fe  mov     ecx, edx
0x18000b800  bts     ecx, 8
0x18000b804  test    sil, 4
0x18000b808  cmovnz  ecx, edx
0x18000b80b  mov     edx, ecx
0x18000b80d  or      edx, r9d
0x18000b810  bt      esi, 0Ch
0x18000b814  cmovnb  edx, ecx
0x18000b817  mov     ecx, edx
0x18000b819  or      ecx, 24h
0x18000b81c  bt      esi, 0Dh
0x18000b820  cmovnb  ecx, edx
0x18000b823  mov     edx, ecx
0x18000b825  or      edx, 20h
0x18000b828  bt      esi, 14h
0x18000b82c  cmovnb  edx, ecx
0x18000b82f  mov     ebx, edx
0x18000b831  and     ebx, 0FFFFFFFEh
0x18000b834  bt      esi, 0Eh
0x18000b838  cmovnb  ebx, edx
0x18000b83b  test    r8d, r8d
0x18000b83e  jz      short loc_18000B88F
0x18000b840  xorps   xmm0, xmm0
0x18000b843  lea     rdx, [rsp+140h+rc]; lprcSrc
0x18000b848  lea     rcx, [rbp+40h+rcDst]; lprcDst
0x18000b84c  movups  xmmword ptr [rbp+40h+rcDst.left], xmm0
0x18000b850  call    cs:__imp_CopyRect
0x18000b856  or      ebx, 4
0x18000b859  lea     r9, [rbp+40h+rcDst]; lprc
0x18000b85d  mov     eax, ebx
0x18000b85f  mov     r8d, r12d; cchText
0x18000b862  bts     eax, 0Ah
0x18000b866  mov     rdx, r15; lpchText
0x18000b869  mov     rcx, rdi; hdc
0x18000b86c  mov     [rsp+140h+format], eax; format
0x18000b870  call    cs:__imp_DrawTextW
0x18000b876  mov     eax, [rbp+40h+rc.bottom]
0x18000b879  cmp     [rbp+40h+rcDst.bottom], eax
0x18000b87c  jg      short loc_18000B88C
0x18000b87e  sub     eax, [rbp+40h+rcDst.bottom]
0x18000b881  cdq
0x18000b882  sub     eax, edx
0x18000b884  sar     eax, 1
0x18000b886  add     [rsp+140h+rc.top], eax
0x18000b88a  jmp     short loc_18000B88F
0x18000b88c  or      ebx, 20h
0x18000b88f  test    r14d, r14d
0x18000b892  jz      short loc_18000B8A8
0x18000b894  sub     r14d, 1
0x18000b898  jz      short loc_18000B8A5
0x18000b89a  cmp     r14d, 1
0x18000b89e  jnz     short loc_18000B8A8
0x18000b8a0  or      ebx, r14d
0x18000b8a3  jmp     short loc_18000B8A8
0x18000b8a5  or      ebx, 2
0x18000b8a8  bt      esi, 12h
0x18000b8ac  jnb     short loc_18000B8F7
0x18000b8ae  mov     [rsp+140h+var_F0], 0; int
0x18000b8b6  lea     r9, [rsp+140h+rc]
0x18000b8bb  mov     [rsp+140h+var_F8], 0FFh; char
0x18000b8c0  mov     r8d, r12d
0x18000b8c3  mov     dword ptr [rsp+140h+pOptions], 2; int
0x18000b8cb  mov     rdx, r15
0x18000b8ce  mov     dword ptr [rsp+140h+pRect], 2; int
0x18000b8d6  mov     rcx, rdi; hdc
0x18000b8d9  mov     [rsp+140h+dwTextFlags], 0; COLORREF
0x18000b8e1  mov     [rsp+140h+cchText], 0FFFFFFh; color
0x18000b8e9  mov     [rsp+140h+format], ebx; UINT
0x18000b8ed  call    DrawShadowTextEx
0x18000b8f2  jmp     loc_18000BA84
0x18000b8f7  bt      esi, 17h
0x18000b8fb  jnb     short loc_18000B947
0x18000b8fd  mov     rcx, rdi; hdc
0x18000b900  call    cs:__imp_GetTextColor
0x18000b906  xor     ecx, ecx
0x18000b908  lea     r9, [rsp+140h+rc]
0x18000b90d  mov     [rsp+140h+var_E8], rcx
0x18000b912  mov     r8d, r12d
0x18000b915  mov     qword ptr [rsp+140h+var_F0], rcx
0x18000b91a  mov     rdx, r15
0x18000b91d  mov     dword ptr [rsp+140h+var_F8], 1
0x18000b925  mov     dword ptr [rsp+140h+pOptions], ecx
0x18000b929  mov     dword ptr [rsp+140h+pRect], ecx
0x18000b92d  mov     [rsp+140h+dwTextFlags], ecx
0x18000b931  mov     rcx, rdi
0x18000b934  mov     [rsp+140h+cchText], eax
0x18000b938  mov     [rsp+140h+format], ebx
0x18000b93c  call    cs:__imp_?DrawTextWithGlow@@YAJPEAUHDC__@@PEBGIPEAUtagRECT@@KKKIIHP6AH0PEAGH2I_J@Z4@Z; DrawTextWithGlow(HDC__ *,ushort const *,uint,tagRECT *,ulong,ulong,ulong,uint,uint,int,int (*)(HDC__ *,ushort *,int,tagRECT *,uint,__int64),__int64)
0x18000b942  jmp     loc_18000BA84
0x18000b947  mov     r14, [rbp+40h+hTheme]
0x18000b94b  test    r14, r14
0x18000b94e  jz      short loc_18000B9CF
0x18000b950  xor     edx, edx; Val
0x18000b952  mov     [rbp+40h+var_A0], 48h ; 'H'
0x18000b959  lea     rcx, [rbp+40h+var_9C]; void *
0x18000b95d  lea     r8d, [rdx+44h]; Size
0x18000b961  call    memset_0
0x18000b966  test    r13, r13
0x18000b969  jz      short loc_18000B972
0x18000b96b  test    byte ptr [r13+4], 1
0x18000b970  jnz     short loc_18000B991
0x18000b972  test    r13, r13
0x18000b975  lea     rax, [rbp+40h+var_A0]
0x18000b979  mov     rcx, rdi; hdc
0x18000b97c  cmovnz  rax, r13
0x18000b980  mov     r13, rax
0x18000b983  or      dword ptr [rax+4], 1
0x18000b987  call    cs:__imp_GetTextColor
0x18000b98d  mov     [r13+8], eax
0x18000b991  mov     r9d, [rsp+140h+iStateId]; iStateId
0x18000b996  lea     rax, [rsp+140h+rc]
0x18000b99b  mov     r8d, [rsp+140h+iPartId]; iPartId
0x18000b9a0  mov     rdx, rdi; hdc
0x18000b9a3  mov     [rsp+140h+pOptions], r13; pOptions
0x18000b9a8  mov     rcx, r14; hTheme
0x18000b9ab  mov     [rsp+140h+pRect], rax; pRect
0x18000b9b0  mov     [rsp+140h+dwTextFlags], ebx; dwTextFlags
0x18000b9b4  mov     [rsp+140h+cchText], 0FFFFFFFFh; cchText
0x18000b9bc  mov     qword ptr [rsp+140h+format], r15; pszText
0x18000b9c1  call    cs:__imp_DrawThemeTextEx
0x18000b9c7  test    eax, eax
0x18000b9c9  jns     loc_18000BA84
0x18000b9cf  lea     r9, [rsp+140h+rc]; lprc
0x18000b9d4  mov     [rsp+140h+format], ebx; format
0x18000b9d8  mov     r8d, r12d; cchText
0x18000b9db  mov     rdx, r15; lpchText
0x18000b9de  mov     rcx, rdi; hdc
0x18000b9e1  call    cs:__imp_DrawTextW
0x18000b9e7  jmp     loc_18000BA84
0x18000b9ec  mov     ebx, [rbp+40h+arg_38]
0x18000b9f2  test    ebx, ebx
0x18000b9f4  jz      short loc_18000BA39
0x18000b9f6  lea     r9, [rbp+40h+hTheme]; lpsz
0x18000b9fa  mov     [rbp+40h+hTheme], 0
0x18000ba02  mov     r8d, r12d; c
0x18000ba05  mov     rdx, r15; lpString
0x18000ba08  mov     rcx, rdi; hdc
0x18000ba0b  call    cs:__imp_GetTextExtentPointW
0x18000ba11  cmp     ebx, 2
0x18000ba14  jnz     short loc_18000BA2D
0x18000ba16  mov     eax, [rbp+40h+rc.right]
0x18000ba19  sub     eax, dword ptr [rbp+40h+hTheme]
0x18000ba1c  add     eax, [rsp+140h+rc.left]
0x18000ba20  cdq
0x18000ba21  sub     eax, edx
0x18000ba23  sar     eax, 1
0x18000ba25  mov     ecx, eax
0x18000ba27  mov     [rsp+140h+rc.left], eax
0x18000ba2b  jmp     short loc_18000BA3D
0x18000ba2d  mov     ecx, [rbp+40h+rc.right]
0x18000ba30  sub     ecx, dword ptr [rbp+40h+hTheme]
0x18000ba33  mov     [rsp+140h+rc.left], ecx
0x18000ba37  jmp     short loc_18000BA3D
0x18000ba39  mov     ecx, [rsp+140h+rc.left]
0x18000ba3d  mov     r8d, [rsp+140h+rc.top]
  ... truncated ...
```
