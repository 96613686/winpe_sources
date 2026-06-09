# TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)

- ea: `0x180557fe8`
- end: `0x1805583d3`
- name: `?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z`
- size: `1003`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d928`
- `0x180011528`
- `0x18006b200`
- `0x180079460`
- `0x18008504c`
- `0x18017930c`
- `0x180179574`
- `0x180558514`
- `0x180559c70`

## callees

- `0x180090488`
- `0x180557fe8`
- `0x1805583dc`
- `0x180594010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18055805c`
- `KERNEL32!FreeLibrary` at `0x180558216`
- `KERNEL32!FreeLibrary` at `0x180558225`
- `KERNEL32!FreeLibrary` at `0x1805583a0`
- `KERNEL32!FreeLibrary` at `0x18055805c`
- `KERNEL32!FreeLibrary` at `0x180558216`
- `KERNEL32!FreeLibrary` at `0x180558225`
- `KERNEL32!FreeLibrary` at `0x1805583a0`
- `KERNEL32!LoadLibraryExW` at `0x180558016`
- `KERNEL32!LoadLibraryExW` at `0x18055807d`
- `KERNEL32!LoadLibraryExW` at `0x1805580a1`
- `KERNEL32!LoadLibraryExW` at `0x180558348`
- `KERNEL32!LoadLibraryExW` at `0x180558016`
- `KERNEL32!LoadLibraryExW` at `0x18055807d`
- `KERNEL32!LoadLibraryExW` at `0x1805580a1`
- `KERNEL32!LoadLibraryExW` at `0x180558348`
- `KERNEL32!GetProcAddress` at `0x180558034`
- `KERNEL32!GetProcAddress` at `0x1805580c3`
- `KERNEL32!GetProcAddress` at `0x1805580dd`
- `KERNEL32!GetProcAddress` at `0x1805580f6`
- `KERNEL32!GetProcAddress` at `0x18055810f`
- `KERNEL32!GetProcAddress` at `0x180558128`
- `KERNEL32!GetProcAddress` at `0x180558369`
- `KERNEL32!GetProcAddress` at `0x180558034`
- `KERNEL32!GetProcAddress` at `0x1805580c3`
- `KERNEL32!GetProcAddress` at `0x1805580dd`
- `KERNEL32!GetProcAddress` at `0x1805580f6`
- `KERNEL32!GetProcAddress` at `0x18055810f`
- `KERNEL32!GetProcAddress` at `0x180558128`
- `KERNEL32!GetProcAddress` at `0x180558369`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180558298`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1805582db`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x18055831e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180558298`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1805582db`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x18055831e`

## string_xrefs

