# PSetupInstallPrinterDriver

- ea: `0x1800113c0`
- end: `0x180011c11`
- name: `PSetupInstallPrinterDriver`
- size: `2129`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, HLOCAL hMem@<rdx>, LPCWSTR@<r8>, int, unsigned __int16 *, HWND hWnd, int, __int64, int, int)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x18000b498`
- `0x18000b7ec`
- `0x18000c368`
- `0x18000ed30`
- `0x1800113c0`
- `0x18001c5c0`
- `0x18001e470`
- `0x180027a10`
- `0x18002ae2c`
- `0x18002c3d0`
- `0x180034bec`
- `0x180035ef8`
- `0x180036664`

## import_xrefs

- `USER32!MessageBoxW` at `0x1800119c3`
- `USER32!MessageBoxW` at `0x1800119c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011aa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011aa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001164f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001164f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800119ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800119dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800119ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800119dc`

## string_xrefs

- `0x180011907`: `InstallDriverFromCurrentInf failed`
- `0x18001144f`: `PSetupInstallPrinterDriver`
- `0x1800119f1`: `PSetupInstallPrinterDriver`
- `0x180011be8`: `PSetupInstallPrinterDriver`
- `0x180011620`: `InstallDriverAfterPromptingForInf failed`
- `0x1800116c0`: `InstallDriverAfterPromptingForInf failed`
- `0x1800117e9`: `InstallDriverAfterPromptingForInf failed`
- `0x18001154d`: `InstallPrinterDriverFromTheWeb failed`

## pseudocode

```c
__int64 __fastcall PSetupInstallPrinterDriver(
        FILETIME a1,
        char *hMem,
        LPCWSTR a3,
        int a4,
        unsigned int a5,
        unsigned __int16 *a6,
        HWND hWnd,
        int a8,
        __int64 a9,
        unsigned int a10,
        int a11)
{
  __int64 v11; // r14
  int dwLowDateTime; // esi
  unsigned int v16; // ecx
  __int64 v17; // rdi
  unsigned int v18; // eax
  int v19; // edi
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // r9
  unsigned __int16 *v22; // r8
  unsigned __int16 *v23; // rdx
  unsigned int v24; // eax
  unsigned int v25; // ecx
  unsigned __int16 *v26; // rdx
  const unsigned __int16 *v27; // rsi
  const unsigned __int16 *v28; // r8
  LPCWSTR v29; // r9
  int v30; // eax
  unsigned int v31; // edx
  unsigned __int16 *v32; // rcx
  int v33; // r9d
  const unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // r8
  signed int LastError; // eax
  signed int v37; // eax
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  int v40; // eax
  HWND v41; // r8
  int v42; // eax
  unsigned int v43; // ecx
  unsigned __int16 *v44; // rdx
  int v45; // eax
  unsigned int v46; // ecx
  unsigned __int16 *v47; // rdx
  int v48; // ebp
  WCHAR *StringFromRcFile; // rsi
  const WCHAR *v50; // rax
  WCHAR *v51; // rdi
  int v52; // edx
  const unsigned __int16 *v53; // rcx
  const unsigned __int16 *v54; // rcx
  int v55; // edx
  const unsigned __int16 *v56; // r9
  const unsigned __int16 *v57; // rax
  const unsigned __int16 *v58; // r8
  int *v59; // rax
  const unsigned __int16 *v60; // rcx
  int v61; // r8d
  const unsigned __int16 *v62; // rax
  const unsigned __int16 *v63; // rdx
  int v64; // [rsp+20h] [rbp-98h]
  int v65; // [rsp+20h] [rbp-98h]
  unsigned __int16 *v66; // [rsp+28h] [rbp-90h]
  unsigned __int16 *v67; // [rsp+28h] [rbp-90h]
  unsigned __int16 *v68; // [rsp+30h] [rbp-88h]
  unsigned __int16 *v69; // [rsp+30h] [rbp-88h]
  unsigned __int16 *v70; // [rsp+38h] [rbp-80h]
  unsigned int v71; // [rsp+38h] [rbp-80h]
  int v72; // [rsp+40h] [rbp-78h]
  int v73; // [rsp+40h] [rbp-78h]
  unsigned __int16 *v74; // [rsp+48h] [rbp-70h]
  unsigned int v75; // [rsp+50h] [rbp-68h]
  unsigned int v76; // [rsp+58h] [rbp-60h]
  int v77; // [rsp+60h] [rbp-58h] BYREF
  char *v78; // [rsp+68h] [rbp-50h]

  v11 = a4;
  dwLowDateTime = a1.dwLowDateTime;
  if ( PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled() )
    return 1260;
  v16 = a5;
  if ( a5 - 1 > 1 && a5 < 5 )
  {
    v17 = a9;
    v78 = hMem;
    if ( a9 )
    {
      v17 = a9 & -(__int64)(*(_WORD *)a9 != 0);
      a9 = v17;
      v16 = a5;
    }
    while ( 1 )
    {
      if ( v16 != 3 || (_DWORD)v11 != MyPlatform )
      {
        if ( hMem && (hMem[80] & 2) != 0 )
        {
          v52 = *((_DWORD *)hMem + 43);
          if ( v52 )
            v53 = (const unsigned __int16 *)*((_QWORD *)hMem + 28);
          else
            v53 = 0;
          SplLogPrinterSetupCoreDriverEvent(
            &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
            L"PSetupInstallPrinterDriver",
            L"Not an NT5 driver requested from the Web",
            a6,
            *(const unsigned __int16 **)hMem,
            a3,
            *((const unsigned __int16 **)hMem + 23),
            (const unsigned __int16 *)PlatformEnv[v11],
            v52,
            v53,
            0,
            0);
          return 0;
        }
        if ( v16 != 3 || (_DWORD)v11 != MyPlatform )
        {
          if ( hMem )
          {
            if ( (a10 & 0x1800) == 0 )
            {
              if ( !(unsigned int)IsInInfDir(*(_QWORD *)hMem) )
              {
                v27 = a6;
                v41 = hWnd;
                v73 = a11;
                v71 = a10;
                v69 = (unsigned __int16 *)(v17 & -(__int64)((a10 & 0x21) != 0));
                v67 = a6;
                v65 = a5;
                goto LABEL_74;
              }
              v16 = a5;
            }
            v29 = (LPCWSTR)*((_QWORD *)hMem + 1);
          }
          else
          {
            v29 = a3;
          }
          LODWORD(v66) = a10;
          v64 = v16;
LABEL_32:
          v27 = a6;
          v30 = InstallDriverAfterPromptingForInf((unsigned int)v11, a6, hWnd, v29, v64);
          v19 = v30;
          if ( !v30 )
            goto LABEL_89;
          if ( v30 > 0 )
            v31 = (unsigned __int16)v30 | 0x80070000;
          else
            v31 = v30;
          if ( hMem && *((_DWORD *)hMem + 43) )
          {
            v32 = (unsigned __int16 *)*((_QWORD *)hMem + 28);
            goto LABEL_40;
          }
          v32 = 0;
          if ( hMem )
LABEL_40:
            v33 = *((_DWORD *)hMem + 43);
          else
            v33 = 0;
          if ( hMem )
          {
            v34 = *(const unsigned __int16 **)hMem;
            v35 = (unsigned __int16 *)*((_QWORD *)hMem + 23);
          }
          else
          {
            v34 = 0;
            v35 = 0;
          }
          v76 = v31;
          v75 = v19;
          v74 = v32;
          v72 = v33;
          v70 = (unsigned __int16 *)PlatformEnv[v11];
          v68 = v35;
          v28 = L"InstallDriverAfterPromptingForInf failed";
          goto LABEL_83;
        }
      }
      if ( hMem && (hMem[80] & 2) != 0 )
        break;
      if ( (a10 & 0x1000) != 0 )
      {
        if ( hMem )
          v29 = (LPCWSTR)*((_QWORD *)hMem + 1);
        else
          v29 = a3;
        LODWORD(v66) = a10;
        v64 = 3;
        goto LABEL_32;
      }
      if ( hMem || (hMem = (char *)PSetupDriverInfoFromName(dwLowDateTime, a3)) != 0 )
      {
        v40 = IsInInfDir(*(_QWORD *)hMem);
        v41 = hWnd;
        if ( !v40 )
        {
          v27 = a6;
          v73 = a11;
          v71 = a10;
          v69 = (unsigned __int16 *)(v17 & -(__int64)((a10 & 0x21) != 0));
          v67 = a6;
          v65 = 3;
LABEL_74:
          v77 = 0;
          v45 = InstallDriverFromCurrentInf(a1, (DWORDLONG *)hMem, v41, v11, v65, v67, v69, v71, v73, (__int64)&v77);
          v19 = v45;
          if ( !v45 )
            goto LABEL_89;
          if ( v45 > 0 )
            v46 = (unsigned __int16)v45 | 0x80070000;
          else
            v46 = v45;
          if ( *((_DWORD *)hMem + 43) )
            v47 = (unsigned __int16 *)*((_QWORD *)hMem + 28);
          else
            v47 = 0;
          v76 = v46;
          v75 = v45;
          v74 = v47;
          v72 = *((_DWORD *)hMem + 43);
          v28 = L"InstallDriverFromCurrentInf failed";
LABEL_82:
          v70 = (unsigned __int16 *)PlatformEnv[v11];
          v68 = (unsigned __int16 *)*((_QWORD *)hMem + 23);
          v34 = *(const unsigned __int16 **)hMem;
LABEL_83:
          SplLogPrinterSetupCoreDriverEvent(
            &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
            L"PSetupInstallPrinterDriver",
            v28,
            v27,
            v34,
            a3,
            v68,
            v70,
            v72,
            v74,
            v75,
            v76);
          goto LABEL_89;
        }
        LODWORD(v66) = a10;
        v42 = InstallDriverAfterPromptingForInf((unsigned int)v11, 0, hWnd, *((_QWORD *)hMem + 1), 3);
        v19 = v42;
        if ( v42 )
        {
          if ( v42 > 0 )
            v43 = (unsigned __int16)v42 | 0x80070000;
          else
            v43 = v42;
          if ( *((_DWORD *)hMem + 43) )
            v44 = (unsigned __int16 *)*((_QWORD *)hMem + 28);
          else
            v44 = 0;
          v27 = a6;
          v76 = v43;
          v75 = v42;
          v74 = v44;
          v72 = *((_DWORD *)hMem + 43);
          v28 = L"InstallDriverAfterPromptingForInf failed";
          goto LABEL_82;
        }
        goto LABEL_88;
      }
      LastError = GetLastError();
      v19 = LastError;
      if ( LastError != 1797 )
      {
        if ( LastError )
        {
          if ( LastError > 0 )
LABEL_58:
            v39 = (unsigned __int16)LastError | 0x80070000;
          else
            v39 = LastError;
          v27 = a6;
          SplLogPrinterSetupCoreDriverEvent(
            &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
            L"PSetupInstallPrinterDriver",
            L"PSetupDriverInfoFromName failed",
            a6,
            0,
            a3,
            0,
            (const unsigned __int16 *)PlatformEnv[v11],
            0,
            0,
            LastError,
            v39);
          goto LABEL_89;
        }
LABEL_88:
        v27 = a6;
        goto LABEL_89;
      }
      if ( (a10 & 0x800) == 0 )
        goto LABEL_58;
      v27 = a6;
      LODWORD(v66) = a10;
      v37 = InstallDriverAfterPromptingForInf((unsigned int)v11, a6, hWnd, a3, 3);
      v19 = v37;
      if ( v37 )
      {
        if ( v37 > 0 )
          v38 = (unsigned __int16)v37 | 0x80070000;
        else
          v38 = v37;
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"PSetupInstallPrinterDriver",
          L"InstallDriverAfterPromptingForInf failed",
          a6,
          0,
          a3,
          0,
          (const unsigned __int16 *)PlatformEnv[v11],
          0,
          0,
          v37,
          v38);
      }
LABEL_89:
      if ( v19 != 216 )
      {
        if ( v19 )
        {
LABEL_116:
          if ( !v78 )
            DestroyLocalData(hMem);
          return (unsigned int)v19;
        }
        if ( hMem && *((_DWORD *)hMem + 43) )
        {
          v54 = (const unsigned __int16 *)*((_QWORD *)hMem + 28);
          goto LABEL_110;
        }
        v54 = 0;
        if ( hMem )
LABEL_110:
          v55 = *((_DWORD *)hMem + 43);
        else
          v55 = 0;
        if ( hMem )
        {
          v56 = (const unsigned __int16 *)*((_QWORD *)hMem + 1);
          v57 = *(const unsigned __int16 **)hMem;
          v58 = (const unsigned __int16 *)*((_QWORD *)hMem + 23);
        }
        else
        {
          v56 = 0;
          v57 = 0;
          v58 = 0;
        }
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
          L"PSetupInstallPrinterDriver",
          v27,
          v56,
          v57,
          a3,
          v58,
          (const unsigned __int16 *)PlatformEnv[v11],
          v55,
          v54,
          0,
          0);
        goto LABEL_116;
      }
      if ( (a10 & 8) != 0 )
        goto LABEL_116;
      v48 = 0;
      StringFromRcFile = (WCHAR *)GetStringFromRcFile(0x3F0u);
      v50 = (const WCHAR *)GetStringFromRcFile(0x3EFu);
      v51 = (WCHAR *)v50;
      if ( StringFromRcFile )
      {
        if ( v50 )
          v48 = MessageBoxW(hWnd, v50, StringFromRcFile, 0x15u);
        LocalFree(StringFromRcFile);
      }
      if ( v51 )
        LocalFree(v51);
      if ( v48 != 4 )
      {
        v19 = 1223;
        SetLastError(0x4C7u);
        goto LABEL_116;
      }
      v17 = a9;
      v16 = a5;
      dwLowDateTime = a1.dwLowDateTime;
      if ( !v78 )
      {
        DestroyLocalData(hMem);
        v16 = a5;
        hMem = 0;
      }
    }
    v77 = 0;
    v18 = RunningAsLUA(&v77);
    v19 = StatusFromHResult(v18);
    if ( v19
      || ((v20 = (unsigned __int16 *)*((_QWORD *)hMem + 4),
           v21 = (unsigned __int16 *)*((_QWORD *)hMem + 7),
           v22 = (unsigned __int16 *)*((_QWORD *)hMem + 5),
           v23 = (unsigned __int16 *)*((_QWORD *)hMem + 1),
           !v77)
        ? (v24 = InstallPrinterDriverFromTheWeb((__int64)hWnd, v23, v22, v21, v20, &OsVersionInfo))
        : (v24 = ElevateAndCallInstallPrinterDriverFromTheWeb(hWnd, v23, v22, v21, v20, (struct _OSVERSIONINFOW *)v66)),
          (v19 = v24) != 0) )
    {
      if ( v19 > 0 )
        v25 = (unsigned __int16)v19 | 0x80070000;
      else
        v25 = v19;
      if ( *((_DWORD *)hMem + 43) )
        v26 = (unsigned __int16 *)*((_QWORD *)hMem + 28);
      else
        v26 = 0;
      v27 = a6;
      v76 = v25;
      v75 = v19;
      v74 = v26;
      v72 = *((_DWORD *)hMem + 43);
      v28 = L"InstallPrinterDriverFromTheWeb failed";
      goto LABEL_82;
    }
    goto LABEL_88;
  }
  v19 = 87;
  SetLastError(0x57u);
  v59 = (int *)(hMem + 172);
  if ( hMem )
  {
    if ( *v59 )
      v60 = (const unsigned __int16 *)*((_QWORD *)hMem + 28);
    else
      v60 = 0;
    v61 = *v59;
  }
  else
  {
    v61 = 0;
    v60 = 0;
  }
  if ( hMem )
  {
    v62 = *(const unsigned __int16 **)hMem;
    v63 = (const unsigned __int16 *)*((_QWORD *)hMem + 23);
  }
  else
  {
    v62 = 0;
    v63 = 0;
  }
  SplLogPrinterSetupCoreDriverEvent(
    &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
    L"PSetupInstallPrinterDriver",
    L"Invalid version argument",
    a6,
    v62,
    a3,
    v63,
    (const unsigned __int16 *)PlatformEnv[v11],
    v61,
    v60,
    0x57u,
    0x80070057);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800113c0  mov     [rsp+arg_0], rcx
