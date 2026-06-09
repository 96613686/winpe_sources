# CModernShareCommand::GetIconAsBitmap(IShellItemArray *,tagSIZE,HBITMAP__ * *)

- ea: `0x18001b9b0`
- end: `0x18001bc2a`
- name: `?GetIconAsBitmap@CModernShareCommand@@UEAAJPEAUIShellItemArray@@UtagSIZE@@PEAPEAUHBITMAP__@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(CModernShareCommand *__hidden this, struct IShellItemArray *, struct tagSIZE, HBITMAP *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044290`
- `0x1800442f0`

## callees

- `0x18001478c`
- `0x18001b9b0`
- `0x18001bc30`
- `0x18001d9d0`
- `0x1800214cc`
- `0x180023408`
- `0x1800254e0`
- `0x180026394`

## import_xrefs

- `UxTheme!__imp_GetUserColorPreference` at `0x18001bb5c`
- `UxTheme!__imp_GetUserColorPreference` at `0x18001bb5c`
- `UxTheme!__imp_GetColorFromPreference` at `0x18001bb72`
- `UxTheme!__imp_GetColorFromPreference` at `0x18001bb72`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x18001bb0b`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x18001bb0b`
- `UxTheme!__imp_IsDarkModeAllowedForApp` at `0x18001bb01`
- `UxTheme!__imp_IsDarkModeAllowedForApp` at `0x18001bb01`
- `GDI32!DeleteObject` at `0x18001bbe7`
- `GDI32!DeleteObject` at `0x18001bbfb`
- `GDI32!DeleteObject` at `0x18001bbe7`
- `GDI32!DeleteObject` at `0x18001bbfb`
- `GDI32!CreateCompatibleDC` at `0x18001ba90`
- `GDI32!CreateCompatibleDC` at `0x18001ba90`
- `GDI32!SelectObject` at `0x18001bb8e`
- `GDI32!SelectObject` at `0x18001bbd3`
- `GDI32!SelectObject` at `0x18001bb8e`
- `GDI32!SelectObject` at `0x18001bbd3`
- `GDI32!DeleteDC` at `0x18001bbf1`
- `GDI32!DeleteDC` at `0x18001bbf1`
- `GDI32!CreateFontIndirectW` at `0x18001ba57`
- `GDI32!CreateFontIndirectW` at `0x18001ba57`
- `USER32!SystemParametersInfoW` at `0x18001bb33`
- `USER32!SystemParametersInfoW` at `0x18001bb33`

## string_xrefs

