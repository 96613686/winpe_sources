# CResourceCache::InitDefaultUIFont(HDC__ *,HFONT__ * *)

- ea: `0x180048fe8`
- end: `0x18004930e`
- name: `?InitDefaultUIFont@CResourceCache@@AEAAXPEAUHDC__@@PEAPEAUHFONT__@@@Z`
- size: `806`
- prototype: `void(CResourceCache *__hidden this, HDC, HFONT *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800053b4`
- `0x1800128a8`
- `0x1800325e0`

## callees

- `0x180048fe8`
- `0x180067798`
- `0x18006c3dc`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `msvcrt!iswdigit` at `0x1800491be`
- `msvcrt!iswdigit` at `0x1800491be`
- `msvcrt!_wtoi` at `0x180049182`
- `msvcrt!_wtoi` at `0x1800491cb`
- `msvcrt!_wtoi` at `0x180049182`
- `msvcrt!_wtoi` at `0x1800491cb`
- `KERNEL32!GetVersionExA` at `0x180049082`
- `KERNEL32!GetVersionExA` at `0x180049082`
- `KERNEL32!MulDiv` at `0x180049194`
- `KERNEL32!MulDiv` at `0x180049194`
- `USER32!SystemParametersInfoA` at `0x18004926f`
- `USER32!SystemParametersInfoA` at `0x18004926f`
- `USER32!ReleaseDC` at `0x18004914b`
- `USER32!ReleaseDC` at `0x18004914b`
- `USER32!GetDC` at `0x1800490e0`
- `USER32!GetDC` at `0x1800490e0`
- `GDI32!GetDeviceCaps` at `0x18004913d`
- `GDI32!GetDeviceCaps` at `0x18004913d`
- `GDI32!GetTextMetricsA` at `0x180049120`
- `GDI32!GetTextMetricsA` at `0x180049120`
- `GDI32!CreateFontW` at `0x180049252`
- `GDI32!CreateFontW` at `0x1800492bd`
- `GDI32!CreateFontW` at `0x180049252`
- `GDI32!CreateFontW` at `0x1800492bd`
- `SHLWAPI!StrChrW` at `0x180049159`
- `SHLWAPI!StrChrW` at `0x1800491a4`
- `SHLWAPI!StrChrW` at `0x180049159`
- `SHLWAPI!StrChrW` at `0x1800491a4`

## pseudocode

```c
void __fastcall CResourceCache::InitDefaultUIFont(CResourceCache *this, HDC a2, HFONT *a3)
{
  UINT v5; // ecx
  const unsigned __int16 *StringResourceW; // rax
  const WCHAR *pszFaceName; // rbx
  const unsigned __int16 *v8; // rax
  HDC DC; // rsi
  int v10; // edi
  unsigned __int16 tmCharSet; // r15
  HDC v12; // rcx
  int DeviceCaps; // r12d
  PWSTR v14; // rax
  const wchar_t *NonSpaceW; // rsi
  int v16; // eax
  PWSTR v17; // rax
  const wchar_t *v18; // rsi
  int v19; // edi
  HFONT FontW; // rax
  HFONT v21; // rsi
  _DWORD pvParam[40]; // [rsp+70h] [rbp-90h] BYREF
  int cHeight; // [rsp+110h] [rbp+10h]
  tagTEXTMETRICA tm; // [rsp+1D0h] [rbp+D0h] BYREF
  struct _OSVERSIONINFOA VersionInformation; // [rsp+210h] [rbp+110h] BYREF
  _OWORD v26[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t v27; // [rsp+2D0h] [rbp+1D0h]

  v27 = aMsShellDlg80[16];
  v26[0] = *(_OWORD *)L"MS Shell Dlg,8,0";
  v26[1] = *(_OWORD *)L" Dlg,8,0";
  if ( a3 || !qword_18008C238 )
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x90u);
    VersionInformation.dwOSVersionInfoSize = 148;
    GetVersionExA(&VersionInformation);
    if ( VersionInformation.dwMajorVersion == 5
      || (v5 = 1027, VersionInformation.dwPlatformId == 1) && VersionInformation.dwMinorVersion == 10 )
    {
      v5 = 1023;
    }
    StringResourceW = GetStringResourceW(v5);
    pszFaceName = StringResourceW;
    if ( !StringResourceW || !*StringResourceW )
    {
      v8 = GetStringResourceW(0x403u);
      pszFaceName = v8;
      if ( !v8 || !*v8 )
        pszFaceName = (const WCHAR *)v26;
    }
    DC = GetDC(0);
    if ( DC )
    {
      memset(&tm, 0, sizeof(tm));
      v10 = 0;
      GetTextMetricsA(DC, &tm);
      tmCharSet = tm.tmCharSet;
      v12 = DC;
      if ( a2 )
        v12 = a2;
      DeviceCaps = GetDeviceCaps(v12, 90);
      ReleaseDC(0, DC);
      v14 = StrChrW(pszFaceName, 0x2Cu);
      NonSpaceW = v14;
      if ( v14 )
      {
        *v14 = 0;
        NonSpaceW = (const wchar_t *)FirstNonSpaceW(v14 + 1);
        if ( (unsigned __int8)(*(_BYTE *)NonSpaceW - 48) <= 9u )
        {
          v16 = _wtoi(NonSpaceW);
          v10 = MulDiv(DeviceCaps, 2 * v16, 144);
        }
      }
      v17 = StrChrW(NonSpaceW, 0x2Cu);
      if ( v17 )
      {
        v18 = (const wchar_t *)FirstNonSpaceW(v17 + 1);
        if ( iswdigit(*v18) )
          tmCharSet = (char)_wtoi(v18);
      }
      if ( !v10 )
        v10 = DeviceCaps / 6;
      if ( g_langSystem == 25 )
        tmCharSet = 204;
      memset_0(pvParam, 0, 0x158u);
      v19 = -v10;
      FontW = CreateFontW(v19, 0, 0, 0, 0, 0, 0, 0, tmCharSet, 0, 0, 0, 0x32u, pszFaceName);
      pvParam[0] = 344;
      v21 = FontW;
      if ( SystemParametersInfoA(0x29u, 0x158u, pvParam, 0) && cHeight < v19 )
        qword_18008C240 = (__int64)CreateFontW(cHeight, 0, 0, 0, 0, 0, 0, 0, tmCharSet, 0, 0, 0, 0x32u, pszFaceName);
      else
        qword_18008C240 = (__int64)v21;
      if ( a3 )
        *a3 = v21;
      else
        qword_18008C238 = (__int64)v21;
    }
  }
}

```

