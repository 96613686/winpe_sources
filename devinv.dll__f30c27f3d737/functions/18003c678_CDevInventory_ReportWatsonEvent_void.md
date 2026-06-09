# CDevInventory::ReportWatsonEvent(void)

- ea: `0x18003c678`
- end: `0x18003cc4c`
- name: `?ReportWatsonEvent@CDevInventory@@QEAAHXZ`
- size: `1492`
- prototype: `__int64 __fastcall(CDevInventory *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a898`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180006ec4`
- `0x180007014`
- `0x18000dcec`
- `0x18003c2bc`
- `0x18003c678`
- `0x18006041c`
- `0x180060984`
- `0x180066c10`
- `0x18010d870`
- `0x180116010`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x18003c741`
- `ntdll!NtQuerySystemTime` at `0x18003c741`
- `ntdll!RtlTimeToTimeFields` at `0x18003c753`
- `ntdll!RtlTimeToTimeFields` at `0x18003c753`
- `ntdll!RtlGetVersion` at `0x18003c8e8`
- `ntdll!RtlGetVersion` at `0x18003c8e8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c804`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c931`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c804`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c931`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c78b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c799`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c78b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c799`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c820`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c94d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c987`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c9a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c9c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c9dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c820`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c94d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c987`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c9a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c9c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c9dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003cad6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003cad6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c832`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cadf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c832`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cadf`

## string_xrefs

- `0x18003c7f7`: `psapi.dll`
- `0x18003c924`: `wer.dll`
- `0x18003c943`: `WerReportCreate`
- `0x18003c9ff`: `CompatFailure01`
- `0x18003ca7d`: `devinv.dll`

## pseudocode

