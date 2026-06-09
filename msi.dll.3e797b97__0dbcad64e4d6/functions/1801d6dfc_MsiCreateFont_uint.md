# MsiCreateFont(uint)

- ea: `0x1801d6dfc`
- end: `0x1801d7305`
- name: `?MsiCreateFont@@YAPEAUHFONT__@@I@Z`
- size: `1289`
- prototype: `HFONT __fastcall(unsigned __int16 *)`
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800d052c`
- `0x18011f208`
- `0x1801cc1c0`
- `0x1801d6874`
- `0x18022eb70`
- `0x18022efd0`

## callees

- `0x18000c4bc`
- `0x1801d6dfc`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801d70d7`
- `KERNEL32!GetLastError` at `0x1801d70d7`
- `KERNEL32!GetACP` at `0x1801d6e33`
- `KERNEL32!GetACP` at `0x1801d6e33`
- `USER32!ReleaseDC` at `0x1801d6ff7`
- `USER32!ReleaseDC` at `0x1801d7278`
- `USER32!ReleaseDC` at `0x1801d6ff7`
- `USER32!ReleaseDC` at `0x1801d7278`
- `USER32!GetDC` at `0x1801d6fc8`
- `USER32!GetDC` at `0x1801d7093`
- `USER32!GetDC` at `0x1801d6fc8`
- `USER32!GetDC` at `0x1801d7093`
- `GDI32!EnumFontFamiliesExW` at `0x1801d723f`
- `GDI32!EnumFontFamiliesExW` at `0x1801d723f`
- `GDI32!CreateFontW` at `0x1801d7079`
- `GDI32!CreateFontW` at `0x1801d7079`
- `GDI32!DeleteObject` at `0x1801d725d`
- `GDI32!DeleteObject` at `0x1801d725d`
- `GDI32!GetTextMetricsW` at `0x1801d70bf`
- `GDI32!GetTextMetricsW` at `0x1801d70bf`
- `GDI32!GetTextFaceW` at `0x1801d7133`
- `GDI32!GetTextFaceW` at `0x1801d7133`
- `GDI32!GetDeviceCaps` at `0x1801d6fe4`
- `GDI32!GetDeviceCaps` at `0x1801d6fe4`
- `GDI32!SelectObject` at `0x1801d70a8`
- `GDI32!SelectObject` at `0x1801d7145`
- `GDI32!SelectObject` at `0x1801d70a8`
- `GDI32!SelectObject` at `0x1801d7145`

## string_xrefs

- `0x1801d72ae`: `CreateFont failed, codepage: %i  CharSet: %i`
- `0x1801d716d`: `Font created.  Charset: Req=%i, Ret=%i, Font: Req=%s, Ret=%s\n`

## pseudocode

