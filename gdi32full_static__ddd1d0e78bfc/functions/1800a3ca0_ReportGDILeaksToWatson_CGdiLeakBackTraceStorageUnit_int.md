# ReportGDILeaksToWatson(CGdiLeakBackTraceStorageUnit *,int)

- ea: `0x1800a3ca0`
- end: `0x1800a43cd`
- name: `?ReportGDILeaksToWatson@@YAXPEAVCGdiLeakBackTraceStorageUnit@@H@Z`
- size: `1837`
- prototype: `void __fastcall(struct CGdiLeakBackTraceStorageUnit *, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180030414`
- `0x18003a6f8`
- `0x18006fb6c`
- `0x180080604`
- `0x1800a3120`
- `0x1800a32ac`
- `0x1800a32f4`
- `0x1800a333c`
- `0x1800a3478`
- `0x1800a362c`
- `0x1800a36a4`
- `0x1800a3ca0`
- `0x1800a47fc`
- `0x1800a68bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a3e63`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a3e63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800a3e0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800a3e0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a41b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a41b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a41c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a41c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a42df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a42fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4317`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4333`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a434f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a436b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4395`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a42df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a42fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4317`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4333`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a434f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a436b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4395`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800a3f09`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800a3f09`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800a3ec0`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800a3ec0`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800a3f39`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800a3f39`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterMemoryBlock` at `0x1800a3dd6`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterMemoryBlock` at `0x1800a3dd6`
- `wer!WerpGetReportConsent` at `0x1800a422c`
- `wer!WerpGetReportConsent` at `0x1800a422c`
- `wer!WerReportSetParameter` at `0x1800a3fe6`
- `wer!WerReportSetParameter` at `0x1800a4030`
- `wer!WerReportSetParameter` at `0x1800a407a`
- `wer!WerReportSetParameter` at `0x1800a40fa`
- `wer!WerReportSetParameter` at `0x1800a413e`
- `wer!WerReportSetParameter` at `0x1800a3fe6`
- `wer!WerReportSetParameter` at `0x1800a4030`
- `wer!WerReportSetParameter` at `0x1800a407a`
- `wer!WerReportSetParameter` at `0x1800a40fa`
- `wer!WerReportSetParameter` at `0x1800a413e`
- `wer!WerReportCloseHandle` at `0x1800a3d7c`
- `wer!WerReportCloseHandle` at `0x1800a3d7c`
- `wer!WerReportSubmit` at `0x1800a4273`
- `wer!WerReportSubmit` at `0x1800a4273`
- `wer!WerReportCreate` at `0x1800a3d9b`
- `wer!WerReportCreate` at `0x1800a3d9b`
- `wer!WerReportAddDump` at `0x1800a41e9`
- `wer!WerReportAddDump` at `0x1800a41e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall ReportGDILeaksToWatson(struct CGdiLeakBackTraceStorageUnit *a1, unsigned int a2)
{
  ExceptionInformationWrapper *v4; // rax
  ExceptionInformationWrapper *v5; // rbx
  HREPORT v6; // rcx
  HRESULT v7; // eax
  HRESULT v8; // eax
  wchar_t *v9; // rax
  const unsigned __int16 *v10; // rax
  int v11; // eax
  bool v12; // r14
  bool v13; // r12
  __int64 FileVersionInfoSizeW; // rdi
  WER_CONSENT v15; // edi
  HRESULT v16; // eax
  const WCHAR *v17; // r9
  HRESULT v18; // eax
  const WCHAR *v19; // r9
  HRESULT v20; // eax
  int v21; // eax
  HRESULT v22; // eax
  HRESULT v23; // eax
  HANDLE CurrentThread; // r15
  HANDLE CurrentProcess; // rax
  HRESULT v26; // eax
  int ReportConsent; // eax
  HRESULT v28; // eax
  struct CGDIHandleLeakTracker *v29; // rcx
  ExceptionInformationWrapper **v30; // rdx
  void *v31; // rcx
  WCHAR *v32; // rcx
  LPWSTR v33; // rcx
  WCHAR *v34; // rcx
  WCHAR *v35; // rcx
  WCHAR *v36; // rcx
  PWER_REPORT_INFORMATION v37; // rcx
  wil *v38; // rcx
  int pExceptionParam; // [rsp+20h] [rbp-B8h]
  int pExceptionParama; // [rsp+20h] [rbp-B8h]
  HREPORT hReportHandle; // [rsp+40h] [rbp-98h] BYREF
  LPCWSTR lptstrFilename; // [rsp+48h] [rbp-90h] BYREF
  LPWSTR lpFilename; // [rsp+50h] [rbp-88h] BYREF
  PWER_REPORT_INFORMATION pReportInformation; // [rsp+58h] [rbp-80h]
  LPVOID lpData; // [rsp+60h] [rbp-78h] BYREF
  PCWSTR v46; // [rsp+68h] [rbp-70h] BYREF
  PCWSTR v47; // [rsp+70h] [rbp-68h] BYREF
  PCWSTR pwzValue; // [rsp+78h] [rbp-60h] BYREF
  ExceptionInformationWrapper *v49; // [rsp+80h] [rbp-58h] BYREF
  LPVOID lpBuffer; // [rsp+88h] [rbp-50h] BYREF
  _QWORD pExceptionObject[4]; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  int v53; // [rsp+F0h] [rbp+18h] BYREF
  unsigned int puLen; // [rsp+F8h] [rbp+20h] BYREF

  hReportHandle = 0;
  try
  {
    wil::make_unique_hlocal<_WER_REPORT_INFORMATION,>();
    memset_0(pReportInformation, 0, sizeof(struct _WER_REPORT_INFORMATION));
    v4 = (ExceptionInformationWrapper *)operator new(0x178u);
    v49 = v4;
    if ( v4 )
      v5 = ExceptionInformationWrapper::ExceptionInformationWrapper(v4, a1);
    else
      v5 = 0;
    v49 = v5;
    wil::make_unique_hlocal<unsigned short [0]>(&lptstrFilename, 260);
    wil::make_unique_hlocal<unsigned short [0]>(&pwzValue, 260);
    wil::make_unique_hlocal<unsigned short [0]>(&v47, 260);
    wil::make_unique_hlocal<unsigned short [0]>(&lpFilename, 260);
    wil::make_unique_hlocal<unsigned short [0]>(&v46, 3);
    pReportInformation->dwSize = 2208;
    v6 = hReportHandle;
    hReportHandle = 0;
    if ( v6 )
      WerReportCloseHandle(v6);
    v7 = WerReportCreate(L"GDIObjectLeak", WerReportNonCritical, pReportInformation, &hReportHandle);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v7,
        pExceptionParam);
    v8 = WerRegisterMemoryBlock((char *)v5 + 184, 0xC0u);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v8,
        pExceptionParam);
    if ( !GetModuleFileNameW(0, lpFilename, 0x104u) )
    {
      pExceptionObject[2] = 0;
      pExceptionObject[1] = "bad exception";
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_exception *)pExceptionObject;
    }
    v9 = wcsrchr(lpFilename, 0x5Cu);
    if ( v9 )
      v10 = v9 + 1;
    else
      v10 = lpFilename;
    v11 = StringCchCopyW((unsigned __int16 *)lptstrFilename, 0x104u, v10);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x134,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v11,
        pExceptionParam);
    v12 = 0;
    v13 = 0;
    FileVersionInfoSizeW = GetFileVersionInfoSizeW(lptstrFilename, 0);
    wil::make_unique_hlocal<unsigned char [0]>(&lpData, FileVersionInfoSizeW);
    puLen = 0;
    lpBuffer = 0;
    if ( (_DWORD)FileVersionInfoSizeW
      && GetFileVersionInfoW(lptstrFilename, 0, FileVersionInfoSizeW, lpData)
      && VerQueryValueW(lpData, L"\\", &lpBuffer, &puLen) )
    {
      v15 = WerConsentNotAsked;
      v12 = StringCchPrintfW(
              (unsigned __int16 *)pwzValue,
              0x104u,
              L"%hu.%hu.%hu.%hu",
              *((unsigned __int16 *)lpBuffer + 9),
              *((unsigned __int16 *)lpBuffer + 8),
              *((unsigned __int16 *)lpBuffer + 11),
              *((unsigned __int16 *)lpBuffer + 10)) >= 0;
      pExceptionParam = *((_DWORD *)lpBuffer + 3);
      v13 = StringCchPrintfW((unsigned __int16 *)v47, 0x104u, L"%u.%u", *((unsigned int *)lpBuffer + 2)) >= 0;
    }
    else
    {
      v15 = WerConsentNotAsked;
    }
    v16 = WerReportSetParameter(hReportHandle, 0, L"AppName", lptstrFilename);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x151,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v16,
        pExceptionParam);
    v17 = L"0.0.0.0";
    if ( v12 )
      v17 = pwzValue;
    v18 = WerReportSetParameter(hReportHandle, 1u, L"AppVersion", v17);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x152,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v18,
        pExceptionParam);
    v19 = L"0.0";
    if ( v13 )
      v19 = v47;
    v20 = WerReportSetParameter(hReportHandle, 2u, L"AppStamp", v19);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x153,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v20,
        pExceptionParam);
    v21 = StringCchPrintfW((unsigned __int16 *)v46, 3u, L"%x", a2);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x155,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v21,
        pExceptionParam);
    v22 = WerReportSetParameter(hReportHandle, 3u, L"GDIObjectType", v46);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v22,
        pExceptionParam);
    v23 = WerReportSetParameter(hReportHandle, 4u, L"StackHash", L"0");
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x158,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v23,
        pExceptionParam);
    *(_DWORD *)v5 = -2143354879;
    *((_QWORD *)v5 + 2) = ReportGDILeaksToWatson;
    *((_DWORD *)v5 + 6) = 3;
    *((_QWORD *)v5 + 4) = (char *)v5 + 184;
    *((_QWORD *)v5 + 5) = *((unsigned int *)v5 + 90);
    *((_QWORD *)v5 + 6) = *((unsigned int *)v5 + 92);
    *((_QWORD *)v5 + 19) = v5;
    *((_QWORD *)v5 + 21) = (char *)v5 + 152;
    *((_DWORD *)v5 + 44) = 1;
    CurrentThread = GetCurrentThread();
    CurrentProcess = GetCurrentProcess();
    v26 = WerReportAddDump(
            hReportHandle,
            CurrentProcess,
            CurrentThread,
            WerDumpTypeMiniDump,
            (PWER_EXCEPTION_INFORMATION)((char *)v5 + 168),
            0,
            0);
    if ( v26 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v26,
        pExceptionParama);
    v53 = 0;
    ReportConsent = WerpGetReportConsent(hReportHandle, 1, &v53);
    if ( ReportConsent < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)ReportConsent,
        pExceptionParama);
    if ( v53 >= 3 )
      v15 = WerConsentApproved;
    v28 = WerReportSubmit(hReportHandle, v15, 0x414u, 0);
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x172,
        (unsigned int)"clientcore\\windows\\core\\ntgdi\\client\\telemetry\\gdihandleleaktracker.cxx",
        (const char *)(unsigned int)v28,
        pExceptionParama);
    v29 = g_pExceptionInformationCacheList;
    v30 = (ExceptionInformationWrapper **)*((_QWORD *)g_pExceptionInformationCacheList + 1);
    if ( v30 == *((ExceptionInformationWrapper ***)g_pExceptionInformationCacheList + 2) )
    {
      std::vector<std::unique_ptr<ExceptionInformationWrapper>>::_Emplace_reallocate<std::unique_ptr<ExceptionInformationWrapper>>(
        g_pExceptionInformationCacheList,
        v30,
        &v49);
    }
    else
    {
      v49 = 0;
      *v30 = v5;
      *((_QWORD *)v29 + 1) += 8LL;
    }
    v31 = lpData;
    lpData = 0;
    if ( v31 )
      LocalFree(v31);
    v32 = (WCHAR *)v46;
    v46 = 0;
    if ( v32 )
      LocalFree(v32);
    v33 = lpFilename;
    lpFilename = 0;
    if ( v33 )
      LocalFree(v33);
    v34 = (WCHAR *)v47;
    v47 = 0;
    if ( v34 )
      LocalFree(v34);
    v35 = (WCHAR *)pwzValue;
    pwzValue = 0;
    if ( v35 )
      LocalFree(v35);
    v36 = (WCHAR *)lptstrFilename;
    lptstrFilename = 0;
    if ( v36 )
      LocalFree(v36);
    std::unique_ptr<ExceptionInformationWrapper>::~unique_ptr<ExceptionInformationWrapper>(&v49);
    v37 = pReportInformation;
    pReportInformation = 0;
    if ( v37 )
      LocalFree(v37);
    tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&long WerReportCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,long (*)(void *),&long WerReportCloseHandle(void *),0>>(&hReportHandle);
  }
  catch ( ... )
  {
    if ( (int)wil::ResultFromCaughtException(v38) >= 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
}

```

