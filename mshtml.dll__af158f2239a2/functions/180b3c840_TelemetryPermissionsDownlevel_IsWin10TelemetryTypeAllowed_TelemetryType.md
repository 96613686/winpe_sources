# TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)

- ea: `0x180b3c840`
- end: `0x180b3cbb6`
- name: `?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z`
- size: `886`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180b3c79c`

## callees

- `0x1804a3948`
- `0x180b3c840`
- `0x180b3cbbc`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180b3c86e`
- `KERNEL32!LoadLibraryExW` at `0x180b3c8c3`
- `KERNEL32!LoadLibraryExW` at `0x180b3c8e1`
- `KERNEL32!LoadLibraryExW` at `0x180b3cb3e`
- `KERNEL32!LoadLibraryExW` at `0x180b3c86e`
- `KERNEL32!LoadLibraryExW` at `0x180b3c8c3`
- `KERNEL32!LoadLibraryExW` at `0x180b3c8e1`
- `KERNEL32!LoadLibraryExW` at `0x180b3cb3e`
- `KERNEL32!GetProcAddress` at `0x180b3c886`
- `KERNEL32!GetProcAddress` at `0x180b3c8fd`
- `KERNEL32!GetProcAddress` at `0x180b3c911`
- `KERNEL32!GetProcAddress` at `0x180b3c924`
- `KERNEL32!GetProcAddress` at `0x180b3c937`
- `KERNEL32!GetProcAddress` at `0x180b3c94a`
- `KERNEL32!GetProcAddress` at `0x180b3cb59`
- `KERNEL32!GetProcAddress` at `0x180b3c886`
- `KERNEL32!GetProcAddress` at `0x180b3c8fd`
- `KERNEL32!GetProcAddress` at `0x180b3c911`
- `KERNEL32!GetProcAddress` at `0x180b3c924`
- `KERNEL32!GetProcAddress` at `0x180b3c937`
- `KERNEL32!GetProcAddress` at `0x180b3c94a`
- `KERNEL32!GetProcAddress` at `0x180b3cb59`
- `KERNEL32!FreeLibrary` at `0x180b3c8a8`
- `KERNEL32!FreeLibrary` at `0x180b3ca32`
- `KERNEL32!FreeLibrary` at `0x180b3ca3b`
- `KERNEL32!FreeLibrary` at `0x180b3cb8a`
- `KERNEL32!FreeLibrary` at `0x180b3c8a8`
- `KERNEL32!FreeLibrary` at `0x180b3ca32`
- `KERNEL32!FreeLibrary` at `0x180b3ca3b`
- `KERNEL32!FreeLibrary` at `0x180b3cb8a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b3caa8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b3cae1`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b3cb1e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b3caa8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b3cae1`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b3cb1e`

## string_xrefs

