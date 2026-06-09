# CRepositoryCorruption::ReportInconsistentBackupCorruption(void)

- ea: `0x18003c21c`
- end: `0x18003c578`
- name: `?ReportInconsistentBackupCorruption@CRepositoryCorruption@@SAJXZ`
- size: `860`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001c950`

## callees

- `0x1800216c8`
- `0x180029fbc`
- `0x18003c21c`
- `0x1800443df`
- `0x180044420`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18003c3da`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18003c3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c52a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c52a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c255`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c255`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c29e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c2b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c2c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c2dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c2ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c29e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c2b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c2c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c2dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c2ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c280`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18003c4b9`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18003c4b9`

## string_xrefs

- `0x18003c24e`: `wer.dll`
- `0x18003c294`: `WerReportCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int CRepositoryCorruption::ReportInconsistentBackupCorruption(void)
{
  HMODULE Library; // rdi
  signed int result; // eax
  int v2; // ebx
  FARPROC v3; // r12
  FARPROC v4; // r14
  FARPROC v5; // r15
  FARPROC v6; // rax
  FARPROC v7; // r13
  __int64 v8; // rdi
  unsigned int i; // esi
  __int64 v10; // rbx
  signed int LastError; // eax
  PDWORD pdwReturnedProductType; // [rsp+20h] [rbp-E0h]
  __int64 v13; // [rsp+28h] [rbp-D8h]
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v15; // [rsp+48h] [rbp-B8h] BYREF
  FARPROC ProcAddress; // [rsp+50h] [rbp-B0h]
  char v17[8]; // [rsp+58h] [rbp-A8h] BYREF
  FARPROC v18; // [rsp+60h] [rbp-A0h]
  __int64 v19; // [rsp+68h] [rbp-98h]
  char v20[8]; // [rsp+70h] [rbp-90h] BYREF
  BOOL (__stdcall *v21)(HMODULE); // [rsp+78h] [rbp-88h]
  HMODULE v22; // [rsp+80h] [rbp-80h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v24; // [rsp+1A4h] [rbp+A4h]
  unsigned __int16 v25; // [rsp+1A6h] [rbp+A6h]
  unsigned __int16 v26[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  Library = LoadLibraryExW(L"wer.dll", 0, 0);
  if ( Library )
  {
    v2 = 0;
    v20[0] = 0;
    v21 = FreeLibrary;
    v22 = Library;
    ProcAddress = GetProcAddress(Library, "WerReportCreate");
    v3 = GetProcAddress(Library, "WerReportAddFile");
    v4 = GetProcAddress(Library, "WerReportSetParameter");
    v5 = GetProcAddress(Library, "WerReportSubmit");
    v6 = GetProcAddress(Library, "WerReportCloseHandle");
    v7 = v6;
    if ( ProcAddress && v3 && v4 && v5 && v6 )
    {
      v8 = 0x133F84CFE133F84DLL
         * ((__int64)(*((_QWORD *)&CRepositoryCorruption::m_aCorruptedBackup + 1)
                    - CRepositoryCorruption::m_aCorruptedBackup) >> 2);
      for ( i = 0; i < (unsigned int)v8; ++i )
      {
        v14 = 0;
        v2 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, __int64 *))ProcAddress)(
               L"WMIInconsistentBackup",
               0,
               0,
               &v14);
        if ( v2 < 0 )
          break;
        v17[0] = 0;
        v18 = v7;
        v19 = v14;
        v10 = 532LL * i;
        LastError = ((__int64 (__fastcall *)(__int64, _QWORD, __int64))v3)(
                      v14,
                      v10 + CRepositoryCorruption::m_aCorruptedBackup,
                      5);
        if ( LastError < 0 )
          goto LABEL_21;
        memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
        VersionInformation.dwOSVersionInfoSize = 284;
        if ( !GetVersionExW(&VersionInformation) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_21:
          v2 = LastError;
LABEL_22:
          ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v17);
          break;
        }
        LODWORD(v13) = VersionInformation.dwBuildNumber;
        LODWORD(pdwReturnedProductType) = VersionInformation.dwMinorVersion;
        StringCchPrintfW(v26, 0x104u, L"%d.%d.%d.%d", VersionInformation.dwMajorVersion, pdwReturnedProductType, v13, 0);
        LastError = ((__int64 (__fastcall *)(__int64, _QWORD, const wchar_t *, unsigned __int16 *))v4)(
                      v14,
                      0,
                      L"Version",
                      v26);
        if ( LastError < 0 )
          goto LABEL_21;
        StringCchPrintfW(v26, 0x104u, L"%d", *(unsigned int *)(v10 + CRepositoryCorruption::m_aCorruptedBackup + 524));
        LastError = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, unsigned __int16 *))v4)(
                      v14,
                      1,
                      L"Startup",
                      v26);
        if ( LastError < 0 )
          goto LABEL_21;
        v15 = 0;
        GetProductInfo(VersionInformation.dwMajorVersion, VersionInformation.dwMinorVersion, v24, v25, &v15);
        StringCchPrintfW(v26, 0x104u, L"%d", v15);
        LastError = ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *, unsigned __int16 *))v4)(
                      v14,
                      2,
                      L"SKU",
                      v26);
        if ( LastError < 0 )
          goto LABEL_21;
        v2 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))v5)(v14, 1, 0, 0);
        if ( v2 < 0 )
          goto LABEL_22;
        ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v17);
      }
    }
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v20);
    return v2;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18003c21c  push    rbp
