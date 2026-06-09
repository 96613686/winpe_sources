# DoFontEnum(HDC__ *,wchar_t *,short *,uint)

- ea: `0x18000fa40`
- end: `0x18000fbd6`
- name: `?DoFontEnum@@YAHPEAUHDC__@@PEA_WPEAFI@Z`
- size: `406`
- prototype: `__int64 __fastcall(HDC hdc, wchar_t *, __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009578`
- `0x18000f910`
- `0x18000fbdc`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x180005e60`
- `0x18000b224`
- `0x18000fa40`
- `0x180012894`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000fb49`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000fb49`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18000fba5`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18000fba5`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18000fa92`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18000fa92`
- `ext-ms-win-gdi-font-l1-1-0!EnumFontFamiliesExW` at `0x18000fb92`
- `ext-ms-win-gdi-font-l1-1-0!EnumFontFamiliesExW` at `0x18000fb92`

## pseudocode

```c
__int64 __fastcall DoFontEnum(HDC hdc, wchar_t *a2, __int16 *a3, int a4)
{
  int v7; // esi
  int v9; // eax
  BYTE lfCharSet; // cl
  int v11; // eax
  int (__stdcall *v12)(const LOGFONTW *, const TEXTMETRICW *, DWORD, LPARAM); // r8
  LPARAM lParam[2]; // [rsp+30h] [rbp-69h] BYREF
  __int128 v15; // [rsp+40h] [rbp-59h]
  tagLOGFONTW Logfont; // [rsp+50h] [rbp-49h] BYREF

  v7 = 0;
  *(_OWORD *)lParam = 0;
  v15 = 0;
  memset_0(&Logfont, 0, sizeof(Logfont));
  if ( !hdc )
  {
    hdc = CreateCompatibleDC(0);
    v7 = 1;
  }
  lParam[0] = (LPARAM)hdc;
  *(_QWORD *)&v15 = a3;
  DWORD2(v15) = a4;
  lParam[1] = a2 == 0;
  memset_0(&Logfont, 0, sizeof(Logfont));
  Logfont.lfCharSet = 1;
  if ( a2 )
  {
    StringCchCopyW(Logfont.lfFaceName, 0x20u, a2);
    if ( !NumberOfFonts
      && g_fEastAsianSystem
      && CodePageToCharSet(OEMCP) != 0x80
      && CodePageToCharSet(OEMCP) != 0x81
      && CodePageToCharSet(OEMCP) != 0x88
      && CodePageToCharSet(OEMCP) != 0x86 )
    {
      v9 = lstrcmpW(a2, L"Terminal");
      lfCharSet = Logfont.lfCharSet;
      if ( !v9 )
        lfCharSet = -1;
      Logfont.lfCharSet = lfCharSet;
    }
  }
  v11 = ShouldAllowAllMonoTTFonts();
  v12 = (int (__stdcall *)(const LOGFONTW *, const TEXTMETRICW *, DWORD, LPARAM))FontEnumForV2Console;
  if ( !v11 )
    v12 = FontEnum;
  EnumFontFamiliesExW(hdc, &Logfont, v12, (LPARAM)lParam, 0);
  if ( v7 )
    DeleteDC(hdc);
  return (HIDWORD(lParam[1]) >> 1) & 1;
}