- `0x180b3c8d8`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x180b3c92a`: `WindowsCreateString`
- `0x180b3c93d`: `WindowsDeleteString`
- `0x180b3c8ba`: `api-ms-win-core-winrt-l1-1-0.dll`
- `0x180b3c85d`: `DiagnosticDataSettings.dll`
- `0x180b3cb35`: `slc.dll`

## pseudocode

```c
bool TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed()
{
  bool v0; // bl
  char v1; // di
  HMODULE Library; // rax
  HMODULE v3; // rsi
  FARPROC ProcAddress; // rax
  int v5; // eax
  unsigned __int16 v6; // dx
  unsigned __int16 v7; // cx
  HMODULE v8; // rsi
  unsigned __int16 v9; // r8
  unsigned __int16 v10; // r9
  HMODULE v11; // r14
  void (*v12)(void); // r13
  FARPROC v13; // r12
  FARPROC v14; // r15
  FARPROC v15; // rax
  char v16; // al
  HMODULE v17; // rax
  HMODULE v18; // rbx
  bool v19; // di
  FARPROC v20; // rax
  _BYTE v22[8]; // [rsp+40h] [rbp-28h] BYREF
  void (*pvData)(void); // [rsp+48h] [rbp-20h] BYREF
  DWORD pcbData[2]; // [rsp+50h] [rbp-18h] BYREF
  _QWORD v25[2]; // [rsp+58h] [rbp-10h] BYREF

  v0 = 0;
  v1 = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings.dll", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TelIsTelemetryTypeAllowed");
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(__int64))ProcAddress)(2);
      if ( v5 >= 0 )
      {
        v1 = 1;
        v0 = v5 == 0;
      }
    }
    FreeLibrary(v3);
    if ( v1 )
      return v0;
  }
  v8 = LoadLibraryExW(L"api-ms-win-core-winrt-l1-1-0.dll", 0, 0x800u);
  if ( v8 )
  {
    v11 = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
    if ( v11 )
    {
      v25[0] = GetProcAddress(v8, "RoInitialize");
      v12 = (void (*)(void))GetProcAddress(v8, "RoUninitialize");
      v13 = GetProcAddress(v8, "RoGetActivationFactory");
      v14 = GetProcAddress(v11, "WindowsCreateString");
      v15 = GetProcAddress(v11, "WindowsDeleteString");
      pvData = (void (*)(void))v15;
      if ( v25[0] && v12 && v13 && v14 && v15 && ((int (__fastcall *)(__int64))v25[0])(1) >= 0 )
      {
        *(_QWORD *)pcbData = 0;
        v25[0] = 0;
        v22[0] = 0;
        if ( ((int (__fastcall *)(const unsigned __int16 *, __int64, DWORD *))v14)(
               L"Windows.System.Profile.PlatformDiagnosticsAndUsageDataSettings",
               62,
               pcbData) >= 0 )
        {
          Microsoft::WRL::ComPtr<ISpellingError>::InternalRelease(v25);
          if ( ((int (__fastcall *)(_QWORD, GUID *, _QWORD *))v13)(
                 *(_QWORD *)pcbData,
                 &GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a,
                 v25) >= 0
            && (*(int (__fastcall **)(_QWORD, __int64, _BYTE *))(*(_QWORD *)v25[0] + 72LL))(v25[0], 2, v22) >= 0 )
          {
            v1 = 1;
            v0 = v22[0] != 0;
          }
        }
        if ( *(_QWORD *)pcbData )
          pvData();
        Microsoft::WRL::ComPtr<ISpellingError>::InternalRelease(v25);
        v12();
      }
      FreeLibrary(v11);
    }
    FreeLibrary(v8);
    if ( v1 )
      return v0;
  }
  if ( IsWindowsVersionOrGreaterEx(v7, v6, v9, v10) )
    return v0;
  LODWORD(pvData) = 0;
  pcbData[0] = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\DataCollection",
         L"AllowTelemetry",
         0x10u,
         0,
         &pvData,
         pcbData) )
  {
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Policies\\Microsoft\\Windows\\DataCollection",
           L"AllowTelemetry_PolicyManager",
           0x10u,
           0,
           &pvData,
           pcbData) )
    {
      LODWORD(pvData) = 4;
      if ( (RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection",
              L"AllowTelemetry",
              0x10u,
              0,
              &pvData,
              pcbData)
          & 0xFFFFFFFD) != 0 )
        return v0;
    }
  }
  v16 = (char)pvData;
  if ( !(_DWORD)pvData )
  {
    v17 = LoadLibraryExW(L"slc.dll", 0, 0x800u);
    v18 = v17;
    if ( !v17 )
      goto LABEL_33;
    v19 = 0;
    v20 = GetProcAddress(v17, "SLGetWindowsInformationDWORD");
    if ( v20 )
    {
      LODWORD(v25[0]) = 0;
      if ( ((int (__fastcall *)(const wchar_t *, _QWORD *))v20)(L"TelemetryPermission-AllowDisable", v25) >= 0 )
        v19 = LODWORD(v25[0]) == 1;
    }
    FreeLibrary(v18);
    v16 = (char)pvData;
    if ( !v19 )
LABEL_33:
      v16 = 1;
  }
  return (v16 & 2) != 0;
}

