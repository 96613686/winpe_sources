# AddFont(tagENUMLOGFONTW *,tagNEWTEXTMETRICW *,int,HDC__ *,tagFACENODE *)

- ea: `0x18000f4b0`
- end: `0x18000f908`
- name: `?AddFont@@YAHPEAUtagENUMLOGFONTW@@PEAUtagNEWTEXTMETRICW@@HPEAUHDC__@@PEAUtagFACENODE@@@Z`
- size: `1112`
- prototype: `__int64 __usercall@<rax>(LOGFONTW *lplf@<rcx>, struct tagNEWTEXTMETRICW *@<rdx>, int@<r8d>, HDC@<r9>, struct tagFACENODE *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ff40`
- `0x180010110`

## callees

- `0x1800015b0`
- `0x18000f4b0`
- `0x180010350`
- `0x180010380`
- `0x180018d18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6ed`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000f709`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000f709`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000f673`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000f673`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000f545`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000f545`
- `ext-ms-win-gdi-font-l1-1-0!GetTextMetricsW` at `0x18000f558`
- `ext-ms-win-gdi-font-l1-1-0!GetTextMetricsW` at `0x18000f558`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18000f523`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18000f7d0`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18000f893`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18000f523`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18000f7d0`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18000f893`
- `ext-ms-win-gdi-font-l1-1-2!GetTextExtentPoint32W` at `0x18000f578`
- `ext-ms-win-gdi-font-l1-1-2!GetTextExtentPoint32W` at `0x18000f578`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000f786`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000f8b5`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000f786`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000f8b5`

## pseudocode

