# DwmWnfDiagnosticEvent::AddCurrentProcessToWerReport(_GUID const &,_WER_DUMP_TYPE,DwmWnfDiagnosticEvent::DwmWnfDiagnosticEventDumpMetadata const &)

- ea: `0x140107a04`
- end: `0x140107cd7`
- name: `?AddCurrentProcessToWerReport@DwmWnfDiagnosticEvent@@YAJAEBU_GUID@@W4_WER_DUMP_TYPE@@AEBUDwmWnfDiagnosticEventDumpMetadata@1@@Z`
- size: `723`
- prototype: `__int64 __fastcall(IID *rclsid, WER_DUMP_TYPE dumpType, enum _WER_DUMP_TYPE, const struct DwmWnfDiagnosticEvent::DwmWnfDiagnosticEventDumpMetadata *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140117ab0`

## callees

- `0x140005810`
- `0x14000fbdc`
- `0x14001b2c8`
- `0x140033ec0`
- `0x14009ac68`
- `0x140107a04`
- `0x140107ce0`
- `0x14010e160`
- `0x14010ed90`
- `0x140117668`

## import_xrefs

- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x140107c35`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x140107c6c`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x140107c35`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x140107c6c`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x140107bb8`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x140107bb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140107aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140107aea`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x140107b6d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x140107b6d`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x140107c05`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x140107c05`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x140107b1e`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x140107b1e`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x140107ad1`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x140107ad1`

## pseudocode

```c
__int64 __fastcall DwmWnfDiagnosticEvent::AddCurrentProcessToWerReport(
        IID *rclsid,
        WER_DUMP_TYPE dumpType,
        __int64 a3,
        const struct DwmWnfDiagnosticEvent::DwmWnfDiagnosticEventDumpMetadata *a4)
{
  int v7; // ebx
  __int64 v8; // rdx
  HRESULT v9; // eax
  __int64 v10; // rdx
  HANDLE CurrentProcess; // rax
  HRESULT v12; // eax
  __int64 v13; // rdx
  HRESULT v14; // eax
  HRESULT v15; // eax
  HRESULT v16; // eax
  int pExceptionParam; // [rsp+20h] [rbp-E0h]
  int pExceptionParama; // [rsp+20h] [rbp-E0h]
  LPOLESTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  HREPORT phReportHandle; // [rsp+48h] [rbp-B8h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v23[3]; // [rsp+58h] [rbp-A8h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+938h] [rbp+838h]

  memset_0(&pReportInformation, 0, sizeof(pReportInformation));
  pReportInformation.dwSize = 2208;
  v7 = StringCchCopyW(pReportInformation.wzFriendlyEventName, 0x80u, L"Black Screen - User Reported");
  if ( v7 >= 0 )
  {
    v7 = StringCchCopyW(
           pReportInformation.wzDescription,
           0x200u,
           L"The user has invoked the Black Screen Diagnostics Tool to generate this report");
    if ( v7 < 0 )
    {
      v8 = 105;
      goto LABEL_3;
    }
    phReportHandle = 0;
    v9 = WerReportCreate(L"WindowsBlackScreenDiagnosticsV1", WerReportCritical, &pReportInformation, &phReportHandle);
    v7 = v9;
    if ( v9 < 0 )
    {
      v10 = 109;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
        (const char *)(unsigned int)v9,
        pExceptionParam);
LABEL_23:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportHandle);
      return (unsigned int)v7;
    }
    CurrentProcess = GetCurrentProcess();
    v9 = WerReportAddDump(phReportHandle, CurrentProcess, 0, dumpType, 0, 0, 0);
    v7 = v9;
    if ( v9 < 0 )
    {
      v10 = 113;
      goto LABEL_10;
    }
    lpsz = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v12 = StringFromCLSID(rclsid, &lpsz);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v12 = WerRegisterCustomMetadata(L"BlackScreenInstanceGuid", lpsz);
      v7 = v12;
      if ( v12 >= 0 )
      {
        v23[1] = a3;
        v23[0] = &phReportHandle;
        _lambda_868f43637e8409a46b7fdcb03681968d_::operator()(v23);
        pSubmitResult = WerCustomAction|WerReportFailed;
        v14 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 4u, &pSubmitResult);
        v7 = v14;
        if ( v14 >= 0 )
        {
          v16 = WerUnregisterCustomMetadata(L"BlackScreenInstanceGuid");
          if ( v16 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x7C,
              (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
              (const char *)(unsigned int)v16,
              pExceptionParam);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
          v7 = 0;
          goto LABEL_23;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9D,
          (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
          (const char *)(unsigned int)v14,
          pExceptionParam);
        v15 = WerUnregisterCustomMetadata(L"BlackScreenInstanceGuid");
        if ( v15 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x7C,
            (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
            (const char *)(unsigned int)v15,
            pExceptionParama);
        goto LABEL_14;
      }
      v13 = 119;
    }
    else
    {
      v13 = 117;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
      (const char *)(unsigned int)v12,
      pExceptionParam);
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    goto LABEL_23;
  }
  v8 = 100;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
    (const char *)(unsigned int)v7,
    pExceptionParam);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140107a04  mov     [rsp-8+arg_10], rbx
