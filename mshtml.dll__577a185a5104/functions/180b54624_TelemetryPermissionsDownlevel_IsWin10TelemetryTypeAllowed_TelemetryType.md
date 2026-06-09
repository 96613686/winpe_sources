# TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)

- ea: `0x180b54624`
- end: `0x180b54a0f`
- name: `?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180b54568`

## callees

- `0x180272880`
- `0x180b54624`
- `0x180b54a18`
- `0x181104010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180b54652`
- `KERNEL32!LoadLibraryExW` at `0x180b546b9`
- `KERNEL32!LoadLibraryExW` at `0x180b546dd`
- `KERNEL32!LoadLibraryExW` at `0x180b54984`
- `KERNEL32!LoadLibraryExW` at `0x180b54652`
- `KERNEL32!LoadLibraryExW` at `0x180b546b9`
- `KERNEL32!LoadLibraryExW` at `0x180b546dd`
- `KERNEL32!LoadLibraryExW` at `0x180b54984`
- `KERNEL32!GetProcAddress` at `0x180b54670`
- `KERNEL32!GetProcAddress` at `0x180b546ff`
- `KERNEL32!GetProcAddress` at `0x180b54719`
- `KERNEL32!GetProcAddress` at `0x180b54732`
- `KERNEL32!GetProcAddress` at `0x180b5474b`
- `KERNEL32!GetProcAddress` at `0x180b54764`
- `KERNEL32!GetProcAddress` at `0x180b549a5`
- `KERNEL32!GetProcAddress` at `0x180b54670`
- `KERNEL32!GetProcAddress` at `0x180b546ff`
- `KERNEL32!GetProcAddress` at `0x180b54719`
- `KERNEL32!GetProcAddress` at `0x180b54732`
- `KERNEL32!GetProcAddress` at `0x180b5474b`
- `KERNEL32!GetProcAddress` at `0x180b54764`
- `KERNEL32!GetProcAddress` at `0x180b549a5`
- `KERNEL32!FreeLibrary` at `0x180b54698`
- `KERNEL32!FreeLibrary` at `0x180b54852`
- `KERNEL32!FreeLibrary` at `0x180b54861`
- `KERNEL32!FreeLibrary` at `0x180b549dc`
- `KERNEL32!FreeLibrary` at `0x180b54698`
- `KERNEL32!FreeLibrary` at `0x180b54852`
- `KERNEL32!FreeLibrary` at `0x180b54861`
- `KERNEL32!FreeLibrary` at `0x180b549dc`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b548d4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b54917`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b5495a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b548d4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b54917`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b5495a`

## string_xrefs

- `0x180b546d4`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x180b5473e`: `WindowsCreateString`
- `0x180b54757`: `WindowsDeleteString`
- `0x180b546b0`: `api-ms-win-core-winrt-l1-1-0.dll`
- `0x180b5497b`: `slc.dll`
- `0x180b54641`: `DiagnosticDataSettings.dll`

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
0x180b54624  mov     [rsp-40h+arg_0], ecx
0x180b54628  push    rbp
0x180b54629  push    rbx
0x180b5462a  push    rsi
0x180b5462b  push    rdi
0x180b5462c  push    r12
0x180b5462e  push    r13
0x180b54630  push    r14
0x180b54632  push    r15
0x180b54634  mov     rbp, rsp
0x180b54637  sub     rsp, 68h
0x180b5463b  mov     r14d, 800h
0x180b54641  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings.dll"
0x180b54648  mov     r8d, r14d; dwFlags
0x180b5464b  xor     edx, edx; hFile
0x180b5464d  xor     bl, bl
0x180b5464f  xor     dil, dil
0x180b54652  call    cs:__imp_LoadLibraryExW
0x180b54659  nop     dword ptr [rax+rax+00h]
0x180b5465e  mov     rsi, rax
0x180b54661  test    rax, rax
0x180b54664  jz      short loc_180B546AD
0x180b54666  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180b5466d  mov     rcx, rax; hModule
0x180b54670  call    cs:__imp_GetProcAddress
0x180b54677  nop     dword ptr [rax+rax+00h]
0x180b5467c  test    rax, rax
0x180b5467f  jz      short loc_180B54695
0x180b54681  mov     ecx, 2
0x180b54686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5468b  test    eax, eax
0x180b5468d  js      short loc_180B54695
0x180b5468f  mov     dil, 1
0x180b54692  setz    bl
0x180b54695  mov     rcx, rsi; hLibModule
0x180b54698  call    cs:__imp_FreeLibrary
0x180b5469f  nop     dword ptr [rax+rax+00h]
0x180b546a4  test    dil, dil
0x180b546a7  jnz     loc_180B549FB
0x180b546ad  mov     r8d, r14d; dwFlags
0x180b546b0  lea     rcx, aApiMsWinCoreWi_4; "api-ms-win-core-winrt-l1-1-0.dll"
0x180b546b7  xor     edx, edx; hFile
0x180b546b9  call    cs:__imp_LoadLibraryExW
0x180b546c0  nop     dword ptr [rax+rax+00h]
0x180b546c5  mov     rsi, rax
0x180b546c8  test    rax, rax
0x180b546cb  jz      loc_180B5487C
0x180b546d1  mov     r8d, r14d; dwFlags
0x180b546d4  lea     rcx, aApiMsWinCoreWi_3; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x180b546db  xor     edx, edx; hFile
0x180b546dd  call    cs:__imp_LoadLibraryExW
0x180b546e4  nop     dword ptr [rax+rax+00h]
0x180b546e9  mov     r14, rax
0x180b546ec  test    rax, rax
0x180b546ef  jz      loc_180B5485E
0x180b546f5  lea     rdx, aRoinitialize_0; "RoInitialize"
0x180b546fc  mov     rcx, rsi; hModule
0x180b546ff  call    cs:__imp_GetProcAddress
0x180b54706  nop     dword ptr [rax+rax+00h]
0x180b5470b  lea     rdx, aRouninitialize_0; "RoUninitialize"
0x180b54712  mov     rcx, rsi; hModule
0x180b54715  mov     [rbp+var_10], rax
0x180b54719  call    cs:__imp_GetProcAddress
0x180b54720  nop     dword ptr [rax+rax+00h]
0x180b54725  lea     rdx, aRogetactivatio_0; "RoGetActivationFactory"
0x180b5472c  mov     rcx, rsi; hModule
0x180b5472f  mov     r13, rax
0x180b54732  call    cs:__imp_GetProcAddress
0x180b54739  nop     dword ptr [rax+rax+00h]
0x180b5473e  lea     rdx, aWindowscreates_2; "WindowsCreateString"
0x180b54745  mov     rcx, r14; hModule
0x180b54748  mov     r12, rax
0x180b5474b  call    cs:__imp_GetProcAddress
0x180b54752  nop     dword ptr [rax+rax+00h]
0x180b54757  lea     rdx, aWindowsdeletes_0; "WindowsDeleteString"
0x180b5475e  mov     rcx, r14; hModule
0x180b54761  mov     r15, rax
0x180b54764  call    cs:__imp_GetProcAddress
0x180b5476b  nop     dword ptr [rax+rax+00h]
0x180b54770  mov     rdx, [rbp+var_10]
0x180b54774  mov     [rbp+var_20], rax
0x180b54778  test    rdx, rdx
0x180b5477b  jz      loc_180B5484F
0x180b54781  test    r13, r13
0x180b54784  jz      loc_180B5484F
0x180b5478a  test    r12, r12
0x180b5478d  jz      loc_180B5484F
0x180b54793  test    r15, r15
0x180b54796  jz      loc_180B5484F
0x180b5479c  test    rax, rax
0x180b5479f  jz      loc_180B5484F
0x180b547a5  mov     ecx, 1
0x180b547aa  mov     rax, rdx
0x180b547ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b547b2  xor     ecx, ecx
0x180b547b4  test    eax, eax
0x180b547b6  js      loc_180B5484F
0x180b547bc  mov     qword ptr [rbp+var_18], rcx
0x180b547c0  lea     edx, [rcx+3Eh]
0x180b547c3  mov     [rbp+var_10], rcx
0x180b547c7  lea     r8, [rbp+var_18]
0x180b547cb  mov     [rbp+var_28], cl
0x180b547ce  mov     rax, r15
0x180b547d1  lea     rcx, ?RuntimeClass_Windows_System_Profile_PlatformDiagnosticsAndUsageDataSettings@@3QBGB; "Windows.System.Profile.PlatformDiagnost"...
0x180b547d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b547dd  test    eax, eax
0x180b547df  js      short loc_180B5482C
0x180b547e1  lea     rcx, [rbp+var_10]
0x180b547e5  call    ?InternalRelease@?$ComPtr@UISpellingError@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpellingError>::InternalRelease(void)
0x180b547ea  mov     rcx, qword ptr [rbp+var_18]
0x180b547ee  lea     r8, [rbp+var_10]
0x180b547f2  lea     rdx, _GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a
0x180b547f9  mov     rax, r12
0x180b547fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b54801  test    eax, eax
0x180b54803  js      short loc_180B5482C
0x180b54805  mov     rcx, [rbp+var_10]
0x180b54809  lea     r8, [rbp+var_28]
0x180b5480d  mov     edx, 2
0x180b54812  mov     rax, [rcx]
0x180b54815  mov     rax, [rax+48h]
0x180b54819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5481e  test    eax, eax
0x180b54820  js      short loc_180B5482C
0x180b54822  cmp     [rbp+var_28], 0
0x180b54826  mov     dil, 1
0x180b54829  setnz   bl
0x180b5482c  mov     rcx, qword ptr [rbp+var_18]
0x180b54830  test    rcx, rcx
0x180b54833  jz      short loc_180B5483E
0x180b54835  mov     rax, [rbp+var_20]
0x180b54839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5483e  lea     rcx, [rbp+var_10]
0x180b54842  call    ?InternalRelease@?$ComPtr@UISpellingError@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpellingError>::InternalRelease(void)
0x180b54847  mov     rax, r13
0x180b5484a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b5484f  mov     rcx, r14; hLibModule
0x180b54852  call    cs:__imp_FreeLibrary
0x180b54859  nop     dword ptr [rax+rax+00h]
0x180b5485e  mov     rcx, rsi; hLibModule
0x180b54861  call    cs:__imp_FreeLibrary
0x180b54868  nop     dword ptr [rax+rax+00h]
0x180b5486d  test    dil, dil
0x180b54870  jnz     loc_180B549FB
0x180b54876  mov     r14d, 800h
0x180b5487c  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x180b54881  test    al, al
0x180b54883  jnz     loc_180B549FB
0x180b54889  mov     r15d, 4
0x180b5488f  mov     dword ptr [rbp+var_20], 0
0x180b54896  lea     rax, [rbp+var_18]
0x180b5489a  mov     [rbp+var_18], r15d
0x180b5489e  mov     [rsp+68h+pcbData], rax; pcbData
0x180b548a3  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x180b548aa  lea     rax, [rbp+var_20]
0x180b548ae  mov     rsi, 0FFFFFFFF80000002h
0x180b548b5  mov     [rsp+68h+pvData], rax; pvData
0x180b548ba  lea     edi, [r15+0Ch]
0x180b548be  mov     r9d, edi; dwFlags
0x180b548c1  mov     [rsp+68h+pdwType], 0; pdwType
0x180b548ca  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180b548d1  mov     rcx, rsi; hkey
0x180b548d4  call    cs:__imp_RegGetValueW
0x180b548db  nop     dword ptr [rax+rax+00h]
0x180b548e0  test    eax, eax
0x180b548e2  jz      loc_180B54971
0x180b548e8  lea     rax, [rbp+var_18]
0x180b548ec  mov     r9d, edi; dwFlags
0x180b548ef  mov     [rsp+68h+pcbData], rax; pcbData
0x180b548f4  lea     r8, aAllowtelemetry; "AllowTelemetry_PolicyManager"
0x180b548fb  lea     rax, [rbp+var_20]
0x180b548ff  mov     rcx, rsi; hkey
0x180b54902  mov     [rsp+68h+pvData], rax; pvData
0x180b54907  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180b5490e  mov     [rsp+68h+pdwType], 0; pdwType
0x180b54917  call    cs:__imp_RegGetValueW
0x180b5491e  nop     dword ptr [rax+rax+00h]
0x180b54923  test    eax, eax
0x180b54925  jz      short loc_180B54971
0x180b54927  lea     rax, [rbp+var_18]
0x180b5492b  mov     dword ptr [rbp+var_20], r15d
0x180b5492f  mov     [rsp+68h+pcbData], rax; pcbData
0x180b54934  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x180b5493b  lea     rax, [rbp+var_20]
0x180b5493f  mov     r9d, edi; dwFlags
0x180b54942  mov     [rsp+68h+pvData], rax; pvData
0x180b54947  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180b5494e  mov     rcx, rsi; hkey
0x180b54951  mov     [rsp+68h+pdwType], 0; pdwType
0x180b5495a  call    cs:__imp_RegGetValueW
0x180b54961  nop     dword ptr [rax+rax+00h]
0x180b54966  test    eax, 0FFFFFFFDh
0x180b5496b  jnz     loc_180B549FB
0x180b54971  mov     eax, dword ptr [rbp+var_20]
0x180b54974  test    eax, eax
0x180b54976  jnz     short loc_180B549F5
0x180b54978  mov     r8d, r14d; dwFlags
0x180b5497b  lea     rcx, aSlcDll; "slc.dll"
0x180b54982  xor     edx, edx; hFile
0x180b54984  call    cs:__imp_LoadLibraryExW
0x180b5498b  nop     dword ptr [rax+rax+00h]
0x180b54990  mov     rbx, rax
0x180b54993  test    rax, rax
0x180b54996  jz      short loc_180B549F0
0x180b54998  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x180b5499f  mov     rcx, rax; hModule
0x180b549a2  xor     dil, dil
0x180b549a5  call    cs:__imp_GetProcAddress
0x180b549ac  nop     dword ptr [rax+rax+00h]
0x180b549b1  test    rax, rax
0x180b549b4  jz      short loc_180B549D9
0x180b549b6  lea     rdx, [rbp+var_10]
0x180b549ba  mov     dword ptr [rbp+var_10], 0
0x180b549c1  lea     rcx, aTelemetrypermi; "TelemetryPermission-AllowDisable"
0x180b549c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b549cd  test    eax, eax
0x180b549cf  js      short loc_180B549D9
0x180b549d1  cmp     dword ptr [rbp+var_10], 1
0x180b549d5  setz    dil
0x180b549d9  mov     rcx, rbx; hLibModule
0x180b549dc  call    cs:__imp_FreeLibrary
0x180b549e3  nop     dword ptr [rax+rax+00h]
0x180b549e8  mov     eax, dword ptr [rbp+var_20]
0x180b549eb  test    dil, dil
0x180b549ee  jnz     short loc_180B549F5
0x180b549f0  mov     eax, 1
0x180b549f5  shr     eax, 1
0x180b549f7  and     al, 1
0x180b549f9  jmp     short loc_180B549FD
0x180b549fb  mov     al, bl
0x180b549fd  add     rsp, 68h
0x180b54a01  pop     r15
0x180b54a03  pop     r14
0x180b54a05  pop     r13
0x180b54a07  pop     r12
0x180b54a09  pop     rdi
0x180b54a0a  pop     rsi
0x180b54a0b  pop     rbx
0x180b54a0c  pop     rbp
0x180b54a0d  retn
```
