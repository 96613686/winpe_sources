# EnumerateFonts(ulong)

- ea: `0x18000fbdc`
- end: `0x18000ff30`
- name: `?EnumerateFonts@@YAJK@Z`
- size: `852`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000a01c`
- `0x1800103b4`

## callees

- `0x1800015b0`
- `0x18000f400`
- `0x18000f910`
- `0x18000fa40`
- `0x18000fbdc`
- `0x1800103ec`
- `0x1800105a4`
- `0x180012a34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fc38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fc38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc21`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x18000fc8f`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x18000fc8f`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000fca1`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18000fca1`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18000fe46`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18000fe46`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18000fc66`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18000fc66`
- `ext-ms-win-gdi-font-l1-1-0!GetTextMetricsW` at `0x18000fcb5`
- `ext-ms-win-gdi-font-l1-1-0!GetTextMetricsW` at `0x18000fcb5`
- `ext-ms-win-gdi-font-l1-1-1!GetTextFaceW` at `0x18000fccf`
- `ext-ms-win-gdi-font-l1-1-1!GetTextFaceW` at `0x18000fccf`

## pseudocode

```c
__int64 __fastcall EnumerateFonts(unsigned __int8 a1)
{
  HANDLE ProcessHeap; // rax
  int v4; // r12d
  HDC CompatibleDC; // rdi
  HGDIOBJ StockObject; // rax
  struct tagFACENODE *v7; // rax
  _DWORD *i; // rcx
  LPVOID j; // rbx
  int v10; // edx
  __int16 *v11; // r8
  unsigned int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rcx
  unsigned __int8 v17; // al
  struct tagTEXTMETRICW tm; // [rsp+20h] [rbp-78h] BYREF

  memset(&tm, 0, sizeof(tm));
  if ( !FontInfo )
  {
    NumberOfFonts = 0;
    ProcessHeap = GetProcessHeap();
    FontInfo = HeapAlloc(ProcessHeap, 0, 0x320u);
    if ( !FontInfo )
      return 3221225495LL;
    FontInfoLength = 20;
  }
  v4 = 323;
  CompatibleDC = CreateCompatibleDC(0);
  if ( (a1 & 0x20) != 0 )
  {
    StockObject = GetStockObject(10);
    SelectObject(CompatibleDC, StockObject);
    GetTextMetricsW(CompatibleDC, &tm);
    GetTextFaceW(CompatibleDC, 32, &DefaultFaceName);
    DefaultFontSize.Y = LOWORD(tm.tmExternalLeading) + LOWORD(tm.tmHeight);
    DefaultFontFamily = tm.tmPitchAndFamily;
    DefaultFontSize.X = tm.tmMaxCharWidth;
    if ( (unsigned __int8)(tm.tmCharSet + 0x80) <= 8u && _bittest(&v4, (unsigned __int8)(tm.tmCharSet + 0x80)) )
      DefaultFontSize.X = SLOWORD(tm.tmMaxCharWidth) / 2;
    v7 = AddFaceNode(&DefaultFaceName);
    if ( v7 )
      *((_DWORD *)v7 + 2) |= 0x28u;
  }
  if ( gbEnumerateFaces )
  {
    for ( i = gpFaceNames; i; i = *(_DWORD **)i )
      i[2] = i[2] & 0xFFFFFFFC | 2;
    DoFontEnum(CompatibleDC, 0, &TTPoints, 1u);
    gbEnumerateFaces = 0;
  }
  for ( j = gpFaceNames; j; j = *(LPVOID *)j )
  {
    v10 = *((_DWORD *)j + 2);
    if ( (v10 & 3) == 2 )
    {
      RemoveFace((LPCWSTR)j + 6);
      *((_DWORD *)j + 2) &= ~4u;
    }
    else if ( (a1 & (unsigned __int8)v10 & 0x38) != 0 && (v10 & 4) == 0 )
    {
      if ( (v10 & 0x10) != 0 )
      {
        if ( !g_fEastAsianSystem || (unsigned int)IsAvailableTTFontCP((const wchar_t *)j + 6, 0) )
        {
          v11 = &TTPoints;
          v12 = 14;
        }
        else
        {
          v11 = (__int16 *)&TTPointsDbcs;
          v12 = 12;
        }
        v13 = 12;
        v14 = (__int64)j;
      }
      else
      {
        v11 = 0;
        v13 = (__int64)j;
        v12 = 0;
        v14 = 12;
      }
      DoFontEnum(CompatibleDC, (wchar_t *)(v14 + v13), v11, v12);
      *((_DWORD *)j + 2) |= 4u;
    }
  }
  v15 = *((unsigned __int16 *)gpStateInfo + 9);
  if ( IsFontSizeCustom((const wchar_t *)gpStateInfo + 14, *((_WORD *)gpStateInfo + 9)) )
    CreateSizeForAllTTFonts(v15);
  DeleteDC(CompatibleDC);
  v16 = 0;
  if ( !g_fEastAsianSystem )
  {
    if ( NumberOfFonts )
    {
      do
      {
        if ( *((_WORD *)FontInfo + 20 * v16 + 4) == DefaultFontSize.X
          && *((_WORD *)FontInfo + 20 * v16 + 5) == DefaultFontSize.Y
          && *((_BYTE *)FontInfo + 40 * v16 + 32) == DefaultFontFamily )
        {
          break;
        }
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < NumberOfFonts );
      goto LABEL_47;
    }
LABEL_48:
    LODWORD(v16) = 0;
    goto LABEL_49;
  }
  if ( !NumberOfFonts )
    goto LABEL_48;
  do
  {
    if ( *((_WORD *)FontInfo + 20 * v16 + 4) == DefaultFontSize.X
      && *((_WORD *)FontInfo + 20 * v16 + 5) == DefaultFontSize.Y )
    {
      if ( (v17 = *((_BYTE *)FontInfo + 40 * v16 + 33) + 0x80, v17 <= 8u) && _bittest(&v4, v17)
        || *((_BYTE *)FontInfo + 40 * v16 + 33) == 0xFF )
      {
        if ( *((_BYTE *)FontInfo + 40 * v16 + 32) == DefaultFontFamily )
          break;
      }
    }
    v16 = (unsigned int)(v16 + 1);
  }
  while ( (unsigned int)v16 < NumberOfFonts );
LABEL_47:
  if ( (unsigned int)v16 >= NumberOfFonts )
    goto LABEL_48;
LABEL_49:
  DefaultFontIndex = v16;
  return 0;
}

