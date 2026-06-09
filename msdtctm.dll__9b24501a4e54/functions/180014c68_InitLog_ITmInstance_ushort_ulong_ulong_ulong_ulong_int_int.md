# InitLog(ITmInstance *,ushort *,ulong,ulong,ulong,ulong,int,int)

- ea: `0x180014c68`
- end: `0x180015095`
- name: `?InitLog@@YAJPEAUITmInstance@@PEAGKKKKHH@Z`
- size: `1069`
- prototype: `__int64 __fastcall(struct ITmInstance *, unsigned __int16 *, __int64, __int64, unsigned int, unsigned int, int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180082c48`
- `0x180083b40`
- `0x180085ae8`

## callees

- `0x180014c68`
- `0x180015230`
- `0x18001d268`
- `0x180085cc8`
- `0x180085d94`
- `0x18008692c`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d06`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180014cb8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180014cb8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015067`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015067`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014cfb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014cfb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180014f9a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180014f9a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014ff5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014ff5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014f62`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014f62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015034`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015034`

## string_xrefs

- `0x180014cd2`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x180014d12`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x180014dff`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x18001501c`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x180015058`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x180015015`: `::InitLog - Failed: RegSetValueEx(...)`
- `0x180014f82`: `::InitLog - Failed: RegOpenKey(...) on FileNotToBackup`
- `0x180014ca9`: `msdtclog.dll`
- `0x180014cdb`: `Failed to load msdtclog.dll`
- `0x180014cf1`: `DllGetDTCLOG2`
- `0x180014d1b`: `Failed to find address of DllGetDtcLog2 function in msdtclog.dll`
- `0x180014d53`: `::InitLog - Failed: DllGetDTCLOG(...)`
- `0x180014e5f`: `::InitLog - Failed: piLogCreateStorage->CreateStream(...)`
- `0x180014e06`: `::InitLog - Failed: piLogCreateStorage->CreateStorage(...)`

## pseudocode

```c
__int64 __fastcall InitLog(
        struct ITmInstance *a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8)
{
  HMODULE Library; // rax
  HMODULE v11; // rsi
  DWORD v12; // eax
  unsigned int v13; // ebx
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  unsigned int v16; // r9d
  char *v17; // rdx
  unsigned __int16 *BSW; // rax
  int v19; // eax
  unsigned __int16 *v20; // rax
  int v21; // r8d
  int v22; // eax
  int v23; // ecx
  unsigned __int16 *DefaultLogPath; // rax
  LSTATUS v25; // eax
  unsigned int v26; // r9d
  char *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  LSTATUS v30; // eax
  LSTATUS v31; // eax
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v36[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v37[264]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 Data[528]; // [rsp+490h] [rbp+390h] BYREF

  v33 = 0;
  dwDisposition[0] = 0;
  hKey = 0;
  Library = LoadLibraryExA("msdtclog.dll", 0, 0);
  v11 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DllGetDTCLOG2");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      TraceFile(
        LastError,
        "Failed to find address of DllGetDtcLog2 function in msdtclog.dll",
        "com\\complus\\dtc\\shared\\util\\initlog.cpp",
        0xB3u);
      v13 = -1073737703;
LABEL_39:
      FreeLibrary(v11);
      return v13;
    }
    if ( ((unsigned int (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
           &CLSID_CLogMgr,
           &IID_ILogCreateStorage2W,
           &v33) )
    {
      v16 = 186;
      v17 = "::InitLog - Failed: DllGetDTCLOG(...)";
      v13 = -1073737703;
LABEL_37:
      v23 = v13;
      goto LABEL_38;
    }
    BSW = SZStripLastBSW(a2);
    TracedStringCchPrintfW(v36, 0x105u, L"%s\\%s", BSW, L"MSDTC.LOG");
    v19 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD, bool, int, int, int))(*(_QWORD *)v33 + 24LL))(
            v33,
            v36,
            a6,
            0,
            a7 == 0,
            10,
            50,
            50000);
    v13 = v19;
    if ( v19 == -2147024816 || v19 == -2147024713 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      v13 = 0;
    }
    else
    {
      if ( v19 )
      {
        TraceFile(
          v19,
          "::InitLog - Failed: piLogCreateStorage->CreateStorage(...)",
          "com\\complus\\dtc\\shared\\util\\initlog.cpp",
          0xE9u);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        goto LABEL_39;
      }
      v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v33 + 32LL))(v33, L"Streamname");
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      if ( v13 )
      {
        v16 = 212;
        v17 = "::InitLog - Failed: piLogCreateStorage->CreateStream(...)";
        goto LABEL_37;
      }
      v20 = SZStripLastBSW(a2);
      v22 = SetSddlOnLogFile(a1, v20, v21);
      v13 = v22;
      if ( v22 < 0 )
      {
        v16 = 220;
        v17 = "ResetLog: SetSddlOnLogFile FAILED";
        v23 = v22;
LABEL_38:
        TraceFile(v23, v17, "com\\complus\\dtc\\shared\\util\\initlog.cpp", v16);
        goto LABEL_39;
      }
    }
    if ( !a8 )
      goto LABEL_39;
    DefaultLogPath = GetDefaultLogPath();
    TracedStringCchPrintfW(v37, 0x105u, L"%s\\%s\\%s", DefaultLogPath, L"trace", L"dtctrace.log");
    TracedStringCchPrintfW(Data, 0x20Bu, L"%s%c%s%c", v36, 0, v37, 0);
    v25 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\BackupRestore\\FilesNotToBackup",
            0,
            (LPWSTR)&cchOriginalDestLength,
            0,
            0x2001Bu,
            0,
            &hKey,
            dwDisposition);
    if ( v25 )
    {
      if ( v25 > 0 )
        v13 = (unsigned __int16)v25 | 0x80070000;
      else
        v13 = v25;
      v26 = 272;
      v27 = "::InitLog - Failed: RegOpenKey(...) on FileNotToBackup";
    }
    else
    {
      RegDeleteValueW(hKey, L"MS Distributed Transaction Coordinatior");
      v28 = -1;
      v29 = -1;
      do
        ++v29;
      while ( v36[v29] );
      do
        ++v28;
      while ( v37[v28] );
      v30 = RegSetValueExW(
              hKey,
              L"MS Distributed Transaction Coordinator",
              0,
              7u,
              (const BYTE *)Data,
              2 * (v29 + v28) + 6);
      if ( !v30 )
        goto LABEL_31;
      if ( v30 > 0 )
        v13 = (unsigned __int16)v30 | 0x80070000;
      else
        v13 = v30;
      v26 = 293;
      v27 = "::InitLog - Failed: RegSetValueEx(...)";
    }
    TraceFile(v13, v27, "com\\complus\\dtc\\shared\\util\\initlog.cpp", v26);