```c
__int64 __fastcall AddFont(LOGFONTW *lplf, struct tagNEWTEXTMETRICW *a2, int a3, HDC a4, struct tagFACENODE *a5)
{
  signed __int16 lfWidth; // r12
  __int16 lfHeight; // di
  HDC v7; // rsi
  HFONT FontIndirectW; // rax
  BYTE tmPitchAndFamily; // r8
  __int16 v11; // dx
  unsigned int v12; // r14d
  unsigned int v13; // r13d
  _QWORD *v14; // rsi
  __int64 v15; // rcx
  __int16 v16; // r13
  __int16 v17; // ax
  __int16 v18; // di
  bool v19; // zf
  bool v20; // cc
  LONG v21; // eax
  __int64 v22; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v24; // rax
  int v25; // r8d
  LONG DPIXScaledPixelSize; // eax
  struct _CONSOLE_STATE_INFO *v27; // rcx
  HFONT v28; // rdx
  __int64 v29; // rcx
  LONG tmWeight; // edx
  BYTE v32; // [rsp+20h] [rbp-71h]
  int v33; // [rsp+24h] [rbp-6Dh]
  unsigned int v34; // [rsp+28h] [rbp-69h]
  __int16 v35; // [rsp+2Ch] [rbp-65h]
  int v37; // [rsp+34h] [rbp-5Dh]
  int v38; // [rsp+38h] [rbp-59h]
  HFONT ho; // [rsp+40h] [rbp-51h]
  char v40; // [rsp+48h] [rbp-49h]
  tagSIZE psizl; // [rsp+50h] [rbp-41h] BYREF
  struct tagNEWTEXTMETRICW *v42; // [rsp+58h] [rbp-39h]
  HDC v43; // [rsp+60h] [rbp-31h]
  struct tagTEXTMETRICW tm; // [rsp+68h] [rbp-29h] BYREF

  lfWidth = lplf->lfWidth;
  lfHeight = lplf->lfHeight;
  v7 = a4;
  LOWORD(v33) = lfWidth;
  HIWORD(v33) = lplf->lfHeight;
  v43 = a4;
  v42 = a2;
  memset(&tm, 0, sizeof(tm));
  psizl = 0;
  v38 = 0;
  lplf->lfQuality = 0;
  FontIndirectW = CreateFontIndirectW(lplf);
  ho = FontIndirectW;
  if ( !FontIndirectW )
    return 1;
  while ( 1 )
  {
    SelectObject(v7, FontIndirectW);
    GetTextMetricsW(v7, &tm);
    GetTextExtentPoint32W(v7, L"0", 1, &psizl);
    tmPitchAndFamily = tm.tmPitchAndFamily;
    v11 = LOWORD(tm.tmExternalLeading) + LOWORD(tm.tmHeight);
    v40 = tm.tmPitchAndFamily & 4;
    LOWORD(v37) = psizl.cx;
    v35 = LOWORD(tm.tmExternalLeading) + LOWORD(tm.tmHeight);
    HIWORD(v37) = LOWORD(tm.tmExternalLeading) + LOWORD(tm.tmHeight);
    v32 = tm.tmPitchAndFamily;
    if ( (tm.tmPitchAndFamily & 4) == 0 || lfHeight < 0 || (v11 = lfHeight, v35 = lfHeight, !lfWidth) )
      lfWidth = psizl.cx;
    v12 = NumberOfFonts;
    v13 = 0;
    v14 = FontInfo;
    v34 = 0;
    if ( NumberOfFonts )
    {
      while ( 1 )
      {
        v15 = 5LL * v13;
        if ( !v14[5 * v13] )
          goto LABEL_32;
        v16 = WORD2(v14[5 * v13 + 1]);
        if ( v16 <= 0 )
          v16 = v14[v15 + 1];
        v17 = HIWORD(v14[v15 + 1]);
        if ( v17 <= 0 )
        {
          v18 = WORD1(v14[v15 + 1]);
          if ( v17 < 0 )
          {
            if ( v33 < 0 && SHIWORD(v33) > v17 )
            {
LABEL_34:
              v13 = v34;
              goto LABEL_35;
            }
            tmPitchAndFamily = v32;
          }
        }
        else
        {
          v18 = HIWORD(v14[v15 + 1]);
        }
        if ( v16 != lfWidth )
          goto LABEL_25;
        v19 = v11 == v18;
        v20 = v11 < v18;
        if ( v11 == v18 )
          break;
LABEL_26:
        if ( v20 )
          goto LABEL_34;
        if ( v19 )
        {
          v20 = lfWidth < v16;
          v13 = v34;
          if ( v20 )
            goto LABEL_35;
        }
        else
        {
          v13 = v34;
        }
        tmPitchAndFamily = v32;
LABEL_32:
        v34 = ++v13;
        if ( v13 >= v12 )
          goto LABEL_35;
      }
      if ( LOBYTE(v14[v15 + 4]) == tmPitchAndFamily )
      {
        v21 = v38 ? tm.tmWeight : v42->tmWeight;
        if ( LODWORD(v14[v15 + 2]) == v21 )
        {
          if ( !lstrcmpW((LPCWSTR)v14[v15 + 3], lplf->lfFaceName) )
          {
            DeleteObject(ho);
            return 2;
          }
          v12 = NumberOfFonts;
          v14 = FontInfo;
          v11 = v35;
        }
      }
LABEL_25:
      v19 = v11 == v18;
      v20 = v11 < v18;
      goto LABEL_26;
    }
LABEL_35:
    if ( v12 == FontInfoLength )
      break;
LABEL_39:
    if ( v13 < v12 )
      memmove_0(&v14[5 * v13 + 5], &v14[5 * v13], 40LL * (v12 - v13));
    v25 = a3;
    if ( a3 == 4 && *((_DWORD *)gpStateInfo + 53) )
    {
      DeleteObject(ho);
      lfWidth = v33;
      DPIXScaledPixelSize = GetDPIXScaledPixelSize(*((HWND *)gpStateInfo + 22), (__int16)v33);
      v27 = gpStateInfo;
      lfHeight = HIWORD(v33);
      lplf->lfWidth = DPIXScaledPixelSize;
      lplf->lfHeight = GetDPIYScaledPixelSize(*((HWND *)v27 + 22), SHIWORD(v33));
      v28 = CreateFontIndirectW(lplf);
      if ( !v28 )
        return 1;
      v12 = NumberOfFonts;
      v14 = FontInfo;
      v25 = 4;
    }
    else
    {
      lfWidth = v33;
      lfHeight = HIWORD(v33);
      v28 = ho;
    }
    v29 = 5LL * v13;
    LOBYTE(v14[v29 + 4]) = v32;
    LODWORD(v14[v29 + 1]) = v37;
    v14[v29] = v28;
    if ( v40 )
      HIDWORD(v14[5 * v13 + 1]) = v33;
    else
      HIDWORD(v14[5 * v13 + 1]) = 0;
    LODWORD(v14[5 * v13 + 2]) = tm.tmWeight;
    tmWeight = tm.tmWeight;
    NumberOfFonts = v12 + 1;
    v14[5 * v13 + 3] = (char *)a5 + 12;
    BYTE1(v14[5 * v13 + 4]) = tm.tmCharSet;
    if ( v25 != 4 || tmWeight >= 600 )
      return 2;
    lplf->lfWidth = lfWidth;
    lplf->lfHeight = lfHeight;
    lplf->lfWeight = 700;
    lplf->lfQuality = 0;
    v38 = 1;
    FontIndirectW = CreateFontIndirectW(lplf);
    ho = FontIndirectW;
    if ( !FontIndirectW )
      return 1;
    v7 = v43;
  }
  v22 = FontInfoLength + 3;
  FontInfoLength = v22;
  if ( (unsigned int)v22 >= 0x6666666 )
    goto LABEL_56;
  ProcessHeap = GetProcessHeap();
  v24 = HeapReAlloc(ProcessHeap, 0, v14, 40 * v22);
  v14 = v24;
  if ( v24 )
  {
    v12 = NumberOfFonts;
    FontInfo = v24;
    goto LABEL_39;
  }
  LODWORD(v22) = FontInfoLength;
LABEL_56:
  FontInfoLength = v22 - 3;
  return 0;
}

```

