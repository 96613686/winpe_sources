# DeadlockMonitor::WatsonReport(void)

- ea: `0x1800b5ab0`
- end: `0x1800b5c78`
- name: `?WatsonReport@DeadlockMonitor@@CAJXZ`
- size: `456`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800b4cfc`

## callees

- `0x180015628`
- `0x180049cb0`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800b5ab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b5af5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b5af5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b5b9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b5b9e`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x1800b5b91`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x1800b5c4c`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x1800b5b91`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCloseHandle` at `0x1800b5c4c`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x1800b5c03`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x1800b5c03`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x1800b5b1c`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x1800b5b1c`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800b5b62`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSetParameter` at `0x1800b5b62`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x1800b5bd1`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x1800b5bd1`

## string_xrefs

- `0x1800b5b2f`: `onecore\net\netprofiles\service\src\host\dll\deadlockmonitor.cpp`
- `0x1800b5b7a`: `onecore\net\netprofiles\service\src\host\dll\deadlockmonitor.cpp`

## pseudocode

```c
__int64 DeadlockMonitor::WatsonReport(void)
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  HREPORT v3; // rbx
  HRESULT v4; // edi
  __int64 v5; // rdx
  HANDLE CurrentThread; // rax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int pExceptionParam; // [rsp+20h] [rbp-E0h]
  _WER_SUBMIT_RESULT v11; // [rsp+40h] [rbp-C0h] BYREF
  HREPORT phReportHandle; // [rsp+48h] [rbp-B8h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+50h] [rbp-B0h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+8F0h] [rbp+7F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+908h] [rbp+808h]

  memset_0(&pReportInformation.dwSize + 1, 0, 0x89Cu);
  pReportInformation.dwSize = 2208;
  phReportHandle = 0;
  pReportInformation.hProcess = GetCurrentProcess();
  v0 = WerReportCreate(L"WindowsNonFatalSuspectedDeadlock", WerReportNonCritical, &pReportInformation, &phReportHandle);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\dll\\deadlockmonitor.cpp",
      (const char *)(unsigned int)v0,
      pExceptionParam);
    return v1;
  }
  v3 = phReportHandle;
  v4 = WerReportSetParameter(phReportHandle, 0, L"Version", L"2");
  if ( v4 < 0 )
  {
    v5 = 225;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\dll\\deadlockmonitor.cpp",
      (const char *)(unsigned int)v4,
      pExceptionParam);
    if ( v3 )
      WerReportCloseHandle(v3);
    return (unsigned int)v4;
  }
  CurrentThread = GetCurrentThread();
  v4 = WerReportAddDump(phReportHandle, pReportInformation.hProcess, CurrentThread, WerDumpTypeMiniDump, 0, 0, 0);
  if ( v4 < 0 )
  {
    v5 = 227;
    goto LABEL_5;
  }
  pSubmitResult = 0;
  v4 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 0x24u, &pSubmitResult);
  if ( v4 < 0 )
  {
    v5 = 230;
    goto LABEL_5;
  }
  if ( (unsigned int)dword_1801BD288 > 5 )
  {
    v11 = pSubmitResult;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)word_18018BD02,
      v8,
      v9,
      (__int64)&v11);
  }
  if ( v3 )
    WerReportCloseHandle(v3);
  return 0;
}

```

## disassembly