## disassembly

```asm
0x180048fe8  mov     [rsp-8+arg_0], rbx
0x180048fed  push    rbp
0x180048fee  push    rsi
0x180048fef  push    rdi
0x180048ff0  push    r12
0x180048ff2  push    r13
0x180048ff4  push    r14
0x180048ff6  push    r15
0x180048ff8  lea     rbp, [rsp-1E0h]
0x180049000  sub     rsp, 2E0h
0x180049007  mov     rax, cs:__security_cookie
0x18004900e  xor     rax, rsp
0x180049011  mov     [rbp+210h+var_38], rax
0x180049018  movups  xmm0, xmmword ptr cs:aMsShellDlg80; "MS Shell Dlg,8,0"
0x18004901f  movzx   eax, word ptr cs:aMsShellDlg80+20h; ""
0x180049026  xor     r13d, r13d
0x180049029  mov     [rbp+210h+var_40], ax
0x180049030  mov     r14, r8
0x180049033  mov     r12, rdx
0x180049036  movups  xmm1, xmmword ptr cs:aMsShellDlg80+10h; " Dlg,8,0"
0x18004903d  movups  [rbp+210h+var_60], xmm0
0x180049044  movups  [rbp+210h+var_50], xmm1
0x18004904b  test    r8, r8
0x18004904e  jnz     short loc_18004905D
0x180049050  cmp     cs:qword_18008C238, r13
0x180049057  jnz     loc_1800492E4
0x18004905d  xor     edx, edx; Val
0x18004905f  lea     rcx, [rbp+210h+VersionInformation.dwMajorVersion]; void *
0x180049066  mov     r8d, 90h; Size
0x18004906c  call    memset_0
0x180049071  lea     rcx, [rbp+210h+VersionInformation]; lpVersionInformation
0x180049078  mov     [rbp+210h+VersionInformation.dwOSVersionInfoSize], 94h
0x180049082  call    cs:__imp_GetVersionExA
0x180049088  cmp     [rbp+210h+VersionInformation.dwMajorVersion], 5
0x18004908f  mov     edi, 403h
0x180049094  jz      short loc_1800490AA
0x180049096  cmp     [rbp+210h+VersionInformation.dwPlatformId], 1
0x18004909d  mov     ecx, edi
0x18004909f  jnz     short loc_1800490AF
0x1800490a1  cmp     [rbp+210h+VersionInformation.dwMinorVersion], 0Ah
0x1800490a8  jnz     short loc_1800490AF
0x1800490aa  mov     ecx, 3FFh; uID
0x1800490af  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x1800490b4  mov     rbx, rax
0x1800490b7  test    rax, rax
0x1800490ba  jz      short loc_1800490C2
0x1800490bc  cmp     [rax], r13w
0x1800490c0  jnz     short loc_1800490DE
0x1800490c2  mov     ecx, edi; uID
0x1800490c4  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x1800490c9  mov     rbx, rax
0x1800490cc  test    rax, rax
0x1800490cf  jz      short loc_1800490D7
0x1800490d1  cmp     [rax], r13w
0x1800490d5  jnz     short loc_1800490DE
0x1800490d7  lea     rbx, [rbp+210h+var_60]
0x1800490de  xor     ecx, ecx; hWnd
0x1800490e0  call    cs:__imp_GetDC
0x1800490e6  mov     rsi, rax
0x1800490e9  test    rax, rax
0x1800490ec  jz      loc_1800492E4
0x1800490f2  xorps   xmm0, xmm0
0x1800490f5  lea     rdx, [rbp+210h+tm]; lptm
0x1800490fc  xor     eax, eax
0x1800490fe  mov     rcx, rsi; hdc
0x180049101  movups  xmmword ptr [rbp+210h+tm.tmHeight], xmm0
0x180049108  mov     qword ptr [rbp+210h+tm.tmItalic], rax
0x18004910f  mov     edi, r13d
0x180049112  movups  xmmword ptr [rbp+210h+tm.tmExternalLeading], xmm0
0x180049119  movups  xmmword ptr [rbp+210h+tm.tmOverhang], xmm0
0x180049120  call    cs:__imp_GetTextMetricsA
0x180049126  movzx   r15d, [rbp+210h+tm.tmCharSet]
0x18004912e  test    r12, r12
0x180049131  mov     rcx, rsi
0x180049134  mov     edx, 5Ah ; 'Z'; index
0x180049139  cmovnz  rcx, r12; hdc
0x18004913d  call    cs:__imp_GetDeviceCaps
0x180049143  mov     rdx, rsi; hDC
0x180049146  xor     ecx, ecx; hWnd
0x180049148  mov     r12d, eax
0x18004914b  call    cs:__imp_ReleaseDC
0x180049151  mov     edx, 2Ch ; ','; wMatch
0x180049156  mov     rcx, rbx; pszStart
0x180049159  call    cs:__imp_StrChrW
0x18004915f  mov     rsi, rax
0x180049162  test    rax, rax
0x180049165  jz      short loc_18004919C
0x180049167  lea     rcx, [rax+2]
0x18004916b  mov     [rax], r13w
0x18004916f  call    FirstNonSpaceW
0x180049174  mov     rsi, rax
0x180049177  mov     al, [rax]
0x180049179  sub     al, 30h ; '0'
0x18004917b  cmp     al, 9
0x18004917d  ja      short loc_18004919C
0x18004917f  mov     rcx, rsi; String
0x180049182  call    cs:__imp__wtoi
0x180049188  mov     r8d, 90h; nDenominator
0x18004918e  mov     ecx, r12d; nNumber
0x180049191  lea     edx, [rax+rax]; nNumerator
0x180049194  call    cs:__imp_MulDiv
0x18004919a  mov     edi, eax
0x18004919c  mov     edx, 2Ch ; ','; wMatch
0x1800491a1  mov     rcx, rsi; pszStart
0x1800491a4  call    cs:__imp_StrChrW
0x1800491aa  test    rax, rax
0x1800491ad  jz      short loc_1800491D5
0x1800491af  lea     rcx, [rax+2]
0x1800491b3  call    FirstNonSpaceW
0x1800491b8  mov     rsi, rax
0x1800491bb  movzx   ecx, word ptr [rax]; C
0x1800491be  call    cs:__imp_iswdigit
0x1800491c4  test    eax, eax
0x1800491c6  jz      short loc_1800491D5
0x1800491c8  mov     rcx, rsi; String
0x1800491cb  call    cs:__imp__wtoi
0x1800491d1  movsx   r15d, al
0x1800491d5  test    edi, edi
0x1800491d7  jnz     short loc_1800491E8
0x1800491d9  mov     eax, 2AAAAAABh
0x1800491de  imul    r12d
0x1800491e1  mov     edi, edx
0x1800491e3  shr     edi, 1Fh
0x1800491e6  add     edi, edx
0x1800491e8  cmp     cs:?g_langSystem@@3GA, 19h; ushort g_langSystem
0x1800491f0  jnz     short loc_1800491F8
0x1800491f2  mov     r15d, 0CCh
0x1800491f8  mov     r12d, 158h
0x1800491fe  lea     rcx, [rsp+310h+pvParam]; void *
0x180049203  mov     r8d, r12d; Size
0x180049206  xor     edx, edx; Val
0x180049208  call    memset_0
0x18004920d  mov     [rsp+310h+pszFaceName], rbx; pszFaceName
0x180049212  neg     edi
0x180049214  mov     [rsp+310h+iPitchAndFamily], 32h ; '2'; iPitchAndFamily
0x18004921c  xor     r9d, r9d; cOrientation
0x18004921f  mov     [rsp+310h+iQuality], r13d; iQuality
0x180049224  xor     r8d, r8d; cEscapement
0x180049227  mov     [rsp+310h+iClipPrecision], r13d; iClipPrecision
0x18004922c  xor     edx, edx; cWidth
0x18004922e  mov     [rsp+310h+iOutPrecision], r13d; iOutPrecision
0x180049233  mov     ecx, edi; cHeight
0x180049235  movzx   r15d, r15w
0x180049239  mov     [rsp+310h+iCharSet], r15d; iCharSet
0x18004923e  mov     [rsp+310h+bStrikeOut], r13d; bStrikeOut
0x180049243  mov     [rsp+310h+bUnderline], r13d; bUnderline
0x180049248  mov     [rsp+310h+bItalic], r13d; bItalic
0x18004924d  mov     [rsp+310h+cWeight], r13d; cWeight
0x180049252  call    cs:__imp_CreateFontW
0x180049258  xor     r9d, r9d; fWinIni
0x18004925b  mov     [rsp+310h+pvParam], r12d
0x180049260  lea     r8, [rsp+310h+pvParam]; pvParam
0x180049265  mov     edx, r12d; uiParam
0x180049268  mov     rsi, rax
0x18004926b  lea     ecx, [r9+29h]; uiAction
0x18004926f  call    cs:__imp_SystemParametersInfoA
0x180049275  test    eax, eax
0x180049277  jz      short loc_1800492CC
0x180049279  mov     ecx, [rbp+210h+cHeight]; cHeight
0x18004927c  cmp     ecx, edi
0x18004927e  jge     short loc_1800492CC
0x180049280  mov     [rsp+310h+pszFaceName], rbx; pszFaceName
0x180049285  xor     r9d, r9d; cOrientation
0x180049288  mov     [rsp+310h+iPitchAndFamily], 32h ; '2'; iPitchAndFamily
0x180049290  xor     r8d, r8d; cEscapement
0x180049293  mov     [rsp+310h+iQuality], r13d; iQuality
0x180049298  xor     edx, edx; cWidth
0x18004929a  mov     [rsp+310h+iClipPrecision], r13d; iClipPrecision
0x18004929f  mov     [rsp+310h+iOutPrecision], r13d; iOutPrecision
0x1800492a4  mov     [rsp+310h+iCharSet], r15d; iCharSet
0x1800492a9  mov     [rsp+310h+bStrikeOut], r13d; bStrikeOut
0x1800492ae  mov     [rsp+310h+bUnderline], r13d; bUnderline
0x1800492b3  mov     [rsp+310h+bItalic], r13d; bItalic
0x1800492b8  mov     [rsp+310h+cWeight], r13d; cWeight
0x1800492bd  call    cs:__imp_CreateFontW
0x1800492c3  mov     cs:qword_18008C240, rax
0x1800492ca  jmp     short loc_1800492D3
0x1800492cc  mov     cs:qword_18008C240, rsi
0x1800492d3  test    r14, r14
0x1800492d6  jz      short loc_1800492DD
0x1800492d8  mov     [r14], rsi
0x1800492db  jmp     short loc_1800492E4
0x1800492dd  mov     cs:qword_18008C238, rsi
0x1800492e4  mov     rcx, [rbp+210h+var_38]
0x1800492eb  xor     rcx, rsp; StackCookie
0x1800492ee  call    __security_check_cookie
0x1800492f3  mov     rbx, [rsp+310h+arg_0]
0x1800492fb  add     rsp, 2E0h
0x180049302  pop     r15
0x180049304  pop     r14
0x180049306  pop     r13
0x180049308  pop     r12
0x18004930a  pop     rdi
0x18004930b  pop     rsi
0x18004930c  pop     rbp
0x18004930d  retn
```