0x140107a09  mov     [rsp-8+arg_18], rsi
0x140107a0e  push    rbp
0x140107a0f  push    rdi
0x140107a10  push    r14
0x140107a12  lea     rbp, [rsp-820h]
0x140107a1a  sub     rsp, 920h
0x140107a21  mov     rax, cs:__security_cookie
0x140107a28  xor     rax, rsp
0x140107a2b  mov     [rbp+830h+var_20], rax
0x140107a32  mov     r14, r8
0x140107a35  mov     esi, edx
0x140107a37  mov     rdi, rcx
0x140107a3a  mov     ebx, 8A0h
0x140107a3f  mov     r8d, ebx; Size
0x140107a42  lea     rcx, [rsp+930h+pReportInformation]; void *
0x140107a47  xor     edx, edx; Val
0x140107a49  call    memset_0
0x140107a4e  lea     r8, aBlackScreenUse; "Black Screen - User Reported"
0x140107a55  mov     [rsp+930h+pReportInformation.dwSize], ebx
0x140107a59  mov     edx, 80h; unsigned __int64
0x140107a5e  lea     rcx, [rbp+830h+pReportInformation.wzFriendlyEventName]; unsigned __int16 *
0x140107a62  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140107a67  mov     ebx, eax
0x140107a69  test    eax, eax
0x140107a6b  jns     short loc_140107A8D
0x140107a6d  mov     edx, 64h ; 'd'; void *
0x140107a72  mov     rcx, [rbp+838h]; this
0x140107a79  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x140107a80  mov     r9d, ebx; char *
0x140107a83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140107a88  jmp     loc_140107CAD
0x140107a8d  lea     r8, aTheUserHasInvo; "The user has invoked the Black Screen D"...
0x140107a94  mov     edx, 200h; unsigned __int64
0x140107a99  lea     rcx, [rbp+830h+pReportInformation.wzDescription]; unsigned __int16 *
0x140107aa0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140107aa5  mov     ebx, eax
0x140107aa7  test    eax, eax
0x140107aa9  jns     short loc_140107AB2
0x140107aab  mov     edx, 69h ; 'i'
0x140107ab0  jmp     short loc_140107A72
0x140107ab2  lea     r9, [rsp+930h+phReportHandle]; phReportHandle
0x140107ab7  mov     [rsp+930h+phReportHandle], 0
0x140107ac0  lea     r8, [rsp+930h+pReportInformation]; pReportInformation
0x140107ac5  mov     edx, 1; repType
0x140107aca  lea     rcx, pwzEventType; "WindowsBlackScreenDiagnosticsV1"
0x140107ad1  call    cs:__imp_WerReportCreate
0x140107ad8  nop     dword ptr [rax+rax+00h]
0x140107add  mov     ebx, eax
0x140107adf  test    eax, eax
0x140107ae1  jns     short loc_140107AEA
0x140107ae3  mov     edx, 6Dh ; 'm'
0x140107ae8  jmp     short loc_140107B35
0x140107aea  call    cs:__imp_GetCurrentProcess
0x140107af1  nop     dword ptr [rax+rax+00h]
0x140107af6  mov     rcx, [rsp+930h+phReportHandle]; hReportHandle
0x140107afb  mov     r9d, esi; dumpType
0x140107afe  mov     [rsp+930h+dwFlags], 0; dwFlags
0x140107b06  mov     rdx, rax; hProcess
0x140107b09  mov     [rsp+930h+pDumpCustomOptions], 0; pDumpCustomOptions
0x140107b12  xor     r8d, r8d; hThread
0x140107b15  mov     [rsp+930h+pExceptionParam], 0; int
0x140107b1e  call    cs:__imp_WerReportAddDump
0x140107b25  nop     dword ptr [rax+rax+00h]
0x140107b2a  mov     ebx, eax
0x140107b2c  test    eax, eax
0x140107b2e  jns     short loc_140107B50
0x140107b30  mov     edx, 71h ; 'q'; void *
0x140107b35  mov     rcx, [rbp+838h]; this
0x140107b3c  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x140107b43  mov     r9d, eax; char *
0x140107b46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140107b4b  jmp     loc_140107CA3
0x140107b50  xor     edx, edx
0x140107b52  mov     [rsp+930h+lpsz], 0
0x140107b5b  lea     rcx, [rsp+930h+lpsz]
0x140107b60  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140107b65  lea     rdx, [rsp+930h+lpsz]; lplpsz
0x140107b6a  mov     rcx, rdi; rclsid
0x140107b6d  call    cs:__imp_StringFromCLSID
0x140107b74  nop     dword ptr [rax+rax+00h]
0x140107b79  mov     ebx, eax
0x140107b7b  test    eax, eax
0x140107b7d  jns     short loc_140107BA9
0x140107b7f  mov     edx, 75h ; 'u'; void *
0x140107b84  mov     rcx, [rbp+838h]; this
0x140107b8b  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x140107b92  mov     r9d, eax; char *
0x140107b95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140107b9a  lea     rcx, [rsp+930h+lpsz]
0x140107b9f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140107ba4  jmp     loc_140107CA3
0x140107ba9  mov     rdx, [rsp+930h+lpsz]; value
0x140107bae  lea     rdi, key; "BlackScreenInstanceGuid"
0x140107bb5  mov     rcx, rdi; key
0x140107bb8  call    cs:__imp_WerRegisterCustomMetadata
0x140107bbf  nop     dword ptr [rax+rax+00h]
0x140107bc4  mov     ebx, eax
0x140107bc6  test    eax, eax
0x140107bc8  jns     short loc_140107BD1
0x140107bca  mov     edx, 77h ; 'w'
0x140107bcf  jmp     short loc_140107B84
0x140107bd1  lea     rax, [rsp+930h+phReportHandle]
0x140107bd6  mov     [rsp+930h+var_8D0], r14
0x140107bdb  lea     rcx, [rsp+930h+var_8D8]
0x140107be0  mov     [rsp+930h+var_8D8], rax
0x140107be5  call    ??R_lambda_868f43637e8409a46b7fdcb03681968d_@@QEBAJXZ; _lambda_868f43637e8409a46b7fdcb03681968d_::operator()(void)
0x140107bea  mov     rcx, [rsp+930h+phReportHandle]; hReportHandle
0x140107bef  lea     r9, [rsp+930h+pSubmitResult]; pSubmitResult
0x140107bf4  mov     edx, 1; consent
0x140107bf9  mov     [rsp+930h+pSubmitResult], 0Dh
0x140107c01  lea     r8d, [rdx+3]; dwFlags
0x140107c05  call    cs:__imp_WerReportSubmit
0x140107c0c  nop     dword ptr [rax+rax+00h]
0x140107c11  mov     ebx, eax
0x140107c13  test    eax, eax
0x140107c15  jns     short loc_140107C69
0x140107c17  mov     rcx, [rbp+838h]; this
0x140107c1e  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x140107c25  mov     r9d, eax; char *
0x140107c28  mov     edx, 9Dh; void *
0x140107c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140107c32  mov     rcx, rdi; key
0x140107c35  call    cs:__imp_WerUnregisterCustomMetadata
0x140107c3c  nop     dword ptr [rax+rax+00h]
0x140107c41  test    eax, eax
0x140107c43  jns     loc_140107B9A
0x140107c49  mov     rcx, [rbp+838h]; this
0x140107c50  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x140107c57  mov     r9d, eax; char *
0x140107c5a  mov     edx, 7Ch ; '|'; void *
0x140107c5f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140107c64  jmp     loc_140107B9A
0x140107c69  mov     rcx, rdi; key
0x140107c6c  call    cs:__imp_WerUnregisterCustomMetadata
0x140107c73  nop     dword ptr [rax+rax+00h]
0x140107c78  test    eax, eax
0x140107c7a  jns     short loc_140107C97
0x140107c7c  mov     rcx, [rbp+838h]; this
0x140107c83  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x140107c8a  mov     r9d, eax; char *
0x140107c8d  mov     edx, 7Ch ; '|'; void *
0x140107c92  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140107c97  lea     rcx, [rsp+930h+lpsz]
0x140107c9c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140107ca1  xor     ebx, ebx
0x140107ca3  lea     rcx, [rsp+930h+phReportHandle]
0x140107ca8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140107cad  mov     eax, ebx
0x140107caf  mov     rcx, [rbp+830h+var_20]
0x140107cb6  xor     rcx, rsp; StackCookie
0x140107cb9  call    __security_check_cookie
0x140107cbe  lea     r11, [rsp+930h+var_10]
0x140107cc6  mov     rbx, [r11+30h]
0x140107cca  mov     rsi, [r11+38h]
0x140107cce  mov     rsp, r11
0x140107cd1  pop     r14
0x140107cd3  pop     rdi
0x140107cd4  pop     rbp
0x140107cd5  retn
```