```c
__int64 __fastcall CDevInventory::ReportWatsonEvent(CDevInventory *this)
{
  HMODULE v1; // rdi
  void (*v2)(void); // r12
  HMODULE v3; // r14
  unsigned int v4; // r13d
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  HANDLE CurrentProcess; // rax
  int v9; // edx
  HMODULE v10; // rax
  FARPROC v11; // rsi
  FARPROC v12; // rbx
  HANDLE CurrentThread; // rbx
  HANDLE v14; // rax
  int v15; // eax
  int v16; // esi
  FILE *v17; // rax
  int v18; // ebx
  FILE *v19; // rax
  FILE *v20; // rax
  __int64 v21; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  FARPROC v27; // [rsp+60h] [rbp-A0h]
  FARPROC v28; // [rsp+68h] [rbp-98h]
  FARPROC v29; // [rsp+70h] [rbp-90h]
  int v30; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+88h] [rbp-78h]
  struct _TIME_FIELDS TimeFields; // [rsp+920h] [rbp+820h] BYREF
  _WORD v33[120]; // [rsp+930h] [rbp+830h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+A20h] [rbp+920h] BYREF
  unsigned __int16 v35[208]; // [rsp+B40h] [rbp+A40h] BYREF
  unsigned __int16 v36[208]; // [rsp+CE0h] [rbp+BE0h] BYREF
  unsigned __int16 v37[208]; // [rsp+E80h] [rbp+D80h] BYREF
  unsigned __int16 v38[208]; // [rsp+1020h] [rbp+F20h] BYREF
  _BYTE v39[528]; // [rsp+11C0h] [rbp+10C0h] BYREF

  memset_0(&v30, 0, 0x8A0u);
  memset_0(v35, 0, 0x192u);
  v24 = 0;
  v23 = 0;
  memset_0(v39, 0, 0x20Au);
  memset_0(v36, 0, 0x192u);
  memset_0(v37, 0, 0x192u);
  memset_0(v38, 0, 0x192u);
  v1 = 0;
  v2 = 0;
  TimeFields = 0;
  SystemTime.QuadPart = 0;
  NtQuerySystemTime(&SystemTime);
  RtlTimeToTimeFields(&SystemTime, &TimeFields);
  if ( TimeFields.Milliseconds != 123 )
  {
    v3 = 0;
LABEL_3:
    v4 = 1;
    goto LABEL_4;
  }
  v4 = 0;
  memset_0(&v30, 0, 0x8A0u);
  v30 = 2208;
  v31 = 0;
  StringCchPrintfW(v35, 0xC8u, L"GetDeviceMap timeout");
  Library = LoadLibraryExW(L"psapi.dll", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetModuleBaseNameW");
    if ( ProcAddress )
    {
      CurrentProcess = GetCurrentProcess();
      ((void (__fastcall *)(HANDLE, _QWORD, _BYTE *, __int64))ProcAddress)(CurrentProcess, 0, v39, 260);
      GetProcessVersionString(v36, v9);
      memset_0(v33, 0, 0xE8u);
      RtlGetVersionResource(&_ImageBase, 0, 2u, (struct _RTL_VERSION_RESOURCE *)v33);
      StringCchPrintfW(v37, 0xC8u, L"%u.%u.%u.%u", v33[0], v33[1], v33[2], v33[3]);
      memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
      VersionInformation.dwOSVersionInfoSize = 284;
      if ( RtlGetVersion(&VersionInformation) >= 0 )
      {
        LODWORD(v22) = VersionInformation.dwBuildNumber;
        LODWORD(v21) = VersionInformation.dwMinorVersion;
        StringCchPrintfW(v38, 0xC8u, L"%u.%u:%u", VersionInformation.dwMajorVersion, v21, v22);
      }
      v10 = LoadLibraryExW(L"wer.dll", 0, 0x800u);
      v1 = v10;
      if ( v10 )
      {
        v11 = GetProcAddress(v10, "WerReportCreate");
        if ( v11 )
        {
          v29 = GetProcAddress(v1, "WerReportSubmit");
          if ( v29 )
          {
            v27 = GetProcAddress(v1, "WerReportAddDump");
            if ( v27 )
            {
              v12 = GetProcAddress(v1, "WerReportSetParameter");
              if ( v12 )
              {
                v2 = (void (*)(void))GetProcAddress(v1, "WerReportCloseHandle");
                if ( v2 )
                {
                  v28 = GetProcAddress(v1, "WerpGetReportConsent");
                  if ( v28 )
                  {
                    if ( ((int (__fastcall *)(const wchar_t *, _QWORD, int *, __int64 *))v11)(
                           L"CompatFailure01",
                           0,
                           &v30,
                           &v24) >= 0
                      && ((int (__fastcall *)(__int64, _QWORD, const wchar_t *, unsigned __int16 *))v12)(
                           v24,
                           0,
                           L"FailureReason",
                           v35) >= 0 )
                    {
                      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _BYTE *))v12)(
                        v24,
                        1,
                        L"ApplicationName",
                        v39);
                      ((void (__fastcall *)(__int64, __int64, const wchar_t *, unsigned __int16 *))v12)(
                        v24,
                        2,
                        L"ApplicationVersion",
                        v36);
                      ((void (__fastcall *)(__int64, __int64, const wchar_t *, const wchar_t *))v12)(
                        v24,
                        3,
                        L"ModuleName",
                        L"devinv.dll");
                      ((void (__fastcall *)(__int64, __int64, const wchar_t *, unsigned __int16 *))v12)(
                        v24,
                        4,
                        L"ModuleVersion",
                        v37);
                      ((void (__fastcall *)(__int64, __int64, const wchar_t *, unsigned __int16 *))v12)(
                        v24,
                        5,
                        L"OSVersion",
                        v38);
                      CurrentThread = GetCurrentThread();
                      v14 = GetCurrentProcess();
                      if ( ((int (__fastcall *)(__int64, HANDLE, HANDLE, __int64, _QWORD, _QWORD, int))v27)(
                             v24,
                             v14,
                             CurrentThread,
                             3,
                             0,
                             0,
                             1) >= 0 )
                      {
                        v25 = 0;
                        if ( ((int (__fastcall *)(__int64, __int64, int *))v28)(v24, 1, &v25) >= 0 && v25 >= 3 )
                        {
                          v15 = ((__int64 (__fastcall *)(__int64, __int64, __int64, int *))v29)(v24, 2, 32, &v23);
                          v16 = v15;
                          if ( v15 >= 0 )
                            goto LABEL_3;
                          AslLogCallPrintf(
                            2,
                            "CDevInventory::ReportWatsonEvent",
                            1080,
                            "[0x%08x] Watson report submission failed. wer:0x%08x",
                            v15,
                            v23);
                          if ( EnableDevInvStdErrLog )
                          {
                            v17 = o___acrt_iob_func_0(2u);
                            fprintf(v17, "Error: %s, %u: ", "CDevInventory::ReportWatsonEvent", 1080);
                            v18 = v23;
                            v19 = o___acrt_iob_func_0(2u);
                            fprintf(v19, "[0x%08x] Watson report submission failed. wer:0x%08x", v16, v18);
                            v20 = o___acrt_iob_func_0(2u);
                            fprintf(v20, "\n");
                          }
                          if ( g_DeviceMapLogFunction )
                            TraceMessageCallback(
                              0x2000000,
                              "[0x%08x] Watson report submission failed. wer:0x%08x",
                              v16,
                              v23);
                          AslLogCallPrintf(
                            1,
                            "CDevInventory::ReportWatsonEvent",
                            1080,
                            "[0x%08x] Watson report submission failed. wer:0x%08x",
                            v16,
                            v23);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_4:
  if ( v24 && v2 )
    v2();
  if ( v3 )
    FreeLibrary(v3);
  if ( v1 )
    FreeLibrary(v1);
  return v4;
}

```

