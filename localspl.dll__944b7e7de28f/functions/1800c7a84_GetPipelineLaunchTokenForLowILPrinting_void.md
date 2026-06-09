# GetPipelineLaunchTokenForLowILPrinting(void * *)

- ea: `0x1800c7a84`
- end: `0x1800c7c14`
- name: `?GetPipelineLaunchTokenForLowILPrinting@@YAJPEAPEAX@Z`
- size: `400`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180081080`

## callees

- `0x18003ea2c`
- `0x1800547e0`
- `0x1800c72e4`
- `0x1800c7a84`
- `0x1800c7c1c`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7b6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7b6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7bba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c7b13`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c7b13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c7afd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c7afd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c7b4d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c7b4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7b64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7ba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7b64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7ba9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c7aa1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c7aa1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c7bf5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c7bf5`

## string_xrefs

- `0x1800c7b82`: `SetThreadToken failed. Error 0x%x`
- `0x1800c7ac9`: `GetPipelineLaunchTokenForLowILPrinting`
- `0x1800c7b89`: `GetPipelineLaunchTokenForLowILPrinting`
- `0x1800c7be5`: `GetPipelineLaunchTokenForLowILPrinting`
- `0x1800c7bb1`: `GetTokenForLowILPrinting failed. Error 0x%x`
- `0x1800c7bd2`: `OpenThreadToken failed. Error 0x%x`
- `0x1800c7bdb`: `GetPrintScanBroker failed. Error 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetPipelineLaunchTokenForLowILPrinting(void **a1)
{
  HRESULT v2; // edi
  unsigned int v3; // ebx
  int PrintScanBroker; // eax
  HANDLE CurrentThread; // rax
  signed int v6; // eax
  unsigned __int16 *v7; // rdx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+40h] [rbp+20h] BYREF
  HANDLE Token; // [rsp+48h] [rbp+28h] BYREF
  __int64 v12; // [rsp+50h] [rbp+30h] BYREF

  *a1 = 0;
  v2 = CoInitializeEx(0, 0);
  if ( (int)(v2 + 0x80000000) >= 0 && v2 != -2147417850 )
  {
    v3 = v2;
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "GetPipelineLaunchTokenForLowILPrinting",
      L"CoInitializeEx failed. Error 0x%x",
      (unsigned int)v2);
    return v3;
  }
  v12 = 0;
  PrintScanBroker = GetPrintScanBroker(&v12);
  v3 = PrintScanBroker;
  if ( PrintScanBroker < 0 )
  {
    v7 = L"GetPrintScanBroker failed. Error 0x%x";
  }
  else
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "GetPipelineLaunchTokenForLowILPrinting",
        L"OpenThreadToken failed. Error 0x%x",
        v3);
      goto LABEL_20;
    }
    Token = 0;
    PrintScanBroker = (*(__int64 (__fastcall **)(__int64, void *, HANDLE *))(*(_QWORD *)v12 + 72LL))(
                        v12,
                        TokenHandle,
                        &Token);
    v3 = PrintScanBroker;
    if ( PrintScanBroker >= 0 )
    {
      if ( SetThreadToken(0, Token) )
      {
        *a1 = TokenHandle;
      }
      else
      {
        CloseHandle(TokenHandle);
        v6 = GetLastError();
        v3 = v6;
        if ( v6 > 0 )
          v3 = (unsigned __int16)v6 | 0x80070000;
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "GetPipelineLaunchTokenForLowILPrinting",
          L"SetThreadToken failed. Error 0x%x",
          v3);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
        CloseHandle(Token);
      goto LABEL_20;
    }
    v7 = L"GetTokenForLowILPrinting failed. Error 0x%x";
  }
  LocalSpoolerTelemetry::WriteDbgTraceError("GetPipelineLaunchTokenForLowILPrinting", v7, (unsigned int)PrintScanBroker);
LABEL_20:
  if ( v2 >= 0 )
    CoUninitialize();
  wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>(&v12);
  return v3;
}