LABEL_31:
    if ( !hKey )
      goto LABEL_39;
    v31 = RegCloseKey(hKey);
    if ( !v31 )
      goto LABEL_39;
    if ( v31 > 0 )
      v13 = (unsigned __int16)v31 | 0x80070000;
    else
      v13 = v31;
    v16 = 306;
    v17 = "::InitLog - Failed: RegCloseKey(...)";
    goto LABEL_37;
  }
  v12 = GetLastError();
  TraceFile(v12, "Failed to load msdtclog.dll", "com\\complus\\dtc\\shared\\util\\initlog.cpp", 0xAAu);
  return (unsigned int)-1073737703;
}

```

## disassembly

```asm
0x180014c68  mov     [rsp-8+arg_10], rbx
0x180014c6d  push    rbp
0x180014c6e  push    rsi
0x180014c6f  push    rdi
0x180014c70  push    r14
0x180014c72  push    r15
0x180014c74  lea     rbp, [rsp-7C0h]
0x180014c7c  sub     rsp, 8C0h
0x180014c83  mov     rax, cs:__security_cookie
0x180014c8a  xor     rax, rsp
0x180014c8d  mov     [rbp+7E0h+var_30], rax
0x180014c94  xor     r15d, r15d
0x180014c97  mov     rdi, rdx
0x180014c9a  mov     r14, rcx
0x180014c9d  mov     [rsp+8E0h+var_890], r15
0x180014ca2  xor     edx, edx; hFile
0x180014ca4  mov     [rsp+8E0h+dwDisposition], r15d
0x180014ca9  lea     rcx, aMsdtclogDll_0; "msdtclog.dll"
0x180014cb0  mov     [rsp+8E0h+hKey], r15
0x180014cb5  xor     r8d, r8d; dwFlags
0x180014cb8  call    cs:__imp_LoadLibraryExA
0x180014cbe  mov     rsi, rax
0x180014cc1  test    rax, rax
0x180014cc4  jnz     short loc_180014CF1
0x180014cc6  call    cs:__imp_GetLastError
0x180014ccc  mov     r9d, 0AAh; unsigned int
0x180014cd2  lea     r8, aComComplusDtcS_11; "com\\complus\\dtc\\shared\\util\\initlo"...
0x180014cd9  mov     ecx, eax; int
0x180014cdb  lea     rdx, aFailedToLoadMs; "Failed to load msdtclog.dll"
0x180014ce2  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180014ce7  mov     ebx, 0C0001019h
0x180014cec  jmp     loc_18001506D
0x180014cf1  lea     rdx, ProcName; "DllGetDTCLOG2"
0x180014cf8  mov     rcx, rsi; hModule
0x180014cfb  call    cs:__imp_GetProcAddress
0x180014d01  test    rax, rax
0x180014d04  jnz     short loc_180014D31
0x180014d06  call    cs:__imp_GetLastError
0x180014d0c  mov     r9d, 0B3h; unsigned int
0x180014d12  lea     r8, aComComplusDtcS_11; "com\\complus\\dtc\\shared\\util\\initlo"...
0x180014d19  mov     ecx, eax; int
0x180014d1b  lea     rdx, aFailedToFindAd; "Failed to find address of DllGetDtcLog2"...
0x180014d22  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180014d27  mov     ebx, 0C0001019h
0x180014d2c  jmp     loc_180015064
0x180014d31  lea     r8, [rsp+8E0h+var_890]
0x180014d36  lea     rdx, IID_ILogCreateStorage2W
0x180014d3d  lea     rcx, CLSID_CLogMgr
0x180014d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d49  test    eax, eax
0x180014d4b  jz      short loc_180014D64
0x180014d4d  mov     r9d, 0BAh
0x180014d53  lea     rdx, aInitlogFailedD; "::InitLog - Failed: DllGetDTCLOG(...)"
0x180014d5a  mov     ebx, 0C0001019h
0x180014d5f  jmp     loc_180015056
0x180014d64  mov     rcx, rdi; unsigned __int16 *
0x180014d67  call    ?SZStripLastBSW@@YAPEAGPEAG@Z; SZStripLastBSW(ushort *)
0x180014d6c  mov     r9, rax
0x180014d6f  lea     r8, aSS_1; "%s\\%s"
0x180014d76  lea     rax, aMsdtcLog_0; "MSDTC.LOG"
0x180014d7d  mov     edx, 105h; unsigned __int64
0x180014d82  lea     rcx, [rsp+8E0h+var_870]; unsigned __int16 *
0x180014d87  mov     qword ptr [rsp+8E0h+dwOptions], rax
0x180014d8c  call    ?TracedStringCchPrintfW@@YAXPEAG_KPEBGZZ; TracedStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014d91  mov     r10, [rsp+8E0h+var_890]
0x180014d96  lea     rdx, [rsp+8E0h+var_870]
0x180014d9b  cmp     [rbp+7E0h+arg_30], r15d
0x180014da2  mov     ecx, r15d
0x180014da5  mov     r8d, [rbp+7E0h+arg_28]
0x180014dac  setz    cl
0x180014daf  mov     dword ptr [rsp+8E0h+phkResult], 0C350h
0x180014db7  mov     rax, [r10]
0x180014dba  xor     r9d, r9d
0x180014dbd  mov     dword ptr [rsp+8E0h+lpSecurityAttributes], 32h ; '2'
0x180014dc5  mov     [rsp+8E0h+samDesired], 0Ah
0x180014dcd  mov     [rsp+8E0h+dwOptions], ecx
0x180014dd1  mov     rcx, r10
0x180014dd4  mov     rax, [rax+18h]
0x180014dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ddd  mov     ebx, eax
0x180014ddf  cmp     eax, 80070050h
0x180014de4  jz      loc_180014E98
0x180014dea  cmp     eax, 800700B7h
0x180014def  jz      loc_180014E98
0x180014df5  test    eax, eax
0x180014df7  jz      short loc_180014E2A
0x180014df9  mov     r9d, 0E9h; unsigned int
0x180014dff  lea     r8, aComComplusDtcS_11; "com\\complus\\dtc\\shared\\util\\initlo"...
0x180014e06  lea     rdx, aInitlogFailedP_0; "::InitLog - Failed: piLogCreateStorage-"...
0x180014e0d  mov     ecx, eax; int
0x180014e0f  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180014e14  mov     rcx, [rsp+8E0h+var_890]
0x180014e19  mov     rax, [rcx]
0x180014e1c  mov     rax, [rax+10h]
0x180014e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e25  jmp     loc_180015064
0x180014e2a  mov     rcx, [rsp+8E0h+var_890]
0x180014e2f  lea     rdx, aStreamname; "Streamname"
0x180014e36  mov     rax, [rcx]
0x180014e39  mov     rax, [rax+20h]
0x180014e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e42  mov     rcx, [rsp+8E0h+var_890]
0x180014e47  mov     ebx, eax
0x180014e49  mov     rax, [rcx]
0x180014e4c  mov     rax, [rax+10h]
0x180014e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e55  test    ebx, ebx
0x180014e57  jz      short loc_180014E6B
0x180014e59  mov     r9d, 0D4h
0x180014e5f  lea     rdx, aInitlogFailedP; "::InitLog - Failed: piLogCreateStorage-"...
0x180014e66  jmp     loc_180015056
0x180014e6b  mov     rcx, rdi; unsigned __int16 *
0x180014e6e  call    ?SZStripLastBSW@@YAPEAGPEAG@Z; SZStripLastBSW(ushort *)
0x180014e73  mov     rdx, rax; unsigned __int16 *
0x180014e76  mov     rcx, r14; struct ITmInstance *
0x180014e79  call    ?SetSddlOnLogFile@@YAJPEAUITmInstance@@PEAGH@Z; SetSddlOnLogFile(ITmInstance *,ushort *,int)
0x180014e7e  mov     ebx, eax
0x180014e80  test    eax, eax
0x180014e82  jns     short loc_180014EAC
0x180014e84  mov     r9d, 0DCh
0x180014e8a  lea     rdx, aResetlogSetsdd_0; "ResetLog: SetSddlOnLogFile FAILED"
0x180014e91  mov     ecx, eax
0x180014e93  jmp     loc_180015058
0x180014e98  mov     rcx, [rsp+8E0h+var_890]
0x180014e9d  mov     rax, [rcx]
0x180014ea0  mov     rax, [rax+10h]
0x180014ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ea9  mov     ebx, r15d
0x180014eac  cmp     [rbp+7E0h+arg_38], r15d
0x180014eb3  jz      loc_180015064
0x180014eb9  call    ?GetDefaultLogPath@@YAPEAGXZ; GetDefaultLogPath(void)
0x180014ebe  lea     rcx, aDtctraceLog; "dtctrace.log"
0x180014ec5  mov     r9, rax
0x180014ec8  mov     qword ptr [rsp+8E0h+samDesired], rcx
0x180014ecd  lea     r8, aSSS; "%s\\%s\\%s"
0x180014ed4  lea     rcx, aTrace; "trace"
0x180014edb  mov     edx, 105h; unsigned __int64
0x180014ee0  mov     qword ptr [rsp+8E0h+dwOptions], rcx
0x180014ee5  lea     rcx, [rbp+7E0h+var_660]; unsigned __int16 *
0x180014eec  call    ?TracedStringCchPrintfW@@YAXPEAG_KPEBGZZ; TracedStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014ef1  lea     rax, [rbp+7E0h+var_660]
0x180014ef8  mov     [rsp+8E0h+lpSecurityAttributes], r15
0x180014efd  mov     qword ptr [rsp+8E0h+samDesired], rax
0x180014f02  lea     r9, [rsp+8E0h+var_870]
0x180014f07  lea     r8, aSCSC; "%s%c%s%c"
0x180014f0e  mov     qword ptr [rsp+8E0h+dwOptions], r15
0x180014f13  mov     edx, 20Bh; unsigned __int64
0x180014f18  lea     rcx, [rbp+7E0h+Data]; unsigned __int16 *
0x180014f1f  call    ?TracedStringCchPrintfW@@YAXPEAG_KPEBGZZ; TracedStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014f24  lea     rax, [rsp+8E0h+dwDisposition]
0x180014f29  xor     r8d, r8d; Reserved
0x180014f2c  mov     [rsp+8E0h+lpdwDisposition], rax; lpdwDisposition
0x180014f31  lea     r9, cchOriginalDestLength; lpClass
0x180014f38  lea     rax, [rsp+8E0h+hKey]
0x180014f3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014f44  mov     [rsp+8E0h+phkResult], rax; phkResult
0x180014f49  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Bac"...
0x180014f50  mov     [rsp+8E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180014f55  mov     [rsp+8E0h+samDesired], 2001Bh; samDesired
0x180014f5d  mov     [rsp+8E0h+dwOptions], r15d; dwOptions
0x180014f62  call    cs:__imp_RegCreateKeyExW
0x180014f68  test    eax, eax
0x180014f6a  jz      short loc_180014F8E
0x180014f6c  mov     edi, 80070000h
0x180014f71  jg      short loc_180014F77
0x180014f73  mov     ebx, eax
0x180014f75  jmp     short loc_180014F7C
0x180014f77  movzx   ebx, ax
0x180014f7a  or      ebx, edi
0x180014f7c  mov     r9d, 110h
0x180014f82  lea     rdx, aInitlogFailedR; "::InitLog - Failed: RegOpenKey(...) on "...
0x180014f89  jmp     loc_18001501C
0x180014f8e  mov     rcx, [rsp+8E0h+hKey]; hKey
0x180014f93  lea     rdx, aMsDistributedT; "MS Distributed Transaction Coordinatior"
0x180014f9a  call    cs:__imp_RegDeleteValueW
0x180014fa0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014fa4  lea     rdx, [rsp+8E0h+var_870]
0x180014fa9  mov     rcx, rax
0x180014fac  inc     rcx
0x180014faf  cmp     [rdx+rcx*2], r15w
0x180014fb4  jnz     short loc_180014FAC
0x180014fb6  lea     rdx, [rbp+7E0h+var_660]
0x180014fbd  inc     rax
0x180014fc0  cmp     [rdx+rax*2], r15w
0x180014fc5  jnz     short loc_180014FBD
0x180014fc7  add     eax, ecx
0x180014fc9  lea     rdx, aMsDistributedT_0; "MS Distributed Transaction Coordinator"
0x180014fd0  mov     rcx, [rsp+8E0h+hKey]; hKey
0x180014fd5  mov     r9d, 7; dwType
0x180014fdb  xor     r8d, r8d; Reserved
0x180014fde  lea     eax, ds:6[rax*2]
0x180014fe5  mov     [rsp+8E0h+samDesired], eax; cbData
0x180014fe9  lea     rax, [rbp+7E0h+Data]
0x180014ff0  mov     qword ptr [rsp+8E0h+dwOptions], rax; lpData
0x180014ff5  call    cs:__imp_RegSetValueExW
0x180014ffb  mov     edi, 80070000h
0x180015000  test    eax, eax
0x180015002  jz      short loc_18001502A
0x180015004  jg      short loc_18001500A
0x180015006  mov     ebx, eax
0x180015008  jmp     short loc_18001500F
0x18001500a  movzx   ebx, ax
0x18001500d  or      ebx, edi
0x18001500f  mov     r9d, 125h; unsigned int
0x180015015  lea     rdx, aInitlogFailedR_0; "::InitLog - Failed: RegSetValueEx(...)"
0x18001501c  lea     r8, aComComplusDtcS_11; "com\\complus\\dtc\\shared\\util\\initlo"...
0x180015023  mov     ecx, ebx; int
0x180015025  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18001502a  mov     rcx, [rsp+8E0h+hKey]; hKey
0x18001502f  test    rcx, rcx
0x180015032  jz      short loc_180015064
0x180015034  call    cs:__imp_RegCloseKey
0x18001503a  test    eax, eax
0x18001503c  jz      short loc_180015064
0x18001503e  jg      short loc_180015044
0x180015040  mov     ebx, eax
0x180015042  jmp     short loc_180015049
0x180015044  movzx   ebx, ax
0x180015047  or      ebx, edi
0x180015049  mov     r9d, 132h; unsigned int
0x18001504f  lea     rdx, aInitlogFailedR_1; "::InitLog - Failed: RegCloseKey(...)"
0x180015056  mov     ecx, ebx; int
0x180015058  lea     r8, aComComplusDtcS_11; "com\\complus\\dtc\\shared\\util\\initlo"...
0x18001505f  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180015064  mov     rcx, rsi; hLibModule
0x180015067  call    cs:__imp_FreeLibrary
0x18001506d  mov     eax, ebx
0x18001506f  mov     rcx, [rbp+7E0h+var_30]
0x180015076  xor     rcx, rsp; StackCookie
0x180015079  call    __security_check_cookie
0x18001507e  mov     rbx, [rsp+8E0h+arg_10]
0x180015086  add     rsp, 8C0h
0x18001508d  pop     r15
0x18001508f  pop     r14
0x180015091  pop     rdi
0x180015092  pop     rsi
0x180015093  pop     rbp
0x180015094  retn
```
