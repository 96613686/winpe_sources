# MsiCreateFont(uint)

- ea: `0x1801ce220`
- end: `0x1801ce6d4`
- name: `?MsiCreateFont@@YAPEAUHFONT__@@I@Z`
- size: `1204`
- prototype: `HFONT __fastcall(unsigned __int16 *)`
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800c2884`
- `0x180118c24`
- `0x1801c3bd0`
- `0x1801cdcf4`
- `0x180224e20`
- `0x180225220`

## callees

- `0x180025a18`
- `0x1801ce220`
- `0x18025ab2a`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801ce4cb`
- `KERNEL32!GetLastError` at `0x1801ce4cb`
- `KERNEL32!GetACP` at `0x1801ce257`
- `KERNEL32!GetACP` at `0x1801ce257`
- `USER32!ReleaseDC` at `0x1801ce409`
- `USER32!ReleaseDC` at `0x1801ce64e`
- `USER32!ReleaseDC` at `0x1801ce409`
- `USER32!ReleaseDC` at `0x1801ce64e`
- `USER32!GetDC` at `0x1801ce3e6`
- `USER32!GetDC` at `0x1801ce499`
- `USER32!GetDC` at `0x1801ce3e6`
- `USER32!GetDC` at `0x1801ce499`
- `GDI32!EnumFontFamiliesExW` at `0x1801ce621`
- `GDI32!EnumFontFamiliesExW` at `0x1801ce621`
- `GDI32!CreateFontW` at `0x1801ce485`
- `GDI32!CreateFontW` at `0x1801ce485`
- `GDI32!DeleteObject` at `0x1801ce639`
- `GDI32!DeleteObject` at `0x1801ce639`
- `GDI32!GetTextMetricsW` at `0x1801ce4b9`
- `GDI32!GetTextMetricsW` at `0x1801ce4b9`
- `GDI32!GetTextFaceW` at `0x1801ce521`
- `GDI32!GetTextFaceW` at `0x1801ce521`
- `GDI32!GetDeviceCaps` at `0x1801ce3fc`
- `GDI32!GetDeviceCaps` at `0x1801ce3fc`
- `GDI32!SelectObject` at `0x1801ce4a8`
- `GDI32!SelectObject` at `0x1801ce52d`
- `GDI32!SelectObject` at `0x1801ce4a8`
- `GDI32!SelectObject` at `0x1801ce52d`

## string_xrefs