- `0x18001ba75`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18001baae`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CModernShareCommand::GetIconAsBitmap(
        CModernShareCommand *this,
        struct IShellItemArray *a2,
        struct tagSIZE a3,
        HBITMAP *a4)
{
  LONG cx; // edi
  LONG cy; // r13d
  __int64 v6; // rcx
  const wchar_t *v7; // r8
  __int64 v8; // rdx
  WCHAR *lfFaceName; // rax
  wchar_t v10; // r9
  WCHAR *v11; // rcx
  HFONT v12; // r12
  HDC CompatibleDC; // rax
  void **v15; // r8
  HDC v16; // rbx
  __int64 v17; // rdx
  unsigned int v18; // esi
  unsigned __int16 ColorFromPreference; // si
  HBITMAP v20; // r15
  HGDIOBJ v21; // r14
  HFONT v22; // r8
  HGDIOBJ v23; // rdi
  int v24; // [rsp+20h] [rbp-99h]
  const struct Geometry::CRect *v25; // [rsp+28h] [rbp-91h]
  _BYTE pvParam[12]; // [rsp+30h] [rbp-89h] BYREF
  LONG v27; // [rsp+3Ch] [rbp-7Dh]
  HGDIOBJ h; // [rsp+40h] [rbp-79h] BYREF
  HFONT v29; // [rsp+48h] [rbp-71h] BYREF
  HBITMAP *v30; // [rsp+50h] [rbp-69h]
  HDC v31; // [rsp+58h] [rbp-61h]
  HDC v32; // [rsp+60h] [rbp-59h]
  HGDIOBJ v33; // [rsp+68h] [rbp-51h]
  LOGFONTW lf; // [rsp+70h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v30 = a4;
  cx = a3.cx;
  cy = a3.cy;
  *a4 = 0;
  memset_0(&lf, 0, sizeof(lf));
  v6 = 2147483646;
  v7 = L"Segoe MDL2 Assets";
  v8 = 32;
  lfFaceName = lf.lfFaceName;
  do
  {
    if ( !v6 )
      break;
    v10 = *v7;
    if ( !*v7 )
      break;
    ++v7;
    *lfFaceName++ = v10;
    --v6;
    --v8;
  }
  while ( v8 );
  v11 = lfFaceName - 1;
  if ( v8 )
    v11 = lfFaceName;
  *v11 = 0;
  lf.lfHeight = -cy;
  lf.lfWeight = 400;
  v12 = CreateFontIndirectW(&lf);
  v29 = v12;
  if ( !v12 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA50,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)0x8007000ELL,
      v24);
    return 2147942414LL;
  }
  CompatibleDC = CreateCompatibleDC(0);
  v16 = CompatibleDC;
  v31 = CompatibleDC;
  if ( !CompatibleDC )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA53,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)0x8007000ELL,
      v24);
    CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(&v29);
    return 2147942414LL;
  }
  *(_DWORD *)pvParam = cx;
  *(_DWORD *)&pvParam[4] = -cy;
  h = 0;
  if ( (int)Create32BitHBITMAP(CompatibleDC, (const struct tagSIZE *)pvParam, v15, (HBITMAP *)&h) < 0 )
  {
    v23 = h;
  }
  else
  {
    LOBYTE(v17) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::GetImpl'::`2'::impl,
      v17,
      0);
    if ( !(unsigned __int8)IsDarkModeAllowedForApp()
      || !(unsigned __int8)ShouldAppsUseDarkMode()
      || (*(_DWORD *)pvParam = 16, *(_QWORD *)&pvParam[4] = 0, v27 = 0, SystemParametersInfoW(0x42u, 0x10u, pvParam, 0))
      && (pvParam[4] & 1) != 0 )
    {
      v18 = 218;
    }
    else
    {
      v18 = 219;
    }
    *(_QWORD *)pvParam = 0;
    GetUserColorPreference(pvParam, 0);
    ColorFromPreference = GetColorFromPreference(pvParam, v18, 0, 1);
    v32 = v16;
    v20 = (HBITMAP)h;
    v21 = SelectObject(v16, h);
    v33 = v21;
    *(_QWORD *)pvParam = 0;
    *(_DWORD *)&pvParam[8] = cx;
    v27 = cy;
    GDIHelpers::RenderTransparentCenteredGlyph(v16, (HDC)v12, v22, ColorFromPreference, (unsigned int)pvParam, v25);
    v23 = 0;
    *v30 = v20;
    SelectObject(v16, v21);
  }
  if ( v23 )
    DeleteObject(v23);
  DeleteDC(v16);
  DeleteObject(v12);
  return 0;
}