```

## disassembly

```asm
0x18000fbdc  push    rbx
0x18000fbde  push    rsi
0x18000fbdf  push    rdi
0x18000fbe0  push    r12
0x18000fbe2  push    r15
0x18000fbe4  sub     rsp, 70h
0x18000fbe8  mov     rax, cs:__security_cookie
0x18000fbef  xor     rax, rsp
0x18000fbf2  mov     [rsp+98h+var_38], rax
0x18000fbf7  xorps   xmm0, xmm0
0x18000fbfa  xor     eax, eax
0x18000fbfc  cmp     cs:?FontInfo@@3PEAU_FONT_INFO@@EA, rax; _FONT_INFO * FontInfo
0x18000fc03  mov     esi, ecx
0x18000fc05  movups  xmmword ptr [rsp+98h+tm.tmOverhang], xmm0
0x18000fc0a  movups  xmmword ptr [rsp+98h+tm.tmFirstChar], xmm0
0x18000fc0f  movups  xmmword ptr [rsp+98h+tm.tmHeight], xmm0
0x18000fc14  movups  xmmword ptr [rsp+98h+tm.tmExternalLeading], xmm0
0x18000fc19  jnz     short loc_18000FC64
0x18000fc1b  mov     cs:?NumberOfFonts@@3KA, eax; ulong NumberOfFonts
0x18000fc21  call    cs:__imp_GetProcessHeap
0x18000fc28  nop     dword ptr [rax+rax+00h]
0x18000fc2d  xor     edx, edx; dwFlags
0x18000fc2f  mov     r8d, 320h; dwBytes
0x18000fc35  mov     rcx, rax; hHeap
0x18000fc38  call    cs:__imp_HeapAlloc
0x18000fc3f  nop     dword ptr [rax+rax+00h]
0x18000fc44  mov     cs:?FontInfo@@3PEAU_FONT_INFO@@EA, rax; _FONT_INFO * FontInfo
0x18000fc4b  test    rax, rax
0x18000fc4e  jnz     short loc_18000FC5A
0x18000fc50  mov     eax, 0C0000017h
0x18000fc55  jmp     loc_18000FF16
0x18000fc5a  mov     cs:?FontInfoLength@@3KA, 14h; ulong FontInfoLength
0x18000fc64  xor     ecx, ecx; hdc
0x18000fc66  call    cs:__imp_CreateCompatibleDC
0x18000fc6d  nop     dword ptr [rax+rax+00h]
0x18000fc72  mov     r12d, 143h
0x18000fc78  mov     rdi, rax
0x18000fc7b  mov     r15d, 2
0x18000fc81  test    sil, 20h
0x18000fc85  jz      loc_18000FD37
0x18000fc8b  lea     ecx, [r15+8]; i
0x18000fc8f  call    cs:__imp_GetStockObject
0x18000fc96  nop     dword ptr [rax+rax+00h]
0x18000fc9b  mov     rdx, rax; h
0x18000fc9e  mov     rcx, rdi; hdc
0x18000fca1  call    cs:__imp_SelectObject
0x18000fca8  nop     dword ptr [rax+rax+00h]
0x18000fcad  lea     rdx, [rsp+98h+tm]; lptm
0x18000fcb2  mov     rcx, rdi; hdc
0x18000fcb5  call    cs:__imp_GetTextMetricsW
0x18000fcbc  nop     dword ptr [rax+rax+00h]
0x18000fcc1  lea     r8, ?DefaultFaceName@@3PA_WA; lpName
0x18000fcc8  mov     rcx, rdi; hdc
0x18000fccb  lea     edx, [r15+1Eh]; c
0x18000fccf  call    cs:__imp_GetTextFaceW
0x18000fcd6  nop     dword ptr [rax+rax+00h]
0x18000fcdb  movzx   eax, word ptr [rsp+98h+tm.tmHeight]
0x18000fce0  add     ax, word ptr [rsp+98h+tm.tmExternalLeading]
0x18000fce5  mov     edx, [rsp+98h+tm.tmMaxCharWidth]
0x18000fce9  mov     word ptr cs:?DefaultFontSize@@3U_COORD@@A+2, ax; _COORD DefaultFontSize
0x18000fcf0  mov     al, [rsp+98h+tm.tmPitchAndFamily]
0x18000fcf4  mov     cs:?DefaultFontFamily@@3EA, al; uchar DefaultFontFamily
0x18000fcfa  mov     al, [rsp+98h+tm.tmCharSet]
0x18000fcfe  sub     al, 80h
0x18000fd00  mov     word ptr cs:?DefaultFontSize@@3U_COORD@@A, dx; _COORD DefaultFontSize
0x18000fd07  cmp     al, 8
0x18000fd09  ja      short loc_18000FD22
0x18000fd0b  movzx   eax, al
0x18000fd0e  bt      r12d, eax
0x18000fd12  jnb     short loc_18000FD22
0x18000fd14  movsx   eax, dx
0x18000fd17  cdq
0x18000fd18  idiv    r15d
0x18000fd1b  mov     word ptr cs:?DefaultFontSize@@3U_COORD@@A, ax; _COORD DefaultFontSize
0x18000fd22  lea     rcx, ?DefaultFaceName@@3PA_WA; wchar_t *
0x18000fd29  call    ?AddFaceNode@@YAPEAUtagFACENODE@@PEB_W@Z; AddFaceNode(wchar_t const *)
0x18000fd2e  test    rax, rax
0x18000fd31  jz      short loc_18000FD37
0x18000fd33  or      dword ptr [rax+8], 28h
0x18000fd37  cmp     cs:?gbEnumerateFaces@@3HA, 0; int gbEnumerateFaces
0x18000fd3e  jz      short loc_18000FD7C
0x18000fd40  mov     rcx, cs:?gpFaceNames@@3PEAUtagFACENODE@@EA; tagFACENODE * gpFaceNames
0x18000fd47  jmp     short loc_18000FD58
0x18000fd49  mov     eax, [rcx+8]
0x18000fd4c  and     eax, 0FFFFFFFEh
0x18000fd4f  or      eax, r15d
0x18000fd52  mov     [rcx+8], eax
0x18000fd55  mov     rcx, [rcx]
0x18000fd58  test    rcx, rcx
0x18000fd5b  jnz     short loc_18000FD49
0x18000fd5d  lea     r9d, [rcx+1]; unsigned int
0x18000fd61  xor     edx, edx; wchar_t *
0x18000fd63  mov     rcx, rdi; hdc
0x18000fd66  lea     r8, ?TTPoints@@3PAFA; __int16 *
0x18000fd6d  call    ?DoFontEnum@@YAHPEAUHDC__@@PEA_WPEAFI@Z; DoFontEnum(HDC__ *,wchar_t *,short *,uint)
0x18000fd72  mov     cs:?gbEnumerateFaces@@3HA, 0; int gbEnumerateFaces
0x18000fd7c  mov     rbx, cs:?gpFaceNames@@3PEAUtagFACENODE@@EA; tagFACENODE * gpFaceNames
0x18000fd83  jmp     loc_18000FE17
0x18000fd88  mov     edx, [rbx+8]
0x18000fd8b  mov     eax, edx
0x18000fd8d  and     al, 3
0x18000fd8f  cmp     al, r15b
0x18000fd92  jnz     short loc_18000FDA3
0x18000fd94  lea     rcx, [rbx+0Ch]; lpString2
0x18000fd98  call    ?RemoveFace@@YAXPEB_W@Z; RemoveFace(wchar_t const *)
0x18000fd9d  and     dword ptr [rbx+8], 0FFFFFFFBh
0x18000fda1  jmp     short loc_18000FE14
0x18000fda3  mov     eax, edx
0x18000fda5  and     eax, esi
0x18000fda7  test    al, 38h
0x18000fda9  setnz   cl
0x18000fdac  test    dl, 4
0x18000fdaf  setz    al
0x18000fdb2  test    al, cl
0x18000fdb4  jz      short loc_18000FE14
0x18000fdb6  test    dl, 10h
0x18000fdb9  jz      short loc_18000FDF7
0x18000fdbb  cmp     cs:?g_fEastAsianSystem@@3HA, 0; int g_fEastAsianSystem
0x18000fdc2  jz      short loc_18000FDE0
0x18000fdc4  lea     rcx, [rbx+0Ch]; wchar_t *
0x18000fdc8  xor     edx, edx; unsigned int
0x18000fdca  call    ?IsAvailableTTFontCP@@YAHPEB_WI@Z; IsAvailableTTFontCP(wchar_t const *,uint)
0x18000fdcf  test    eax, eax
0x18000fdd1  jnz     short loc_18000FDE0
0x18000fdd3  lea     r8, ?TTPointsDbcs@@3PAFA; short near * TTPointsDbcs
0x18000fdda  lea     r9d, [rax+0Ch]
0x18000fdde  jmp     short loc_18000FDED
0x18000fde0  lea     r8, ?TTPoints@@3PAFA; short near * TTPoints
0x18000fde7  mov     r9d, 0Eh
0x18000fded  mov     eax, 0Ch
0x18000fdf2  mov     rcx, rbx
0x18000fdf5  jmp     short loc_18000FE04
0x18000fdf7  xor     r8d, r8d; __int16 *
0x18000fdfa  mov     rax, rbx
0x18000fdfd  xor     r9d, r9d; unsigned int
0x18000fe00  lea     ecx, [r8+0Ch]
0x18000fe04  lea     rdx, [rcx+rax]; wchar_t *
0x18000fe08  mov     rcx, rdi; hdc
0x18000fe0b  call    ?DoFontEnum@@YAHPEAUHDC__@@PEA_WPEAFI@Z; DoFontEnum(HDC__ *,wchar_t *,short *,uint)
0x18000fe10  or      dword ptr [rbx+8], 4
0x18000fe14  mov     rbx, [rbx]
0x18000fe17  test    rbx, rbx
0x18000fe1a  jnz     loc_18000FD88
0x18000fe20  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000fe27  movzx   ebx, word ptr [rcx+12h]
0x18000fe2b  add     rcx, 1Ch; wchar_t *
0x18000fe2f  movzx   edx, bx; __int16
0x18000fe32  call    ?IsFontSizeCustom@@YA_NPEB_WF@Z; IsFontSizeCustom(wchar_t const *,short)
0x18000fe37  test    al, al
0x18000fe39  jz      short loc_18000FE43
0x18000fe3b  movzx   ecx, bx; __int16
0x18000fe3e  call    ?CreateSizeForAllTTFonts@@YAXF@Z; CreateSizeForAllTTFonts(short)
0x18000fe43  mov     rcx, rdi; hdc
0x18000fe46  call    cs:__imp_DeleteDC
0x18000fe4d  nop     dword ptr [rax+rax+00h]
0x18000fe52  mov     edx, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18000fe58  xor     ecx, ecx
0x18000fe5a  cmp     cs:?g_fEastAsianSystem@@3HA, ecx; int g_fEastAsianSystem
0x18000fe60  jz      short loc_18000FEC6
0x18000fe62  test    edx, edx
0x18000fe64  jz      loc_18000FF0C
0x18000fe6a  mov     r8, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000fe71  movzx   r10d, word ptr cs:?DefaultFontSize@@3U_COORD@@A+2; _COORD DefaultFontSize
0x18000fe79  movzx   ebx, word ptr cs:?DefaultFontSize@@3U_COORD@@A; _COORD DefaultFontSize
0x18000fe80  mov     r11b, cs:?DefaultFontFamily@@3EA; uchar DefaultFontFamily
0x18000fe87  lea     r9, [rcx+rcx*4]
0x18000fe8b  cmp     [r8+r9*8+8], bx
0x18000fe91  jnz     short loc_18000FEBE
0x18000fe93  cmp     [r8+r9*8+0Ah], r10w
0x18000fe99  jnz     short loc_18000FEBE
0x18000fe9b  mov     al, [r8+r9*8+21h]
0x18000fea0  sub     al, 80h
0x18000fea2  cmp     al, 8
0x18000fea4  ja      short loc_18000FEAF
0x18000fea6  movzx   eax, al
0x18000fea9  bt      r12d, eax
0x18000fead  jb      short loc_18000FEB7
0x18000feaf  cmp     byte ptr [r8+r9*8+21h], 0FFh
0x18000feb5  jnz     short loc_18000FEBE
0x18000feb7  cmp     [r8+r9*8+20h], r11b
0x18000febc  jz      short loc_18000FF08
0x18000febe  inc     ecx
0x18000fec0  cmp     ecx, edx
0x18000fec2  jb      short loc_18000FE87
0x18000fec4  jmp     short loc_18000FF08
0x18000fec6  test    edx, edx
0x18000fec8  jz      short loc_18000FF0C
0x18000feca  mov     r8, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000fed1  movzx   r10d, word ptr cs:?DefaultFontSize@@3U_COORD@@A+2; _COORD DefaultFontSize
0x18000fed9  movzx   ebx, word ptr cs:?DefaultFontSize@@3U_COORD@@A; _COORD DefaultFontSize
0x18000fee0  mov     r11b, cs:?DefaultFontFamily@@3EA; uchar DefaultFontFamily
0x18000fee7  lea     r9, [rcx+rcx*4]
0x18000feeb  cmp     [r8+r9*8+8], bx
0x18000fef1  jnz     short loc_18000FF02
0x18000fef3  cmp     [r8+r9*8+0Ah], r10w
0x18000fef9  jnz     short loc_18000FF02
0x18000fefb  cmp     [r8+r9*8+20h], r11b
0x18000ff00  jz      short loc_18000FF08
0x18000ff02  inc     ecx
0x18000ff04  cmp     ecx, edx
0x18000ff06  jb      short loc_18000FEE7
0x18000ff08  cmp     ecx, edx
0x18000ff0a  jb      short loc_18000FF0E
0x18000ff0c  xor     ecx, ecx
0x18000ff0e  mov     cs:?DefaultFontIndex@@3KA, ecx; ulong DefaultFontIndex
0x18000ff14  xor     eax, eax
0x18000ff16  mov     rcx, [rsp+98h+var_38]
0x18000ff1b  xor     rcx, rsp; StackCookie
0x18000ff1e  call    __security_check_cookie
0x18000ff23  add     rsp, 70h
0x18000ff27  pop     r15
0x18000ff29  pop     r12
0x18000ff2b  pop     rdi
0x18000ff2c  pop     rsi
0x18000ff2d  pop     rbx
0x18000ff2e  retn
```
