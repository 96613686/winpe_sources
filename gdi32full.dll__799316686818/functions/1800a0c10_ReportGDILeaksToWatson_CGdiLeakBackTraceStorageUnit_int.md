# ReportGDILeaksToWatson(CGdiLeakBackTraceStorageUnit *,int)

- ea: `0x1800a0c10`
- end: `0x1800a12a6`
- name: `?ReportGDILeaksToWatson@@YAXPEAVCGdiLeakBackTraceStorageUnit@@H@Z`
- size: `1686`
- prototype: `void __fastcall(struct CGdiLeakBackTraceStorageUnit *, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180027320`
- `0x1800346b8`
- `0x18006b28c`
- `0x18007ba24`
- `0x1800a00cc`
- `0x1800a0250`
- `0x1800a0298`
- `0x1800a02e0`
- `0x1800a0404`
- `0x1800a05b8`
- `0x1800a0624`
- `0x1800a0c10`
- `0x1800a156c`
- `0x1800a34fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a0dbb`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a0dbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800a0d6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800a0d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a10d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a10d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a10dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a10dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a11e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a11f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a120f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1225`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a123b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1275`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a11e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a11f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a120f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1225`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a123b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1275`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800a0e55`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800a0e55`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800a0e12`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800a0e12`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800a0e7f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800a0e7f`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterMemoryBlock` at `0x1800a0d3a`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterMemoryBlock` at `0x1800a0d3a`
- `wer!WerpGetReportConsent` at `0x1800a113c`
- `wer!WerpGetReportConsent` at `0x1800a113c`
- `wer!WerReportSetParameter` at `0x1800a0f26`
- `wer!WerReportSetParameter` at `0x1800a0f6a`
- `wer!WerReportSetParameter` at `0x1800a0fae`
- `wer!WerReportSetParameter` at `0x1800a1028`
- `wer!WerReportSetParameter` at `0x1800a1066`
- `wer!WerReportSetParameter` at `0x1800a0f26`
- `wer!WerReportSetParameter` at `0x1800a0f6a`
- `wer!WerReportSetParameter` at `0x1800a0fae`
- `wer!WerReportSetParameter` at `0x1800a1028`
- `wer!WerReportSetParameter` at `0x1800a1066`
- `wer!WerReportCloseHandle` at `0x1800a0cec`
- `wer!WerReportCloseHandle` at `0x1800a0cec`
- `wer!WerReportSubmit` at `0x1800a117d`
- `wer!WerReportSubmit` at `0x1800a117d`
- `wer!WerReportCreate` at `0x1800a0d05`
- `wer!WerReportCreate` at `0x1800a0d05`
- `wer!WerReportAddDump` at `0x1800a10ff`
- `wer!WerReportAddDump` at `0x1800a10ff`

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
0x1800a0c10  mov     [rsp+arg_0], rbx
0x1800a0c15  mov     [rsp+arg_8], rsi
0x1800a0c1a  push    rdi
0x1800a0c1b  push    r12
0x1800a0c1d  push    r13
0x1800a0c1f  push    r14
0x1800a0c21  push    r15
0x1800a0c23  sub     rsp, 0B0h
0x1800a0c2a  mov     r13d, edx
0x1800a0c2d  mov     rbx, rcx
0x1800a0c30  xor     edi, edi
0x1800a0c32  mov     [rsp+0D8h+hReportHandle], rdi
0x1800a0c37  lea     rcx, [rsp+0D8h+pReportInformation]
0x1800a0c3c  call    ??$make_unique_hlocal@U_WER_REPORT_INFORMATION@@$$V@wil@@YA?AV?$unique_ptr@U_WER_REPORT_INFORMATION@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_WER_REPORT_INFORMATION,>(void)
0x1800a0c41  nop
0x1800a0c42  mov     esi, 8A0h
0x1800a0c47  mov     r8d, esi; Size
0x1800a0c4a  xor     edx, edx; Val
0x1800a0c4c  mov     rcx, [rsp+0D8h+pReportInformation]; void *
0x1800a0c51  call    memset_0
0x1800a0c56  mov     ecx, 178h; dwBytes
0x1800a0c5b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a0c60  mov     [rsp+0D8h+var_58], rax
0x1800a0c68  test    rax, rax
0x1800a0c6b  jz      short loc_1800A0C7D
0x1800a0c6d  mov     rdx, rbx; struct CGdiLeakBackTraceStorageUnit *
0x1800a0c70  mov     rcx, rax; this
0x1800a0c73  call    ??0ExceptionInformationWrapper@@QEAA@PEAVCGdiLeakBackTraceStorageUnit@@@Z; ExceptionInformationWrapper::ExceptionInformationWrapper(CGdiLeakBackTraceStorageUnit *)
0x1800a0c78  mov     rbx, rax
0x1800a0c7b  jmp     short loc_1800A0C80
0x1800a0c7d  mov     rbx, rdi
0x1800a0c80  mov     [rsp+0D8h+var_58], rbx
0x1800a0c88  mov     r14d, 104h
0x1800a0c8e  mov     edx, r14d
0x1800a0c91  lea     rcx, [rsp+0D8h+lptstrFilename]
0x1800a0c96  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a0c9b  nop
0x1800a0c9c  mov     edx, r14d
0x1800a0c9f  lea     rcx, [rsp+0D8h+pwzValue]
0x1800a0ca4  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a0ca9  nop
0x1800a0caa  mov     edx, r14d
0x1800a0cad  lea     rcx, [rsp+0D8h+var_68]
0x1800a0cb2  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a0cb7  nop
0x1800a0cb8  mov     edx, r14d
0x1800a0cbb  lea     rcx, [rsp+0D8h+lpFilename]
0x1800a0cc0  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a0cc5  nop
0x1800a0cc6  mov     edx, 3
0x1800a0ccb  lea     rcx, [rsp+0D8h+var_70]
0x1800a0cd0  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a0cd5  nop
0x1800a0cd6  mov     rax, [rsp+0D8h+pReportInformation]
0x1800a0cdb  mov     [rax], esi
0x1800a0cdd  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a0ce2  mov     [rsp+0D8h+hReportHandle], rdi
0x1800a0ce7  test    rcx, rcx
0x1800a0cea  jz      short loc_1800A0CF2
0x1800a0cec  call    cs:__imp_WerReportCloseHandle
0x1800a0cf2  lea     r9, [rsp+0D8h+hReportHandle]; phReportHandle
0x1800a0cf7  mov     r8, [rsp+0D8h+pReportInformation]; pReportInformation
0x1800a0cfc  xor     edx, edx; repType
0x1800a0cfe  lea     rcx, pwzEventType; "GDIObjectLeak"
0x1800a0d05  call    cs:__imp_WerReportCreate
0x1800a0d0b  mov     rcx, [rsp+0D8h]; this
0x1800a0d13  test    eax, eax
0x1800a0d15  jns     short loc_1800A0D2B
0x1800a0d17  mov     r9d, eax; char *
0x1800a0d1a  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a0d21  mov     edx, 125h; void *
0x1800a0d26  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a0d2b  lea     r15, [rbx+0B8h]
0x1800a0d32  mov     edx, 0C0h; dwSize
0x1800a0d37  mov     rcx, r15; pvAddress
0x1800a0d3a  call    cs:__imp_WerRegisterMemoryBlock
0x1800a0d40  mov     rcx, [rsp+0D8h]; this
0x1800a0d48  test    eax, eax
0x1800a0d4a  jns     short loc_1800A0D60
0x1800a0d4c  mov     r9d, eax; char *
0x1800a0d4f  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a0d56  mov     edx, 127h; void *
0x1800a0d5b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a0d60  mov     r8d, r14d; nSize
0x1800a0d63  mov     rdx, [rsp+0D8h+lpFilename]; lpFilename
0x1800a0d68  xor     ecx, ecx; hModule
0x1800a0d6a  call    cs:__imp_GetModuleFileNameW
0x1800a0d70  test    eax, eax
0x1800a0d72  jnz     short loc_1800A0DB1
0x1800a0d74  xorps   xmm0, xmm0
0x1800a0d77  movups  [rsp+0D8h+var_40], xmm0
0x1800a0d7f  lea     rax, aBadException; "bad exception"
0x1800a0d86  mov     qword ptr [rsp+0D8h+var_40], rax
0x1800a0d8e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800a0d95  mov     [rsp+0D8h+pExceptionObject], rax
0x1800a0d9d  lea     rdx, _TI2?AVbad_exception@std@@; pThrowInfo
0x1800a0da4  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x1800a0dac  call    _CxxThrowException_0
0x1800a0db1  mov     edx, 5Ch ; '\'; Ch
0x1800a0db6  mov     rcx, [rsp+0D8h+lpFilename]; Str
0x1800a0dbb  call    cs:__imp_wcsrchr
0x1800a0dc1  mov     esi, 2
0x1800a0dc6  test    rax, rax
0x1800a0dc9  jz      short loc_1800A0DD0
0x1800a0dcb  add     rax, rsi
0x1800a0dce  jmp     short loc_1800A0DD5
0x1800a0dd0  mov     rax, [rsp+0D8h+lpFilename]
0x1800a0dd5  mov     r8, rax; unsigned __int16 *
0x1800a0dd8  mov     rdx, r14; unsigned __int64
0x1800a0ddb  mov     rcx, [rsp+0D8h+lptstrFilename]; unsigned __int16 *
0x1800a0de0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a0de5  mov     rcx, [rsp+0D8h]; this
0x1800a0ded  test    eax, eax
0x1800a0def  jns     short loc_1800A0E05
0x1800a0df1  mov     r9d, eax; char *
0x1800a0df4  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a0dfb  mov     edx, 134h; void *
0x1800a0e00  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a0e05  mov     r14b, dil
0x1800a0e08  mov     r12b, dil
0x1800a0e0b  xor     edx, edx; lpdwHandle
0x1800a0e0d  mov     rcx, [rsp+0D8h+lptstrFilename]; lptstrFilename
0x1800a0e12  call    cs:__imp_GetFileVersionInfoSizeW
0x1800a0e18  mov     edi, eax
0x1800a0e1a  mov     edx, eax
0x1800a0e1c  lea     rcx, [rsp+0D8h+lpData]
0x1800a0e21  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x1800a0e26  nop
0x1800a0e27  mov     [rsp+0D8h+puLen], 0
0x1800a0e32  mov     [rsp+0D8h+lpBuffer], 0
0x1800a0e3e  test    edi, edi
0x1800a0e40  jz      loc_1800A0F0E
0x1800a0e46  mov     r9, [rsp+0D8h+lpData]; lpData
0x1800a0e4b  mov     r8d, edi; dwLen
0x1800a0e4e  xor     edx, edx; dwHandle
0x1800a0e50  mov     rcx, [rsp+0D8h+lptstrFilename]; lptstrFilename
0x1800a0e55  call    cs:__imp_GetFileVersionInfoW
0x1800a0e5b  test    eax, eax
0x1800a0e5d  jz      loc_1800A0F0E
0x1800a0e63  lea     r9, [rsp+0D8h+puLen]; puLen
0x1800a0e6b  lea     r8, [rsp+0D8h+lpBuffer]; lplpBuffer
0x1800a0e73  lea     rdx, SubBlock; "\\"
0x1800a0e7a  mov     rcx, [rsp+0D8h+lpData]; pBlock
0x1800a0e7f  call    cs:__imp_VerQueryValueW
0x1800a0e85  test    eax, eax
0x1800a0e87  jz      loc_1800A0F0E
0x1800a0e8d  mov     r8, [rsp+0D8h+lpBuffer]
0x1800a0e95  movzx   eax, word ptr [r8+14h]
0x1800a0e9a  movzx   ecx, word ptr [r8+16h]
0x1800a0e9f  movzx   edx, word ptr [r8+10h]
0x1800a0ea4  movzx   r9d, word ptr [r8+12h]
0x1800a0ea9  mov     [rsp+0D8h+dwFlags], eax
0x1800a0ead  mov     dword ptr [rsp+0D8h+pDumpCustomOptions], ecx
0x1800a0eb1  mov     dword ptr [rsp+0D8h+pExceptionParam], edx
0x1800a0eb5  lea     r8, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x1800a0ebc  mov     edx, 104h; unsigned __int64
0x1800a0ec1  mov     rcx, [rsp+0D8h+pwzValue]; unsigned __int16 *
0x1800a0ec6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a0ecb  mov     r14d, eax
0x1800a0ece  shr     r14d, 1Fh
0x1800a0ed2  mov     edi, 1
0x1800a0ed7  xor     r14b, dil
0x1800a0eda  mov     r9, [rsp+0D8h+lpBuffer]
0x1800a0ee2  mov     r8d, [r9+0Ch]
0x1800a0ee6  mov     dword ptr [rsp+0D8h+pExceptionParam], r8d
0x1800a0eeb  mov     r9d, [r9+8]
0x1800a0eef  lea     r8, aUU; "%u.%u"
0x1800a0ef6  mov     edx, 104h; unsigned __int64
0x1800a0efb  mov     rcx, [rsp+0D8h+var_68]; unsigned __int16 *
0x1800a0f00  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a0f05  test    eax, eax
0x1800a0f07  js      short loc_1800A0F13
0x1800a0f09  mov     r12b, dil
0x1800a0f0c  jmp     short loc_1800A0F13
0x1800a0f0e  mov     edi, 1
0x1800a0f13  mov     r9, [rsp+0D8h+lptstrFilename]; pwzValue
0x1800a0f18  lea     r8, pwzName; "AppName"
0x1800a0f1f  xor     edx, edx; dwparamID
0x1800a0f21  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a0f26  call    cs:__imp_WerReportSetParameter
0x1800a0f2c  mov     rcx, [rsp+0D8h]; this
0x1800a0f34  test    eax, eax
0x1800a0f36  jns     short loc_1800A0F4C
0x1800a0f38  mov     r9d, eax; char *
0x1800a0f3b  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a0f42  mov     edx, 151h; void *
0x1800a0f47  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a0f4c  lea     r9, a0000; "0.0.0.0"
0x1800a0f53  test    r14b, r14b
0x1800a0f56  cmovnz  r9, [rsp+0D8h+pwzValue]; pwzValue
0x1800a0f5c  lea     r8, aAppversion; "AppVersion"
0x1800a0f63  mov     edx, edi; dwparamID
0x1800a0f65  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a0f6a  call    cs:__imp_WerReportSetParameter
0x1800a0f70  test    eax, eax
0x1800a0f72  jns     short loc_1800A0F90
0x1800a0f74  mov     rcx, [rsp+0D8h]; this
0x1800a0f7c  mov     r9d, eax; char *
0x1800a0f7f  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a0f86  mov     edx, 152h; void *
0x1800a0f8b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a0f90  lea     r9, a00; "0.0"
0x1800a0f97  test    r12b, r12b
0x1800a0f9a  cmovnz  r9, [rsp+0D8h+var_68]; pwzValue
0x1800a0fa0  lea     r8, aAppstamp; "AppStamp"
0x1800a0fa7  mov     edx, esi; dwparamID
0x1800a0fa9  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a0fae  call    cs:__imp_WerReportSetParameter
0x1800a0fb4  mov     rcx, [rsp+0D8h]; this
0x1800a0fbc  xor     r12d, r12d
0x1800a0fbf  test    eax, eax
0x1800a0fc1  jns     short loc_1800A0FD7
0x1800a0fc3  mov     r9d, eax; char *
0x1800a0fc6  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a0fcd  mov     edx, 153h; void *
0x1800a0fd2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a0fd7  mov     r9d, r13d
0x1800a0fda  lea     r8, asc_1800E3FC8; "%x"
0x1800a0fe1  mov     r13d, 3
0x1800a0fe7  mov     edx, r13d; unsigned __int64
0x1800a0fea  mov     rcx, [rsp+0D8h+var_70]; unsigned __int16 *
0x1800a0fef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a0ff4  mov     rcx, [rsp+0D8h]; this
0x1800a0ffc  test    eax, eax
0x1800a0ffe  jns     short loc_1800A1014
0x1800a1000  mov     r9d, eax; char *
0x1800a1003  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a100a  mov     edx, 155h; void *
0x1800a100f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a1014  mov     r9, [rsp+0D8h+var_70]; pwzValue
0x1800a1019  lea     r8, aGdiobjecttype; "GDIObjectType"
0x1800a1020  mov     edx, r13d; dwparamID
0x1800a1023  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a1028  call    cs:__imp_WerReportSetParameter
0x1800a102e  mov     rcx, [rsp+0D8h]; this
0x1800a1036  test    eax, eax
0x1800a1038  jns     short loc_1800A104E
0x1800a103a  mov     r9d, eax; char *
0x1800a103d  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a1044  mov     edx, 156h; void *
0x1800a1049  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a104e  lea     r9, pwzValue; "0"
0x1800a1055  lea     r8, aStackhash; "StackHash"
0x1800a105c  mov     edx, 4; dwparamID
0x1800a1061  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a1066  call    cs:__imp_WerReportSetParameter
0x1800a106c  mov     rcx, [rsp+0D8h]; this
0x1800a1074  test    eax, eax
0x1800a1076  jns     short loc_1800A108C
0x1800a1078  mov     r9d, eax; char *
0x1800a107b  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a1082  mov     edx, 158h; void *
0x1800a1087  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a108c  lea     rcx, [rbx+98h]
0x1800a1093  lea     r14, [rbx+0A8h]
0x1800a109a  mov     dword ptr [rbx], 803F0001h
0x1800a10a0  lea     rax, ?ReportGDILeaksToWatson@@YAXPEAVCGdiLeakBackTraceStorageUnit@@H@Z; ReportGDILeaksToWatson(CGdiLeakBackTraceStorageUnit *,int)
0x1800a10a7  mov     [rbx+10h], rax
0x1800a10ab  mov     [rbx+18h], r13d
0x1800a10af  mov     [rbx+20h], r15
0x1800a10b3  mov     eax, [r15+0B0h]
0x1800a10ba  mov     [rbx+28h], rax
0x1800a10be  mov     eax, [r15+0B8h]
0x1800a10c5  mov     [rbx+30h], rax
0x1800a10c9  mov     [rcx], rbx
0x1800a10cc  mov     [r14], rcx
0x1800a10cf  mov     [r14+8], edi
0x1800a10d3  call    cs:__imp_GetCurrentThread
0x1800a10d9  mov     r15, rax
0x1800a10dc  call    cs:__imp_GetCurrentProcess
0x1800a10e2  mov     [rsp+0D8h+dwFlags], r12d; dwFlags
0x1800a10e7  mov     [rsp+0D8h+pDumpCustomOptions], r12; pDumpCustomOptions
0x1800a10ec  mov     [rsp+0D8h+pExceptionParam], r14; int
0x1800a10f1  mov     r9d, esi; dumpType
0x1800a10f4  mov     r8, r15; hThread
0x1800a10f7  mov     rdx, rax; hProcess
0x1800a10fa  mov     rcx, [rsp+0D8h+hReportHandle]; hReportHandle
0x1800a10ff  call    cs:__imp_WerReportAddDump
0x1800a1105  mov     rcx, [rsp+0D8h]; this
0x1800a110d  test    eax, eax
0x1800a110f  jns     short loc_1800A1125
0x1800a1111  mov     r9d, eax; char *
0x1800a1114  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a111b  mov     edx, 166h; void *
0x1800a1120  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a1125  mov     [rsp+0D8h+arg_10], r12d
0x1800a112d  lea     r8, [rsp+0D8h+arg_10]
0x1800a1135  mov     edx, edi
0x1800a1137  mov     rcx, [rsp+0D8h+hReportHandle]
0x1800a113c  call    cs:__imp_WerpGetReportConsent
0x1800a1142  mov     rcx, [rsp+0D8h]; this
0x1800a114a  test    eax, eax
0x1800a114c  jns     short loc_1800A1162
0x1800a114e  mov     r9d, eax; char *
0x1800a1151  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\clien"...
0x1800a1158  mov     edx, 16Dh; void *
0x1800a115d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a1162  cmp     [rsp+0D8h+arg_10], r13d
0x1800a116a  cmovge  edi, esi
0x1800a116d  xor     r9d, r9d; pSubmitResult
  ... truncated ...
```