```

## disassembly

```asm
0x18001b9b0  mov     [rsp-8+arg_0], rbx
0x18001b9b5  push    rbp
0x18001b9b6  push    rsi
0x18001b9b7  push    rdi
0x18001b9b8  push    r12
0x18001b9ba  push    r13
0x18001b9bc  push    r14
0x18001b9be  push    r15
0x18001b9c0  lea     rbp, [rsp-27h]
0x18001b9c5  sub     rsp, 0E0h
0x18001b9cc  mov     rax, cs:__security_cookie
0x18001b9d3  xor     rax, rsp
0x18001b9d6  mov     [rbp+57h+var_40], rax
0x18001b9da  mov     [rbp+57h+var_C0], r9
0x18001b9de  mov     rdi, r8
0x18001b9e1  mov     r13, r8
0x18001b9e4  shr     r13, 20h
0x18001b9e8  xor     r14d, r14d
0x18001b9eb  mov     [r9], r14
0x18001b9ee  xor     edx, edx; Val
0x18001b9f0  lea     r8d, [r14+5Ch]; Size
0x18001b9f4  lea     rcx, [rbp+57h+lf]; void *
0x18001b9f8  call    memset_0
0x18001b9fd  mov     ecx, 7FFFFFFEh
0x18001ba02  lea     r8, aSegoeMdl2Asset; "Segoe MDL2 Assets"
0x18001ba09  lea     edx, [r14+20h]
0x18001ba0d  lea     rax, [rbp+57h+lf.lfFaceName]
0x18001ba11  test    rcx, rcx
0x18001ba14  jz      short loc_18001BA35
0x18001ba16  movzx   r9d, word ptr [r8]
0x18001ba1a  test    r9w, r9w
0x18001ba1e  jz      short loc_18001BA35
0x18001ba20  add     r8, 2
0x18001ba24  mov     [rax], r9w
0x18001ba28  add     rax, 2
0x18001ba2c  dec     rcx
0x18001ba2f  sub     rdx, 1
0x18001ba33  jnz     short loc_18001BA11
0x18001ba35  lea     rcx, [rax-2]
0x18001ba39  test    rdx, rdx
0x18001ba3c  cmovnz  rcx, rax
0x18001ba40  mov     [rcx], r14w
0x18001ba44  mov     esi, r13d
0x18001ba47  neg     esi
0x18001ba49  mov     [rbp+57h+lf.lfHeight], esi
0x18001ba4c  mov     [rbp+57h+lf.lfWeight], 190h
0x18001ba53  lea     rcx, [rbp+57h+lf]; lplf
0x18001ba57  call    cs:__imp_CreateFontIndirectW
0x18001ba5d  mov     r12, rax
0x18001ba60  mov     [rbp+57h+var_C8], rax
0x18001ba64  test    rax, rax
0x18001ba67  jnz     short loc_18001BA8E
0x18001ba69  mov     rcx, [rbp+5Fh]; this
0x18001ba6d  mov     ebx, 8007000Eh
0x18001ba72  mov     r9d, ebx; char *
0x18001ba75  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18001ba7c  mov     edx, 0A50h; void *
0x18001ba81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba86  nop
0x18001ba87  mov     eax, ebx
0x18001ba89  jmp     loc_18001BC03
0x18001ba8e  xor     ecx, ecx; hdc
0x18001ba90  call    cs:__imp_CreateCompatibleDC
0x18001ba96  mov     rbx, rax
0x18001ba99  mov     [rbp+57h+var_B8], rax
0x18001ba9d  test    rax, rax
0x18001baa0  jnz     short loc_18001BACB
0x18001baa2  mov     rcx, [rbp+5Fh]; this
0x18001baa6  mov     ebx, 8007000Eh
0x18001baab  mov     r9d, ebx; char *
0x18001baae  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18001bab5  mov     edx, 0A53h; void *
0x18001baba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001babf  nop
0x18001bac0  lea     rcx, [rbp+57h+var_C8]
0x18001bac4  call    ??1?$CAutoHandle@PEAUHBITMAP__@@@@QEAA@XZ; CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(void)
0x18001bac9  jmp     short loc_18001BA87
0x18001bacb  mov     dword ptr [rsp+110h+pvParam], edi
0x18001bacf  mov     dword ptr [rsp+110h+pvParam+4], esi
0x18001bad3  mov     [rbp+57h+h], r14
0x18001bad7  lea     r9, [rbp+57h+h]; HBITMAP *
0x18001badb  lea     rdx, [rsp+110h+pvParam]; struct tagSIZE *
0x18001bae0  mov     rcx, rbx; hDC
0x18001bae3  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x18001bae8  test    eax, eax
0x18001baea  js      loc_18001BBDB
0x18001baf0  xor     r8d, r8d
0x18001baf3  mov     dl, 1
0x18001baf5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FileExplorerDarkTheme@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FileExplorerDarkTheme@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerDarkTheme> `wil::Feature<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::GetImpl(void)'::`2'::impl
0x18001bafc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_FileExplorerDarkTheme@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001bb01  call    cs:__imp_IsDarkModeAllowedForApp
0x18001bb07  test    al, al
0x18001bb09  jz      short loc_18001BB4B
0x18001bb0b  call    cs:__imp_ShouldAppsUseDarkMode
0x18001bb11  test    al, al
0x18001bb13  jz      short loc_18001BB4B
0x18001bb15  mov     edx, 10h; uiParam
0x18001bb1a  mov     dword ptr [rsp+110h+pvParam], edx
0x18001bb1e  xor     eax, eax
0x18001bb20  mov     [rsp+110h+pvParam+4], rax
0x18001bb25  mov     [rbp+57h+var_D4], eax
0x18001bb28  xor     r9d, r9d; fWinIni
0x18001bb2b  lea     r8, [rsp+110h+pvParam]; pvParam
0x18001bb30  lea     ecx, [rdx+32h]; uiAction
0x18001bb33  call    cs:__imp_SystemParametersInfoW
0x18001bb39  test    eax, eax
0x18001bb3b  jz      short loc_18001BB44
0x18001bb3d  test    byte ptr [rsp+110h+pvParam+4], 1
0x18001bb42  jnz     short loc_18001BB4B
0x18001bb44  mov     esi, 0DBh
0x18001bb49  jmp     short loc_18001BB50
0x18001bb4b  mov     esi, 0DAh
0x18001bb50  mov     [rsp+110h+pvParam], r14
0x18001bb55  xor     edx, edx
0x18001bb57  lea     rcx, [rsp+110h+pvParam]
0x18001bb5c  call    cs:__imp_GetUserColorPreference
0x18001bb62  mov     r9d, 1
0x18001bb68  xor     r8d, r8d
0x18001bb6b  mov     edx, esi
0x18001bb6d  lea     rcx, [rsp+110h+pvParam]
0x18001bb72  call    cs:__imp_GetColorFromPreference
0x18001bb78  mov     esi, eax
0x18001bb7a  and     esi, 0FFFFFFh
0x18001bb80  mov     [rbp+57h+var_B0], rbx
0x18001bb84  mov     r15, [rbp+57h+h]
0x18001bb88  mov     rdx, r15; h
0x18001bb8b  mov     rcx, rbx; hdc
0x18001bb8e  call    cs:__imp_SelectObject
0x18001bb94  mov     r14, rax
0x18001bb97  mov     [rbp+57h+var_A8], rax
0x18001bb9b  mov     [rsp+110h+pvParam], 0
0x18001bba4  mov     [rsp+110h+var_D8], edi
0x18001bba8  mov     [rbp+57h+var_D4], r13d
0x18001bbac  lea     rax, [rsp+110h+pvParam]
0x18001bbb1  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int
0x18001bbb6  mov     r9d, esi; unsigned __int16
0x18001bbb9  mov     rdx, r12; HDC
0x18001bbbc  mov     rcx, rbx; hdc
0x18001bbbf  call    ?RenderTransparentCenteredGlyph@GDIHelpers@@YAXPEAUHDC__@@PEAUHFONT__@@GKAEBUCRect@Geometry@@@Z; GDIHelpers::RenderTransparentCenteredGlyph(HDC__ *,HFONT__ *,ushort,ulong,Geometry::CRect const &)
0x18001bbc4  xor     edi, edi
0x18001bbc6  mov     rax, [rbp+57h+var_C0]
0x18001bbca  mov     [rax], r15
0x18001bbcd  mov     rdx, r14; h
0x18001bbd0  mov     rcx, rbx; hdc
0x18001bbd3  call    cs:__imp_SelectObject
0x18001bbd9  jmp     short loc_18001BBDF
0x18001bbdb  mov     rdi, [rbp+57h+h]
0x18001bbdf  test    rdi, rdi
0x18001bbe2  jz      short loc_18001BBEE
0x18001bbe4  mov     rcx, rdi; ho
0x18001bbe7  call    cs:__imp_DeleteObject
0x18001bbed  nop
0x18001bbee  mov     rcx, rbx; hdc
0x18001bbf1  call    cs:__imp_DeleteDC
0x18001bbf7  nop
0x18001bbf8  mov     rcx, r12; ho
0x18001bbfb  call    cs:__imp_DeleteObject
0x18001bc01  xor     eax, eax
0x18001bc03  mov     rcx, [rbp+57h+var_40]
0x18001bc07  xor     rcx, rsp; StackCookie
0x18001bc0a  call    __security_check_cookie
0x18001bc0f  mov     rbx, [rsp+110h+arg_0]
0x18001bc17  add     rsp, 0E0h
0x18001bc1e  pop     r15
0x18001bc20  pop     r14
0x18001bc22  pop     r13
0x18001bc24  pop     r12
0x18001bc26  pop     rdi
0x18001bc27  pop     rsi
0x18001bc28  pop     rbp
0x18001bc29  retn
```