## disassembly

```asm
0x1800a3ca0  mov     [rsp+arg_0], rbx
0x1800a3ca5  mov     [rsp+arg_8], rsi
0x1800a3caa  push    rdi
0x1800a3cab  push    r12
0x1800a3cad  push    r13
0x1800a3caf  push    r14
0x1800a3cb1  push    r15
0x1800a3cb3  sub     rsp, 0B0h
0x1800a3cba  mov     r13d, edx
0x1800a3cbd  mov     rbx, rcx
0x1800a3cc0  xor     edi, edi
0x1800a3cc2  mov     [rsp+0D8h+hReportHandle], rdi
0x1800a3cc7  lea     rcx, [rsp+0D8h+pReportInformation]
0x1800a3ccc  call    ??$make_unique_hlocal@U_WER_REPORT_INFORMATION@@$$V@wil@@YA?AV?$unique_ptr@U_WER_REPORT_INFORMATION@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_WER_REPORT_INFORMATION,>(void)
0x1800a3cd1  nop
0x1800a3cd2  mov     esi, 8A0h
0x1800a3cd7  mov     r8d, esi; Size
0x1800a3cda  xor     edx, edx; Val
0x1800a3cdc  mov     rcx, [rsp+0D8h+pReportInformation]; void *
0x1800a3ce1  call    memset_0
0x1800a3ce6  mov     ecx, 178h; dwBytes
0x1800a3ceb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a3cf0  mov     [rsp+0D8h+var_58], rax
0x1800a3cf8  test    rax, rax
0x1800a3cfb  jz      short loc_1800A3D0D
0x1800a3cfd  mov     rdx, rbx; struct CGdiLeakBackTraceStorageUnit *
0x1800a3d00  mov     rcx, rax; this
0x1800a3d03  call    ??0ExceptionInformationWrapper@@QEAA@PEAVCGdiLeakBackTraceStorageUnit@@@Z; ExceptionInformationWrapper::ExceptionInformationWrapper(CGdiLeakBackTraceStorageUnit *)
0x1800a3d08  mov     rbx, rax
0x1800a3d0b  jmp     short loc_1800A3D10
0x1800a3d0d  mov     rbx, rdi
0x1800a3d10  mov     [rsp+0D8h+var_58], rbx
0x1800a3d18  mov     r14d, 104h
0x1800a3d1e  mov     edx, r14d
0x1800a3d21  lea     rcx, [rsp+0D8h+lptstrFilename]
0x1800a3d26  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a3d2b  nop
0x1800a3d2c  mov     edx, r14d
0x1800a3d2f  lea     rcx, [rsp+0D8h+pwzValue]
0x1800a3d34  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a3d39  nop
0x1800a3d3a  mov     edx, r14d
0x1800a3d3d  lea     rcx, [rsp+0D8h+var_68]
0x1800a3d42  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a3d47  nop
0x1800a3d48  mov     edx, r14d
0x1800a3d4b  lea     rcx, [rsp+0D8h+lpFilename]
0x1800a3d50  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a3d55  nop
0x1800a3d56  mov     edx, 3
0x1800a3d5b  lea     rcx, [rsp+0D8h+var_70]
0x1800a3d60  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a3d65  nop
0x1800a3d66  mov     rax, [rsp+0D8h+pReportInformation]
0x1800a3d6b  mov     [rax], esi
0x1800a3d6d  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a3d72  mov     [rsp+0D8h+hReportHandle], rdi
0x1800a3d77  test    rcx, rcx
0x1800a3d7a  jz      short loc_1800A3D88
0x1800a3d7c  call    cs:__imp_WerReportCloseHandle
0x1800a3d83  nop     dword ptr [rax+rax+00h]
0x1800a3d88  lea     r9, [rsp+0D8h+hReportHandle]; phReportHandle
0x1800a3d8d  mov     r8, [rsp+0D8h+pReportInformation]; pReportInformation
0x1800a3d92  xor     edx, edx; repType
0x1800a3d94  lea     rcx, pwzEventType; "GDIObjectLeak"
0x1800a3d9b  call    cs:__imp_WerReportCreate
0x1800a3da2  nop     dword ptr [rax+rax+00h]
0x1800a3da7  mov     rcx, [rsp+0D8h]; this
0x1800a3daf  test    eax, eax
0x1800a3db1  jns     short loc_1800A3DC7
0x1800a3db3  mov     r9d, eax; char *
0x1800a3db6  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a3dbd  mov     edx, 125h; void *
0x1800a3dc2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a3dc7  lea     r15, [rbx+0B8h]
0x1800a3dce  mov     edx, 0C0h; dwSize
0x1800a3dd3  mov     rcx, r15; pvAddress
0x1800a3dd6  call    cs:__imp_WerRegisterMemoryBlock
0x1800a3ddd  nop     dword ptr [rax+rax+00h]
0x1800a3de2  mov     rcx, [rsp+0D8h]; this
0x1800a3dea  test    eax, eax
0x1800a3dec  jns     short loc_1800A3E02
0x1800a3dee  mov     r9d, eax; char *
0x1800a3df1  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a3df8  mov     edx, 127h; void *
0x1800a3dfd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a3e02  mov     r8d, r14d; nSize
0x1800a3e05  mov     rdx, [rsp+0D8h+lpFilename]; lpFilename
0x1800a3e0a  xor     ecx, ecx; hModule
0x1800a3e0c  call    cs:__imp_GetModuleFileNameW
0x1800a3e13  nop     dword ptr [rax+rax+00h]
0x1800a3e18  test    eax, eax
0x1800a3e1a  jnz     short loc_1800A3E59
0x1800a3e1c  xorps   xmm0, xmm0
0x1800a3e1f  movups  [rsp+0D8h+var_40], xmm0
0x1800a3e27  lea     rax, aBadException; "bad exception"
0x1800a3e2e  mov     qword ptr [rsp+0D8h+var_40], rax
0x1800a3e36  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800a3e3d  mov     [rsp+0D8h+pExceptionObject], rax
0x1800a3e45  lea     rdx, _TI2?AVbad_exception@std@@; pThrowInfo
0x1800a3e4c  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x1800a3e54  call    _CxxThrowException_0
0x1800a3e59  mov     edx, 5Ch ; '\'; Ch
0x1800a3e5e  mov     rcx, [rsp+0D8h+lpFilename]; Str
0x1800a3e63  call    cs:__imp_wcsrchr
0x1800a3e6a  nop     dword ptr [rax+rax+00h]
0x1800a3e6f  mov     esi, 2
0x1800a3e74  test    rax, rax
0x1800a3e77  jz      short loc_1800A3E7E
0x1800a3e79  add     rax, rsi
0x1800a3e7c  jmp     short loc_1800A3E83
0x1800a3e7e  mov     rax, [rsp+0D8h+lpFilename]
0x1800a3e83  mov     r8, rax; unsigned __int16 *
0x1800a3e86  mov     rdx, r14; unsigned __int64
0x1800a3e89  mov     rcx, [rsp+0D8h+lptstrFilename]; unsigned __int16 *
0x1800a3e8e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a3e93  mov     rcx, [rsp+0D8h]; this
0x1800a3e9b  test    eax, eax
0x1800a3e9d  jns     short loc_1800A3EB3
0x1800a3e9f  mov     r9d, eax; char *
0x1800a3ea2  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a3ea9  mov     edx, 134h; void *
0x1800a3eae  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a3eb3  mov     r14b, dil
0x1800a3eb6  mov     r12b, dil
0x1800a3eb9  xor     edx, edx; lpdwHandle
0x1800a3ebb  mov     rcx, [rsp+0D8h+lptstrFilename]; lptstrFilename
0x1800a3ec0  call    cs:__imp_GetFileVersionInfoSizeW
0x1800a3ec7  nop     dword ptr [rax+rax+00h]
0x1800a3ecc  mov     edi, eax
0x1800a3ece  mov     edx, eax
0x1800a3ed0  lea     rcx, [rsp+0D8h+lpData]
0x1800a3ed5  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x1800a3eda  nop
0x1800a3edb  mov     [rsp+0D8h+puLen], 0
0x1800a3ee6  mov     [rsp+0D8h+lpBuffer], 0
0x1800a3ef2  test    edi, edi
0x1800a3ef4  jz      loc_1800A3FCE
0x1800a3efa  mov     r9, [rsp+0D8h+lpData]; lpData
0x1800a3eff  mov     r8d, edi; dwLen
0x1800a3f02  xor     edx, edx; dwHandle
0x1800a3f04  mov     rcx, [rsp+0D8h+lptstrFilename]; lptstrFilename
0x1800a3f09  call    cs:__imp_GetFileVersionInfoW
0x1800a3f10  nop     dword ptr [rax+rax+00h]
0x1800a3f15  test    eax, eax
0x1800a3f17  jz      loc_1800A3FCE
0x1800a3f1d  lea     r9, [rsp+0D8h+puLen]; puLen
0x1800a3f25  lea     r8, [rsp+0D8h+lpBuffer]; lplpBuffer
0x1800a3f2d  lea     rdx, SubBlock; "\\"
0x1800a3f34  mov     rcx, [rsp+0D8h+lpData]; pBlock
0x1800a3f39  call    cs:__imp_VerQueryValueW
0x1800a3f40  nop     dword ptr [rax+rax+00h]
0x1800a3f45  test    eax, eax
0x1800a3f47  jz      loc_1800A3FCE
0x1800a3f4d  mov     r8, [rsp+0D8h+lpBuffer]
0x1800a3f55  movzx   eax, word ptr [r8+14h]
0x1800a3f5a  movzx   ecx, word ptr [r8+16h]
0x1800a3f5f  movzx   edx, word ptr [r8+10h]
0x1800a3f64  movzx   r9d, word ptr [r8+12h]
0x1800a3f69  mov     [rsp+0D8h+dwFlags], eax
0x1800a3f6d  mov     dword ptr [rsp+0D8h+pDumpCustomOptions], ecx
0x1800a3f71  mov     dword ptr [rsp+0D8h+pExceptionParam], edx
0x1800a3f75  lea     r8, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x1800a3f7c  mov     edx, 104h; unsigned __int64
0x1800a3f81  mov     rcx, [rsp+0D8h+pwzValue]; unsigned __int16 *
0x1800a3f86  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3f8b  mov     r14d, eax
0x1800a3f8e  shr     r14d, 1Fh
0x1800a3f92  mov     edi, 1
0x1800a3f97  xor     r14b, dil
0x1800a3f9a  mov     r9, [rsp+0D8h+lpBuffer]
0x1800a3fa2  mov     r8d, [r9+0Ch]
0x1800a3fa6  mov     dword ptr [rsp+0D8h+pExceptionParam], r8d
0x1800a3fab  mov     r9d, [r9+8]
0x1800a3faf  lea     r8, aUU; "%u.%u"
0x1800a3fb6  mov     edx, 104h; unsigned __int64
0x1800a3fbb  mov     rcx, [rsp+0D8h+var_68]; unsigned __int16 *
0x1800a3fc0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3fc5  test    eax, eax
0x1800a3fc7  js      short loc_1800A3FD3
0x1800a3fc9  mov     r12b, dil
0x1800a3fcc  jmp     short loc_1800A3FD3
0x1800a3fce  mov     edi, 1
0x1800a3fd3  mov     r9, [rsp+0D8h+lptstrFilename]; pwzValue
0x1800a3fd8  lea     r8, pwzName; "AppName"
0x1800a3fdf  xor     edx, edx; dwparamID
0x1800a3fe1  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a3fe6  call    cs:__imp_WerReportSetParameter
0x1800a3fed  nop     dword ptr [rax+rax+00h]
0x1800a3ff2  mov     rcx, [rsp+0D8h]; this
0x1800a3ffa  test    eax, eax
0x1800a3ffc  jns     short loc_1800A4012
0x1800a3ffe  mov     r9d, eax; char *
0x1800a4001  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a4008  mov     edx, 151h; void *
0x1800a400d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a4012  lea     r9, a0000; "0.0.0.0"
0x1800a4019  test    r14b, r14b
0x1800a401c  cmovnz  r9, [rsp+0D8h+pwzValue]; pwzValue
0x1800a4022  lea     r8, aAppversion; "AppVersion"
0x1800a4029  mov     edx, edi; dwparamID
0x1800a402b  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a4030  call    cs:__imp_WerReportSetParameter
0x1800a4037  nop     dword ptr [rax+rax+00h]
0x1800a403c  test    eax, eax
0x1800a403e  jns     short loc_1800A405C
0x1800a4040  mov     rcx, [rsp+0D8h]; this
0x1800a4048  mov     r9d, eax; char *
0x1800a404b  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a4052  mov     edx, 152h; void *
0x1800a4057  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a405c  lea     r9, a00; "0.0"
0x1800a4063  test    r12b, r12b
0x1800a4066  cmovnz  r9, [rsp+0D8h+var_68]; pwzValue
0x1800a406c  lea     r8, aAppstamp; "AppStamp"
0x1800a4073  mov     edx, esi; dwparamID
0x1800a4075  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a407a  call    cs:__imp_WerReportSetParameter
0x1800a4081  nop     dword ptr [rax+rax+00h]
0x1800a4086  mov     rcx, [rsp+0D8h]; this
0x1800a408e  xor     r12d, r12d
0x1800a4091  test    eax, eax
0x1800a4093  jns     short loc_1800A40A9
0x1800a4095  mov     r9d, eax; char *
0x1800a4098  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a409f  mov     edx, 153h; void *
0x1800a40a4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a40a9  mov     r9d, r13d
0x1800a40ac  lea     r8, asc_1800E6FE4; "%x"
0x1800a40b3  mov     r13d, 3
0x1800a40b9  mov     edx, r13d; unsigned __int64
0x1800a40bc  mov     rcx, [rsp+0D8h+var_70]; unsigned __int16 *
0x1800a40c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a40c6  mov     rcx, [rsp+0D8h]; this
0x1800a40ce  test    eax, eax
0x1800a40d0  jns     short loc_1800A40E6
0x1800a40d2  mov     r9d, eax; char *
0x1800a40d5  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a40dc  mov     edx, 155h; void *
0x1800a40e1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a40e6  mov     r9, [rsp+0D8h+var_70]; pwzValue
0x1800a40eb  lea     r8, aGdiobjecttype; "GDIObjectType"
0x1800a40f2  mov     edx, r13d; dwparamID
0x1800a40f5  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a40fa  call    cs:__imp_WerReportSetParameter
0x1800a4101  nop     dword ptr [rax+rax+00h]
0x1800a4106  mov     rcx, [rsp+0D8h]; this
0x1800a410e  test    eax, eax
0x1800a4110  jns     short loc_1800A4126
0x1800a4112  mov     r9d, eax; char *
0x1800a4115  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a411c  mov     edx, 156h; void *
0x1800a4121  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a4126  lea     r9, pwzValue; "0"
0x1800a412d  lea     r8, aStackhash; "StackHash"
0x1800a4134  mov     edx, 4; dwparamID
0x1800a4139  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a413e  call    cs:__imp_WerReportSetParameter
0x1800a4145  nop     dword ptr [rax+rax+00h]
0x1800a414a  mov     rcx, [rsp+0D8h]; this
0x1800a4152  test    eax, eax
0x1800a4154  jns     short loc_1800A416A
0x1800a4156  mov     r9d, eax; char *
0x1800a4159  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a4160  mov     edx, 158h; void *
0x1800a4165  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a416a  lea     rcx, [rbx+98h]
0x1800a4171  lea     r14, [rbx+0A8h]
0x1800a4178  mov     dword ptr [rbx], 803F0001h
0x1800a417e  lea     rax, ?ReportGDILeaksToWatson@@YAXPEAVCGdiLeakBackTraceStorageUnit@@H@Z; ReportGDILeaksToWatson(CGdiLeakBackTraceStorageUnit *,int)
0x1800a4185  mov     [rbx+10h], rax
0x1800a4189  mov     [rbx+18h], r13d
0x1800a418d  mov     [rbx+20h], r15
0x1800a4191  mov     eax, [r15+0B0h]
0x1800a4198  mov     [rbx+28h], rax
0x1800a419c  mov     eax, [r15+0B8h]
0x1800a41a3  mov     [rbx+30h], rax
0x1800a41a7  mov     [rcx], rbx
0x1800a41aa  mov     [r14], rcx
0x1800a41ad  mov     [r14+8], edi
0x1800a41b1  call    cs:__imp_GetCurrentThread
0x1800a41b8  nop     dword ptr [rax+rax+00h]
0x1800a41bd  mov     r15, rax
0x1800a41c0  call    cs:__imp_GetCurrentProcess
0x1800a41c7  nop     dword ptr [rax+rax+00h]
0x1800a41cc  mov     [rsp+0D8h+dwFlags], r12d; dwFlags
0x1800a41d1  mov     [rsp+0D8h+pDumpCustomOptions], r12; pDumpCustomOptions
0x1800a41d6  mov     [rsp+0D8h+pExceptionParam], r14; int
0x1800a41db  mov     r9d, esi; dumpType
0x1800a41de  mov     r8, r15; hThread
0x1800a41e1  mov     rdx, rax; hProcess
0x1800a41e4  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a41e9  call    cs:__imp_WerReportAddDump
0x1800a41f0  nop     dword ptr [rax+rax+00h]
0x1800a41f5  mov     rcx, [rsp+0D8h]; this
0x1800a41fd  test    eax, eax
0x1800a41ff  jns     short loc_1800A4215
0x1800a4201  mov     r9d, eax; char *
0x1800a4204  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a420b  mov     edx, 166h; void *
  ... truncated ...
```