0x18003c21e  push    rbx
0x18003c21f  push    rsi
0x18003c220  push    rdi
0x18003c221  push    r12
0x18003c223  push    r13
0x18003c225  push    r14
0x18003c227  push    r15
0x18003c229  lea     rbp, [rsp-2D8h]
0x18003c231  sub     rsp, 3D8h
0x18003c238  mov     rax, cs:__security_cookie
0x18003c23f  xor     rax, rsp
0x18003c242  mov     [rbp+310h+var_50], rax
0x18003c249  xor     r8d, r8d; dwFlags
0x18003c24c  xor     edx, edx; hFile
0x18003c24e  lea     rcx, aWerDll; "wer.dll"
0x18003c255  call    cs:__imp_LoadLibraryExW
0x18003c25b  mov     rdi, rax
0x18003c25e  test    rax, rax
0x18003c261  jnz     short loc_18003C27E
0x18003c263  call    cs:__imp_GetLastError
0x18003c269  test    eax, eax
0x18003c26b  jle     loc_18003C555
0x18003c271  movzx   eax, ax
0x18003c274  or      eax, 80070000h
0x18003c279  jmp     loc_18003C555
0x18003c27e  xor     ebx, ebx
0x18003c280  mov     rax, cs:__imp_FreeLibrary
0x18003c287  mov     [rsp+410h+var_3A0], bl
0x18003c28b  mov     [rsp+410h+var_398], rax
0x18003c290  mov     [rbp+310h+var_390], rdi
0x18003c294  lea     rdx, aWerreportcreat; "WerReportCreate"
0x18003c29b  mov     rcx, rdi; hModule
0x18003c29e  call    cs:__imp_GetProcAddress
0x18003c2a4  mov     rsi, rax
0x18003c2a7  mov     [rsp+410h+var_3C0], rax
0x18003c2ac  lea     rdx, aWerreportaddfi; "WerReportAddFile"
0x18003c2b3  mov     rcx, rdi; hModule
0x18003c2b6  call    cs:__imp_GetProcAddress
0x18003c2bc  mov     r12, rax
0x18003c2bf  lea     rdx, aWerreportsetpa; "WerReportSetParameter"
0x18003c2c6  mov     rcx, rdi; hModule
0x18003c2c9  call    cs:__imp_GetProcAddress
0x18003c2cf  mov     r14, rax
0x18003c2d2  lea     rdx, aWerreportsubmi; "WerReportSubmit"
0x18003c2d9  mov     rcx, rdi; hModule
0x18003c2dc  call    cs:__imp_GetProcAddress
0x18003c2e2  mov     r15, rax
0x18003c2e5  lea     rdx, aWerreportclose; "WerReportCloseHandle"
0x18003c2ec  mov     rcx, rdi; hModule
0x18003c2ef  call    cs:__imp_GetProcAddress
0x18003c2f5  mov     r13, rax
0x18003c2f8  test    rsi, rsi
0x18003c2fb  jz      loc_18003C549
0x18003c301  test    r12, r12
0x18003c304  jz      loc_18003C549
0x18003c30a  test    r14, r14
0x18003c30d  jz      loc_18003C549
0x18003c313  test    r15, r15
0x18003c316  jz      loc_18003C549
0x18003c31c  test    rax, rax
0x18003c31f  jz      loc_18003C549
0x18003c325  mov     rdi, qword ptr cs:?m_aCorruptedBackup@CRepositoryCorruption@@2V?$vector@UWMIRepositoryCorruptionReport@@V?$wbem_allocator@UWMIRepositoryCorruptionReport@@@@@std@@A+8; std::vector<WMIRepositoryCorruptionReport,wbem_allocator<WMIRepositoryCorruptionReport>> CRepositoryCorruption::m_aCorruptedBackup
0x18003c32c  sub     rdi, qword ptr cs:?m_aCorruptedBackup@CRepositoryCorruption@@2V?$vector@UWMIRepositoryCorruptionReport@@V?$wbem_allocator@UWMIRepositoryCorruptionReport@@@@@std@@A; std::vector<WMIRepositoryCorruptionReport,wbem_allocator<WMIRepositoryCorruptionReport>> CRepositoryCorruption::m_aCorruptedBackup
0x18003c333  sar     rdi, 2
0x18003c337  mov     rax, 133F84CFE133F84Dh
0x18003c341  imul    rdi, rax
0x18003c345  xor     esi, esi
0x18003c347  cmp     esi, edi
0x18003c349  jnb     loc_18003C549
0x18003c34f  mov     [rsp+410h+var_3D0], 0
0x18003c358  lea     r9, [rsp+410h+var_3D0]
0x18003c35d  xor     r8d, r8d
0x18003c360  xor     edx, edx
0x18003c362  lea     rcx, aWmiinconsisten_0; "WMIInconsistentBackup"
0x18003c369  mov     rax, [rsp+410h+var_3C0]
0x18003c36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c373  mov     ebx, eax
0x18003c375  test    eax, eax
0x18003c377  js      loc_18003C549
0x18003c37d  mov     rcx, [rsp+410h+var_3D0]
0x18003c382  mov     [rsp+410h+var_3B8], 0
0x18003c387  mov     [rsp+410h+var_3B0], r13
0x18003c38c  mov     [rsp+410h+var_3A8], rcx
0x18003c391  mov     eax, esi
0x18003c393  imul    rbx, rax, 214h
0x18003c39a  mov     rdx, qword ptr cs:?m_aCorruptedBackup@CRepositoryCorruption@@2V?$vector@UWMIRepositoryCorruptionReport@@V?$wbem_allocator@UWMIRepositoryCorruptionReport@@@@@std@@A; std::vector<WMIRepositoryCorruptionReport,wbem_allocator<WMIRepositoryCorruptionReport>> CRepositoryCorruption::m_aCorruptedBackup
0x18003c3a1  add     rdx, rbx
0x18003c3a4  mov     r9d, 1
0x18003c3aa  lea     r8d, [r9+4]
0x18003c3ae  mov     rax, r12
0x18003c3b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3b6  test    eax, eax
0x18003c3b8  js      loc_18003C53C
0x18003c3be  xor     edx, edx; Val
0x18003c3c0  mov     r8d, 118h; Size
0x18003c3c6  lea     rcx, [rbp+310h+VersionInformation.dwMajorVersion]; void *
0x18003c3ca  call    memset_0
0x18003c3cf  mov     [rbp+310h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18003c3d6  lea     rcx, [rbp+310h+VersionInformation]; lpVersionInformation
0x18003c3da  call    cs:__imp_GetVersionExW
0x18003c3e0  test    eax, eax
0x18003c3e2  jz      loc_18003C52A
0x18003c3e8  mov     [rsp+410h+var_3E0], 0
0x18003c3f1  mov     eax, [rbp+310h+VersionInformation.dwBuildNumber]
0x18003c3f4  mov     dword ptr [rsp+410h+var_3E8], eax
0x18003c3f8  mov     eax, [rbp+310h+VersionInformation.dwMinorVersion]
0x18003c3fb  mov     dword ptr [rsp+410h+pdwReturnedProductType], eax
0x18003c3ff  mov     r9d, [rbp+310h+VersionInformation.dwMajorVersion]
0x18003c403  lea     r8, aDDDD; "%d.%d.%d.%d"
0x18003c40a  mov     edx, 104h; unsigned __int64
0x18003c40f  lea     rcx, [rbp+310h+var_260]; unsigned __int16 *
0x18003c416  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c41b  lea     r9, [rbp+310h+var_260]
0x18003c422  lea     r8, aVersion; "Version"
0x18003c429  xor     edx, edx
0x18003c42b  mov     rcx, [rsp+410h+var_3D0]
0x18003c430  mov     rax, r14
0x18003c433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c438  test    eax, eax
0x18003c43a  js      loc_18003C53C
0x18003c440  mov     r9, qword ptr cs:?m_aCorruptedBackup@CRepositoryCorruption@@2V?$vector@UWMIRepositoryCorruptionReport@@V?$wbem_allocator@UWMIRepositoryCorruptionReport@@@@@std@@A; std::vector<WMIRepositoryCorruptionReport,wbem_allocator<WMIRepositoryCorruptionReport>> CRepositoryCorruption::m_aCorruptedBackup
0x18003c447  mov     r9d, [rbx+r9+20Ch]
0x18003c44f  lea     r8, aD; "%d"
0x18003c456  mov     edx, 104h; unsigned __int64
0x18003c45b  lea     rcx, [rbp+310h+var_260]; unsigned __int16 *
0x18003c462  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c467  lea     r9, [rbp+310h+var_260]
0x18003c46e  lea     r8, aStartup; "Startup"
0x18003c475  mov     ebx, 1
0x18003c47a  mov     edx, ebx
0x18003c47c  mov     rcx, [rsp+410h+var_3D0]
0x18003c481  mov     rax, r14
0x18003c484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c489  test    eax, eax
0x18003c48b  js      loc_18003C53C
0x18003c491  mov     [rsp+410h+var_3C8], 0
0x18003c499  movzx   r9d, [rbp+310h+var_26A]; dwSpMinorVersion
0x18003c4a1  movzx   r8d, [rbp+310h+var_26C]; dwSpMajorVersion
0x18003c4a9  lea     rax, [rsp+410h+var_3C8]
0x18003c4ae  mov     [rsp+410h+pdwReturnedProductType], rax; pdwReturnedProductType
0x18003c4b3  mov     edx, [rbp+310h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x18003c4b6  mov     ecx, [rbp+310h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x18003c4b9  call    cs:__imp_GetProductInfo
0x18003c4bf  mov     r9d, [rsp+410h+var_3C8]
0x18003c4c4  lea     r8, aD; "%d"
0x18003c4cb  mov     edx, 104h; unsigned __int64
0x18003c4d0  lea     rcx, [rbp+310h+var_260]; unsigned __int16 *
0x18003c4d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c4dc  lea     r9, [rbp+310h+var_260]
0x18003c4e3  lea     r8, aSku; "SKU"
0x18003c4ea  lea     edx, [rbx+1]
0x18003c4ed  mov     rcx, [rsp+410h+var_3D0]
0x18003c4f2  mov     rax, r14
0x18003c4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4fa  test    eax, eax
0x18003c4fc  js      short loc_18003C53C
0x18003c4fe  xor     r9d, r9d
0x18003c501  xor     r8d, r8d
0x18003c504  mov     edx, ebx
0x18003c506  mov     rcx, [rsp+410h+var_3D0]
0x18003c50b  mov     rax, r15
0x18003c50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c513  mov     ebx, eax
0x18003c515  test    eax, eax
0x18003c517  js      short loc_18003C53E
0x18003c519  lea     rcx, [rsp+410h+var_3B8]
0x18003c51e  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003c523  inc     esi
0x18003c525  jmp     loc_18003C347
0x18003c52a  call    cs:__imp_GetLastError
0x18003c530  test    eax, eax
0x18003c532  jle     short loc_18003C53C
0x18003c534  movzx   eax, ax
0x18003c537  or      eax, 80070000h
0x18003c53c  mov     ebx, eax
0x18003c53e  lea     rcx, [rsp+410h+var_3B8]
0x18003c543  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003c548  nop
0x18003c549  lea     rcx, [rsp+410h+var_3A0]
0x18003c54e  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003c553  mov     eax, ebx
0x18003c555  mov     rcx, [rbp+310h+var_50]
0x18003c55c  xor     rcx, rsp; StackCookie
0x18003c55f  call    __security_check_cookie
0x18003c564  add     rsp, 3D8h
0x18003c56b  pop     r15
0x18003c56d  pop     r14
0x18003c56f  pop     r13
0x18003c571  pop     r12
0x18003c573  pop     rdi
0x18003c574  pop     rsi
0x18003c575  pop     rbx
0x18003c576  pop     rbp
0x18003c577  retn
```