- `0x180558102`: `WindowsCreateString`
- `0x18055811b`: `WindowsDeleteString`
- `0x180558098`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x180558074`: `api-ms-win-core-winrt-l1-1-0.dll`
- `0x18055833f`: `slc.dll`
- `0x180558005`: `DiagnosticDataSettings.dll`

## pseudocode

```c
bool __fastcall TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(int a1)
{
  bool v1; // bl
  char v2; // di
  HMODULE Library; // rax
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rax
  int v6; // eax
  unsigned __int16 v7; // dx
  unsigned __int16 v8; // cx
  HMODULE v9; // rsi
  unsigned __int16 v10; // r8
  unsigned __int16 v11; // r9
  HMODULE v12; // r14
  void (*v13)(void); // r13
  FARPROC v14; // r12
  FARPROC v15; // r15
  FARPROC v16; // rax
  char v17; // al
  HMODULE v18; // rax
  HMODULE v19; // rbx
  bool v20; // di
  FARPROC v21; // rax
  int pvData; // [rsp+90h] [rbp+48h] BYREF
  FARPROC pcbData; // [rsp+98h] [rbp+50h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+58h] BYREF
  void (*v26)(void); // [rsp+A8h] [rbp+60h]

  pvData = a1;
  v1 = 0;
  v2 = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings.dll", 0, 0x800u);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TelIsTelemetryTypeAllowed");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(__int64))ProcAddress)(2);
      if ( v6 >= 0 )
      {
        v2 = 1;
        v1 = v6 == 0;
      }
    }
    FreeLibrary(v4);
    if ( v2 )
      return v1;
  }
  v9 = LoadLibraryExW(L"api-ms-win-core-winrt-l1-1-0.dll", 0, 0x800u);
  if ( v9 )
  {
    v12 = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
    if ( v12 )
    {
      pcbData = GetProcAddress(v9, "RoInitialize");
      v13 = (void (*)(void))GetProcAddress(v9, "RoUninitialize");
      v14 = GetProcAddress(v9, "RoGetActivationFactory");
      v15 = GetProcAddress(v12, "WindowsCreateString");
      v16 = GetProcAddress(v12, "WindowsDeleteString");
      v26 = (void (*)(void))v16;
      if ( pcbData && v13 && v14 && v15 && v16 && ((int (__fastcall *)(__int64))pcbData)(1) >= 0 )
      {
        v25 = 0;
        pcbData = 0;
        LOBYTE(pvData) = 0;
        if ( ((int (__fastcall *)(const unsigned __int16 *, __int64, __int64 *))v15)(
               L"Windows.System.Profile.PlatformDiagnosticsAndUsageDataSettings",
               62,
               &v25) >= 0 )
        {
          Microsoft::WRL::ComPtr<IProtectionPolicyManagerInterop>::InternalRelease(&pcbData);
          if ( ((int (__fastcall *)(__int64, GUID *, FARPROC *))v14)(
                 v25,
                 &GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a,
                 &pcbData) >= 0
            && (*(int (__fastcall **)(FARPROC, __int64, int *))(*(_QWORD *)pcbData + 72LL))(pcbData, 2, &pvData) >= 0 )
          {
            v2 = 1;
            v1 = (_BYTE)pvData != 0;
          }
        }
        if ( v25 )
          v26();
        Microsoft::WRL::ComPtr<IProtectionPolicyManagerInterop>::InternalRelease(&pcbData);
        v13();
      }
      FreeLibrary(v12);
    }
    FreeLibrary(v9);
    if ( v2 )
      return v1;
  }
  if ( IsWindowsVersionOrGreaterEx(v8, v7, v10, v11) )
    return v1;
  pvData = 0;
  LODWORD(pcbData) = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\DataCollection",
         L"AllowTelemetry",
         0x10u,
         0,
         &pvData,
         (LPDWORD)&pcbData) )
  {
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Policies\\Microsoft\\Windows\\DataCollection",
           L"AllowTelemetry_PolicyManager",
           0x10u,
           0,
           &pvData,
           (LPDWORD)&pcbData) )
    {
      pvData = 4;
      if ( (RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection",
              L"AllowTelemetry",
              0x10u,
              0,
              &pvData,
              (LPDWORD)&pcbData)
          & 0xFFFFFFFD) != 0 )
        return v1;
    }
  }
  v17 = pvData;
  if ( !pvData )
  {
    v18 = LoadLibraryExW(L"slc.dll", 0, 0x800u);
    v19 = v18;
    if ( !v18 )
      goto LABEL_33;
    v20 = 0;
    v21 = GetProcAddress(v18, "SLGetWindowsInformationDWORD");
    if ( v21 )
    {
      LODWORD(v25) = 0;
      if ( ((int (__fastcall *)(const wchar_t *, __int64 *))v21)(L"TelemetryPermission-AllowDisable", &v25) >= 0 )
        v20 = (_DWORD)v25 == 1;
    }
    FreeLibrary(v19);
    v17 = pvData;
    if ( !v20 )
LABEL_33:
      v17 = 1;
  }
  return (v17 & 2) != 0;
}