```

## disassembly

```asm
0x18000fa40  push    rbp
0x18000fa42  push    rbx
0x18000fa43  push    rsi
0x18000fa44  push    rdi
0x18000fa45  push    r14
0x18000fa47  push    r15
0x18000fa49  lea     rbp, [rsp-2Fh]
0x18000fa4e  sub     rsp, 0C8h
0x18000fa55  mov     rax, cs:__security_cookie
0x18000fa5c  xor     rax, rsp
0x18000fa5f  mov     [rbp+57h+var_40], rax
0x18000fa63  xorps   xmm0, xmm0
0x18000fa66  mov     r14, r8
0x18000fa69  mov     rdi, rdx
0x18000fa6c  mov     rbx, rcx
0x18000fa6f  xor     esi, esi
0x18000fa71  lea     rcx, [rbp+57h+Logfont]; void *
0x18000fa75  xor     edx, edx; Val
0x18000fa77  mov     r15d, r9d
0x18000fa7a  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x18000fa7e  lea     r8d, [rsi+5Ch]; Size
0x18000fa82  movups  [rbp+57h+var_B0], xmm0
0x18000fa86  call    memset_0
0x18000fa8b  test    rbx, rbx
0x18000fa8e  jnz     short loc_18000FAA6
0x18000fa90  xor     ecx, ecx; hdc
0x18000fa92  call    cs:__imp_CreateCompatibleDC
0x18000fa99  nop     dword ptr [rax+rax+00h]
0x18000fa9e  mov     rbx, rax
0x18000faa1  mov     esi, 1
0x18000faa6  xor     ecx, ecx
0x18000faa8  mov     [rbp+57h+lParam], rbx
0x18000faac  test    rdi, rdi
0x18000faaf  mov     dword ptr [rbp+57h+lParam+0Ch], 0
0x18000fab6  mov     qword ptr [rbp+57h+var_B0], r14
0x18000faba  setz    cl
0x18000fabd  mov     dword ptr [rbp+57h+var_B0+8], r15d
0x18000fac1  xor     edx, edx; Val
0x18000fac3  mov     dword ptr [rbp+57h+lParam+8], ecx
0x18000fac6  lea     rcx, [rbp+57h+Logfont]; void *
0x18000faca  lea     r8d, [rdx+5Ch]; Size
0x18000face  call    memset_0
0x18000fad3  mov     [rbp+57h+Logfont.lfCharSet], 1
0x18000fad7  test    rdi, rdi
0x18000fada  jz      loc_18000FB66
0x18000fae0  mov     r8, rdi; wchar_t *
0x18000fae3  lea     rcx, [rbp+57h+Logfont.lfFaceName]; wchar_t *
0x18000fae7  mov     edx, 20h ; ' '; unsigned __int64
0x18000faec  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000faf1  cmp     cs:?NumberOfFonts@@3KA, 0; ulong NumberOfFonts
0x18000faf8  jnz     short loc_18000FB66
0x18000fafa  cmp     cs:?g_fEastAsianSystem@@3HA, 0; int g_fEastAsianSystem
0x18000fb01  jz      short loc_18000FB66
0x18000fb03  mov     ecx, cs:?OEMCP@@3IA; unsigned int
0x18000fb09  call    ?CodePageToCharSet@@YAEI@Z; CodePageToCharSet(uint)
0x18000fb0e  cmp     al, 80h
0x18000fb10  jz      short loc_18000FB66
0x18000fb12  mov     ecx, cs:?OEMCP@@3IA; unsigned int
0x18000fb18  call    ?CodePageToCharSet@@YAEI@Z; CodePageToCharSet(uint)
0x18000fb1d  cmp     al, 81h
0x18000fb1f  jz      short loc_18000FB66
0x18000fb21  mov     ecx, cs:?OEMCP@@3IA; unsigned int
0x18000fb27  call    ?CodePageToCharSet@@YAEI@Z; CodePageToCharSet(uint)
0x18000fb2c  cmp     al, 88h
0x18000fb2e  jz      short loc_18000FB66
0x18000fb30  mov     ecx, cs:?OEMCP@@3IA; unsigned int
0x18000fb36  call    ?CodePageToCharSet@@YAEI@Z; CodePageToCharSet(uint)
0x18000fb3b  cmp     al, 86h
0x18000fb3d  jz      short loc_18000FB66
0x18000fb3f  lea     rdx, aTerminal; "Terminal"
0x18000fb46  mov     rcx, rdi; lpString1
0x18000fb49  call    cs:__imp_lstrcmpW
0x18000fb50  nop     dword ptr [rax+rax+00h]
0x18000fb55  movzx   ecx, [rbp+57h+Logfont.lfCharSet]
0x18000fb59  mov     edx, 0FFh
0x18000fb5e  test    eax, eax
0x18000fb60  cmovz   ecx, edx
0x18000fb63  mov     [rbp+57h+Logfont.lfCharSet], cl
0x18000fb66  call    ?ShouldAllowAllMonoTTFonts@@YAHXZ; ShouldAllowAllMonoTTFonts(void)
0x18000fb6b  test    eax, eax
0x18000fb6d  mov     [rsp+0F0h+dwFlags], 0; dwFlags
0x18000fb75  lea     rcx, ?FontEnum@@YAHPEAUtagENUMLOGFONTW@@PEAUtagNEWTEXTMETRICW@@H_J@Z; FontEnum(tagENUMLOGFONTW *,tagNEWTEXTMETRICW *,int,__int64)
0x18000fb7c  lea     r8, ?FontEnumForV2Console@@YAHPEAUtagENUMLOGFONTW@@PEAUtagNEWTEXTMETRICW@@H_J@Z; FontEnumForV2Console(tagENUMLOGFONTW *,tagNEWTEXTMETRICW *,int,__int64)
0x18000fb83  cmovz   r8, rcx; lpProc
0x18000fb87  lea     r9, [rbp+57h+lParam]; lParam
0x18000fb8b  mov     rcx, rbx; hdc
0x18000fb8e  lea     rdx, [rbp+57h+Logfont]; lpLogfont
0x18000fb92  call    cs:__imp_EnumFontFamiliesExW
0x18000fb99  nop     dword ptr [rax+rax+00h]
0x18000fb9e  test    esi, esi
0x18000fba0  jz      short loc_18000FBB1
0x18000fba2  mov     rcx, rbx; hdc
0x18000fba5  call    cs:__imp_DeleteDC
0x18000fbac  nop     dword ptr [rax+rax+00h]
0x18000fbb1  mov     eax, dword ptr [rbp+57h+lParam+0Ch]
0x18000fbb4  shr     eax, 1
0x18000fbb6  and     eax, 1
0x18000fbb9  mov     rcx, [rbp+57h+var_40]
0x18000fbbd  xor     rcx, rsp; StackCookie
0x18000fbc0  call    __security_check_cookie
0x18000fbc5  add     rsp, 0C8h
0x18000fbcc  pop     r15
0x18000fbce  pop     r14
0x18000fbd0  pop     rdi
0x18000fbd1  pop     rsi
0x18000fbd2  pop     rbx
0x18000fbd3  pop     rbp
0x18000fbd4  retn
```