- `0x1801ce67e`: `CreateFont failed, codepage: %i  CharSet: %i`
- `0x1801ce54f`: `Font created.  Charset: Req=%i, Ret=%i, Font: Req=%s, Ret=%s\n`

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
        pszFaceName = (WCHAR *)&unk_1802B5960;
        v6 = L"MS PGothic";
        v7 = ACP == 932;
      }
      else if ( (_DWORD)v2 == 936 )
      {
        iCharSet = 134;
        pszFaceName = (WCHAR *)&unk_1802B594C;
        v6 = L"SimSun";
        v7 = ACP == 936;
      }
      else if ( (_DWORD)v2 == 949 )
      {
        iCharSet = 129;
        pszFaceName = (WCHAR *)&unk_1802B5944;
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
        pszFaceName = (WCHAR *)&unk_1802B5938;
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
0x1801ce220  push    rbp
0x1801ce222  push    rbx
0x1801ce223  push    rsi
0x1801ce224  push    rdi
0x1801ce225  push    r12
0x1801ce227  push    r13
0x1801ce229  push    r14
0x1801ce22b  push    r15
0x1801ce22d  lea     rbp, [rsp-78h]
0x1801ce232  sub     rsp, 178h
0x1801ce239  mov     rax, cs:__security_cookie
0x1801ce240  xor     rax, rsp
0x1801ce243  mov     [rbp+0B0h+var_50], rax
0x1801ce247  mov     edx, cs:?g_iACP@@3HA; int g_iACP
0x1801ce24d  xor     r13d, r13d
0x1801ce250  mov     r14d, ecx
0x1801ce253  test    edx, edx
0x1801ce255  jnz     short loc_1801CE265
0x1801ce257  call    cs:__imp_GetACP
0x1801ce25d  mov     edx, eax
0x1801ce25f  mov     cs:?g_iACP@@3HA, eax; int g_iACP
0x1801ce265  cmp     r14d, edx
0x1801ce268  mov     [rsp+1B0h+var_140], r13b
0x1801ce26d  lea     rax, Default
0x1801ce274  mov     r15d, 8
0x1801ce27a  lea     rdi, aMsShellDlg; "MS Shell Dlg"
0x1801ce281  cmovnz  rdi, rax
0x1801ce285  mov     eax, 4E5h
0x1801ce28a  lea     ecx, [r15+1]
0x1801ce28e  lea     ebx, [rcx-8]
0x1801ce291  cmp     r14d, eax
0x1801ce294  ja      loc_1801CE375
0x1801ce29a  jz      loc_1801CE36E
0x1801ce2a0  mov     eax, r14d
0x1801ce2a3  sub     eax, 36Ah
0x1801ce2a8  jz      loc_1801CE367
0x1801ce2ae  sub     eax, 3Ah ; ':'
0x1801ce2b1  jz      loc_1801CE345
0x1801ce2b7  sub     eax, 4
0x1801ce2ba  jz      short loc_1801CE32A
0x1801ce2bc  sub     eax, 0Dh
0x1801ce2bf  jz      short loc_1801CE30F
0x1801ce2c1  sub     eax, ebx
0x1801ce2c3  jz      short loc_1801CE2F4
0x1801ce2c5  sub     eax, 12Ch
0x1801ce2ca  jz      short loc_1801CE2EA
0x1801ce2cc  sub     eax, ebx
0x1801ce2ce  jz      short loc_1801CE2E0
0x1801ce2d0  cmp     eax, ebx
0x1801ce2d2  jnz     loc_1801CE3C1
0x1801ce2d8  mov     ebx, r13d
0x1801ce2db  jmp     loc_1801CE3C1
0x1801ce2e0  mov     ebx, 0CCh
0x1801ce2e5  jmp     loc_1801CE3C1
0x1801ce2ea  mov     ebx, 0EEh
0x1801ce2ef  jmp     loc_1801CE3C1
0x1801ce2f4  mov     ebx, 88h
0x1801ce2f9  lea     rdi, unk_1802B5938
0x1801ce300  lea     rax, aPmingliu; "PMingLiU"
0x1801ce307  cmp     edx, 3B6h
0x1801ce30d  jmp     short loc_1801CE35E
0x1801ce30f  mov     ebx, 81h
0x1801ce314  lea     rdi, unk_1802B5944
0x1801ce31b  lea     rax, aGulim; "Gulim"
0x1801ce322  cmp     edx, 3B5h
0x1801ce328  jmp     short loc_1801CE35E
0x1801ce32a  mov     ebx, 86h
0x1801ce32f  lea     rdi, unk_1802B594C
0x1801ce336  lea     rax, aSimsun; "SimSun"
0x1801ce33d  cmp     edx, 3A8h
0x1801ce343  jmp     short loc_1801CE35E
0x1801ce345  mov     ebx, 80h
0x1801ce34a  lea     rdi, unk_1802B5960
0x1801ce351  lea     rax, aMsPgothic; "MS PGothic"
0x1801ce358  cmp     edx, 3A4h
0x1801ce35e  cmovnz  rdi, rax
0x1801ce362  mov     r15d, ecx
0x1801ce365  jmp     short loc_1801CE3C1
0x1801ce367  mov     ebx, 0DEh
0x1801ce36c  jmp     short loc_1801CE3C1
0x1801ce36e  mov     ebx, 0A1h
0x1801ce373  jmp     short loc_1801CE3C1
0x1801ce375  mov     eax, r14d
0x1801ce378  sub     eax, 4E6h
0x1801ce37d  jz      short loc_1801CE3BC
0x1801ce37f  sub     eax, ebx
0x1801ce381  jz      short loc_1801CE3B5
0x1801ce383  sub     eax, ebx
0x1801ce385  jz      short loc_1801CE3AE
0x1801ce387  sub     eax, ebx
0x1801ce389  jz      short loc_1801CE3A7
0x1801ce38b  sub     eax, ebx
0x1801ce38d  jz      short loc_1801CE3A0
0x1801ce38f  sub     eax, 0F8FEh
0x1801ce394  jz      short loc_1801CE39A
0x1801ce396  cmp     eax, ebx
0x1801ce398  jnz     short loc_1801CE3C1
0x1801ce39a  mov     [rsp+1B0h+var_140], bl
0x1801ce39e  jmp     short loc_1801CE3C1
0x1801ce3a0  mov     ebx, 0A3h
0x1801ce3a5  jmp     short loc_1801CE3C1
0x1801ce3a7  mov     ebx, 0BAh
0x1801ce3ac  jmp     short loc_1801CE3C1
0x1801ce3ae  mov     ebx, 0B2h
0x1801ce3b3  jmp     short loc_1801CE3C1
0x1801ce3b5  mov     ebx, 0B1h
0x1801ce3ba  jmp     short loc_1801CE3C1
0x1801ce3bc  mov     ebx, 0A2h
0x1801ce3c1  xorps   xmm0, xmm0
0x1801ce3c4  lea     rcx, [rbp+0B0h+Logfont]; void *
0x1801ce3c8  xor     edx, edx; Val
0x1801ce3ca  movups  xmmword ptr [rbp+0B0h+tm.tmOverhang], xmm0
0x1801ce3ce  movups  xmmword ptr [rsp+1B0h+tm.tmHeight], xmm0
0x1801ce3d3  lea     r8d, [rdx+5Ch]; Size
0x1801ce3d7  movups  xmmword ptr [rbp+0B0h+tm.tmExternalLeading], xmm0
0x1801ce3db  movups  xmmword ptr [rbp+0B0h+tm.tmFirstChar], xmm0
0x1801ce3df  call    memset_0
0x1801ce3e4  xor     ecx, ecx; hWnd
0x1801ce3e6  call    cs:__imp_GetDC
0x1801ce3ec  mov     r12, rax
0x1801ce3ef  test    rax, rax
0x1801ce3f2  jz      short loc_1801CE414
0x1801ce3f4  mov     edx, 5Ah ; 'Z'; index
0x1801ce3f9  mov     rcx, rax; hdc
0x1801ce3fc  call    cs:__imp_GetDeviceCaps
0x1801ce402  mov     rdx, r12; hDC
0x1801ce405  xor     ecx, ecx; hWnd
0x1801ce407  mov     esi, eax
0x1801ce409  call    cs:__imp_ReleaseDC
0x1801ce40f  cmp     esi, 60h ; '`'
0x1801ce412  jg      short loc_1801CE419
0x1801ce414  mov     esi, 60h ; '`'
0x1801ce419  imul    esi, r15d
0x1801ce41d  mov     eax, 0C71C71C7h
0x1801ce422  add     esi, 24h ; '$'
0x1801ce425  imul    esi
0x1801ce427  mov     r12d, edx
0x1801ce42a  sar     r12d, 4
0x1801ce42e  mov     eax, r12d
0x1801ce431  shr     eax, 1Fh
0x1801ce434  add     r12d, eax
0x1801ce437  movzx   eax, word ptr [rdi]
0x1801ce43a  mov     [rsp+1B0h+pszFaceName], rdi; pszFaceName
0x1801ce43f  neg     ax
0x1801ce442  sbb     ecx, ecx
0x1801ce444  xor     r9d, r9d; cOrientation
0x1801ce447  not     ecx
0x1801ce449  xor     r8d, r8d; cEscapement
0x1801ce44c  and     ecx, 20h
0x1801ce44f  xor     edx, edx; cWidth
0x1801ce451  mov     [rsp+1B0h+iPitchAndFamily], ecx; iPitchAndFamily
0x1801ce455  mov     ecx, r12d; cHeight
0x1801ce458  mov     [rsp+1B0h+iQuality], r13d; iQuality
0x1801ce45d  mov     [rsp+1B0h+iClipPrecision], 40h ; '@'; iClipPrecision
0x1801ce465  mov     [rsp+1B0h+iOutPrecision], r13d; iOutPrecision
0x1801ce46a  mov     [rsp+1B0h+iCharSet], ebx; iCharSet
0x1801ce46e  mov     [rsp+1B0h+bStrikeOut], r13d; bStrikeOut
0x1801ce473  mov     [rsp+1B0h+bUnderline], r13d; bUnderline
0x1801ce478  mov     [rsp+1B0h+bItalic], r13d; bItalic
0x1801ce47d  mov     [rsp+1B0h+cWeight], 190h; cWeight
0x1801ce485  call    cs:__imp_CreateFontW
0x1801ce48b  mov     rsi, rax
0x1801ce48e  test    rax, rax
0x1801ce491  jz      loc_1801CE664
0x1801ce497  xor     ecx, ecx; hWnd
0x1801ce499  call    cs:__imp_GetDC
0x1801ce49f  mov     rcx, rax; hdc
0x1801ce4a2  mov     rdx, rsi; h
0x1801ce4a5  mov     r15, rax
0x1801ce4a8  call    cs:__imp_SelectObject
0x1801ce4ae  lea     rdx, [rsp+1B0h+tm]; lptm
0x1801ce4b3  mov     rcx, r15; hdc
0x1801ce4b6  mov     r13, rax
0x1801ce4b9  call    cs:__imp_GetTextMetricsW
0x1801ce4bf  test    eax, eax
0x1801ce4c1  jnz     short loc_1801CE515
0x1801ce4c3  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x1801ce4c9  jz      short loc_1801CE515
0x1801ce4cb  call    cs:__imp_GetLastError
0x1801ce4d1  xor     edx, edx; unsigned __int16
0x1801ce4d3  mov     ecx, eax
0x1801ce4d5  mov     qword ptr [rsp+1B0h+iQuality], rdx; void *
0x1801ce4da  lea     r9, aGettextmetrics; "GetTextMetrics failed: GetLastError = %"...
0x1801ce4e1  mov     [rsp+1B0h+iClipPrecision], edx; unsigned int
0x1801ce4e5  lea     rax, aNull; "(NULL)"
0x1801ce4ec  mov     qword ptr [rsp+1B0h+iOutPrecision], rax; unsigned __int16 *
0x1801ce4f1  xor     r8d, r8d; int
0x1801ce4f4  mov     qword ptr [rsp+1B0h+iCharSet], rax; unsigned __int16 *
0x1801ce4f9  mov     qword ptr [rsp+1B0h+bStrikeOut], rax; unsigned __int16 *
0x1801ce4fe  mov     qword ptr [rsp+1B0h+bUnderline], rax; unsigned __int16 *
0x1801ce503  mov     qword ptr [rsp+1B0h+bItalic], rax; unsigned __int16 *
0x1801ce508  mov     qword ptr [rsp+1B0h+cWeight], rcx; unsigned __int16 *
0x1801ce50d  lea     ecx, [rdx+9]; int
0x1801ce510  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801ce515  lea     r8, [rbp+0B0h+Name]; lpName
0x1801ce519  mov     edx, 20h ; ' '; c
0x1801ce51e  mov     rcx, r15; hdc
0x1801ce521  call    cs:__imp_GetTextFaceW
0x1801ce527  mov     rdx, r13; h
0x1801ce52a  mov     rcx, r15; hdc
0x1801ce52d  call    cs:__imp_SelectObject
0x1801ce533  xor     r13d, r13d
0x1801ce536  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801ce53d  jz      short loc_1801CE58C
0x1801ce53f  movzx   eax, [rbp+0B0h+tm.tmCharSet]
0x1801ce543  lea     r8, aNull; "(NULL)"
0x1801ce54a  mov     qword ptr [rsp+1B0h+iQuality], r13; void *
0x1801ce54f  lea     r9, aFontCreatedCha; "Font created.  Charset: Req=%i, Ret=%i,"...
0x1801ce556  mov     [rsp+1B0h+iClipPrecision], r13d; unsigned int
0x1801ce55b  xor     edx, edx; unsigned __int16
0x1801ce55d  mov     qword ptr [rsp+1B0h+iOutPrecision], r8; unsigned __int16 *
0x1801ce562  mov     qword ptr [rsp+1B0h+iCharSet], r8; unsigned __int16 *
0x1801ce567  lea     r8, [rbp+0B0h+Name]
0x1801ce56b  mov     qword ptr [rsp+1B0h+bStrikeOut], r8; unsigned __int16 *
0x1801ce570  xor     r8d, r8d; int
0x1801ce573  mov     ecx, ebx
0x1801ce575  mov     qword ptr [rsp+1B0h+bUnderline], rdi; unsigned __int16 *
0x1801ce57a  mov     qword ptr [rsp+1B0h+bItalic], rax; unsigned __int16 *
0x1801ce57f  mov     qword ptr [rsp+1B0h+cWeight], rcx; unsigned __int16 *
0x1801ce584  lea     ecx, [rdx+9]; int
0x1801ce587  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801ce58c  movzx   eax, [rbp+0B0h+tm.tmCharSet]
0x1801ce590  cmp     eax, ebx
0x1801ce592  jz      loc_1801CE644
0x1801ce598  cmp     [rsp+1B0h+var_140], r13b
0x1801ce59d  jnz     loc_1801CE644
0x1801ce5a3  cmp     [rbp+0B0h+Logfont.lfFaceName], r13w
0x1801ce5a8  jz      short loc_1801CE603
0x1801ce5aa  mov     [rbp+0B0h+Logfont.lfFaceName], r13w
0x1801ce5af  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801ce5b6  jz      loc_1801CE649
0x1801ce5bc  mov     qword ptr [rsp+1B0h+iQuality], r13; void *
0x1801ce5c1  lea     r8, aNull; "(NULL)"
0x1801ce5c8  mov     [rsp+1B0h+iClipPrecision], r13d; unsigned int
0x1801ce5cd  lea     r9, aFontEnumeratio; "Font enumeration failed to select chars"...
0x1801ce5d4  mov     qword ptr [rsp+1B0h+iOutPrecision], r8; unsigned __int16 *
0x1801ce5d9  xor     edx, edx; unsigned __int16
0x1801ce5db  mov     qword ptr [rsp+1B0h+iCharSet], r8; unsigned __int16 *
0x1801ce5e0  mov     qword ptr [rsp+1B0h+bStrikeOut], r8; unsigned __int16 *
0x1801ce5e5  mov     qword ptr [rsp+1B0h+bUnderline], r8; unsigned __int16 *
0x1801ce5ea  xor     r8d, r8d; int
0x1801ce5ed  mov     eax, ebx
0x1801ce5ef  lea     ecx, [rdx+9]; int
0x1801ce5f2  mov     qword ptr [rsp+1B0h+bItalic], rax; unsigned __int16 *
0x1801ce5f7  mov     qword ptr [rsp+1B0h+cWeight], r14; unsigned __int16 *
0x1801ce5fc  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801ce601  jmp     short loc_1801CE649
0x1801ce603  lea     r9, [rbp+0B0h+Logfont]; lParam
0x1801ce607  mov     [rbp+0B0h+Logfont.lfCharSet], bl
0x1801ce60a  lea     r8, ?EnumFontProc@@YAHPEAUtagENUMLOGFONTEXW@@PEAUtagNEWTEXTMETRICEXW@@H_J@Z; lpProc
0x1801ce611  mov     [rbp+0B0h+Logfont.lfPitchAndFamily], r13b
0x1801ce615  lea     rdx, [rbp+0B0h+Logfont]; lpLogfont
0x1801ce619  mov     [rsp+1B0h+cWeight], r13d; dwFlags
0x1801ce61e  mov     rcx, r15; hdc
0x1801ce621  call    cs:__imp_EnumFontFamiliesExW
0x1801ce627  lea     rdi, [rbp+0B0h+Logfont.lfFaceName]
0x1801ce62b  cmp     [rbp+0B0h+Logfont.lfFaceName], r13w
0x1801ce630  jz      loc_1801CE5AF
0x1801ce636  mov     rcx, rsi; ho
0x1801ce639  call    cs:__imp_DeleteObject
0x1801ce63f  mov     rsi, r13
0x1801ce642  jmp     short loc_1801CE649
0x1801ce644  mov     [rbp+0B0h+Logfont.lfFaceName], r13w
0x1801ce649  mov     rdx, r15; hDC
0x1801ce64c  xor     ecx, ecx; hWnd
0x1801ce64e  call    cs:__imp_ReleaseDC
0x1801ce654  cmp     [rbp+0B0h+Logfont.lfFaceName], r13w
0x1801ce659  jnz     loc_1801CE437
0x1801ce65f  mov     rax, rsi
0x1801ce662  jmp     short loc_1801CE6B4
0x1801ce664  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801ce66b  jz      short loc_1801CE6B2
0x1801ce66d  mov     qword ptr [rsp+1B0h+iQuality], r13; void *
0x1801ce672  lea     r15, aNull; "(NULL)"
0x1801ce679  mov     [rsp+1B0h+iClipPrecision], r13d; unsigned int
0x1801ce67e  lea     r9, aCreatefontFail; "CreateFont failed, codepage: %i  CharSe"...
0x1801ce685  mov     qword ptr [rsp+1B0h+iOutPrecision], r15; unsigned __int16 *
0x1801ce68a  xor     edx, edx; unsigned __int16
0x1801ce68c  mov     qword ptr [rsp+1B0h+iCharSet], r15; unsigned __int16 *
0x1801ce691  xor     r8d, r8d; int
0x1801ce694  mov     qword ptr [rsp+1B0h+bStrikeOut], r15; unsigned __int16 *
0x1801ce699  mov     eax, ebx
0x1801ce69b  mov     qword ptr [rsp+1B0h+bUnderline], r15; unsigned __int16 *
0x1801ce6a0  lea     ecx, [rdx+9]; int
0x1801ce6a3  mov     qword ptr [rsp+1B0h+bItalic], rax; unsigned __int16 *
0x1801ce6a8  mov     qword ptr [rsp+1B0h+cWeight], r14; unsigned __int16 *
0x1801ce6ad  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801ce6b2  xor     eax, eax
0x1801ce6b4  mov     rcx, [rbp+0B0h+var_50]
0x1801ce6b8  xor     rcx, rsp; StackCookie
0x1801ce6bb  call    __security_check_cookie
0x1801ce6c0  add     rsp, 178h
0x1801ce6c7  pop     r15
0x1801ce6c9  pop     r14
0x1801ce6cb  pop     r13
0x1801ce6cd  pop     r12
0x1801ce6cf  pop     rdi
0x1801ce6d0  pop     rsi
0x1801ce6d1  pop     rbx
0x1801ce6d2  pop     rbp
  ... truncated ...
```