```

## disassembly

```asm
0x180557fe8  mov     [rsp-40h+arg_0], ecx
0x180557fec  push    rbp
0x180557fed  push    rbx
0x180557fee  push    rsi
0x180557fef  push    rdi
0x180557ff0  push    r12
0x180557ff2  push    r13
0x180557ff4  push    r14
0x180557ff6  push    r15
0x180557ff8  mov     rbp, rsp
0x180557ffb  sub     rsp, 48h
0x180557fff  mov     r14d, 800h
0x180558005  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings.dll"
0x18055800c  mov     r8d, r14d; dwFlags
0x18055800f  xor     edx, edx; hFile
0x180558011  xor     bl, bl
0x180558013  xor     dil, dil
0x180558016  call    cs:__imp_LoadLibraryExW
0x18055801d  nop     dword ptr [rax+rax+00h]
0x180558022  mov     rsi, rax
0x180558025  test    rax, rax
0x180558028  jz      short loc_180558071
0x18055802a  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180558031  mov     rcx, rax; hModule
0x180558034  call    cs:__imp_GetProcAddress
0x18055803b  nop     dword ptr [rax+rax+00h]
0x180558040  test    rax, rax
0x180558043  jz      short loc_180558059
0x180558045  mov     ecx, 2
0x18055804a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055804f  test    eax, eax
0x180558051  js      short loc_180558059
0x180558053  mov     dil, 1
0x180558056  setz    bl
0x180558059  mov     rcx, rsi; hLibModule
0x18055805c  call    cs:__imp_FreeLibrary
0x180558063  nop     dword ptr [rax+rax+00h]
0x180558068  test    dil, dil
0x18055806b  jnz     loc_1805583BF
0x180558071  mov     r8d, r14d; dwFlags
0x180558074  lea     rcx, aApiMsWinCoreWi_1; "api-ms-win-core-winrt-l1-1-0.dll"
0x18055807b  xor     edx, edx; hFile
0x18055807d  call    cs:__imp_LoadLibraryExW
0x180558084  nop     dword ptr [rax+rax+00h]
0x180558089  mov     rsi, rax
0x18055808c  test    rax, rax
0x18055808f  jz      loc_180558240
0x180558095  mov     r8d, r14d; dwFlags
0x180558098  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x18055809f  xor     edx, edx; hFile
0x1805580a1  call    cs:__imp_LoadLibraryExW
0x1805580a8  nop     dword ptr [rax+rax+00h]
0x1805580ad  mov     r14, rax
0x1805580b0  test    rax, rax
0x1805580b3  jz      loc_180558222
0x1805580b9  lea     rdx, aRoinitialize; "RoInitialize"
0x1805580c0  mov     rcx, rsi; hModule
0x1805580c3  call    cs:__imp_GetProcAddress
0x1805580ca  nop     dword ptr [rax+rax+00h]
0x1805580cf  lea     rdx, aRouninitialize; "RoUninitialize"
0x1805580d6  mov     rcx, rsi; hModule
0x1805580d9  mov     [rbp+arg_8], rax
0x1805580dd  call    cs:__imp_GetProcAddress
0x1805580e4  nop     dword ptr [rax+rax+00h]
0x1805580e9  lea     rdx, aRogetactivatio; "RoGetActivationFactory"
0x1805580f0  mov     rcx, rsi; hModule
0x1805580f3  mov     r13, rax
0x1805580f6  call    cs:__imp_GetProcAddress
0x1805580fd  nop     dword ptr [rax+rax+00h]
0x180558102  lea     rdx, aWindowscreates_0; "WindowsCreateString"
0x180558109  mov     rcx, r14; hModule
0x18055810c  mov     r12, rax
0x18055810f  call    cs:__imp_GetProcAddress
0x180558116  nop     dword ptr [rax+rax+00h]
0x18055811b  lea     rdx, aWindowsdeletes; "WindowsDeleteString"
0x180558122  mov     rcx, r14; hModule
0x180558125  mov     r15, rax
0x180558128  call    cs:__imp_GetProcAddress
0x18055812f  nop     dword ptr [rax+rax+00h]
0x180558134  mov     rdx, [rbp+arg_8]
0x180558138  mov     [rbp+arg_18], rax
0x18055813c  test    rdx, rdx
0x18055813f  jz      loc_180558213
0x180558145  test    r13, r13
0x180558148  jz      loc_180558213
0x18055814e  test    r12, r12
0x180558151  jz      loc_180558213
0x180558157  test    r15, r15
0x18055815a  jz      loc_180558213
0x180558160  test    rax, rax
0x180558163  jz      loc_180558213
0x180558169  mov     ecx, 1
0x18055816e  mov     rax, rdx
0x180558171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180558176  xor     ecx, ecx
0x180558178  test    eax, eax
0x18055817a  js      loc_180558213
0x180558180  mov     [rbp+arg_10], rcx
0x180558184  lea     edx, [rcx+3Eh]
0x180558187  mov     [rbp+arg_8], rcx
0x18055818b  lea     r8, [rbp+arg_10]
0x18055818f  mov     byte ptr [rbp+arg_0], cl
0x180558192  mov     rax, r15
0x180558195  lea     rcx, ?RuntimeClass_Windows_System_Profile_PlatformDiagnosticsAndUsageDataSettings@@3QBGB; "Windows.System.Profile.PlatformDiagnost"...
0x18055819c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805581a1  test    eax, eax
0x1805581a3  js      short loc_1805581F0
0x1805581a5  lea     rcx, [rbp+arg_8]
0x1805581a9  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProtectionPolicyManagerInterop>::InternalRelease(void)
0x1805581ae  mov     rcx, [rbp+arg_10]
0x1805581b2  lea     r8, [rbp+arg_8]
0x1805581b6  lea     rdx, _GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a
0x1805581bd  mov     rax, r12
0x1805581c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805581c5  test    eax, eax
0x1805581c7  js      short loc_1805581F0
0x1805581c9  mov     rcx, [rbp+arg_8]
0x1805581cd  lea     r8, [rbp+arg_0]
0x1805581d1  mov     edx, 2
0x1805581d6  mov     rax, [rcx]
0x1805581d9  mov     rax, [rax+48h]
0x1805581dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805581e2  test    eax, eax
0x1805581e4  js      short loc_1805581F0
0x1805581e6  cmp     byte ptr [rbp+arg_0], 0
0x1805581ea  mov     dil, 1
0x1805581ed  setnz   bl
0x1805581f0  mov     rcx, [rbp+arg_10]
0x1805581f4  test    rcx, rcx
0x1805581f7  jz      short loc_180558202
0x1805581f9  mov     rax, [rbp+arg_18]
0x1805581fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180558202  lea     rcx, [rbp+arg_8]
0x180558206  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProtectionPolicyManagerInterop>::InternalRelease(void)
0x18055820b  mov     rax, r13
0x18055820e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180558213  mov     rcx, r14; hLibModule
0x180558216  call    cs:__imp_FreeLibrary
0x18055821d  nop     dword ptr [rax+rax+00h]
0x180558222  mov     rcx, rsi; hLibModule
0x180558225  call    cs:__imp_FreeLibrary
0x18055822c  nop     dword ptr [rax+rax+00h]
0x180558231  test    dil, dil
0x180558234  jnz     loc_1805583BF
0x18055823a  mov     r14d, 800h
0x180558240  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x180558245  test    al, al
0x180558247  jnz     loc_1805583BF
0x18055824d  mov     r15d, 4
0x180558253  mov     [rbp+arg_0], 0
0x18055825a  lea     rax, [rbp+arg_8]
0x18055825e  mov     dword ptr [rbp+arg_8], r15d
0x180558262  mov     [rsp+48h+pcbData], rax; pcbData
0x180558267  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x18055826e  lea     rax, [rbp+arg_0]
0x180558272  mov     rsi, 0FFFFFFFF80000002h
0x180558279  mov     [rsp+48h+pvData], rax; pvData
0x18055827e  lea     edi, [r15+0Ch]
0x180558282  mov     r9d, edi; dwFlags
0x180558285  mov     [rsp+48h+pdwType], 0; pdwType
0x18055828e  lea     rdx, aSoftwarePolici_11; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180558295  mov     rcx, rsi; hkey
0x180558298  call    cs:__imp_RegGetValueW
0x18055829f  nop     dword ptr [rax+rax+00h]
0x1805582a4  test    eax, eax
0x1805582a6  jz      loc_180558335
0x1805582ac  lea     rax, [rbp+arg_8]
0x1805582b0  mov     r9d, edi; dwFlags
0x1805582b3  mov     [rsp+48h+pcbData], rax; pcbData
0x1805582b8  lea     r8, aAllowtelemetry; "AllowTelemetry_PolicyManager"
0x1805582bf  lea     rax, [rbp+arg_0]
0x1805582c3  mov     rcx, rsi; hkey
0x1805582c6  mov     [rsp+48h+pvData], rax; pvData
0x1805582cb  lea     rdx, aSoftwarePolici_11; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1805582d2  mov     [rsp+48h+pdwType], 0; pdwType
0x1805582db  call    cs:__imp_RegGetValueW
0x1805582e2  nop     dword ptr [rax+rax+00h]
0x1805582e7  test    eax, eax
0x1805582e9  jz      short loc_180558335
0x1805582eb  lea     rax, [rbp+arg_8]
0x1805582ef  mov     [rbp+arg_0], r15d
0x1805582f3  mov     [rsp+48h+pcbData], rax; pcbData
0x1805582f8  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x1805582ff  lea     rax, [rbp+arg_0]
0x180558303  mov     r9d, edi; dwFlags
0x180558306  mov     [rsp+48h+pvData], rax; pvData
0x18055830b  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180558312  mov     rcx, rsi; hkey
0x180558315  mov     [rsp+48h+pdwType], 0; pdwType
0x18055831e  call    cs:__imp_RegGetValueW
0x180558325  nop     dword ptr [rax+rax+00h]
0x18055832a  test    eax, 0FFFFFFFDh
0x18055832f  jnz     loc_1805583BF
0x180558335  mov     eax, [rbp+arg_0]
0x180558338  test    eax, eax
0x18055833a  jnz     short loc_1805583B9
0x18055833c  mov     r8d, r14d; dwFlags
0x18055833f  lea     rcx, aSlcDll_0; "slc.dll"
0x180558346  xor     edx, edx; hFile
0x180558348  call    cs:__imp_LoadLibraryExW
0x18055834f  nop     dword ptr [rax+rax+00h]
0x180558354  mov     rbx, rax
0x180558357  test    rax, rax
0x18055835a  jz      short loc_1805583B4
0x18055835c  lea     rdx, aSlgetwindowsin_1; "SLGetWindowsInformationDWORD"
0x180558363  mov     rcx, rax; hModule
0x180558366  xor     dil, dil
0x180558369  call    cs:__imp_GetProcAddress
0x180558370  nop     dword ptr [rax+rax+00h]
0x180558375  test    rax, rax
0x180558378  jz      short loc_18055839D
0x18055837a  lea     rdx, [rbp+arg_10]
0x18055837e  mov     dword ptr [rbp+arg_10], 0
0x180558385  lea     rcx, aTelemetrypermi; "TelemetryPermission-AllowDisable"
0x18055838c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180558391  test    eax, eax
0x180558393  js      short loc_18055839D
0x180558395  cmp     dword ptr [rbp+arg_10], 1
0x180558399  setz    dil
0x18055839d  mov     rcx, rbx; hLibModule
0x1805583a0  call    cs:__imp_FreeLibrary
0x1805583a7  nop     dword ptr [rax+rax+00h]
0x1805583ac  mov     eax, [rbp+arg_0]
0x1805583af  test    dil, dil
0x1805583b2  jnz     short loc_1805583B9
0x1805583b4  mov     eax, 1
0x1805583b9  shr     eax, 1
0x1805583bb  and     al, 1
0x1805583bd  jmp     short loc_1805583C1
0x1805583bf  mov     al, bl
0x1805583c1  add     rsp, 48h
0x1805583c5  pop     r15
0x1805583c7  pop     r14
0x1805583c9  pop     r13
0x1805583cb  pop     r12
0x1805583cd  pop     rdi
0x1805583ce  pop     rsi
0x1805583cf  pop     rbx
0x1805583d0  pop     rbp
0x1805583d1  retn
```