```

## disassembly

```asm
0x1800c7a84  mov     [rsp-18h+arg_18], rbx
0x1800c7a89  push    rbp
0x1800c7a8a  push    rsi
0x1800c7a8b  push    rdi
0x1800c7a8c  mov     rbp, rsp
0x1800c7a8f  sub     rsp, 20h
0x1800c7a93  mov     rsi, rcx
0x1800c7a96  mov     qword ptr [rcx], 0
0x1800c7a9d  xor     edx, edx; dwCoInit
0x1800c7a9f  xor     ecx, ecx; pvReserved
0x1800c7aa1  call    cs:__imp_CoInitializeEx
0x1800c7aa7  mov     edi, eax
0x1800c7aa9  mov     eax, 80000000h
0x1800c7aae  lea     edx, [rdi+rax]
0x1800c7ab1  test    eax, edx
0x1800c7ab3  jnz     short loc_1800C7ADA
0x1800c7ab5  cmp     edi, 80010106h
0x1800c7abb  jz      short loc_1800C7ADA
0x1800c7abd  mov     ebx, edi
0x1800c7abf  mov     r8d, edi
0x1800c7ac2  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed. Error 0x%x"
0x1800c7ac9  lea     rcx, aGetpipelinelau; "GetPipelineLaunchTokenForLowILPrinting"
0x1800c7ad0  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c7ad5  jmp     loc_1800C7C05
0x1800c7ada  mov     [rbp+arg_10], 0
0x1800c7ae2  lea     rcx, [rbp+arg_10]
0x1800c7ae6  call    ?GetPrintScanBroker@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x1800c7aeb  mov     ebx, eax
0x1800c7aed  test    eax, eax
0x1800c7aef  js      loc_1800C7BDB
0x1800c7af5  mov     [rbp+TokenHandle], 0
0x1800c7afd  call    cs:__imp_GetCurrentThread
0x1800c7b03  mov     rcx, rax; ThreadHandle
0x1800c7b06  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c7b0a  mov     edx, 0Eh; DesiredAccess
0x1800c7b0f  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800c7b13  call    cs:__imp_OpenThreadToken
0x1800c7b19  test    eax, eax
0x1800c7b1b  jz      loc_1800C7BBA
0x1800c7b21  mov     [rbp+Token], 0
0x1800c7b29  mov     rcx, [rbp+arg_10]
0x1800c7b2d  mov     rax, [rcx]
0x1800c7b30  lea     r8, [rbp+Token]
0x1800c7b34  mov     rdx, [rbp+TokenHandle]
0x1800c7b38  mov     rax, [rax+48h]
0x1800c7b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7b41  mov     ebx, eax
0x1800c7b43  test    eax, eax
0x1800c7b45  js      short loc_1800C7BB1
0x1800c7b47  mov     rdx, [rbp+Token]; Token
0x1800c7b4b  xor     ecx, ecx; Thread
0x1800c7b4d  call    cs:__imp_SetThreadToken
0x1800c7b53  test    eax, eax
0x1800c7b55  jz      short loc_1800C7B60
0x1800c7b57  mov     rax, [rbp+TokenHandle]
0x1800c7b5b  mov     [rsi], rax
0x1800c7b5e  jmp     short loc_1800C7B95
0x1800c7b60  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c7b64  call    cs:__imp_CloseHandle
0x1800c7b6a  call    cs:__imp_GetLastError
0x1800c7b70  mov     ebx, eax
0x1800c7b72  test    eax, eax
0x1800c7b74  jle     short loc_1800C7B7F
0x1800c7b76  movzx   ebx, ax
0x1800c7b79  or      ebx, 80070000h
0x1800c7b7f  mov     r8d, ebx
0x1800c7b82  lea     rdx, aSetthreadtoken; "SetThreadToken failed. Error 0x%x"
0x1800c7b89  lea     rcx, aGetpipelinelau; "GetPipelineLaunchTokenForLowILPrinting"
0x1800c7b90  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c7b95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800c7b9c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800c7ba1  test    al, al
0x1800c7ba3  jz      short loc_1800C7BF1
0x1800c7ba5  mov     rcx, [rbp+Token]; hObject
0x1800c7ba9  call    cs:__imp_CloseHandle
0x1800c7baf  jmp     short loc_1800C7BF1
0x1800c7bb1  lea     rdx, aGettokenforlow; "GetTokenForLowILPrinting failed. Error "...
0x1800c7bb8  jmp     short loc_1800C7BE2
0x1800c7bba  call    cs:__imp_GetLastError
0x1800c7bc0  mov     ebx, eax
0x1800c7bc2  test    eax, eax
0x1800c7bc4  jle     short loc_1800C7BCF
0x1800c7bc6  movzx   ebx, ax
0x1800c7bc9  or      ebx, 80070000h
0x1800c7bcf  mov     r8d, ebx
0x1800c7bd2  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed. Error 0x%x"
0x1800c7bd9  jmp     short loc_1800C7BE5
0x1800c7bdb  lea     rdx, aGetprintscanbr; "GetPrintScanBroker failed. Error 0x%x"
0x1800c7be2  mov     r8d, eax
0x1800c7be5  lea     rcx, aGetpipelinelau; "GetPipelineLaunchTokenForLowILPrinting"
0x1800c7bec  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c7bf1  test    edi, edi
0x1800c7bf3  js      short loc_1800C7BFC
0x1800c7bf5  call    cs:__imp_CoUninitialize
0x1800c7bfb  nop
0x1800c7bfc  lea     rcx, [rbp+arg_10]
0x1800c7c00  call    ??1?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>(void)
0x1800c7c05  mov     eax, ebx
0x1800c7c07  mov     rbx, [rsp+20h+arg_18]
0x1800c7c0c  add     rsp, 20h
0x1800c7c10  pop     rdi
0x1800c7c11  pop     rsi
0x1800c7c12  pop     rbp
0x1800c7c13  retn
```