```c
HFONT __fastcall MsiCreateFont(unsigned __int16 *a1)
{
  UINT ACP; // edx
  const unsigned __int16 *v2; // r14
  int v3; // r15d
  WCHAR *pszFaceName; // rdi
  DWORD iCharSet; // ebx
  const wchar_t *v6; // rax
  bool v7; // zf
  HDC DC; // rax
  HDC v9; // r12
  int DeviceCaps; // esi
  int v11; // r12d
  HFONT FontW; // rsi
  HDC v13; // r15
  HGDIOBJ v14; // r13
  DWORD LastError; // eax
  char v17; // [rsp+70h] [rbp-90h]
  struct tagTEXTMETRICW tm; // [rsp+78h] [rbp-88h] BYREF
  struct tagLOGFONTW Logfont; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[32]; // [rsp+120h] [rbp+20h] BYREF

  ACP = g_iACP;
  v2 = (const unsigned __int16 *)(unsigned int)a1;
  if ( !g_iACP )
  {
    ACP = GetACP();
    g_iACP = ACP;
  }
  v17 = 0;
  v3 = 8;
  pszFaceName = L"MS Shell Dlg";
  if ( (_DWORD)v2 != ACP )
    pszFaceName = (WCHAR *)&Default;
  iCharSet = 1;
  if ( (unsigned int)v2 > 0x4E5 )
  {
    switch ( (_DWORD)v2 )
    {
      case 0x4E6:
        iCharSet = 162;
        break;
      case 0x4E7:
        iCharSet = 177;
        break;
      case 0x4E8:
        iCharSet = 178;
        break;
      case 0x4E9:
        iCharSet = 186;
        break;
      case 0x4EA:
        iCharSet = 163;
        break;
      default:
        if ( (unsigned int)((_DWORD)v2 - 65000) <= 1 )
          v17 = 1;
        break;
    }
    goto LABEL_38;
  }
  if ( (_DWORD)v2 == 1253 )
  {
    iCharSet = 161;
  }
  else
  {
    if ( (_DWORD)v2 != 874 )
    {
      if ( (_DWORD)v2 == 932 )
      {
        iCharSet = 128;
        pszFaceName = (WCHAR *)qword_1802BF868;
        v6 = L"MS PGothic";
        v7 = ACP == 932;
      }
      else if ( (_DWORD)v2 == 936 )
      {
        iCharSet = 134;
        pszFaceName = (WCHAR *)&dword_1802BF85C;
        v6 = L"SimSun";
        v7 = ACP == 936;
      }
      else if ( (_DWORD)v2 == 949 )
      {
        iCharSet = 129;
        pszFaceName = (WCHAR *)&dword_1802BF854;
        v6 = L"Gulim";
        v7 = ACP == 949;
      }
      else
      {
        if ( (_DWORD)v2 != 950 )
        {
          if ( (_DWORD)v2 == 1250 )
          {
            iCharSet = 238;
          }
          else if ( (_DWORD)v2 == 1251 )
          {
            iCharSet = 204;
          }
          else
          {
            iCharSet = (_DWORD)v2 != 1252;
          }
          goto LABEL_38;
        }
        iCharSet = 136;
        pszFaceName = (WCHAR *)&qword_1802BF848;
        v6 = L"PMingLiU";
        v7 = ACP == 950;
      }
      if ( !v7 )
        pszFaceName = (WCHAR *)v6;
      v3 = 9;
      goto LABEL_38;
    }
    iCharSet = 222;
  }
LABEL_38:
  memset(&tm, 0, sizeof(tm));
  memset_0(&Logfont, 0, sizeof(Logfont));
  DC = GetDC(0);
  v9 = DC;
  if ( !DC || (DeviceCaps = GetDeviceCaps(DC, 90), ReleaseDC(0, v9), DeviceCaps <= 96) )
    DeviceCaps = 96;
  v11 = (v3 * DeviceCaps + 36) / -72;
  while ( 1 )
  {
    FontW = CreateFontW(v11, 0, 0, 0, 400, 0, 0, 0, iCharSet, 0, 0x40u, 0, *pszFaceName == 0 ? 0x20 : 0, pszFaceName);
    if ( !FontW )
      break;
    v13 = GetDC(0);
    v14 = SelectObject(v13, FontW);
    if ( !GetTextMetricsW(v13, &tm) && g_dmDiagnosticMode )
    {
      LastError = GetLastError();
      DebugString(
        9,
        0,
        0,
        L"GetTextMetrics failed: GetLastError = %i",
        (const unsigned __int16 *)LastError,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    GetTextFaceW(v13, 32, Name);
    SelectObject(v13, v14);
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"Font created.  Charset: Req=%i, Ret=%i, Font: Req=%s, Ret=%s\n",
        (const unsigned __int16 *)iCharSet,
        (const unsigned __int16 *)tm.tmCharSet,
        pszFaceName,
        Name,
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    if ( tm.tmCharSet == iCharSet || v17 )
    {
      Logfont.lfFaceName[0] = 0;
    }
    else
    {
      if ( Logfont.lfFaceName[0] )
      {
        Logfont.lfFaceName[0] = 0;
LABEL_52:
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Font enumeration failed to select charset, codepage: %i  CharSet: %i\n",
            v2,
            (const unsigned __int16 *)iCharSet,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_57;
      }
      Logfont.lfCharSet = iCharSet;
      Logfont.lfPitchAndFamily = 0;
      EnumFontFamiliesExW(v13, &Logfont, EnumFontProc, (LPARAM)&Logfont, 0);
      pszFaceName = Logfont.lfFaceName;
      if ( !Logfont.lfFaceName[0] )
        goto LABEL_52;
      DeleteObject(FontW);
      FontW = 0;
    }
LABEL_57:
    ReleaseDC(0, v13);
    if ( !Logfont.lfFaceName[0] )
      return FontW;
  }
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"CreateFont failed, codepage: %i  CharSet: %i",
      v2,
      (const unsigned __int16 *)iCharSet,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  return 0;
}

```