0x1800113c5  push    rbx
0x1800113c6  push    rbp
0x1800113c7  push    rsi
0x1800113c8  push    rdi
0x1800113c9  push    r12
0x1800113cb  push    r13
0x1800113cd  push    r14
0x1800113cf  push    r15
0x1800113d1  sub     rsp, 78h
0x1800113d5  movsxd  r14, r9d
0x1800113d8  mov     r15, r8
0x1800113db  mov     rbx, rdx
0x1800113de  mov     rsi, rcx
0x1800113e1  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x1800113e6  test    al, al
0x1800113e8  jz      short loc_1800113F4
0x1800113ea  mov     eax, 4ECh
0x1800113ef  jmp     loc_180011C00
0x1800113f4  mov     ecx, [rsp+0B8h+arg_20]
0x1800113fb  lea     eax, [rcx-1]
0x1800113fe  cmp     eax, 1
0x180011401  jbe     loc_180011B5A
0x180011407  cmp     ecx, 5
0x18001140a  jnb     loc_180011B5A
0x180011410  mov     rdi, [rsp+0B8h+arg_40]
0x180011418  mov     [rsp+0B8h+var_50], rbx
0x18001141d  test    rdi, rdi
0x180011420  jz      short loc_180011440
0x180011422  movzx   eax, word ptr [rdi]
0x180011425  neg     ax
0x180011428  sbb     rcx, rcx
0x18001142b  and     rcx, rdi
0x18001142e  mov     rdi, rcx
0x180011431  mov     [rsp+0B8h+arg_40], rcx
0x180011439  mov     ecx, [rsp+0B8h+arg_20]
0x180011440  mov     r13d, [rsp+0B8h+arg_48]
0x180011448  lea     r12, PlatformEnv
0x18001144f  lea     rbp, aPsetupinstallp_0; "PSetupInstallPrinterDriver"
0x180011456  mov     eax, cs:MyPlatform
0x18001145c  cmp     ecx, 3
0x18001145f  jnz     short loc_180011466
0x180011461  cmp     r14d, eax
0x180011464  jz      short loc_180011487
0x180011466  test    rbx, rbx
0x180011469  jz      short loc_180011475
0x18001146b  test    byte ptr [rbx+50h], 2
0x18001146f  jnz     loc_180011A2B
0x180011475  cmp     ecx, 3
0x180011478  jnz     loc_180011838
0x18001147e  cmp     r14d, eax
0x180011481  jnz     loc_180011838
0x180011487  test    rbx, rbx
0x18001148a  jz      loc_180011559
0x180011490  test    byte ptr [rbx+50h], 2
0x180011494  jz      loc_180011559
0x18001149a  lea     rcx, [rsp+0B8h+var_58]; int *
0x18001149f  mov     [rsp+0B8h+var_58], 0
0x1800114a7  call    ?RunningAsLUA@@YAJPEAH@Z; RunningAsLUA(int *)
0x1800114ac  mov     ecx, eax
0x1800114ae  call    StatusFromHResult
0x1800114b3  mov     edi, eax
0x1800114b5  test    eax, eax
0x1800114b7  jnz     short loc_18001150B
0x1800114b9  mov     rax, [rbx+20h]
0x1800114bd  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800114c1  mov     r8, [rbx+28h]; unsigned __int16 *
0x1800114c5  mov     rdx, [rbx+8]; unsigned __int16 *
0x1800114c9  cmp     [rsp+0B8h+var_58], edi
0x1800114cd  jz      short loc_1800114E3
0x1800114cf  mov     rcx, [rsp+0B8h+hWnd]; HWND
0x1800114d7  mov     [rsp+0B8h+var_98], rax; unsigned __int16 *
0x1800114dc  call    ?ElevateAndCallInstallPrinterDriverFromTheWeb@@YAKPEAUHWND__@@PEAG111PEAU_OSVERSIONINFOW@@@Z; ElevateAndCallInstallPrinterDriverFromTheWeb(HWND__ *,ushort *,ushort *,ushort *,ushort *,_OSVERSIONINFOW *)
0x1800114e1  jmp     short loc_180011501
0x1800114e3  lea     rcx, OsVersionInfo
0x1800114ea  mov     [rsp+0B8h+var_90], rcx
0x1800114ef  mov     rcx, [rsp+0B8h+hWnd]
0x1800114f7  mov     [rsp+0B8h+var_98], rax
0x1800114fc  call    InstallPrinterDriverFromTheWeb
0x180011501  mov     edi, eax
0x180011503  test    eax, eax
0x180011505  jz      loc_18001196D
0x18001150b  test    edi, edi
0x18001150d  jg      short loc_180011513
0x18001150f  mov     ecx, edi
0x180011511  jmp     short loc_18001151C
0x180011513  movzx   ecx, di
0x180011516  or      ecx, 80070000h
0x18001151c  mov     r8d, [rbx+0ACh]
0x180011523  test    r8d, r8d
0x180011526  jz      short loc_180011531
0x180011528  mov     rdx, [rbx+0E0h]
0x18001152f  jmp     short loc_180011533
0x180011531  xor     edx, edx
0x180011533  mov     rsi, [rsp+0B8h+arg_28]
0x18001153b  mov     [rsp+0B8h+var_60], ecx
0x18001153f  mov     [rsp+0B8h+var_68], edi
0x180011543  mov     [rsp+0B8h+var_70], rdx
0x180011548  mov     [rsp+0B8h+var_78], r8d
0x18001154d  lea     r8, aInstallprinter_3; "InstallPrinterDriverFromTheWeb failed"
0x180011554  jmp     loc_18001190E
0x180011559  bt      r13d, 0Ch
0x18001155e  jnb     loc_18001162C
0x180011564  test    rbx, rbx
0x180011567  jz      short loc_18001156F
0x180011569  mov     r9, [rbx+8]
0x18001156d  jmp     short loc_180011572
0x18001156f  mov     r9, r15
0x180011572  mov     eax, [rsp+0B8h+arg_50]
0x180011579  mov     dword ptr [rsp+0B8h+var_88], eax
0x18001157d  mov     dword ptr [rsp+0B8h+var_90], r13d
0x180011582  mov     dword ptr [rsp+0B8h+var_98], 3
0x18001158a  mov     rsi, [rsp+0B8h+arg_28]
0x180011592  mov     ecx, r14d
0x180011595  mov     r8, [rsp+0B8h+hWnd]
0x18001159d  mov     rdx, rsi
0x1800115a0  call    ?InstallDriverAfterPromptingForInf@@YAKW4PLATFORM@@PEBGPEAUHWND__@@1KKK@Z; InstallDriverAfterPromptingForInf(PLATFORM,ushort const *,HWND__ *,ushort const *,ulong,ulong,ulong)
0x1800115a5  mov     edi, eax
0x1800115a7  test    eax, eax
0x1800115a9  jz      loc_180011975
0x1800115af  test    eax, eax
0x1800115b1  jg      short loc_1800115B7
0x1800115b3  mov     edx, eax
0x1800115b5  jmp     short loc_1800115C0
0x1800115b7  movzx   edx, di
0x1800115ba  or      edx, 80070000h
0x1800115c0  test    rbx, rbx
0x1800115c3  jz      short loc_1800115D7
0x1800115c5  cmp     dword ptr [rbx+0ACh], 0
0x1800115cc  jz      short loc_1800115D7
0x1800115ce  mov     rcx, [rbx+0E0h]
0x1800115d5  jmp     short loc_1800115DE
0x1800115d7  xor     ecx, ecx
0x1800115d9  test    rbx, rbx
0x1800115dc  jz      short loc_1800115E7
0x1800115de  mov     r9d, [rbx+0ACh]
0x1800115e5  jmp     short loc_1800115EA
0x1800115e7  xor     r9d, r9d
0x1800115ea  mov     r10, [r12+r14*8]
0x1800115ee  test    rbx, rbx
0x1800115f1  jz      short loc_1800115FF
0x1800115f3  mov     rax, [rbx]
0x1800115f6  mov     r8, [rbx+0B8h]
0x1800115fd  jmp     short loc_180011604
0x1800115ff  xor     eax, eax
0x180011601  xor     r8d, r8d
0x180011604  mov     [rsp+0B8h+var_60], edx
0x180011608  mov     [rsp+0B8h+var_68], edi
0x18001160c  mov     [rsp+0B8h+var_70], rcx
0x180011611  mov     [rsp+0B8h+var_78], r9d
0x180011616  mov     [rsp+0B8h+var_80], r10
0x18001161b  mov     [rsp+0B8h+var_88], r8
0x180011620  lea     r8, aInstalldrivera_0; "InstallDriverAfterPromptingForInf faile"...
0x180011627  jmp     loc_180011926
0x18001162c  test    rbx, rbx
0x18001162f  jnz     loc_180011765
0x180011635  mov     r8d, r14d
0x180011638  mov     rdx, r15; LPCWSTR
0x18001163b  mov     rcx, rsi; int
0x18001163e  call    PSetupDriverInfoFromName
0x180011643  mov     rbx, rax
0x180011646  test    rax, rax
0x180011649  jnz     loc_180011765
0x18001164f  call    cs:__imp_GetLastError
0x180011655  mov     edi, eax
0x180011657  cmp     eax, 705h
0x18001165c  jnz     loc_180011701
0x180011662  bt      r13d, 0Bh
0x180011667  jnb     loc_18001170F
0x18001166d  mov     eax, [rsp+0B8h+arg_50]
0x180011674  mov     r9, r15
0x180011677  mov     rsi, [rsp+0B8h+arg_28]
0x18001167f  mov     ecx, r14d
0x180011682  mov     r8, [rsp+0B8h+hWnd]
0x18001168a  mov     rdx, rsi
0x18001168d  mov     dword ptr [rsp+0B8h+var_88], eax
0x180011691  mov     dword ptr [rsp+0B8h+var_90], r13d
0x180011696  mov     dword ptr [rsp+0B8h+var_98], 3
0x18001169e  call    ?InstallDriverAfterPromptingForInf@@YAKW4PLATFORM@@PEBGPEAUHWND__@@1KKK@Z; InstallDriverAfterPromptingForInf(PLATFORM,ushort const *,HWND__ *,ushort const *,ulong,ulong,ulong)
0x1800116a3  mov     edi, eax
0x1800116a5  test    eax, eax
0x1800116a7  jz      loc_180011975
0x1800116ad  jg      short loc_1800116B3
0x1800116af  mov     ecx, eax
0x1800116b1  jmp     short loc_1800116BC
0x1800116b3  movzx   ecx, ax
0x1800116b6  or      ecx, 80070000h
0x1800116bc  mov     [rsp+0B8h+var_60], ecx
0x1800116c0  lea     r8, aInstalldrivera_0; "InstallDriverAfterPromptingForInf faile"...
0x1800116c7  mov     [rsp+0B8h+var_68], eax
0x1800116cb  mov     rax, [r12+r14*8]
0x1800116cf  mov     [rsp+0B8h+var_70], 0
0x1800116d8  mov     [rsp+0B8h+var_78], 0
0x1800116e0  mov     [rsp+0B8h+var_80], rax
0x1800116e5  mov     [rsp+0B8h+var_88], 0
0x1800116ee  mov     [rsp+0B8h+var_90], r15
0x1800116f3  mov     [rsp+0B8h+var_98], 0
0x1800116fc  jmp     loc_180011930
0x180011701  test    eax, eax
0x180011703  jz      loc_18001196D
0x180011709  jg      short loc_18001170F
0x18001170b  mov     ecx, eax
0x18001170d  jmp     short loc_180011718
0x18001170f  movzx   ecx, ax
0x180011712  or      ecx, 80070000h
0x180011718  mov     rsi, [rsp+0B8h+arg_28]
0x180011720  lea     r8, aPsetupdriverin_1; "PSetupDriverInfoFromName failed"
0x180011727  mov     [rsp+0B8h+var_60], ecx
0x18001172b  mov     [rsp+0B8h+var_68], eax
0x18001172f  mov     rax, [r12+r14*8]
0x180011733  mov     [rsp+0B8h+var_70], 0
0x18001173c  mov     [rsp+0B8h+var_78], 0
0x180011744  mov     [rsp+0B8h+var_80], rax
0x180011749  mov     [rsp+0B8h+var_88], 0
0x180011752  mov     [rsp+0B8h+var_90], r15
0x180011757  mov     [rsp+0B8h+var_98], 0
0x180011760  jmp     loc_180011930
0x180011765  mov     rcx, [rbx]
0x180011768  call    IsInInfDir
0x18001176d  mov     r8, [rsp+0B8h+hWnd]
0x180011775  test    eax, eax
0x180011777  jz      short loc_1800117F5
0x180011779  mov     eax, [rsp+0B8h+arg_50]
0x180011780  xor     edx, edx
0x180011782  mov     r9, [rbx+8]
0x180011786  mov     ecx, r14d
0x180011789  mov     dword ptr [rsp+0B8h+var_88], eax
0x18001178d  mov     dword ptr [rsp+0B8h+var_90], r13d
0x180011792  mov     dword ptr [rsp+0B8h+var_98], 3
0x18001179a  call    ?InstallDriverAfterPromptingForInf@@YAKW4PLATFORM@@PEBGPEAUHWND__@@1KKK@Z; InstallDriverAfterPromptingForInf(PLATFORM,ushort const *,HWND__ *,ushort const *,ulong,ulong,ulong)
0x18001179f  mov     edi, eax
0x1800117a1  test    eax, eax
0x1800117a3  jz      loc_18001196D
0x1800117a9  jg      short loc_1800117AF
0x1800117ab  mov     ecx, eax
0x1800117ad  jmp     short loc_1800117B8
0x1800117af  movzx   ecx, ax
0x1800117b2  or      ecx, 80070000h
0x1800117b8  mov     r8d, [rbx+0ACh]
0x1800117bf  test    r8d, r8d
0x1800117c2  jz      short loc_1800117CD
0x1800117c4  mov     rdx, [rbx+0E0h]
0x1800117cb  jmp     short loc_1800117CF
0x1800117cd  xor     edx, edx
0x1800117cf  mov     rsi, [rsp+0B8h+arg_28]
0x1800117d7  mov     [rsp+0B8h+var_60], ecx
0x1800117db  mov     [rsp+0B8h+var_68], eax
0x1800117df  mov     [rsp+0B8h+var_70], rdx
0x1800117e4  mov     [rsp+0B8h+var_78], r8d
0x1800117e9  lea     r8, aInstalldrivera_0; "InstallDriverAfterPromptingForInf faile"...
0x1800117f0  jmp     loc_18001190E
0x1800117f5  mov     rsi, [rsp+0B8h+arg_28]
0x1800117fd  mov     al, r13b
0x180011800  and     al, 21h
0x180011802  neg     al
0x180011804  lea     rax, [rsp+0B8h+var_58]
0x180011809  mov     [rsp+0B8h+var_70], rax
0x18001180e  sbb     rcx, rcx
0x180011811  mov     eax, [rsp+0B8h+arg_50]
0x180011818  and     rcx, rdi
0x18001181b  mov     [rsp+0B8h+var_78], eax
0x18001181f  mov     dword ptr [rsp+0B8h+var_80], r13d
0x180011824  mov     [rsp+0B8h+var_88], rcx
0x180011829  mov     [rsp+0B8h+var_90], rsi
0x18001182e  mov     dword ptr [rsp+0B8h+var_98], 3
0x180011836  jmp     short loc_1800118AA
0x180011838  test    rbx, rbx
0x18001183b  jz      loc_180011951
0x180011841  test    r13d, 1800h
0x180011848  jnz     loc_18001194B
0x18001184e  mov     rcx, [rbx]
0x180011851  call    IsInInfDir
0x180011856  test    eax, eax
0x180011858  jnz     loc_180011944
0x18001185e  mov     rsi, [rsp+0B8h+arg_28]
0x180011866  mov     al, r13b
0x180011869  mov     r8, [rsp+0B8h+hWnd]
0x180011871  and     al, 21h
0x180011873  neg     al
0x180011875  lea     rax, [rsp+0B8h+var_58]
0x18001187a  mov     [rsp+0B8h+var_70], rax
0x18001187f  sbb     rcx, rcx
0x180011882  mov     eax, [rsp+0B8h+arg_50]
0x180011889  and     rcx, rdi
0x18001188c  mov     [rsp+0B8h+var_78], eax
0x180011890  mov     eax, [rsp+0B8h+arg_20]
0x180011897  mov     dword ptr [rsp+0B8h+var_80], r13d
0x18001189c  mov     [rsp+0B8h+var_88], rcx
0x1800118a1  mov     [rsp+0B8h+var_90], rsi
0x1800118a6  mov     dword ptr [rsp+0B8h+var_98], eax
0x1800118aa  mov     rcx, [rsp+0B8h+arg_0]
0x1800118b2  mov     r9d, r14d
0x1800118b5  mov     rdx, rbx
0x1800118b8  mov     [rsp+0B8h+var_58], 0
0x1800118c0  call    ?InstallDriverFromCurrentInf@@YAKPEAXPEAU_PSETUP_LOCAL_DATA@@PEAUHWND__@@W4PLATFORM@@KPEBG4KKPEAK@Z; InstallDriverFromCurrentInf(void *,_PSETUP_LOCAL_DATA *,HWND__ *,PLATFORM,ulong,ushort const *,ushort const *,ulong,ulong,ulong *)
0x1800118c5  mov     edi, eax
0x1800118c7  test    eax, eax
0x1800118c9  jz      loc_180011975
0x1800118cf  jg      short loc_1800118D5
0x1800118d1  mov     ecx, eax
  ... truncated ...
```