## disassembly

```asm
0x18000f4b0  mov     [rsp-8+arg_8], rbx
0x18000f4b5  push    rbp
0x18000f4b6  push    rsi
0x18000f4b7  push    rdi
0x18000f4b8  push    r12
0x18000f4ba  push    r13
0x18000f4bc  push    r14
0x18000f4be  push    r15
0x18000f4c0  lea     rbp, [rsp-1Fh]
0x18000f4c5  sub     rsp, 0B0h
0x18000f4cc  mov     rax, cs:__security_cookie
0x18000f4d3  xor     rax, rsp
0x18000f4d6  mov     [rbp+4Fh+var_38], rax
0x18000f4da  movzx   r12d, word ptr [rcx+4]
0x18000f4df  xorps   xmm0, xmm0
0x18000f4e2  movzx   edi, word ptr [rcx]
0x18000f4e5  xor     r14d, r14d
0x18000f4e8  movups  xmmword ptr [rbp+4Fh+tm.tmOverhang], xmm0
0x18000f4ec  mov     [rbp+4Fh+var_BC], r14d
0x18000f4f0  mov     rsi, r9
0x18000f4f3  movups  xmmword ptr [rbp+4Fh+tm.tmFirstChar], xmm0
0x18000f4f7  mov     word ptr [rbp+4Fh+var_BC], r12w
0x18000f4fc  mov     r15, rcx
0x18000f4ff  mov     word ptr [rbp+4Fh+var_BC+2], di
0x18000f503  mov     [rbp+4Fh+var_80], r9
0x18000f507  mov     [rbp+4Fh+var_B0], r8d
0x18000f50b  mov     [rbp+4Fh+var_88], rdx
0x18000f50f  movups  xmmword ptr [rbp+4Fh+tm.tmHeight], xmm0
0x18000f513  mov     qword ptr [rbp+4Fh+psizl.cx], r14
0x18000f517  movups  xmmword ptr [rbp+4Fh+tm.tmExternalLeading], xmm0
0x18000f51b  mov     [rbp+4Fh+var_A8], r14d
0x18000f51f  mov     [rcx+1Ah], r14b
0x18000f523  call    cs:__imp_CreateFontIndirectW
0x18000f52a  nop     dword ptr [rax+rax+00h]
0x18000f52f  mov     [rbp+4Fh+ho], rax
0x18000f533  test    rax, rax
0x18000f536  jz      loc_18000F8DB
0x18000f53c  mov     ebx, [rbp+4Fh+var_BC]
0x18000f53f  mov     rdx, rax; h
0x18000f542  mov     rcx, rsi; hdc
0x18000f545  call    cs:__imp_SelectObject
0x18000f54c  nop     dword ptr [rax+rax+00h]
0x18000f551  lea     rdx, [rbp+4Fh+tm]; lptm
0x18000f555  mov     rcx, rsi; hdc
0x18000f558  call    cs:__imp_GetTextMetricsW
0x18000f55f  nop     dword ptr [rax+rax+00h]
0x18000f564  lea     r9, [rbp+4Fh+psizl]; psizl
0x18000f568  mov     r8d, 1; c
0x18000f56e  lea     rdx, String; "0"
0x18000f575  mov     rcx, rsi; hdc
0x18000f578  call    cs:__imp_GetTextExtentPoint32W
0x18000f57f  nop     dword ptr [rax+rax+00h]
0x18000f584  mov     r8b, [rbp+4Fh+tm.tmPitchAndFamily]
0x18000f588  movzx   edx, word ptr [rbp+4Fh+tm.tmHeight]
0x18000f58c  mov     cl, r8b
0x18000f58f  add     dx, word ptr [rbp+4Fh+tm.tmExternalLeading]
0x18000f593  mov     rax, qword ptr [rbp+4Fh+psizl.cx]
0x18000f597  and     cl, 4
0x18000f59a  mov     [rbp+4Fh+var_98], cl
0x18000f59d  mov     word ptr [rbp+4Fh+var_AC], ax
0x18000f5a1  mov     [rbp+4Fh+var_B4], dx
0x18000f5a5  mov     word ptr [rbp+4Fh+var_AC+2], dx
0x18000f5a9  mov     [rbp+4Fh+var_C0], r8b
0x18000f5ad  jz      short loc_18000F5C6
0x18000f5af  xor     r9d, r9d
0x18000f5b2  test    di, di
0x18000f5b5  js      short loc_18000F5C9
0x18000f5b7  movzx   edx, di
0x18000f5ba  mov     [rbp+4Fh+var_B4], dx
0x18000f5be  test    r12w, r12w
0x18000f5c2  jnz     short loc_18000F5CD
0x18000f5c4  jmp     short loc_18000F5C9
0x18000f5c6  xor     r9d, r9d
0x18000f5c9  movzx   r12d, ax
0x18000f5cd  mov     r14d, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18000f5d4  mov     r13d, r9d
0x18000f5d7  mov     rsi, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000f5de  mov     [rbp+4Fh+var_B8], r9d
0x18000f5e2  test    r14d, r14d
0x18000f5e5  jz      loc_18000F6CD
0x18000f5eb  mov     eax, r13d
0x18000f5ee  lea     rcx, [rax+rax*4]
0x18000f5f2  cmp     [rsi+rcx*8], r9
0x18000f5f6  jz      loc_18000F6B7
0x18000f5fc  movzx   r13d, word ptr [rsi+rcx*8+0Ch]
0x18000f602  test    r13w, r13w
0x18000f606  jg      short loc_18000F60E
0x18000f608  movzx   r13d, word ptr [rsi+rcx*8+8]
0x18000f60e  movzx   eax, word ptr [rsi+rcx*8+0Eh]
0x18000f613  test    ax, ax
0x18000f616  jle     short loc_18000F61D
0x18000f618  movzx   edi, ax
0x18000f61b  jmp     short loc_18000F640
0x18000f61d  movzx   edi, word ptr [rsi+rcx*8+0Ah]
0x18000f622  test    ax, ax
0x18000f625  jns     short loc_18000F640
0x18000f627  movzx   r8d, word ptr [rbp+4Fh+var_BC+2]
0x18000f62c  test    r8w, r8w
0x18000f630  jns     short loc_18000F63C
0x18000f632  cmp     r8w, ax
0x18000f636  jg      loc_18000F6C9
0x18000f63c  mov     r8b, [rbp+4Fh+var_C0]
0x18000f640  cmp     r13w, r12w
0x18000f644  jnz     short loc_18000F69C
0x18000f646  cmp     dx, di
0x18000f649  jnz     short loc_18000F69F
0x18000f64b  cmp     [rsi+rcx*8+20h], r8b
0x18000f650  jnz     short loc_18000F69C
0x18000f652  cmp     [rbp+4Fh+var_A8], r9d
0x18000f656  jz      short loc_18000F65D
0x18000f658  mov     eax, [rbp+4Fh+tm.tmWeight]
0x18000f65b  jmp     short loc_18000F664
0x18000f65d  mov     rax, [rbp+4Fh+var_88]
0x18000f661  mov     eax, [rax+1Ch]
0x18000f664  cmp     [rsi+rcx*8+10h], eax
0x18000f668  jnz     short loc_18000F69C
0x18000f66a  mov     rcx, [rsi+rcx*8+18h]; lpString1
0x18000f66f  lea     rdx, [r15+1Ch]; lpString2
0x18000f673  call    cs:__imp_lstrcmpW
0x18000f67a  nop     dword ptr [rax+rax+00h]
0x18000f67f  xor     r9d, r9d
0x18000f682  test    eax, eax
0x18000f684  jz      loc_18000F8B1
0x18000f68a  mov     r14d, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18000f691  mov     rsi, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000f698  movzx   edx, [rbp+4Fh+var_B4]
0x18000f69c  cmp     dx, di
0x18000f69f  jl      short loc_18000F6C9
0x18000f6a1  jnz     short loc_18000F6AF
0x18000f6a3  cmp     r12w, r13w
0x18000f6a7  mov     r13d, [rbp+4Fh+var_B8]
0x18000f6ab  jl      short loc_18000F6CD
0x18000f6ad  jmp     short loc_18000F6B3
0x18000f6af  mov     r13d, [rbp+4Fh+var_B8]
0x18000f6b3  mov     r8b, [rbp+4Fh+var_C0]
0x18000f6b7  inc     r13d
0x18000f6ba  mov     [rbp+4Fh+var_B8], r13d
0x18000f6be  cmp     r13d, r14d
0x18000f6c1  jb      loc_18000F5EB
0x18000f6c7  jmp     short loc_18000F6CD
0x18000f6c9  mov     r13d, [rbp+4Fh+var_B8]
0x18000f6cd  mov     edi, cs:?FontInfoLength@@3KA; ulong FontInfoLength
0x18000f6d3  cmp     r14d, edi
0x18000f6d6  jnz     short loc_18000F732
0x18000f6d8  add     edi, 3
0x18000f6db  mov     cs:?FontInfoLength@@3KA, edi; ulong FontInfoLength
0x18000f6e1  cmp     edi, 6666666h
0x18000f6e7  jnb     loc_18000F8CE
0x18000f6ed  call    cs:__imp_GetProcessHeap
0x18000f6f4  nop     dword ptr [rax+rax+00h]
0x18000f6f9  lea     r9, [rdi+rdi*4]
0x18000f6fd  mov     r8, rsi; lpMem
0x18000f700  shl     r9, 3; dwBytes
0x18000f704  xor     edx, edx; dwFlags
0x18000f706  mov     rcx, rax; hHeap
0x18000f709  call    cs:__imp_HeapReAlloc
0x18000f710  nop     dword ptr [rax+rax+00h]
0x18000f715  xor     r9d, r9d
0x18000f718  mov     rsi, rax
0x18000f71b  test    rax, rax
0x18000f71e  jz      loc_18000F8C8
0x18000f724  mov     r14d, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18000f72b  mov     cs:?FontInfo@@3PEAU_FONT_INFO@@EA, rax; _FONT_INFO * FontInfo
0x18000f732  cmp     r13d, r14d
0x18000f735  jnb     short loc_18000F764
0x18000f737  mov     ecx, r14d
0x18000f73a  mov     eax, r13d
0x18000f73d  sub     ecx, r13d
0x18000f740  lea     r8, [rcx+rcx*4]
0x18000f744  lea     rcx, [rax+rax*4]
0x18000f748  shl     r8, 3; Size
0x18000f74c  lea     rdx, [rsi+rcx*8]; Src
0x18000f750  lea     eax, [r13+1]
0x18000f754  lea     rax, [rax+rax*4]
0x18000f758  lea     rcx, [rsi+rax*8]; void *
0x18000f75c  call    memmove_0
0x18000f761  xor     r9d, r9d
0x18000f764  mov     r8d, [rbp+4Fh+var_B0]
0x18000f768  cmp     r8d, 4
0x18000f76c  jnz     loc_18000F7FF
0x18000f772  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000f779  cmp     [rax+0D4h], r9d
0x18000f780  jz      short loc_18000F7FF
0x18000f782  mov     rcx, [rbp+4Fh+ho]; ho
0x18000f786  call    cs:__imp_DeleteObject
0x18000f78d  nop     dword ptr [rax+rax+00h]
0x18000f792  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000f799  movsx   r12d, word ptr [rbp+4Fh+var_BC]
0x18000f79e  mov     edx, r12d; int
0x18000f7a1  mov     rcx, [rcx+0B0h]; HWND
0x18000f7a8  call    ?GetDPIXScaledPixelSize@@YAHQEAUHWND__@@H@Z; GetDPIXScaledPixelSize(HWND__ * const,int)
0x18000f7ad  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000f7b4  movsx   edi, word ptr [rbp+4Fh+var_BC+2]
0x18000f7b8  mov     [r15+4], eax
0x18000f7bc  mov     edx, edi; int
0x18000f7be  mov     rcx, [rcx+0B0h]; HWND
0x18000f7c5  call    ?GetDPIYScaledPixelSize@@YAHQEAUHWND__@@H@Z; GetDPIYScaledPixelSize(HWND__ * const,int)
0x18000f7ca  mov     rcx, r15; lplf
0x18000f7cd  mov     [r15], eax
0x18000f7d0  call    cs:__imp_CreateFontIndirectW
0x18000f7d7  nop     dword ptr [rax+rax+00h]
0x18000f7dc  xor     r9d, r9d
0x18000f7df  mov     rdx, rax
0x18000f7e2  test    rax, rax
0x18000f7e5  jz      loc_18000F8DB
0x18000f7eb  mov     r14d, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18000f7f2  mov     rsi, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000f7f9  mov     r8d, [rbp+4Fh+var_B0]
0x18000f7fd  jmp     short loc_18000F80C
0x18000f7ff  movzx   r12d, word ptr [rbp+4Fh+var_BC]
0x18000f804  movzx   edi, word ptr [rbp+4Fh+var_BC+2]
0x18000f808  mov     rdx, [rbp+4Fh+ho]
0x18000f80c  mov     eax, r13d
0x18000f80f  lea     rcx, [rax+rax*4]
0x18000f813  mov     al, [rbp+4Fh+var_C0]
0x18000f816  mov     [rsi+rcx*8+20h], al
0x18000f81a  mov     eax, [rbp+4Fh+var_AC]
0x18000f81d  mov     [rsi+rcx*8+8], eax
0x18000f821  mov     [rsi+rcx*8], rdx
0x18000f825  cmp     [rbp+4Fh+var_98], r9b
0x18000f829  jz      short loc_18000F831
0x18000f82b  mov     [rsi+rcx*8+0Ch], ebx
0x18000f82f  jmp     short loc_18000F839
0x18000f831  mov     dword ptr [rsi+rcx*8+0Ch], 0
0x18000f839  mov     eax, [rbp+4Fh+tm.tmWeight]
0x18000f83c  inc     r14d
0x18000f83f  mov     [rsi+rcx*8+10h], eax
0x18000f843  mov     edx, [rbp+4Fh+tm.tmWeight]
0x18000f846  mov     rax, [rbp+4Fh+arg_20]
0x18000f84a  add     rax, 0Ch
0x18000f84e  mov     cs:?NumberOfFonts@@3KA, r14d; ulong NumberOfFonts
0x18000f855  mov     [rsi+rcx*8+18h], rax
0x18000f85a  mov     al, [rbp+4Fh+tm.tmCharSet]
0x18000f85d  mov     [rsi+rcx*8+21h], al
0x18000f861  cmp     r8d, 4
0x18000f865  jnz     short loc_18000F8C1
0x18000f867  cmp     edx, 258h
0x18000f86d  jge     short loc_18000F8C1
0x18000f86f  movsx   eax, r12w
0x18000f873  mov     rcx, r15; lplf
0x18000f876  mov     [r15+4], eax
0x18000f87a  movsx   eax, di
0x18000f87d  mov     [r15], eax
0x18000f880  mov     dword ptr [r15+10h], 2BCh
0x18000f888  mov     [r15+1Ah], r9b
0x18000f88c  mov     [rbp+4Fh+var_A8], 1
0x18000f893  call    cs:__imp_CreateFontIndirectW
0x18000f89a  nop     dword ptr [rax+rax+00h]
0x18000f89f  mov     [rbp+4Fh+ho], rax
0x18000f8a3  test    rax, rax
0x18000f8a6  jz      short loc_18000F8DB
0x18000f8a8  mov     rsi, [rbp+4Fh+var_80]
0x18000f8ac  jmp     loc_18000F53F
0x18000f8b1  mov     rcx, [rbp+4Fh+ho]; ho
0x18000f8b5  call    cs:__imp_DeleteObject
0x18000f8bc  nop     dword ptr [rax+rax+00h]
0x18000f8c1  mov     eax, 2
0x18000f8c6  jmp     short loc_18000F8E0
0x18000f8c8  mov     edi, cs:?FontInfoLength@@3KA; ulong FontInfoLength
0x18000f8ce  add     edi, 0FFFFFFFDh
0x18000f8d1  mov     cs:?FontInfoLength@@3KA, edi; ulong FontInfoLength
0x18000f8d7  xor     eax, eax
0x18000f8d9  jmp     short loc_18000F8E0
0x18000f8db  mov     eax, 1
0x18000f8e0  mov     rcx, [rbp+4Fh+var_38]
0x18000f8e4  xor     rcx, rsp; StackCookie
0x18000f8e7  call    __security_check_cookie
0x18000f8ec  mov     rbx, [rsp+0E0h+arg_8]
0x18000f8f4  add     rsp, 0B0h
0x18000f8fb  pop     r15
0x18000f8fd  pop     r14
0x18000f8ff  pop     r13
0x18000f901  pop     r12
0x18000f903  pop     rdi
0x18000f904  pop     rsi
0x18000f905  pop     rbp
0x18000f906  retn
```