```asm
0x1800b5ab0  mov     [rsp-8+arg_0], rbx
0x1800b5ab5  mov     [rsp-8+arg_8], rdi
0x1800b5aba  push    rbp
0x1800b5abb  lea     rbp, [rsp-800h]
0x1800b5ac3  sub     rsp, 900h
0x1800b5aca  mov     rax, cs:__security_cookie
0x1800b5ad1  xor     rax, rsp
0x1800b5ad4  mov     [rbp+800h+var_8], rax
0x1800b5adb  xor     edx, edx; Val
0x1800b5add  lea     rcx, [rsp+900h+pReportInformation+4]; void *
0x1800b5ae2  mov     r8d, 89Ch; Size
0x1800b5ae8  call    memset_0
0x1800b5aed  mov     [rsp+900h+pReportInformation.dwSize], 8A0h
0x1800b5af5  call    cs:__imp_GetCurrentProcess
0x1800b5afb  lea     r9, [rsp+900h+phReportHandle]; phReportHandle
0x1800b5b00  mov     [rsp+900h+phReportHandle], 0
0x1800b5b09  lea     r8, [rsp+900h+pReportInformation]; pReportInformation
0x1800b5b0e  mov     [rsp+900h+pReportInformation.hProcess], rax
0x1800b5b13  xor     edx, edx; repType
0x1800b5b15  lea     rcx, pwzEventType; "WindowsNonFatalSuspectedDeadlock"
0x1800b5b1c  call    cs:__imp_WerReportCreate
0x1800b5b22  mov     ebx, eax
0x1800b5b24  test    eax, eax
0x1800b5b26  jns     short loc_1800B5B4A
0x1800b5b28  mov     rcx, [rbp+808h]; this
0x1800b5b2f  lea     r8, aOnecoreNetNetp_11; "onecore\\net\\netprofiles\\service\\src"...
0x1800b5b36  mov     r9d, eax; char *
0x1800b5b39  mov     edx, 0D7h; void *
0x1800b5b3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5b43  mov     eax, ebx
0x1800b5b45  jmp     loc_1800B5C54
0x1800b5b4a  mov     rbx, [rsp+900h+phReportHandle]
0x1800b5b4f  lea     r9, pwzValue; "2"
0x1800b5b56  mov     rcx, rbx; hReportHandle
0x1800b5b59  lea     r8, pwzName; "Version"
0x1800b5b60  xor     edx, edx; dwparamID
0x1800b5b62  call    cs:__imp_WerReportSetParameter
0x1800b5b68  mov     edi, eax
0x1800b5b6a  test    eax, eax
0x1800b5b6c  jns     short loc_1800B5B9E
0x1800b5b6e  mov     edx, 0E1h; void *
0x1800b5b73  mov     rcx, [rbp+808h]; this
0x1800b5b7a  lea     r8, aOnecoreNetNetp_11; "onecore\\net\\netprofiles\\service\\src"...
0x1800b5b81  mov     r9d, edi; char *
0x1800b5b84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5b89  test    rbx, rbx
0x1800b5b8c  jz      short loc_1800B5B97
0x1800b5b8e  mov     rcx, rbx; hReportHandle
0x1800b5b91  call    cs:__imp_WerReportCloseHandle
0x1800b5b97  mov     eax, edi
0x1800b5b99  jmp     loc_1800B5C54
0x1800b5b9e  call    cs:__imp_GetCurrentThread
0x1800b5ba4  mov     rdx, [rsp+900h+pReportInformation.hProcess]; hProcess
0x1800b5ba9  mov     r9d, 2; dumpType
0x1800b5baf  mov     rcx, [rsp+900h+phReportHandle]; hReportHandle
0x1800b5bb4  mov     r8, rax; hThread
0x1800b5bb7  mov     [rsp+900h+dwFlags], 0; dwFlags
0x1800b5bbf  mov     [rsp+900h+pDumpCustomOptions], 0; pDumpCustomOptions
0x1800b5bc8  mov     [rsp+900h+pExceptionParam], 0; pExceptionParam
0x1800b5bd1  call    cs:__imp_WerReportAddDump
0x1800b5bd7  mov     edi, eax
0x1800b5bd9  test    eax, eax
0x1800b5bdb  jns     short loc_1800B5BE4
0x1800b5bdd  mov     edx, 0E3h
0x1800b5be2  jmp     short loc_1800B5B73
0x1800b5be4  mov     rcx, [rsp+900h+phReportHandle]; hReportHandle
0x1800b5be9  lea     r9, [rbp+800h+pSubmitResult]; pSubmitResult
0x1800b5bf0  mov     edx, 1; consent
0x1800b5bf5  mov     [rbp+800h+pSubmitResult], 0
0x1800b5bff  lea     r8d, [rdx+23h]; dwFlags
0x1800b5c03  call    cs:__imp_WerReportSubmit
0x1800b5c09  mov     edi, eax
0x1800b5c0b  test    eax, eax
0x1800b5c0d  jns     short loc_1800B5C19
0x1800b5c0f  mov     edx, 0E6h
0x1800b5c14  jmp     loc_1800B5B73
0x1800b5c19  mov     eax, cs:dword_1801BD288
0x1800b5c1f  cmp     eax, 5
0x1800b5c22  jbe     short loc_1800B5C44
0x1800b5c24  mov     eax, [rbp+800h+pSubmitResult]
0x1800b5c2a  lea     rdx, word_18018BD02
0x1800b5c31  mov     [rsp+900h+var_8C0], eax
0x1800b5c35  lea     rax, [rsp+900h+var_8C0]
0x1800b5c3a  mov     [rsp+900h+pExceptionParam], rax
0x1800b5c3f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800b5c44  test    rbx, rbx
0x1800b5c47  jz      short loc_1800B5C52
0x1800b5c49  mov     rcx, rbx; hReportHandle
0x1800b5c4c  call    cs:__imp_WerReportCloseHandle
0x1800b5c52  xor     eax, eax
0x1800b5c54  mov     rcx, [rbp+800h+var_8]
0x1800b5c5b  xor     rcx, rsp; StackCookie
0x1800b5c5e  call    __security_check_cookie
0x1800b5c63  lea     r11, [rsp+900h+var_s0]
0x1800b5c6b  mov     rbx, [r11+10h]
0x1800b5c6f  mov     rdi, [r11+18h]
0x1800b5c73  mov     rsp, r11
0x1800b5c76  pop     rbp
0x1800b5c77  retn
```