```

## disassembly

```asm
0x180b3c840  mov     [rsp-40h+arg_0], ecx
0x180b3c844  push    rbp
0x180b3c845  push    rbx
0x180b3c846  push    rsi
0x180b3c847  push    rdi
0x180b3c848  push    r12
0x180b3c84a  push    r13
0x180b3c84c  push    r14
0x180b3c84e  push    r15
0x180b3c850  mov     rbp, rsp
0x180b3c853  sub     rsp, 68h
0x180b3c857  mov     r14d, 800h
0x180b3c85d  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings.dll"
0x180b3c864  mov     r8d, r14d; dwFlags
0x180b3c867  xor     edx, edx; hFile
0x180b3c869  xor     bl, bl
0x180b3c86b  xor     dil, dil
0x180b3c86e  call    cs:__imp_LoadLibraryExW
0x180b3c874  mov     rsi, rax
0x180b3c877  test    rax, rax
0x180b3c87a  jz      short loc_180B3C8B7
0x180b3c87c  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180b3c883  mov     rcx, rax; hModule
0x180b3c886  call    cs:__imp_GetProcAddress
0x180b3c88c  test    rax, rax
0x180b3c88f  jz      short loc_180B3C8A5
0x180b3c891  mov     ecx, 2
0x180b3c896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b3c89b  test    eax, eax
0x180b3c89d  js      short loc_180B3C8A5
0x180b3c89f  mov     dil, 1
0x180b3c8a2  setz    bl
0x180b3c8a5  mov     rcx, rsi; hLibModule
0x180b3c8a8  call    cs:__imp_FreeLibrary
0x180b3c8ae  test    dil, dil
0x180b3c8b1  jnz     loc_180B3CBA3
0x180b3c8b7  mov     r8d, r14d; dwFlags
0x180b3c8ba  lea     rcx, aApiMsWinCoreWi_4; "api-ms-win-core-winrt-l1-1-0.dll"
0x180b3c8c1  xor     edx, edx; hFile
0x180b3c8c3  call    cs:__imp_LoadLibraryExW
0x180b3c8c9  mov     rsi, rax
0x180b3c8cc  test    rax, rax
0x180b3c8cf  jz      loc_180B3CA50
0x180b3c8d5  mov     r8d, r14d; dwFlags
0x180b3c8d8  lea     rcx, aApiMsWinCoreWi_3; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x180b3c8df  xor     edx, edx; hFile
0x180b3c8e1  call    cs:__imp_LoadLibraryExW
0x180b3c8e7  mov     r14, rax
0x180b3c8ea  test    rax, rax
0x180b3c8ed  jz      loc_180B3CA38
0x180b3c8f3  lea     rdx, aRoinitialize_0; "RoInitialize"
0x180b3c8fa  mov     rcx, rsi; hModule
0x180b3c8fd  call    cs:__imp_GetProcAddress
0x180b3c903  lea     rdx, aRouninitialize_0; "RoUninitialize"
0x180b3c90a  mov     rcx, rsi; hModule
0x180b3c90d  mov     [rbp+var_10], rax
0x180b3c911  call    cs:__imp_GetProcAddress
0x180b3c917  lea     rdx, aRogetactivatio_0; "RoGetActivationFactory"
0x180b3c91e  mov     rcx, rsi; hModule
0x180b3c921  mov     r13, rax
0x180b3c924  call    cs:__imp_GetProcAddress
0x180b3c92a  lea     rdx, aWindowscreates_2; "WindowsCreateString"
0x180b3c931  mov     rcx, r14; hModule
0x180b3c934  mov     r12, rax
0x180b3c937  call    cs:__imp_GetProcAddress
0x180b3c93d  lea     rdx, aWindowsdeletes_0; "WindowsDeleteString"
0x180b3c944  mov     rcx, r14; hModule
0x180b3c947  mov     r15, rax
0x180b3c94a  call    cs:__imp_GetProcAddress
0x180b3c950  mov     rdx, [rbp+var_10]
0x180b3c954  mov     [rbp+var_20], rax
0x180b3c958  test    rdx, rdx
0x180b3c95b  jz      loc_180B3CA2F
0x180b3c961  test    r13, r13
0x180b3c964  jz      loc_180B3CA2F
0x180b3c96a  test    r12, r12
0x180b3c96d  jz      loc_180B3CA2F
0x180b3c973  test    r15, r15
0x180b3c976  jz      loc_180B3CA2F
0x180b3c97c  test    rax, rax
0x180b3c97f  jz      loc_180B3CA2F
0x180b3c985  mov     ecx, 1
0x180b3c98a  mov     rax, rdx
0x180b3c98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b3c992  xor     ecx, ecx
0x180b3c994  test    eax, eax
0x180b3c996  js      loc_180B3CA2F
0x180b3c99c  mov     qword ptr [rbp+var_18], rcx
0x180b3c9a0  lea     edx, [rcx+3Eh]
0x180b3c9a3  mov     [rbp+var_10], rcx
0x180b3c9a7  lea     r8, [rbp+var_18]
0x180b3c9ab  mov     [rbp+var_28], cl
0x180b3c9ae  mov     rax, r15
0x180b3c9b1  lea     rcx, ?RuntimeClass_Windows_System_Profile_PlatformDiagnosticsAndUsageDataSettings@@3QBGB; "Windows.System.Profile.PlatformDiagnost"...
0x180b3c9b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b3c9bd  test    eax, eax
0x180b3c9bf  js      short loc_180B3CA0C
0x180b3c9c1  lea     rcx, [rbp+var_10]
0x180b3c9c5  call    ?InternalRelease@?$ComPtr@UISpellingError@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpellingError>::InternalRelease(void)
0x180b3c9ca  mov     rcx, qword ptr [rbp+var_18]
0x180b3c9ce  lea     r8, [rbp+var_10]
0x180b3c9d2  lea     rdx, _GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a
0x180b3c9d9  mov     rax, r12
0x180b3c9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b3c9e1  test    eax, eax
0x180b3c9e3  js      short loc_180B3CA0C
0x180b3c9e5  mov     rcx, [rbp+var_10]
0x180b3c9e9  lea     r8, [rbp+var_28]
0x180b3c9ed  mov     edx, 2
0x180b3c9f2  mov     rax, [rcx]
0x180b3c9f5  mov     rax, [rax+48h]
0x180b3c9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b3c9fe  test    eax, eax
0x180b3ca00  js      short loc_180B3CA0C
0x180b3ca02  cmp     [rbp+var_28], 0
0x180b3ca06  mov     dil, 1
0x180b3ca09  setnz   bl
0x180b3ca0c  mov     rcx, qword ptr [rbp+var_18]
0x180b3ca10  test    rcx, rcx
0x180b3ca13  jz      short loc_180B3CA1E
0x180b3ca15  mov     rax, [rbp+var_20]
0x180b3ca19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b3ca1e  lea     rcx, [rbp+var_10]
0x180b3ca22  call    ?InternalRelease@?$ComPtr@UISpellingError@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpellingError>::InternalRelease(void)
0x180b3ca27  mov     rax, r13
0x180b3ca2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b3ca2f  mov     rcx, r14; hLibModule
0x180b3ca32  call    cs:__imp_FreeLibrary
0x180b3ca38  mov     rcx, rsi; hLibModule
0x180b3ca3b  call    cs:__imp_FreeLibrary
0x180b3ca41  test    dil, dil
0x180b3ca44  jnz     loc_180B3CBA3
0x180b3ca4a  mov     r14d, 800h
0x180b3ca50  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x180b3ca55  test    al, al
0x180b3ca57  jnz     loc_180B3CBA3
0x180b3ca5d  mov     r15d, 4
0x180b3ca63  mov     dword ptr [rbp+var_20], 0
0x180b3ca6a  lea     rax, [rbp+var_18]
0x180b3ca6e  mov     [rbp+var_18], r15d
0x180b3ca72  mov     [rsp+68h+pcbData], rax; pcbData
0x180b3ca77  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x180b3ca7e  lea     rax, [rbp+var_20]
0x180b3ca82  mov     rsi, 0FFFFFFFF80000002h
0x180b3ca89  mov     [rsp+68h+pvData], rax; pvData
0x180b3ca8e  lea     edi, [r15+0Ch]
0x180b3ca92  mov     r9d, edi; dwFlags
0x180b3ca95  mov     [rsp+68h+pdwType], 0; pdwType
0x180b3ca9e  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180b3caa5  mov     rcx, rsi; hkey
0x180b3caa8  call    cs:__imp_RegGetValueW
0x180b3caae  test    eax, eax
0x180b3cab0  jz      short loc_180B3CB2B
0x180b3cab2  lea     rax, [rbp+var_18]
0x180b3cab6  mov     r9d, edi; dwFlags
0x180b3cab9  mov     [rsp+68h+pcbData], rax; pcbData
0x180b3cabe  lea     r8, aAllowtelemetry; "AllowTelemetry_PolicyManager"
0x180b3cac5  lea     rax, [rbp+var_20]
0x180b3cac9  mov     rcx, rsi; hkey
0x180b3cacc  mov     [rsp+68h+pvData], rax; pvData
0x180b3cad1  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180b3cad8  mov     [rsp+68h+pdwType], 0; pdwType
0x180b3cae1  call    cs:__imp_RegGetValueW
0x180b3cae7  test    eax, eax
0x180b3cae9  jz      short loc_180B3CB2B
0x180b3caeb  lea     rax, [rbp+var_18]
0x180b3caef  mov     dword ptr [rbp+var_20], r15d
0x180b3caf3  mov     [rsp+68h+pcbData], rax; pcbData
0x180b3caf8  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x180b3caff  lea     rax, [rbp+var_20]
0x180b3cb03  mov     r9d, edi; dwFlags
0x180b3cb06  mov     [rsp+68h+pvData], rax; pvData
0x180b3cb0b  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180b3cb12  mov     rcx, rsi; hkey
0x180b3cb15  mov     [rsp+68h+pdwType], 0; pdwType
0x180b3cb1e  call    cs:__imp_RegGetValueW
0x180b3cb24  test    eax, 0FFFFFFFDh
0x180b3cb29  jnz     short loc_180B3CBA3
0x180b3cb2b  mov     eax, dword ptr [rbp+var_20]
0x180b3cb2e  test    eax, eax
0x180b3cb30  jnz     short loc_180B3CB9D
0x180b3cb32  mov     r8d, r14d; dwFlags
0x180b3cb35  lea     rcx, aSlcDll; "slc.dll"
0x180b3cb3c  xor     edx, edx; hFile
0x180b3cb3e  call    cs:__imp_LoadLibraryExW
0x180b3cb44  mov     rbx, rax
0x180b3cb47  test    rax, rax
0x180b3cb4a  jz      short loc_180B3CB98
0x180b3cb4c  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x180b3cb53  mov     rcx, rax; hModule
0x180b3cb56  xor     dil, dil
0x180b3cb59  call    cs:__imp_GetProcAddress
0x180b3cb5f  test    rax, rax
0x180b3cb62  jz      short loc_180B3CB87
0x180b3cb64  lea     rdx, [rbp+var_10]
0x180b3cb68  mov     dword ptr [rbp+var_10], 0
0x180b3cb6f  lea     rcx, aTelemetrypermi; "TelemetryPermission-AllowDisable"
0x180b3cb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b3cb7b  test    eax, eax
0x180b3cb7d  js      short loc_180B3CB87
0x180b3cb7f  cmp     dword ptr [rbp+var_10], 1
0x180b3cb83  setz    dil
0x180b3cb87  mov     rcx, rbx; hLibModule
0x180b3cb8a  call    cs:__imp_FreeLibrary
0x180b3cb90  mov     eax, dword ptr [rbp+var_20]
0x180b3cb93  test    dil, dil
0x180b3cb96  jnz     short loc_180B3CB9D
0x180b3cb98  mov     eax, 1
0x180b3cb9d  shr     eax, 1
0x180b3cb9f  and     al, 1
0x180b3cba1  jmp     short loc_180B3CBA5
0x180b3cba3  mov     al, bl
0x180b3cba5  add     rsp, 68h
0x180b3cba9  pop     r15
0x180b3cbab  pop     r14
0x180b3cbad  pop     r13
0x180b3cbaf  pop     r12
0x180b3cbb1  pop     rdi
0x180b3cbb2  pop     rsi
0x180b3cbb3  pop     rbx
0x180b3cbb4  pop     rbp
0x180b3cbb5  retn
```
