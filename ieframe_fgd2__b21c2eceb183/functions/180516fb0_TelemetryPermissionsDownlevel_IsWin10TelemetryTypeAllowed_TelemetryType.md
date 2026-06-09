# TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)

- ea: `0x180516fb0`
- end: `0x180517326`
- name: `?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z`
- size: `886`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000679c`
- `0x180009d18`
- `0x180066380`
- `0x180073a10`
- `0x18007eba8`
- `0x180167f58`
- `0x1801681a0`
- `0x180517448`
- `0x180518a50`

## callees

- `0x1800876bc`
- `0x180516fb0`
- `0x18051732c`
- `0x180550010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180517018`
- `KERNEL32!FreeLibrary` at `0x1805171a2`
- `KERNEL32!FreeLibrary` at `0x1805171ab`
- `KERNEL32!FreeLibrary` at `0x1805172fa`
- `KERNEL32!FreeLibrary` at `0x180517018`
- `KERNEL32!FreeLibrary` at `0x1805171a2`
- `KERNEL32!FreeLibrary` at `0x1805171ab`
- `KERNEL32!FreeLibrary` at `0x1805172fa`
- `KERNEL32!LoadLibraryExW` at `0x180516fde`
- `KERNEL32!LoadLibraryExW` at `0x180517033`
- `KERNEL32!LoadLibraryExW` at `0x180517051`
- `KERNEL32!LoadLibraryExW` at `0x1805172ae`
- `KERNEL32!LoadLibraryExW` at `0x180516fde`
- `KERNEL32!LoadLibraryExW` at `0x180517033`
- `KERNEL32!LoadLibraryExW` at `0x180517051`
- `KERNEL32!LoadLibraryExW` at `0x1805172ae`
- `KERNEL32!GetProcAddress` at `0x180516ff6`
- `KERNEL32!GetProcAddress` at `0x18051706d`
- `KERNEL32!GetProcAddress` at `0x180517081`
- `KERNEL32!GetProcAddress` at `0x180517094`
- `KERNEL32!GetProcAddress` at `0x1805170a7`
- `KERNEL32!GetProcAddress` at `0x1805170ba`
- `KERNEL32!GetProcAddress` at `0x1805172c9`
- `KERNEL32!GetProcAddress` at `0x180516ff6`
- `KERNEL32!GetProcAddress` at `0x18051706d`
- `KERNEL32!GetProcAddress` at `0x180517081`
- `KERNEL32!GetProcAddress` at `0x180517094`
- `KERNEL32!GetProcAddress` at `0x1805170a7`
- `KERNEL32!GetProcAddress` at `0x1805170ba`
- `KERNEL32!GetProcAddress` at `0x1805172c9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180517218`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180517251`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x18051728e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180517218`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180517251`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x18051728e`

## string_xrefs

- `0x18051709a`: `WindowsCreateString`
- `0x1805170ad`: `WindowsDeleteString`
- `0x180517048`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x18051702a`: `api-ms-win-core-winrt-l1-1-0.dll`
- `0x1805172a5`: `slc.dll`
- `0x180516fcd`: `DiagnosticDataSettings.dll`

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
0x180516fb0  mov     [rsp-40h+arg_0], ecx
0x180516fb4  push    rbp
0x180516fb5  push    rbx
0x180516fb6  push    rsi
0x180516fb7  push    rdi
0x180516fb8  push    r12
0x180516fba  push    r13
0x180516fbc  push    r14
0x180516fbe  push    r15
0x180516fc0  mov     rbp, rsp
0x180516fc3  sub     rsp, 48h
0x180516fc7  mov     r14d, 800h
0x180516fcd  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings.dll"
0x180516fd4  mov     r8d, r14d; dwFlags
0x180516fd7  xor     edx, edx; hFile
0x180516fd9  xor     bl, bl
0x180516fdb  xor     dil, dil
0x180516fde  call    cs:__imp_LoadLibraryExW
0x180516fe4  mov     rsi, rax
0x180516fe7  test    rax, rax
0x180516fea  jz      short loc_180517027
0x180516fec  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180516ff3  mov     rcx, rax; hModule
0x180516ff6  call    cs:__imp_GetProcAddress
0x180516ffc  test    rax, rax
0x180516fff  jz      short loc_180517015
0x180517001  mov     ecx, 2
0x180517006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051700b  test    eax, eax
0x18051700d  js      short loc_180517015
0x18051700f  mov     dil, 1
0x180517012  setz    bl
0x180517015  mov     rcx, rsi; hLibModule
0x180517018  call    cs:__imp_FreeLibrary
0x18051701e  test    dil, dil
0x180517021  jnz     loc_180517313
0x180517027  mov     r8d, r14d; dwFlags
0x18051702a  lea     rcx, aApiMsWinCoreWi_1; "api-ms-win-core-winrt-l1-1-0.dll"
0x180517031  xor     edx, edx; hFile
0x180517033  call    cs:__imp_LoadLibraryExW
0x180517039  mov     rsi, rax
0x18051703c  test    rax, rax
0x18051703f  jz      loc_1805171C0
0x180517045  mov     r8d, r14d; dwFlags
0x180517048  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x18051704f  xor     edx, edx; hFile
0x180517051  call    cs:__imp_LoadLibraryExW
0x180517057  mov     r14, rax
0x18051705a  test    rax, rax
0x18051705d  jz      loc_1805171A8
0x180517063  lea     rdx, aRoinitialize; "RoInitialize"
0x18051706a  mov     rcx, rsi; hModule
0x18051706d  call    cs:__imp_GetProcAddress
0x180517073  lea     rdx, aRouninitialize; "RoUninitialize"
0x18051707a  mov     rcx, rsi; hModule
0x18051707d  mov     [rbp+arg_8], rax
0x180517081  call    cs:__imp_GetProcAddress
0x180517087  lea     rdx, aRogetactivatio; "RoGetActivationFactory"
0x18051708e  mov     rcx, rsi; hModule
0x180517091  mov     r13, rax
0x180517094  call    cs:__imp_GetProcAddress
0x18051709a  lea     rdx, aWindowscreates_0; "WindowsCreateString"
0x1805170a1  mov     rcx, r14; hModule
0x1805170a4  mov     r12, rax
0x1805170a7  call    cs:__imp_GetProcAddress
0x1805170ad  lea     rdx, aWindowsdeletes; "WindowsDeleteString"
0x1805170b4  mov     rcx, r14; hModule
0x1805170b7  mov     r15, rax
0x1805170ba  call    cs:__imp_GetProcAddress
0x1805170c0  mov     rdx, [rbp+arg_8]
0x1805170c4  mov     [rbp+arg_18], rax
0x1805170c8  test    rdx, rdx
0x1805170cb  jz      loc_18051719F
0x1805170d1  test    r13, r13
0x1805170d4  jz      loc_18051719F
0x1805170da  test    r12, r12
0x1805170dd  jz      loc_18051719F
0x1805170e3  test    r15, r15
0x1805170e6  jz      loc_18051719F
0x1805170ec  test    rax, rax
0x1805170ef  jz      loc_18051719F
0x1805170f5  mov     ecx, 1
0x1805170fa  mov     rax, rdx
0x1805170fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180517102  xor     ecx, ecx
0x180517104  test    eax, eax
0x180517106  js      loc_18051719F
0x18051710c  mov     [rbp+arg_10], rcx
0x180517110  lea     edx, [rcx+3Eh]
0x180517113  mov     [rbp+arg_8], rcx
0x180517117  lea     r8, [rbp+arg_10]
0x18051711b  mov     byte ptr [rbp+arg_0], cl
0x18051711e  mov     rax, r15
0x180517121  lea     rcx, ?RuntimeClass_Windows_System_Profile_PlatformDiagnosticsAndUsageDataSettings@@3QBGB; "Windows.System.Profile.PlatformDiagnost"...
0x180517128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051712d  test    eax, eax
0x18051712f  js      short loc_18051717C
0x180517131  lea     rcx, [rbp+arg_8]
0x180517135  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProtectionPolicyManagerInterop>::InternalRelease(void)
0x18051713a  mov     rcx, [rbp+arg_10]
0x18051713e  lea     r8, [rbp+arg_8]
0x180517142  lea     rdx, _GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a
0x180517149  mov     rax, r12
0x18051714c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180517151  test    eax, eax
0x180517153  js      short loc_18051717C
0x180517155  mov     rcx, [rbp+arg_8]
0x180517159  lea     r8, [rbp+arg_0]
0x18051715d  mov     edx, 2
0x180517162  mov     rax, [rcx]
0x180517165  mov     rax, [rax+48h]
0x180517169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051716e  test    eax, eax
0x180517170  js      short loc_18051717C
0x180517172  cmp     byte ptr [rbp+arg_0], 0
0x180517176  mov     dil, 1
0x180517179  setnz   bl
0x18051717c  mov     rcx, [rbp+arg_10]
0x180517180  test    rcx, rcx
0x180517183  jz      short loc_18051718E
0x180517185  mov     rax, [rbp+arg_18]
0x180517189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051718e  lea     rcx, [rbp+arg_8]
0x180517192  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProtectionPolicyManagerInterop>::InternalRelease(void)
0x180517197  mov     rax, r13
0x18051719a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051719f  mov     rcx, r14; hLibModule
0x1805171a2  call    cs:__imp_FreeLibrary
0x1805171a8  mov     rcx, rsi; hLibModule
0x1805171ab  call    cs:__imp_FreeLibrary
0x1805171b1  test    dil, dil
0x1805171b4  jnz     loc_180517313
0x1805171ba  mov     r14d, 800h
0x1805171c0  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1805171c5  test    al, al
0x1805171c7  jnz     loc_180517313
0x1805171cd  mov     r15d, 4
0x1805171d3  mov     [rbp+arg_0], 0
0x1805171da  lea     rax, [rbp+arg_8]
0x1805171de  mov     dword ptr [rbp+arg_8], r15d
0x1805171e2  mov     [rsp+48h+pcbData], rax; pcbData
0x1805171e7  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x1805171ee  lea     rax, [rbp+arg_0]
0x1805171f2  mov     rsi, 0FFFFFFFF80000002h
0x1805171f9  mov     [rsp+48h+pvData], rax; pvData
0x1805171fe  lea     edi, [r15+0Ch]
0x180517202  mov     r9d, edi; dwFlags
0x180517205  mov     [rsp+48h+pdwType], 0; pdwType
0x18051720e  lea     rdx, aSoftwarePolici_11; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180517215  mov     rcx, rsi; hkey
0x180517218  call    cs:__imp_RegGetValueW
0x18051721e  test    eax, eax
0x180517220  jz      short loc_18051729B
0x180517222  lea     rax, [rbp+arg_8]
0x180517226  mov     r9d, edi; dwFlags
0x180517229  mov     [rsp+48h+pcbData], rax; pcbData
0x18051722e  lea     r8, aAllowtelemetry; "AllowTelemetry_PolicyManager"
0x180517235  lea     rax, [rbp+arg_0]
0x180517239  mov     rcx, rsi; hkey
0x18051723c  mov     [rsp+48h+pvData], rax; pvData
0x180517241  lea     rdx, aSoftwarePolici_11; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180517248  mov     [rsp+48h+pdwType], 0; pdwType
0x180517251  call    cs:__imp_RegGetValueW
0x180517257  test    eax, eax
0x180517259  jz      short loc_18051729B
0x18051725b  lea     rax, [rbp+arg_8]
0x18051725f  mov     [rbp+arg_0], r15d
0x180517263  mov     [rsp+48h+pcbData], rax; pcbData
0x180517268  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x18051726f  lea     rax, [rbp+arg_0]
0x180517273  mov     r9d, edi; dwFlags
0x180517276  mov     [rsp+48h+pvData], rax; pvData
0x18051727b  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180517282  mov     rcx, rsi; hkey
0x180517285  mov     [rsp+48h+pdwType], 0; pdwType
0x18051728e  call    cs:__imp_RegGetValueW
0x180517294  test    eax, 0FFFFFFFDh
0x180517299  jnz     short loc_180517313
0x18051729b  mov     eax, [rbp+arg_0]
0x18051729e  test    eax, eax
0x1805172a0  jnz     short loc_18051730D
0x1805172a2  mov     r8d, r14d; dwFlags
0x1805172a5  lea     rcx, aSlcDll_0; "slc.dll"
0x1805172ac  xor     edx, edx; hFile
0x1805172ae  call    cs:__imp_LoadLibraryExW
0x1805172b4  mov     rbx, rax
0x1805172b7  test    rax, rax
0x1805172ba  jz      short loc_180517308
0x1805172bc  lea     rdx, aSlgetwindowsin_1; "SLGetWindowsInformationDWORD"
0x1805172c3  mov     rcx, rax; hModule
0x1805172c6  xor     dil, dil
0x1805172c9  call    cs:__imp_GetProcAddress
0x1805172cf  test    rax, rax
0x1805172d2  jz      short loc_1805172F7
0x1805172d4  lea     rdx, [rbp+arg_10]
0x1805172d8  mov     dword ptr [rbp+arg_10], 0
0x1805172df  lea     rcx, aTelemetrypermi; "TelemetryPermission-AllowDisable"
0x1805172e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805172eb  test    eax, eax
0x1805172ed  js      short loc_1805172F7
0x1805172ef  cmp     dword ptr [rbp+arg_10], 1
0x1805172f3  setz    dil
0x1805172f7  mov     rcx, rbx; hLibModule
0x1805172fa  call    cs:__imp_FreeLibrary
0x180517300  mov     eax, [rbp+arg_0]
0x180517303  test    dil, dil
0x180517306  jnz     short loc_18051730D
0x180517308  mov     eax, 1
0x18051730d  shr     eax, 1
0x18051730f  and     al, 1
0x180517311  jmp     short loc_180517315
0x180517313  mov     al, bl
0x180517315  add     rsp, 48h
0x180517319  pop     r15
0x18051731b  pop     r14
0x18051731d  pop     r13
0x18051731f  pop     r12
0x180517321  pop     rdi
0x180517322  pop     rsi
0x180517323  pop     rbx
0x180517324  pop     rbp
0x180517325  retn
```