## disassembly

```asm
0x1801d6dfc  push    rbp
0x1801d6dfe  push    rbx
0x1801d6dff  push    rsi
0x1801d6e00  push    rdi
0x1801d6e01  push    r12
0x1801d6e03  push    r13
0x1801d6e05  push    r14
0x1801d6e07  push    r15
0x1801d6e09  lea     rbp, [rsp-78h]
0x1801d6e0e  sub     rsp, 178h
0x1801d6e15  mov     rax, cs:__security_cookie
0x1801d6e1c  xor     rax, rsp
0x1801d6e1f  mov     [rbp+0B0h+var_50], rax
0x1801d6e23  mov     edx, cs:?g_iACP@@3HA; int g_iACP
0x1801d6e29  xor     r13d, r13d
0x1801d6e2c  mov     r14d, ecx
0x1801d6e2f  test    edx, edx
0x1801d6e31  jnz     short loc_1801D6E47
0x1801d6e33  call    cs:__imp_GetACP
0x1801d6e3a  nop     dword ptr [rax+rax+00h]
0x1801d6e3f  mov     edx, eax
0x1801d6e41  mov     cs:?g_iACP@@3HA, eax; int g_iACP
0x1801d6e47  cmp     r14d, edx
0x1801d6e4a  mov     [rsp+1B0h+var_140], r13b
0x1801d6e4f  lea     rax, Default
0x1801d6e56  mov     r15d, 8
0x1801d6e5c  lea     rdi, aMsShellDlg; "MS Shell Dlg"
0x1801d6e63  cmovnz  rdi, rax
0x1801d6e67  mov     eax, 4E5h
0x1801d6e6c  lea     ecx, [r15+1]
0x1801d6e70  lea     ebx, [rcx-8]
0x1801d6e73  cmp     r14d, eax
0x1801d6e76  ja      loc_1801D6F57
0x1801d6e7c  jz      loc_1801D6F50
0x1801d6e82  mov     eax, r14d
0x1801d6e85  sub     eax, 36Ah
0x1801d6e8a  jz      loc_1801D6F49
0x1801d6e90  sub     eax, 3Ah ; ':'
0x1801d6e93  jz      loc_1801D6F27
0x1801d6e99  sub     eax, 4
0x1801d6e9c  jz      short loc_1801D6F0C
0x1801d6e9e  sub     eax, 0Dh
0x1801d6ea1  jz      short loc_1801D6EF1
0x1801d6ea3  sub     eax, ebx
0x1801d6ea5  jz      short loc_1801D6ED6
0x1801d6ea7  sub     eax, 12Ch
0x1801d6eac  jz      short loc_1801D6ECC
0x1801d6eae  sub     eax, ebx
0x1801d6eb0  jz      short loc_1801D6EC2
0x1801d6eb2  cmp     eax, ebx
0x1801d6eb4  jnz     loc_1801D6FA3
0x1801d6eba  mov     ebx, r13d
0x1801d6ebd  jmp     loc_1801D6FA3
0x1801d6ec2  mov     ebx, 0CCh
0x1801d6ec7  jmp     loc_1801D6FA3
0x1801d6ecc  mov     ebx, 0EEh
0x1801d6ed1  jmp     loc_1801D6FA3
0x1801d6ed6  mov     ebx, 88h
0x1801d6edb  lea     rdi, qword_1802BF848
0x1801d6ee2  lea     rax, aPmingliu; "PMingLiU"
0x1801d6ee9  cmp     edx, 3B6h
0x1801d6eef  jmp     short loc_1801D6F40
0x1801d6ef1  mov     ebx, 81h
0x1801d6ef6  lea     rdi, dword_1802BF854
0x1801d6efd  lea     rax, aGulim; "Gulim"
0x1801d6f04  cmp     edx, 3B5h
0x1801d6f0a  jmp     short loc_1801D6F40
0x1801d6f0c  mov     ebx, 86h
0x1801d6f11  lea     rdi, dword_1802BF85C
0x1801d6f18  lea     rax, aSimsun; "SimSun"
0x1801d6f1f  cmp     edx, 3A8h
0x1801d6f25  jmp     short loc_1801D6F40
0x1801d6f27  mov     ebx, 80h
0x1801d6f2c  lea     rdi, qword_1802BF868
0x1801d6f33  lea     rax, aMsPgothic; "MS PGothic"
0x1801d6f3a  cmp     edx, 3A4h
0x1801d6f40  cmovnz  rdi, rax
0x1801d6f44  mov     r15d, ecx
0x1801d6f47  jmp     short loc_1801D6FA3
0x1801d6f49  mov     ebx, 0DEh
0x1801d6f4e  jmp     short loc_1801D6FA3
0x1801d6f50  mov     ebx, 0A1h
0x1801d6f55  jmp     short loc_1801D6FA3
0x1801d6f57  mov     eax, r14d
0x1801d6f5a  sub     eax, 4E6h
0x1801d6f5f  jz      short loc_1801D6F9E
0x1801d6f61  sub     eax, ebx
0x1801d6f63  jz      short loc_1801D6F97
0x1801d6f65  sub     eax, ebx
0x1801d6f67  jz      short loc_1801D6F90
0x1801d6f69  sub     eax, ebx
0x1801d6f6b  jz      short loc_1801D6F89
0x1801d6f6d  sub     eax, ebx
0x1801d6f6f  jz      short loc_1801D6F82
0x1801d6f71  sub     eax, 0F8FEh
0x1801d6f76  jz      short loc_1801D6F7C
0x1801d6f78  cmp     eax, ebx
0x1801d6f7a  jnz     short loc_1801D6FA3
0x1801d6f7c  mov     [rsp+1B0h+var_140], bl
0x1801d6f80  jmp     short loc_1801D6FA3
0x1801d6f82  mov     ebx, 0A3h
0x1801d6f87  jmp     short loc_1801D6FA3
0x1801d6f89  mov     ebx, 0BAh
0x1801d6f8e  jmp     short loc_1801D6FA3
0x1801d6f90  mov     ebx, 0B2h
0x1801d6f95  jmp     short loc_1801D6FA3
0x1801d6f97  mov     ebx, 0B1h
0x1801d6f9c  jmp     short loc_1801D6FA3
0x1801d6f9e  mov     ebx, 0A2h
0x1801d6fa3  xorps   xmm0, xmm0
0x1801d6fa6  lea     rcx, [rbp+0B0h+Logfont]; void *
0x1801d6faa  xor     edx, edx; Val
0x1801d6fac  movups  xmmword ptr [rbp+0B0h+tm.tmOverhang], xmm0
0x1801d6fb0  movups  xmmword ptr [rsp+1B0h+tm.tmHeight], xmm0
0x1801d6fb5  lea     r8d, [rdx+5Ch]; Size
0x1801d6fb9  movups  xmmword ptr [rbp+0B0h+tm.tmExternalLeading], xmm0
0x1801d6fbd  movups  xmmword ptr [rbp+0B0h+tm.tmFirstChar], xmm0
0x1801d6fc1  call    memset_0
0x1801d6fc6  xor     ecx, ecx; hWnd
0x1801d6fc8  call    cs:__imp_GetDC
0x1801d6fcf  nop     dword ptr [rax+rax+00h]
0x1801d6fd4  mov     r12, rax
0x1801d6fd7  test    rax, rax
0x1801d6fda  jz      short loc_1801D7008
0x1801d6fdc  mov     edx, 5Ah ; 'Z'; index
0x1801d6fe1  mov     rcx, rax; hdc
0x1801d6fe4  call    cs:__imp_GetDeviceCaps
0x1801d6feb  nop     dword ptr [rax+rax+00h]
0x1801d6ff0  mov     rdx, r12; hDC
0x1801d6ff3  xor     ecx, ecx; hWnd
0x1801d6ff5  mov     esi, eax
0x1801d6ff7  call    cs:__imp_ReleaseDC
0x1801d6ffe  nop     dword ptr [rax+rax+00h]
0x1801d7003  cmp     esi, 60h ; '`'
0x1801d7006  jg      short loc_1801D700D
0x1801d7008  mov     esi, 60h ; '`'
0x1801d700d  imul    esi, r15d
0x1801d7011  mov     eax, 0C71C71C7h
0x1801d7016  add     esi, 24h ; '$'
0x1801d7019  imul    esi
0x1801d701b  mov     r12d, edx
0x1801d701e  sar     r12d, 4
0x1801d7022  mov     eax, r12d
0x1801d7025  shr     eax, 1Fh
0x1801d7028  add     r12d, eax
0x1801d702b  movzx   eax, word ptr [rdi]
0x1801d702e  mov     [rsp+1B0h+pszFaceName], rdi; pszFaceName
0x1801d7033  neg     ax
0x1801d7036  sbb     ecx, ecx
0x1801d7038  xor     r9d, r9d; cOrientation
0x1801d703b  not     ecx
0x1801d703d  xor     r8d, r8d; cEscapement
0x1801d7040  and     ecx, 20h
0x1801d7043  xor     edx, edx; cWidth
0x1801d7045  mov     [rsp+1B0h+iPitchAndFamily], ecx; iPitchAndFamily
0x1801d7049  mov     ecx, r12d; cHeight
0x1801d704c  mov     [rsp+1B0h+iQuality], r13d; iQuality
0x1801d7051  mov     [rsp+1B0h+iClipPrecision], 40h ; '@'; iClipPrecision
0x1801d7059  mov     [rsp+1B0h+iOutPrecision], r13d; iOutPrecision
0x1801d705e  mov     [rsp+1B0h+iCharSet], ebx; iCharSet
0x1801d7062  mov     [rsp+1B0h+bStrikeOut], r13d; bStrikeOut
0x1801d7067  mov     [rsp+1B0h+bUnderline], r13d; bUnderline
0x1801d706c  mov     [rsp+1B0h+bItalic], r13d; bItalic
0x1801d7071  mov     [rsp+1B0h+cWeight], 190h; cWeight
0x1801d7079  call    cs:__imp_CreateFontW
0x1801d7080  nop     dword ptr [rax+rax+00h]
0x1801d7085  mov     rsi, rax
0x1801d7088  test    rax, rax
0x1801d708b  jz      loc_1801D7294
0x1801d7091  xor     ecx, ecx; hWnd
0x1801d7093  call    cs:__imp_GetDC
0x1801d709a  nop     dword ptr [rax+rax+00h]
0x1801d709f  mov     rcx, rax; hdc
0x1801d70a2  mov     rdx, rsi; h
0x1801d70a5  mov     r15, rax
0x1801d70a8  call    cs:__imp_SelectObject
0x1801d70af  nop     dword ptr [rax+rax+00h]
0x1801d70b4  lea     rdx, [rsp+1B0h+tm]; lptm
0x1801d70b9  mov     rcx, r15; hdc
0x1801d70bc  mov     r13, rax
0x1801d70bf  call    cs:__imp_GetTextMetricsW
0x1801d70c6  nop     dword ptr [rax+rax+00h]
0x1801d70cb  test    eax, eax
0x1801d70cd  jnz     short loc_1801D7127
0x1801d70cf  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x1801d70d5  jz      short loc_1801D7127
0x1801d70d7  call    cs:__imp_GetLastError
0x1801d70de  nop     dword ptr [rax+rax+00h]
0x1801d70e3  xor     edx, edx; unsigned __int16
0x1801d70e5  mov     ecx, eax
0x1801d70e7  mov     qword ptr [rsp+1B0h+iQuality], rdx; void *
0x1801d70ec  lea     r9, aGettextmetrics; "GetTextMetrics failed: GetLastError = %"...
0x1801d70f3  mov     [rsp+1B0h+iClipPrecision], edx; unsigned int
0x1801d70f7  lea     rax, aNull; "(NULL)"
0x1801d70fe  mov     qword ptr [rsp+1B0h+iOutPrecision], rax; unsigned __int16 *
0x1801d7103  xor     r8d, r8d; int
0x1801d7106  mov     qword ptr [rsp+1B0h+iCharSet], rax; unsigned __int16 *
0x1801d710b  mov     qword ptr [rsp+1B0h+bStrikeOut], rax; unsigned __int16 *
0x1801d7110  mov     qword ptr [rsp+1B0h+bUnderline], rax; unsigned __int16 *
0x1801d7115  mov     qword ptr [rsp+1B0h+bItalic], rax; unsigned __int16 *
0x1801d711a  mov     qword ptr [rsp+1B0h+cWeight], rcx; unsigned __int16 *
0x1801d711f  lea     ecx, [rdx+9]; int
0x1801d7122  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801d7127  lea     r8, [rbp+0B0h+Name]; lpName
0x1801d712b  mov     edx, 20h ; ' '; c
0x1801d7130  mov     rcx, r15; hdc
0x1801d7133  call    cs:__imp_GetTextFaceW
0x1801d713a  nop     dword ptr [rax+rax+00h]
0x1801d713f  mov     rdx, r13; h
0x1801d7142  mov     rcx, r15; hdc
0x1801d7145  call    cs:__imp_SelectObject
0x1801d714c  nop     dword ptr [rax+rax+00h]
0x1801d7151  xor     r13d, r13d
0x1801d7154  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801d715b  jz      short loc_1801D71AA
0x1801d715d  movzx   eax, [rbp+0B0h+tm.tmCharSet]
0x1801d7161  lea     r8, aNull; "(NULL)"
0x1801d7168  mov     qword ptr [rsp+1B0h+iQuality], r13; void *
0x1801d716d  lea     r9, aFontCreatedCha; "Font created.  Charset: Req=%i, Ret=%i,"...
0x1801d7174  mov     [rsp+1B0h+iClipPrecision], r13d; unsigned int
0x1801d7179  xor     edx, edx; unsigned __int16
0x1801d717b  mov     qword ptr [rsp+1B0h+iOutPrecision], r8; unsigned __int16 *
0x1801d7180  mov     qword ptr [rsp+1B0h+iCharSet], r8; unsigned __int16 *
0x1801d7185  lea     r8, [rbp+0B0h+Name]
0x1801d7189  mov     qword ptr [rsp+1B0h+bStrikeOut], r8; unsigned __int16 *
0x1801d718e  xor     r8d, r8d; int
0x1801d7191  mov     ecx, ebx
0x1801d7193  mov     qword ptr [rsp+1B0h+bUnderline], rdi; unsigned __int16 *
0x1801d7198  mov     qword ptr [rsp+1B0h+bItalic], rax; unsigned __int16 *
0x1801d719d  mov     qword ptr [rsp+1B0h+cWeight], rcx; unsigned __int16 *
0x1801d71a2  lea     ecx, [rdx+9]; int
0x1801d71a5  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801d71aa  movzx   eax, [rbp+0B0h+tm.tmCharSet]
0x1801d71ae  cmp     eax, ebx
0x1801d71b0  jz      loc_1801D726E
0x1801d71b6  cmp     [rsp+1B0h+var_140], r13b
0x1801d71bb  jnz     loc_1801D726E
0x1801d71c1  cmp     [rbp+0B0h+Logfont.lfFaceName], r13w
0x1801d71c6  jz      short loc_1801D7221
0x1801d71c8  mov     [rbp+0B0h+Logfont.lfFaceName], r13w
0x1801d71cd  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801d71d4  jz      loc_1801D7273
0x1801d71da  mov     qword ptr [rsp+1B0h+iQuality], r13; void *
0x1801d71df  lea     r8, aNull; "(NULL)"
0x1801d71e6  mov     [rsp+1B0h+iClipPrecision], r13d; unsigned int
0x1801d71eb  lea     r9, aFontEnumeratio; "Font enumeration failed to select chars"...
0x1801d71f2  mov     qword ptr [rsp+1B0h+iOutPrecision], r8; unsigned __int16 *
0x1801d71f7  xor     edx, edx; unsigned __int16
0x1801d71f9  mov     qword ptr [rsp+1B0h+iCharSet], r8; unsigned __int16 *
0x1801d71fe  mov     qword ptr [rsp+1B0h+bStrikeOut], r8; unsigned __int16 *
0x1801d7203  mov     qword ptr [rsp+1B0h+bUnderline], r8; unsigned __int16 *
0x1801d7208  xor     r8d, r8d; int
0x1801d720b  mov     eax, ebx
0x1801d720d  lea     ecx, [rdx+9]; int
0x1801d7210  mov     qword ptr [rsp+1B0h+bItalic], rax; unsigned __int16 *
0x1801d7215  mov     qword ptr [rsp+1B0h+cWeight], r14; unsigned __int16 *
0x1801d721a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801d721f  jmp     short loc_1801D7273
0x1801d7221  lea     r9, [rbp+0B0h+Logfont]; lParam
0x1801d7225  mov     [rbp+0B0h+Logfont.lfCharSet], bl
0x1801d7228  lea     r8, ?EnumFontProc@@YAHPEAUtagENUMLOGFONTEXW@@PEAUtagNEWTEXTMETRICEXW@@H_J@Z; lpProc
0x1801d722f  mov     [rbp+0B0h+Logfont.lfPitchAndFamily], r13b
0x1801d7233  lea     rdx, [rbp+0B0h+Logfont]; lpLogfont
0x1801d7237  mov     [rsp+1B0h+cWeight], r13d; dwFlags
0x1801d723c  mov     rcx, r15; hdc
0x1801d723f  call    cs:__imp_EnumFontFamiliesExW
0x1801d7246  nop     dword ptr [rax+rax+00h]
0x1801d724b  lea     rdi, [rbp+0B0h+Logfont.lfFaceName]
0x1801d724f  cmp     [rbp+0B0h+Logfont.lfFaceName], r13w
0x1801d7254  jz      loc_1801D71CD
0x1801d725a  mov     rcx, rsi; ho
0x1801d725d  call    cs:__imp_DeleteObject
0x1801d7264  nop     dword ptr [rax+rax+00h]
0x1801d7269  mov     rsi, r13
0x1801d726c  jmp     short loc_1801D7273
0x1801d726e  mov     [rbp+0B0h+Logfont.lfFaceName], r13w
0x1801d7273  mov     rdx, r15; hDC
0x1801d7276  xor     ecx, ecx; hWnd
0x1801d7278  call    cs:__imp_ReleaseDC
0x1801d727f  nop     dword ptr [rax+rax+00h]
0x1801d7284  cmp     [rbp+0B0h+Logfont.lfFaceName], r13w
0x1801d7289  jnz     loc_1801D702B
0x1801d728f  mov     rax, rsi
0x1801d7292  jmp     short loc_1801D72E4
0x1801d7294  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801d729b  jz      short loc_1801D72E2
0x1801d729d  mov     qword ptr [rsp+1B0h+iQuality], r13; void *
0x1801d72a2  lea     r15, aNull; "(NULL)"
0x1801d72a9  mov     [rsp+1B0h+iClipPrecision], r13d; unsigned int
0x1801d72ae  lea     r9, aCreatefontFail; "CreateFont failed, codepage: %i  CharSe"...
0x1801d72b5  mov     qword ptr [rsp+1B0h+iOutPrecision], r15; unsigned __int16 *
0x1801d72ba  xor     edx, edx; unsigned __int16
0x1801d72bc  mov     qword ptr [rsp+1B0h+iCharSet], r15; unsigned __int16 *
0x1801d72c1  xor     r8d, r8d; int
0x1801d72c4  mov     qword ptr [rsp+1B0h+bStrikeOut], r15; unsigned __int16 *
0x1801d72c9  mov     eax, ebx
0x1801d72cb  mov     qword ptr [rsp+1B0h+bUnderline], r15; unsigned __int16 *
0x1801d72d0  lea     ecx, [rdx+9]; int
0x1801d72d3  mov     qword ptr [rsp+1B0h+bItalic], rax; unsigned __int16 *
0x1801d72d8  mov     qword ptr [rsp+1B0h+cWeight], r14; unsigned __int16 *
  ... truncated ...
```