## disassembly

```asm
0x18003c678  push    rbp
0x18003c67a  push    rbx
0x18003c67b  push    rsi
0x18003c67c  push    rdi
0x18003c67d  push    r12
0x18003c67f  push    r13
0x18003c681  push    r14
0x18003c683  lea     rbp, [rsp-12E0h]
0x18003c68b  mov     eax, 13E0h
0x18003c690  call    _alloca_probe
0x18003c695  sub     rsp, rax
0x18003c698  mov     rax, cs:__security_cookie
0x18003c69f  xor     rax, rsp
0x18003c6a2  mov     [rbp+1310h+var_40], rax
0x18003c6a9  mov     esi, 8A0h
0x18003c6ae  lea     rcx, [rbp+1310h+var_1390]; void *
0x18003c6b2  mov     r8d, esi; Size
0x18003c6b5  xor     edx, edx; Val
0x18003c6b7  call    memset_0
0x18003c6bc  mov     ebx, 192h
0x18003c6c1  lea     rcx, [rbp+1310h+var_8D0]; void *
0x18003c6c8  mov     r8d, ebx; Size
0x18003c6cb  xor     edx, edx; Val
0x18003c6cd  call    memset_0
0x18003c6d2  xor     edx, edx; Val
0x18003c6d4  mov     [rsp+1410h+var_13C8], 0
0x18003c6dd  lea     r8d, [rbx+78h]; Size
0x18003c6e1  mov     [rsp+1410h+var_13D0], 0
0x18003c6e9  lea     rcx, [rbp+1310h+var_250]; void *
0x18003c6f0  call    memset_0
0x18003c6f5  mov     r8d, ebx; Size
0x18003c6f8  lea     rcx, [rbp+1310h+var_730]; void *
0x18003c6ff  xor     edx, edx; Val
0x18003c701  call    memset_0
0x18003c706  mov     r8d, ebx; Size
0x18003c709  lea     rcx, [rbp+1310h+var_590]; void *
0x18003c710  xor     edx, edx; Val
0x18003c712  call    memset_0
0x18003c717  mov     r8d, ebx; Size
0x18003c71a  lea     rcx, [rbp+1310h+var_3F0]; void *
0x18003c721  xor     edx, edx; Val
0x18003c723  call    memset_0
0x18003c728  xorps   xmm0, xmm0
0x18003c72b  lea     rcx, [rsp+1410h+SystemTime]; SystemTime
0x18003c730  xor     edi, edi
0x18003c732  xor     r12d, r12d
0x18003c735  movups  xmmword ptr [rbp+1310h+TimeFields.Year], xmm0
0x18003c73c  mov     qword ptr [rsp+1410h+SystemTime], rdi
0x18003c741  call    cs:__imp_NtQuerySystemTime
0x18003c747  lea     rdx, [rbp+1310h+TimeFields]; TimeFields
0x18003c74e  lea     rcx, [rsp+1410h+SystemTime]; Time
0x18003c753  call    cs:__imp_RtlTimeToTimeFields
0x18003c759  cmp     [rbp+1310h+TimeFields.Milliseconds], 7Bh ; '{'
0x18003c761  jz      short loc_18003C7C3
0x18003c763  xor     r14d, r14d
0x18003c766  mov     r13d, 1
0x18003c76c  mov     rcx, [rsp+1410h+var_13C8]
0x18003c771  test    rcx, rcx
0x18003c774  jz      short loc_18003C783
0x18003c776  test    r12, r12
0x18003c779  jz      short loc_18003C783
0x18003c77b  mov     rax, r12
0x18003c77e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c783  test    r14, r14
0x18003c786  jz      short loc_18003C791
0x18003c788  mov     rcx, r14; hLibModule
0x18003c78b  call    cs:__imp_FreeLibrary
0x18003c791  test    rdi, rdi
0x18003c794  jz      short loc_18003C79F
0x18003c796  mov     rcx, rdi; hLibModule
0x18003c799  call    cs:__imp_FreeLibrary
0x18003c79f  mov     eax, r13d
0x18003c7a2  mov     rcx, [rbp+1310h+var_40]
0x18003c7a9  xor     rcx, rsp; StackCookie
0x18003c7ac  call    __security_check_cookie
0x18003c7b1  add     rsp, 13E0h
0x18003c7b8  pop     r14
0x18003c7ba  pop     r13
0x18003c7bc  pop     r12
0x18003c7be  pop     rdi
0x18003c7bf  pop     rsi
0x18003c7c0  pop     rbx
0x18003c7c1  pop     rbp
0x18003c7c2  retn
0x18003c7c3  mov     r8, rsi; Size
0x18003c7c6  lea     rcx, [rbp+1310h+var_1390]; void *
0x18003c7ca  xor     edx, edx; Val
0x18003c7cc  xor     r13d, r13d
0x18003c7cf  call    memset_0
0x18003c7d4  mov     [rbp+1310h+var_1390], esi
0x18003c7d7  lea     r8, aGetdevicemapTi; "GetDeviceMap timeout"
0x18003c7de  mov     esi, 0C8h
0x18003c7e3  mov     [rbp+1310h+var_1388], rdi
0x18003c7e7  mov     edx, esi; unsigned __int64
0x18003c7e9  lea     rcx, [rbp+1310h+var_8D0]; unsigned __int16 *
0x18003c7f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c7f5  xor     edx, edx; hFile
0x18003c7f7  lea     rcx, aPsapiDll; "psapi.dll"
0x18003c7fe  mov     r8d, 800h; dwFlags
0x18003c804  call    cs:__imp_LoadLibraryExW
0x18003c80a  mov     r14, rax
0x18003c80d  test    rax, rax
0x18003c810  jz      loc_18003C76C
0x18003c816  lea     rdx, aGetmodulebasen; "GetModuleBaseNameW"
0x18003c81d  mov     rcx, rax; hModule
0x18003c820  call    cs:__imp_GetProcAddress
0x18003c826  mov     rbx, rax
0x18003c829  test    rax, rax
0x18003c82c  jz      loc_18003C76C
0x18003c832  call    cs:__imp_GetCurrentProcess
0x18003c838  lea     r9d, [rsi+3Ch]
0x18003c83c  xor     edx, edx
0x18003c83e  mov     rcx, rax
0x18003c841  lea     r8, [rbp+1310h+var_250]
0x18003c848  mov     rax, rbx
0x18003c84b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c850  lea     rcx, [rbp+1310h+var_730]; unsigned __int16 *
0x18003c857  call    ?GetProcessVersionString@@YAHPEAGH@Z; GetProcessVersionString(ushort *,int)
0x18003c85c  xor     edx, edx; Val
0x18003c85e  lea     r8d, [rsi+20h]; Size
0x18003c862  lea     rcx, [rbp+1310h+var_AE0]; void *
0x18003c869  call    memset_0
0x18003c86e  lea     r9, [rbp+1310h+var_AE0]; struct _RTL_VERSION_RESOURCE *
0x18003c875  xor     edx, edx; unsigned __int64
0x18003c877  lea     r8d, [r13+2]; unsigned int
0x18003c87b  lea     rcx, __ImageBase; void *
0x18003c882  call    ?RtlGetVersionResource@@YAXPEAX_KKPEAU_RTL_VERSION_RESOURCE@@@Z; RtlGetVersionResource(void *,unsigned __int64,ulong,_RTL_VERSION_RESOURCE *)
0x18003c887  movzx   ecx, [rbp+1310h+var_ADC]
0x18003c88e  lea     r8, aUUUU; "%u.%u.%u.%u"
0x18003c895  movzx   edx, [rbp+1310h+var_ADE]
0x18003c89c  movzx   eax, [rbp+1310h+var_ADA]
0x18003c8a3  movzx   r9d, [rbp+1310h+var_AE0]
0x18003c8ab  mov     [rsp+1410h+var_13E0], eax
0x18003c8af  mov     dword ptr [rsp+1410h+var_13E8], ecx
0x18003c8b3  lea     rcx, [rbp+1310h+var_590]; unsigned __int16 *
0x18003c8ba  mov     dword ptr [rsp+1410h+var_13F0], edx
0x18003c8be  mov     edx, esi; unsigned __int64
0x18003c8c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c8c5  xor     edx, edx; Val
0x18003c8c7  lea     r8d, [rsi+50h]; Size
0x18003c8cb  lea     rcx, [rbp+1310h+VersionInformation.dwMajorVersion]; void *
0x18003c8d2  call    memset_0
0x18003c8d7  lea     rcx, [rbp+1310h+VersionInformation]; lpVersionInformation
0x18003c8de  mov     [rbp+1310h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18003c8e8  call    cs:__imp_RtlGetVersion
0x18003c8ee  test    eax, eax
0x18003c8f0  js      short loc_18003C922
0x18003c8f2  mov     eax, [rbp+1310h+VersionInformation.dwBuildNumber]
0x18003c8f8  lea     r8, aUUU; "%u.%u:%u"
0x18003c8ff  mov     r9d, [rbp+1310h+VersionInformation.dwMajorVersion]
0x18003c906  lea     rcx, [rbp+1310h+var_3F0]; unsigned __int16 *
0x18003c90d  mov     dword ptr [rsp+1410h+var_13E8], eax
0x18003c911  mov     edx, esi; unsigned __int64
0x18003c913  mov     eax, [rbp+1310h+VersionInformation.dwMinorVersion]
0x18003c919  mov     dword ptr [rsp+1410h+var_13F0], eax
0x18003c91d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c922  xor     edx, edx; hFile
0x18003c924  lea     rcx, aWerDll; "wer.dll"
0x18003c92b  mov     r8d, 800h; dwFlags
0x18003c931  call    cs:__imp_LoadLibraryExW
0x18003c937  mov     rdi, rax
0x18003c93a  test    rax, rax
0x18003c93d  jz      loc_18003C76C
0x18003c943  lea     rdx, aWerreportcreat; "WerReportCreate"
0x18003c94a  mov     rcx, rax; hModule
0x18003c94d  call    cs:__imp_GetProcAddress
0x18003c953  mov     rsi, rax
0x18003c956  test    rax, rax
0x18003c959  jz      loc_18003C76C
0x18003c95f  lea     rdx, aWerreportsubmi; "WerReportSubmit"
0x18003c966  mov     rcx, rdi; hModule
0x18003c969  call    cs:__imp_GetProcAddress
0x18003c96f  mov     [rsp+1410h+var_13A0], rax
0x18003c974  test    rax, rax
0x18003c977  jz      loc_18003C76C
0x18003c97d  lea     rdx, aWerreportadddu; "WerReportAddDump"
0x18003c984  mov     rcx, rdi; hModule
0x18003c987  call    cs:__imp_GetProcAddress
0x18003c98d  mov     [rsp+1410h+var_13B0], rax
0x18003c992  test    rax, rax
0x18003c995  jz      loc_18003C76C
0x18003c99b  lea     rdx, aWerreportsetpa; "WerReportSetParameter"
0x18003c9a2  mov     rcx, rdi; hModule
0x18003c9a5  call    cs:__imp_GetProcAddress
0x18003c9ab  mov     rbx, rax
0x18003c9ae  test    rax, rax
0x18003c9b1  jz      loc_18003C76C
0x18003c9b7  lea     rdx, aWerreportclose; "WerReportCloseHandle"
0x18003c9be  mov     rcx, rdi; hModule
0x18003c9c1  call    cs:__imp_GetProcAddress
0x18003c9c7  mov     r12, rax
0x18003c9ca  test    rax, rax
0x18003c9cd  jz      loc_18003C76C
0x18003c9d3  lea     rdx, aWerpgetreportc; "WerpGetReportConsent"
0x18003c9da  mov     rcx, rdi; hModule
0x18003c9dd  call    cs:__imp_GetProcAddress
0x18003c9e3  mov     [rsp+1410h+var_13A8], rax
0x18003c9e8  test    rax, rax
0x18003c9eb  jz      loc_18003C76C
0x18003c9f1  lea     r9, [rsp+1410h+var_13C8]
0x18003c9f6  xor     edx, edx
0x18003c9f8  lea     r8, [rbp+1310h+var_1390]
0x18003c9fc  mov     rax, rsi
0x18003c9ff  lea     rcx, aCompatfailure0; "CompatFailure01"
0x18003ca06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca0b  test    eax, eax
0x18003ca0d  js      loc_18003C76C
0x18003ca13  mov     rcx, [rsp+1410h+var_13C8]
0x18003ca18  lea     r9, [rbp+1310h+var_8D0]
0x18003ca1f  lea     r8, aFailurereason; "FailureReason"
0x18003ca26  xor     edx, edx
0x18003ca28  mov     rax, rbx
0x18003ca2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca30  test    eax, eax
0x18003ca32  js      loc_18003C76C
0x18003ca38  mov     rcx, [rsp+1410h+var_13C8]
0x18003ca3d  lea     r9, [rbp+1310h+var_250]
0x18003ca44  lea     r8, aApplicationnam; "ApplicationName"
0x18003ca4b  mov     edx, 1
0x18003ca50  mov     rax, rbx
0x18003ca53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca58  mov     rcx, [rsp+1410h+var_13C8]
0x18003ca5d  lea     r9, [rbp+1310h+var_730]
0x18003ca64  lea     r8, aApplicationver; "ApplicationVersion"
0x18003ca6b  mov     edx, 2
0x18003ca70  mov     rax, rbx
0x18003ca73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca78  mov     rcx, [rsp+1410h+var_13C8]
0x18003ca7d  lea     r9, aDevinvDll_0; "devinv.dll"
0x18003ca84  mov     esi, 3
0x18003ca89  lea     r8, aModulename; "ModuleName"
0x18003ca90  mov     edx, esi
0x18003ca92  mov     rax, rbx
0x18003ca95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca9a  mov     rcx, [rsp+1410h+var_13C8]
0x18003ca9f  lea     r9, [rbp+1310h+var_590]
0x18003caa6  lea     r8, aModuleversion; "ModuleVersion"
0x18003caad  mov     rax, rbx
0x18003cab0  lea     edx, [rsi+1]
0x18003cab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cab8  mov     rcx, [rsp+1410h+var_13C8]
0x18003cabd  lea     r9, [rbp+1310h+var_3F0]
0x18003cac4  lea     r8, aOsversion; "OSVersion"
0x18003cacb  mov     rax, rbx
0x18003cace  lea     edx, [rsi+2]
0x18003cad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cad6  call    cs:__imp_GetCurrentThread
0x18003cadc  mov     rbx, rax
0x18003cadf  call    cs:__imp_GetCurrentProcess
0x18003cae5  mov     rcx, [rsp+1410h+var_13C8]
0x18003caea  mov     r9d, esi
0x18003caed  mov     rdx, rax
0x18003caf0  mov     [rsp+1410h+var_13E0], 1
0x18003caf8  mov     rax, [rsp+1410h+var_13B0]
0x18003cafd  mov     r8, rbx
0x18003cb00  mov     [rsp+1410h+var_13E8], r13
0x18003cb05  mov     [rsp+1410h+var_13F0], r13
0x18003cb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb0f  test    eax, eax
0x18003cb11  js      loc_18003C76C
0x18003cb17  mov     rcx, [rsp+1410h+var_13C8]
0x18003cb1c  lea     r8, [rsp+1410h+var_13C0]
0x18003cb21  mov     rax, [rsp+1410h+var_13A8]
0x18003cb26  lea     edx, [rsi-2]
0x18003cb29  mov     [rsp+1410h+var_13C0], r13d
0x18003cb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb33  test    eax, eax
0x18003cb35  js      loc_18003C76C
0x18003cb3b  cmp     [rsp+1410h+var_13C0], esi
0x18003cb3f  jl      loc_18003C76C
0x18003cb45  mov     rcx, [rsp+1410h+var_13C8]
0x18003cb4a  lea     ebx, [rsi-1]
0x18003cb4d  mov     rax, [rsp+1410h+var_13A0]
0x18003cb52  lea     r9, [rsp+1410h+var_13D0]
0x18003cb57  mov     edx, ebx
0x18003cb59  lea     r8d, [rsi+1Dh]
0x18003cb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb62  mov     esi, eax
0x18003cb64  test    eax, eax
0x18003cb66  jns     loc_18003C766
0x18003cb6c  mov     ecx, [rsp+1410h+var_13D0]
0x18003cb70  lea     r9, a0x08xWatsonRep; "[0x%08x] Watson report submission faile"...
0x18003cb77  mov     dword ptr [rsp+1410h+var_13E8], ecx
0x18003cb7b  lea     rdx, aCdevinventoryR; "CDevInventory::ReportWatsonEvent"
0x18003cb82  mov     ecx, ebx
0x18003cb84  mov     dword ptr [rsp+1410h+var_13F0], eax
0x18003cb88  mov     r8d, 438h
0x18003cb8e  call    AslLogCallPrintf
0x18003cb93  cmp     cs:EnableDevInvStdErrLog, r13d
0x18003cb9a  jz      short loc_18003CBFB
0x18003cb9c  mov     ecx, ebx; Ix
0x18003cb9e  call    _o___acrt_iob_func_0
0x18003cba3  mov     rcx, rax; Stream
0x18003cba6  lea     r8, aCdevinventoryR; "CDevInventory::ReportWatsonEvent"
0x18003cbad  mov     r9d, 438h
0x18003cbb3  lea     rdx, Format; "Error: %s, %u: "
0x18003cbba  call    fprintf
0x18003cbbf  mov     ebx, [rsp+1410h+var_13D0]
0x18003cbc3  mov     ecx, 2; Ix
0x18003cbc8  call    _o___acrt_iob_func_0
  ... truncated ...
```
