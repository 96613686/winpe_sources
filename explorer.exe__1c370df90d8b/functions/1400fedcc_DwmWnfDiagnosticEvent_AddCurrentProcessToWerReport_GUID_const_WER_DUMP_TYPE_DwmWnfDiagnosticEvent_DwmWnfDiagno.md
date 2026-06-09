# DwmWnfDiagnosticEvent::AddCurrentProcessToWerReport(_GUID const &,_WER_DUMP_TYPE,DwmWnfDiagnosticEvent::DwmWnfDiagnosticEventDumpMetadata const &)

- ea: `0x1400fedcc`
- end: `0x1400ff06e`
- name: `?AddCurrentProcessToWerReport@DwmWnfDiagnosticEvent@@YAJAEBU_GUID@@W4_WER_DUMP_TYPE@@AEBUDwmWnfDiagnosticEventDumpMetadata@1@@Z`
- size: `674`
- prototype: `__int64 __fastcall(IID *rclsid, WER_DUMP_TYPE dumpType, enum _WER_DUMP_TYPE, const struct DwmWnfDiagnosticEvent::DwmWnfDiagnosticEventDumpMetadata *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14010d760`

## callees

- `0x14001eba8`
- `0x140034af0`
- `0x14003dd00`
- `0x140065b60`
- `0x1400954e0`
- `0x1400fedcc`
- `0x1400ff074`
- `0x1401040e0`
- `0x140104ce0`
- `0x14010d348`

## import_xrefs

- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x1400fefd9`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x1400ff00a`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x1400fefd9`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x1400ff00a`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x1400fef68`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x1400fef68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400feeac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400feeac`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400fef23`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400fef23`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x1400fefaf`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x1400fefaf`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x1400feeda`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x1400feeda`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x1400fee99`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x1400fee99`

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
0x1400fedcc  mov     [rsp-8+arg_10], rbx
0x1400fedd1  mov     [rsp-8+arg_18], rsi
0x1400fedd6  push    rbp
0x1400fedd7  push    rdi
0x1400fedd8  push    r14
0x1400fedda  lea     rbp, [rsp-820h]
0x1400fede2  sub     rsp, 920h
0x1400fede9  mov     rax, cs:__security_cookie
0x1400fedf0  xor     rax, rsp
0x1400fedf3  mov     [rbp+830h+var_20], rax
0x1400fedfa  mov     r14, r8
0x1400fedfd  mov     esi, edx
0x1400fedff  mov     rdi, rcx
0x1400fee02  mov     ebx, 8A0h
0x1400fee07  mov     r8d, ebx; Size
0x1400fee0a  lea     rcx, [rsp+930h+pReportInformation]; void *
0x1400fee0f  xor     edx, edx; Val
0x1400fee11  call    memset_0
0x1400fee16  lea     r8, aBlackScreenUse; "Black Screen - User Reported"
0x1400fee1d  mov     [rsp+930h+pReportInformation.dwSize], ebx
0x1400fee21  mov     edx, 80h; unsigned __int64
0x1400fee26  lea     rcx, [rbp+830h+pReportInformation.wzFriendlyEventName]; unsigned __int16 *
0x1400fee2a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400fee2f  mov     ebx, eax
0x1400fee31  test    eax, eax
0x1400fee33  jns     short loc_1400FEE55
0x1400fee35  mov     edx, 64h ; 'd'; void *
0x1400fee3a  mov     rcx, [rbp+838h]; this
0x1400fee41  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x1400fee48  mov     r9d, ebx; char *
0x1400fee4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400fee50  jmp     loc_1400FF045
0x1400fee55  lea     r8, aTheUserHasInvo; "The user has invoked the Black Screen D"...
0x1400fee5c  mov     edx, 200h; unsigned __int64
0x1400fee61  lea     rcx, [rbp+830h+pReportInformation.wzDescription]; unsigned __int16 *
0x1400fee68  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400fee6d  mov     ebx, eax
0x1400fee6f  test    eax, eax
0x1400fee71  jns     short loc_1400FEE7A
0x1400fee73  mov     edx, 69h ; 'i'
0x1400fee78  jmp     short loc_1400FEE3A
0x1400fee7a  lea     r9, [rsp+930h+phReportHandle]; phReportHandle
0x1400fee7f  mov     [rsp+930h+phReportHandle], 0
0x1400fee88  lea     r8, [rsp+930h+pReportInformation]; pReportInformation
0x1400fee8d  mov     edx, 1; repType
0x1400fee92  lea     rcx, pwzEventType; "WindowsBlackScreenDiagnosticsV1"
0x1400fee99  call    cs:__imp_WerReportCreate
0x1400fee9f  mov     ebx, eax
0x1400feea1  test    eax, eax
0x1400feea3  jns     short loc_1400FEEAC
0x1400feea5  mov     edx, 6Dh ; 'm'
0x1400feeaa  jmp     short loc_1400FEEEB
0x1400feeac  call    cs:__imp_GetCurrentProcess
0x1400feeb2  mov     rcx, [rsp+930h+phReportHandle]; hReportHandle
0x1400feeb7  mov     r9d, esi; dumpType
0x1400feeba  mov     [rsp+930h+dwFlags], 0; dwFlags
0x1400feec2  mov     rdx, rax; hProcess
0x1400feec5  mov     [rsp+930h+pDumpCustomOptions], 0; pDumpCustomOptions
0x1400feece  xor     r8d, r8d; hThread
0x1400feed1  mov     [rsp+930h+pExceptionParam], 0; int
0x1400feeda  call    cs:__imp_WerReportAddDump
0x1400feee0  mov     ebx, eax
0x1400feee2  test    eax, eax
0x1400feee4  jns     short loc_1400FEF06
0x1400feee6  mov     edx, 71h ; 'q'; void *
0x1400feeeb  mov     rcx, [rbp+838h]; this
0x1400feef2  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x1400feef9  mov     r9d, eax; char *
0x1400feefc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400fef01  jmp     loc_1400FF03B
0x1400fef06  xor     edx, edx
0x1400fef08  mov     [rsp+930h+lpsz], 0
0x1400fef11  lea     rcx, [rsp+930h+lpsz]
0x1400fef16  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400fef1b  lea     rdx, [rsp+930h+lpsz]; lplpsz
0x1400fef20  mov     rcx, rdi; rclsid
0x1400fef23  call    cs:__imp_StringFromCLSID
0x1400fef29  mov     ebx, eax
0x1400fef2b  test    eax, eax
0x1400fef2d  jns     short loc_1400FEF59
0x1400fef2f  mov     edx, 75h ; 'u'; void *
0x1400fef34  mov     rcx, [rbp+838h]; this
0x1400fef3b  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x1400fef42  mov     r9d, eax; char *
0x1400fef45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400fef4a  lea     rcx, [rsp+930h+lpsz]
0x1400fef4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400fef54  jmp     loc_1400FF03B
0x1400fef59  mov     rdx, [rsp+930h+lpsz]; value
0x1400fef5e  lea     rdi, key; "BlackScreenInstanceGuid"
0x1400fef65  mov     rcx, rdi; key
0x1400fef68  call    cs:__imp_WerRegisterCustomMetadata
0x1400fef6e  mov     ebx, eax
0x1400fef70  test    eax, eax
0x1400fef72  jns     short loc_1400FEF7B
0x1400fef74  mov     edx, 77h ; 'w'
0x1400fef79  jmp     short loc_1400FEF34
0x1400fef7b  lea     rax, [rsp+930h+phReportHandle]
0x1400fef80  mov     [rsp+930h+var_8D0], r14
0x1400fef85  lea     rcx, [rsp+930h+var_8D8]
0x1400fef8a  mov     [rsp+930h+var_8D8], rax
0x1400fef8f  call    ??R_lambda_868f43637e8409a46b7fdcb03681968d_@@QEBAJXZ; _lambda_868f43637e8409a46b7fdcb03681968d_::operator()(void)
0x1400fef94  mov     rcx, [rsp+930h+phReportHandle]; hReportHandle
0x1400fef99  lea     r9, [rsp+930h+pSubmitResult]; pSubmitResult
0x1400fef9e  mov     edx, 1; consent
0x1400fefa3  mov     [rsp+930h+pSubmitResult], 0Dh
0x1400fefab  lea     r8d, [rdx+3]; dwFlags
0x1400fefaf  call    cs:__imp_WerReportSubmit
0x1400fefb5  mov     ebx, eax
0x1400fefb7  test    eax, eax
0x1400fefb9  jns     short loc_1400FF007
0x1400fefbb  mov     rcx, [rbp+838h]; this
0x1400fefc2  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x1400fefc9  mov     r9d, eax; char *
0x1400fefcc  mov     edx, 9Dh; void *
0x1400fefd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400fefd6  mov     rcx, rdi; key
0x1400fefd9  call    cs:__imp_WerUnregisterCustomMetadata
0x1400fefdf  test    eax, eax
0x1400fefe1  jns     loc_1400FEF4A
0x1400fefe7  mov     rcx, [rbp+838h]; this
0x1400fefee  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x1400feff5  mov     r9d, eax; char *
0x1400feff8  mov     edx, 7Ch ; '|'; void *
0x1400feffd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400ff002  jmp     loc_1400FEF4A
0x1400ff007  mov     rcx, rdi; key
0x1400ff00a  call    cs:__imp_WerUnregisterCustomMetadata
0x1400ff010  test    eax, eax
0x1400ff012  jns     short loc_1400FF02F
0x1400ff014  mov     rcx, [rbp+838h]; this
0x1400ff01b  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x1400ff022  mov     r9d, eax; char *
0x1400ff025  mov     edx, 7Ch ; '|'; void *
0x1400ff02a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400ff02f  lea     rcx, [rsp+930h+lpsz]
0x1400ff034  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400ff039  xor     ebx, ebx
0x1400ff03b  lea     rcx, [rsp+930h+phReportHandle]
0x1400ff040  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400ff045  mov     eax, ebx
0x1400ff047  mov     rcx, [rbp+830h+var_20]
0x1400ff04e  xor     rcx, rsp; StackCookie
0x1400ff051  call    __security_check_cookie
0x1400ff056  lea     r11, [rsp+930h+var_10]
0x1400ff05e  mov     rbx, [r11+30h]
0x1400ff062  mov     rsi, [r11+38h]
0x1400ff066  mov     rsp, r11
0x1400ff069  pop     r14
0x1400ff06b  pop     rdi
0x1400ff06c  pop     rbp
0x1400ff06d  retn
```
