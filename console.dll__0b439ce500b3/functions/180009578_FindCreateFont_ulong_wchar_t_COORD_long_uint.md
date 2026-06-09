# FindCreateFont(ulong,wchar_t *,_COORD,long,uint)

- ea: `0x180009578`
- end: `0x18000996f`
- name: `?FindCreateFont@@YAHKPEA_WU_COORD@@JI@Z`
- size: `1015`
- prototype: `int(unsigned int, wchar_t *, struct _COORD, int, unsigned int)`
- caller_count: `6`
- callee_count: `12`
- tags: ``

## callers

- `0x18000752c`
- `0x180007a68`
- `0x180008d68`
- `0x180009980`
- `0x18000ab50`
- `0x18000ac68`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x180005e60`
- `0x180009578`
- `0x18000b224`
- `0x18000b254`
- `0x18000fa40`
- `0x180012894`
- `0x1800128f8`
- `0x1800129bc`
- `0x180012d1c`
- `0x180018cf4`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800097f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000980f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800097f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000980f`

## string_xrefs

- `0x1800095e8`: `onecore\windows\core\console\open\src\propsheet\fontdlg.cpp`
- `0x180009933`: `onecore\windows\core\console\open\src\propsheet\fontdlg.cpp`

## pseudocode

```c
__int64 __fastcall FindCreateFont(int a1, wchar_t *a2, struct _COORD a3, int a4, unsigned int a5)
{
  int v5; // r13d
  unsigned int v6; // r14d
  const char *v9; // r9
  signed int v10; // edi
  int v11; // ecx
  _COORD v12; // eax
  const wchar_t *v13; // r11
  int v14; // ecx
  int v15; // eax
  const char *v16; // r9
  const WCHAR *AltFaceName; // r15
  _BYTE *v18; // r8
  __int64 v19; // rsi
  char v20; // al
  unsigned int i; // edx
  __int64 v22; // rcx
  bool v23; // zf
  struct _COORD v25; // [rsp+30h] [rbp-91h] BYREF
  unsigned __int8 v26[4]; // [rsp+38h] [rbp-89h] BYREF
  _COORD v27; // [rsp+3Ch] [rbp-85h] BYREF
  unsigned int v28; // [rsp+40h] [rbp-81h] BYREF
  int v29; // [rsp+44h] [rbp-7Dh]
  wchar_t v30[32]; // [rsp+50h] [rbp-71h] BYREF
  wchar_t v31[32]; // [rsp+90h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v6 = 0;
  v25 = a3;
  v29 = a4;
  v27 = 0;
  v26[0] = 0;
  v28 = 0;
  LOBYTE(v5) = CodePageToCharSet(a5);
  if ( !OEMCP )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x477,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\fontdlg.cpp",
      v9);
  v10 = -1;
  if ( !g_fEastAsianSystem
    || (unsigned __int8)(v5 + 0x80) <= 8u && (v11 = 323, _bittest(&v11, v5 - 128))
    || (_BYTE)v5 == 0xFF )
  {
    if ( !a2 || !*a2 )
      a2 = &DefaultFaceName;
    if ( v25.Y )
      goto LABEL_18;
    v12 = DefaultFontSize;
  }
  else
  {
    MakeAltRasterFont(a5, &v27, v26, &v28, v31);
    if ( !a2 || !*a2 )
      a2 = v31;
    if ( v25.Y )
      goto LABEL_18;
    v12 = v27;
  }
  v25 = v12;
LABEL_18:
  if ( !wcscmp_0(a2, L"__DefaultTTFont__") )
  {
    memset_0(v30, 0, sizeof(v30));
    v13 = (const wchar_t *)TrueTypeFontList::s_ttFontList;
    v14 = 0;
    v15 = 0;
    if ( TrueTypeFontList::s_ttFontList )
    {
      while ( !v15 )
      {
        if ( *((_DWORD *)v13 + 2) == a5 )
        {
          v14 = StringCchCopyW(v30, 0x20u, v13 + 8);
          v15 = 1;
        }
        v13 = *(const wchar_t **)v13;
        if ( !v13 )
        {
          if ( v15 )
            break;
          goto LABEL_25;
        }
      }
    }
    else
    {
LABEL_25:
      v14 = StringCchCopyW(v30, 0x20u, L"Consolas");
    }
    if ( v14 >= 0 && StringCchCopyW(&DefaultTTFaceName, 0x20u, v30) >= 0 )
    {
      a2 = &DefaultTTFaceName;
      v25.X = 0;
    }
  }
  if ( (unsigned int)ShouldAllowAllMonoTTFonts() || (unsigned int)IsAvailableTTFont(a2) )
    AltFaceName = GetAltFaceName(a2);
  else
    AltFaceName = a2;
  while ( 1 )
  {
    v18 = FontInfo;
    while ( v6 < NumberOfFonts )
    {
      v19 = 40LL * v6;
      if ( (!a1 || (_BYTE)a1 == v18[v19 + 32])
        && (*(_WORD *)&v18[v19 + 14] == v25.Y || *(_WORD *)&v18[v19 + 8] == v25.X && *(_WORD *)&v18[v19 + 10] == v25.Y)
        && (!v29 || v29 == *(_DWORD *)&v18[v19 + 16]) )
      {
        if ( (v18[v19 + 32] & 4) != 0 || (v20 = v18[v19 + 33], v20 == (_BYTE)v5) || v20 == -1 && g_fEastAsianSystem )
        {
          if ( !a2
            || !*a2
            || !lstrcmpW(*(LPCWSTR *)&v18[v19 + 24], a2)
            || !lstrcmpW(*(LPCWSTR *)((char *)FontInfo + v19 + 24), AltFaceName) )
          {
            v10 = v6;
            goto LABEL_80;
          }
          v18 = FontInfo;
          if ( (*((_BYTE *)FontInfo + v19 + 32) & 4) == 0 )
            v10 = v6;
        }
      }
      ++v6;
    }
    v6 = 0;
    if ( v10 != -1 )
      break;
    if ( v25.Y < 0 )
      v25.Y = -v25.Y;
    if ( !(unsigned int)DoFontEnum(0, a2, &v25.Y, 1) )
    {
      v18 = FontInfo;
      goto LABEL_61;
    }
    v10 = -2;
  }
  if ( v10 >= 0 )
    goto LABEL_80;
LABEL_61:
  for ( i = 0; i < NumberOfFonts; ++i )
  {
    if ( !g_fEastAsianSystem )
    {
      v22 = 40LL * i;
      v23 = (_BYTE)a1 == v18[v22 + 32];
LABEL_69:
      if ( !v23 )
        continue;
      goto LABEL_70;
    }
    if ( a1 && (_BYTE)a1 != v18[40 * i + 32] )
      continue;
    v22 = 40LL * i;
    if ( (v18[v22 + 32] & 4) == 0 )
    {
      v23 = v18[v22 + 33] == (unsigned __int8)v5;
      goto LABEL_69;
    }
LABEL_70:
    if ( *(__int16 *)&v18[v22 + 10] >= v25.Y && *(__int16 *)&v18[v22 + 8] >= v25.X )
    {
      v10 = i;
      break;
    }
  }
  if ( v10 < 0 )
  {
    if ( g_fEastAsianSystem )
    {
      v10 = v28;
      if ( a5 == OEMCP )
        v10 = DefaultFontIndex;
    }
    else
    {
      v10 = DefaultFontIndex;
    }
  }
LABEL_80:
  if ( v10 >= (int)NumberOfFonts )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x54B,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\fontdlg.cpp",
      v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009578  mov     [rsp-8+arg_0], rbx
0x18000957d  push    rbp
0x18000957e  push    rsi
0x18000957f  push    rdi
0x180009580  push    r12
0x180009582  push    r13
0x180009584  push    r14
0x180009586  push    r15
0x180009588  lea     rbp, [rsp-1Fh]
0x18000958d  sub     rsp, 0E0h
0x180009594  mov     rax, cs:__security_cookie
0x18000959b  xor     rax, rsp
0x18000959e  mov     [rbp+4Fh+var_40], rax
0x1800095a2  mov     esi, [rbp+4Fh+arg_20]
0x1800095a5  xor     r14d, r14d
0x1800095a8  mov     [rsp+110h+var_E0.X], r8w
0x1800095ae  mov     r12d, ecx
0x1800095b1  shr     r8d, 10h
0x1800095b5  mov     ecx, esi; unsigned int
0x1800095b7  mov     [rsp+110h+var_E0.Y], r8w
0x1800095bd  mov     rbx, rdx
0x1800095c0  mov     [rbp+4Fh+var_CC], r9d
0x1800095c4  mov     dword ptr [rsp+110h+var_D4.X], r14d
0x1800095c9  mov     [rsp+110h+var_D8], r14b
0x1800095ce  mov     [rsp+110h+var_D0], r14d
0x1800095d3  call    ?CodePageToCharSet@@YAEI@Z; CodePageToCharSet(uint)
0x1800095d8  cmp     cs:?OEMCP@@3IA, r14d; uint OEMCP
0x1800095df  mov     r13b, al
0x1800095e2  jnz     short loc_1800095FA
0x1800095e4  mov     rcx, [rbp+57h]; this
0x1800095e8  lea     r8, aOnecoreWindows_2; "onecore\\windows\\core\\console\\open\\"...
0x1800095ef  mov     edx, 477h; void *
0x1800095f4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800095fa  or      edi, 0FFFFFFFFh
0x1800095fd  cmp     cs:?g_fEastAsianSystem@@3HA, r14d; int g_fEastAsianSystem
0x180009604  jz      short loc_18000965A
0x180009606  lea     eax, [r13-80h]
0x18000960a  cmp     al, 8
0x18000960c  ja      short loc_180009618
0x18000960e  mov     ecx, 143h
0x180009613  bt      ecx, eax
0x180009616  jb      short loc_18000965A
0x180009618  cmp     r13b, 0FFh
0x18000961c  jz      short loc_18000965A
0x18000961e  lea     rax, [rbp+4Fh+var_80]
0x180009622  mov     ecx, esi; unsigned int
0x180009624  lea     r9, [rsp+110h+var_D0]; unsigned int *
0x180009629  mov     [rsp+110h+var_F0], rax; wchar_t *
0x18000962e  lea     r8, [rsp+110h+var_D8]; unsigned __int8 *
0x180009633  lea     rdx, [rsp+110h+var_D4]; struct _COORD *
0x180009638  call    ?MakeAltRasterFont@@YAXIPEAU_COORD@@PEAEPEAKPEA_W@Z; MakeAltRasterFont(uint,_COORD *,uchar *,ulong *,wchar_t *)
0x18000963d  test    rbx, rbx
0x180009640  jz      short loc_180009648
0x180009642  cmp     [rbx], r14w
0x180009646  jnz     short loc_18000964C
0x180009648  lea     rbx, [rbp+4Fh+var_80]
0x18000964c  cmp     [rsp+110h+var_E0.Y], r14w
0x180009652  jnz     short loc_18000967E
0x180009654  mov     eax, dword ptr [rsp+110h+var_D4.X]
0x180009658  jmp     short loc_18000967A
0x18000965a  test    rbx, rbx
0x18000965d  jz      short loc_180009665
0x18000965f  cmp     [rbx], r14w
0x180009663  jnz     short loc_18000966C
0x180009665  lea     rbx, ?DefaultFaceName@@3PA_WA; wchar_t near * DefaultFaceName
0x18000966c  cmp     [rsp+110h+var_E0.Y], r14w
0x180009672  jnz     short loc_18000967E
0x180009674  mov     eax, cs:?DefaultFontSize@@3U_COORD@@A; _COORD DefaultFontSize
0x18000967a  mov     dword ptr [rsp+110h+var_E0.X], eax
0x18000967e  lea     rdx, aDefaultttfont; "__DefaultTTFont__"
0x180009685  mov     rcx, rbx; String1
0x180009688  call    wcscmp_0
0x18000968d  test    eax, eax
0x18000968f  jnz     loc_180009726
0x180009695  xor     edx, edx; Val
0x180009697  lea     r8d, [rax+40h]; Size
0x18000969b  lea     rcx, [rbp+4Fh+var_C0]; void *
0x18000969f  call    memset_0
0x1800096a4  mov     r11, cs:?s_ttFontList@TrueTypeFontList@@2U_SINGLE_LIST_ENTRY@@A; _SINGLE_LIST_ENTRY TrueTypeFontList::s_ttFontList
0x1800096ab  mov     ecx, r14d
0x1800096ae  mov     eax, r14d
0x1800096b1  mov     r15d, 20h ; ' '
0x1800096b7  test    r11, r11
0x1800096ba  jz      short loc_1800096E9
0x1800096bc  test    eax, eax
0x1800096be  jnz     short loc_1800096FE
0x1800096c0  cmp     [r11+8], esi
0x1800096c4  jnz     short loc_1800096DD
0x1800096c6  lea     r8, [r11+10h]; wchar_t *
0x1800096ca  mov     rdx, r15; unsigned __int64
0x1800096cd  lea     rcx, [rbp+4Fh+var_C0]; wchar_t *
0x1800096d1  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800096d6  mov     ecx, eax
0x1800096d8  mov     eax, 1
0x1800096dd  mov     r11, [r11]
0x1800096e0  test    r11, r11
0x1800096e3  jnz     short loc_1800096BC
0x1800096e5  test    eax, eax
0x1800096e7  jnz     short loc_1800096FE
0x1800096e9  lea     r8, aConsolas; "Consolas"
0x1800096f0  mov     rdx, r15; unsigned __int64
0x1800096f3  lea     rcx, [rbp+4Fh+var_C0]; wchar_t *
0x1800096f7  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800096fc  mov     ecx, eax
0x1800096fe  test    ecx, ecx
0x180009700  js      short loc_180009726
0x180009702  lea     r8, [rbp+4Fh+var_C0]; wchar_t *
0x180009706  mov     rdx, r15; unsigned __int64
0x180009709  lea     rcx, ?DefaultTTFaceName@@3PA_WA; wchar_t *
0x180009710  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009715  test    eax, eax
0x180009717  js      short loc_180009726
0x180009719  lea     rbx, ?DefaultTTFaceName@@3PA_WA; wchar_t near * DefaultTTFaceName
0x180009720  mov     [rsp+110h+var_E0.X], r14w
0x180009726  call    ?ShouldAllowAllMonoTTFonts@@YAHXZ; ShouldAllowAllMonoTTFonts(void)
0x18000972b  test    eax, eax
0x18000972d  jnz     short loc_180009740
0x18000972f  mov     rcx, rbx; wchar_t *
0x180009732  call    ?IsAvailableTTFont@@YAHPEB_W@Z; IsAvailableTTFont(wchar_t const *)
0x180009737  test    eax, eax
0x180009739  jnz     short loc_180009740
0x18000973b  mov     r15, rbx
0x18000973e  jmp     short loc_18000974B
0x180009740  mov     rcx, rbx; wchar_t *
0x180009743  call    ?GetAltFaceName@@YAPEA_WPEB_W@Z; GetAltFaceName(wchar_t const *)
0x180009748  mov     r15, rax
0x18000974b  mov     r8, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180009752  cmp     r14d, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x180009759  jnb     loc_180009838
0x18000975f  mov     eax, r14d
0x180009762  xor     edx, edx
0x180009764  lea     rcx, [rax+rax*4]
0x180009768  lea     rsi, ds:0[rcx*8]
0x180009770  test    r12d, r12d
0x180009773  jz      short loc_180009780
0x180009775  cmp     r12b, [rsi+r8+20h]
0x18000977a  jnz     loc_180009830
0x180009780  movzx   ecx, [rsp+110h+var_E0.Y]
0x180009785  cmp     [rsi+r8+0Eh], cx
0x18000978b  jz      short loc_1800097AA
0x18000978d  movzx   eax, [rsp+110h+var_E0.X]
0x180009792  cmp     [rsi+r8+8], ax
0x180009798  jnz     loc_180009830
0x18000979e  cmp     [rsi+r8+0Ah], cx
0x1800097a4  jnz     loc_180009830
0x1800097aa  mov     eax, [rbp+4Fh+var_CC]
0x1800097ad  test    eax, eax
0x1800097af  jz      short loc_1800097B8
0x1800097b1  cmp     eax, [rsi+r8+10h]
0x1800097b6  jnz     short loc_180009830
0x1800097b8  test    byte ptr [rsi+r8+20h], 4
0x1800097be  jnz     short loc_1800097D6
0x1800097c0  mov     al, [rsi+r8+21h]
0x1800097c5  cmp     al, r13b
0x1800097c8  jz      short loc_1800097D6
0x1800097ca  cmp     al, 0FFh
0x1800097cc  jnz     short loc_180009830
0x1800097ce  cmp     cs:?g_fEastAsianSystem@@3HA, edx; int g_fEastAsianSystem
0x1800097d4  jz      short loc_180009830
0x1800097d6  test    rbx, rbx
0x1800097d9  jz      loc_180009875
0x1800097df  cmp     [rbx], dx
0x1800097e2  jz      loc_180009875
0x1800097e8  mov     rcx, [rsi+r8+18h]; lpString1
0x1800097ed  mov     rdx, rbx; lpString2
0x1800097f0  call    cs:__imp_lstrcmpW
0x1800097f7  nop     dword ptr [rax+rax+00h]
0x1800097fc  test    eax, eax
0x1800097fe  jz      short loc_180009875
0x180009800  mov     rcx, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180009807  mov     rdx, r15; lpString2
0x18000980a  mov     rcx, [rsi+rcx+18h]; lpString1
0x18000980f  call    cs:__imp_lstrcmpW
0x180009816  nop     dword ptr [rax+rax+00h]
0x18000981b  test    eax, eax
0x18000981d  jz      short loc_180009875
0x18000981f  mov     r8, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180009826  test    byte ptr [rsi+r8+20h], 4
0x18000982c  cmovz   edi, r14d
0x180009830  inc     r14d
0x180009833  jmp     loc_180009752
0x180009838  xor     r14d, r14d
0x18000983b  cmp     edi, 0FFFFFFFFh
0x18000983e  jnz     short loc_180009886
0x180009840  movzx   ecx, [rsp+110h+var_E0.Y]
0x180009845  test    cx, cx
0x180009848  jns     short loc_180009852
0x18000984a  neg     cx
0x18000984d  mov     [rsp+110h+var_E0.Y], cx
0x180009852  mov     r9d, 1; unsigned int
0x180009858  lea     r8, [rsp+110h+var_E0.Y]; __int16 *
0x18000985d  mov     rdx, rbx; wchar_t *
0x180009860  xor     ecx, ecx; hdc
0x180009862  call    ?DoFontEnum@@YAHPEAUHDC__@@PEA_WPEAFI@Z; DoFontEnum(HDC__ *,wchar_t *,short *,uint)
0x180009867  test    eax, eax
0x180009869  jz      short loc_18000987D
0x18000986b  mov     edi, 0FFFFFFFEh
0x180009870  jmp     loc_18000974B
0x180009875  mov     edi, r14d
0x180009878  jmp     loc_180009927
0x18000987d  mov     r8, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180009884  jmp     short loc_18000988E
0x180009886  test    edi, edi
0x180009888  jns     loc_180009927
0x18000988e  mov     edx, r14d
0x180009891  cmp     edx, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x180009897  jnb     short loc_1800098FE
0x180009899  cmp     cs:?g_fEastAsianSystem@@3HA, r14d; int g_fEastAsianSystem
0x1800098a0  jz      short loc_1800098CD
0x1800098a2  test    r12d, r12d
0x1800098a5  jz      short loc_1800098B4
0x1800098a7  mov     eax, edx
0x1800098a9  lea     rcx, [rax+rax*4]
0x1800098ad  cmp     r12b, [r8+rcx*8+20h]
0x1800098b2  jnz     short loc_1800098F8
0x1800098b4  mov     eax, edx
0x1800098b6  lea     rcx, [rax+rax*4]
0x1800098ba  shl     rcx, 3
0x1800098be  test    byte ptr [rcx+r8+20h], 4
0x1800098c4  jnz     short loc_1800098DE
0x1800098c6  cmp     [rcx+r8+21h], r13b
0x1800098cb  jmp     short loc_1800098DC
0x1800098cd  mov     eax, edx
0x1800098cf  lea     rcx, [rax+rax*4]
0x1800098d3  shl     rcx, 3
0x1800098d7  cmp     r12b, [rcx+r8+20h]
0x1800098dc  jnz     short loc_1800098F8
0x1800098de  movzx   eax, [rsp+110h+var_E0.Y]
0x1800098e3  cmp     [rcx+r8+0Ah], ax
0x1800098e9  jl      short loc_1800098F8
0x1800098eb  movzx   eax, [rsp+110h+var_E0.X]
0x1800098f0  cmp     [rcx+r8+8], ax
0x1800098f6  jge     short loc_1800098FC
0x1800098f8  inc     edx
0x1800098fa  jmp     short loc_180009891
0x1800098fc  mov     edi, edx
0x1800098fe  test    edi, edi
0x180009900  jns     short loc_180009927
0x180009902  cmp     cs:?g_fEastAsianSystem@@3HA, r14d; int g_fEastAsianSystem
0x180009909  jz      short loc_180009921
0x18000990b  mov     eax, [rbp+4Fh+arg_20]
0x18000990e  cmp     eax, cs:?OEMCP@@3IA; uint OEMCP
0x180009914  mov     edi, [rsp+110h+var_D0]
0x180009918  cmovz   edi, cs:?DefaultFontIndex@@3KA; ulong DefaultFontIndex
0x18000991f  jmp     short loc_180009927
0x180009921  mov     edi, cs:?DefaultFontIndex@@3KA; ulong DefaultFontIndex
0x180009927  cmp     edi, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18000992d  jl      short loc_180009945
0x18000992f  mov     rcx, [rbp+57h]; this
0x180009933  lea     r8, aOnecoreWindows_2; "onecore\\windows\\core\\console\\open\\"...
0x18000993a  mov     edx, 54Bh; void *
0x18000993f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009945  mov     eax, edi
0x180009947  mov     rcx, [rbp+4Fh+var_40]
0x18000994b  xor     rcx, rsp; StackCookie
0x18000994e  call    __security_check_cookie
0x180009953  mov     rbx, [rsp+110h+arg_0]
0x18000995b  add     rsp, 0E0h
0x180009962  pop     r15
0x180009964  pop     r14
0x180009966  pop     r13
0x180009968  pop     r12
0x18000996a  pop     rdi
0x18000996b  pop     rsi
0x18000996c  pop     rbp
0x18000996d  retn
```
