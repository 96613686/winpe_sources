# NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(void * *,int *)

- ea: `0x1800ce7e0`
- end: `0x1800cea0b`
- name: `?ElevateIntegrityLevelIfLowViaBroker@NSecurityLibrary@@YAJPEAPEAXPEAH@Z`
- size: `555`
- prototype: `__int64 __fastcall(NSecurityLibrary *__hidden this, void **, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003d1f8`

## callees

- `0x18003f734`
- `0x18003f754`
- `0x180046650`
- `0x180047330`
- `0x1800c72e4`
- `0x1800ce530`
- `0x1800ce7e0`
- `0x1800cea14`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce88a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce9a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce88a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce9a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce835`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce880`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce835`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ce821`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ce86c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ce821`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ce86c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ce98b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ce98b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce859`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce859`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce8d4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce8d4`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800ce904`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800ce904`
- `KERNELBASE!GetIsEdpEnabled` at `0x1800ce910`
- `KERNELBASE!GetIsEdpEnabled` at `0x1800ce910`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800ce922`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800ce922`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800ce9d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800ce9d6`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(NSecurityLibrary *this, void **a2, int *a3)
{
  signed int PrintScanBroker; // ebx
  HANDLE CurrentThread; // rax
  void *v7; // rdi
  HANDLE v8; // rax
  signed int LastError; // eax
  signed int v10; // eax
  BOOL v11; // eax
  HRESULT v12; // edi
  signed int v13; // eax
  void *TokenHandle; // [rsp+30h] [rbp-59h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-51h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-49h] BYREF
  __int64 v18; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v19[2]; // [rsp+50h] [rbp-39h] BYREF
  PSID TokenInformation[12]; // [rsp+60h] [rbp-29h] BYREF

  *(_QWORD *)this = 0;
  PrintScanBroker = 0;
  TokenHandle = 0;
  *(_DWORD *)a2 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    v7 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&Token);
      CloseHandle(v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&Token);
    }
    TokenHandle = 0;
    v8 = GetCurrentThread();
    if ( !OpenThreadToken(v8, 0xEu, 0, &TokenHandle) )
    {
      LastError = GetLastError();
      PrintScanBroker = LastError;
      if ( LastError > 0 )
        PrintScanBroker = (unsigned __int16)LastError | 0x80070000;
    }
  }
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 88;
  if ( PrintScanBroker >= 0 )
  {
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, TokenInformation, 0x58u, &ReturnLength) )
      goto LABEL_12;
    v10 = GetLastError();
    PrintScanBroker = v10;
    if ( v10 > 0 )
      PrintScanBroker = (unsigned __int16)v10 | 0x80070000;
    if ( PrintScanBroker >= 0 )
    {
LABEL_12:
      v11 = IsWellKnownSid(TokenInformation[0], WinLowLabelSid);
      *(_DWORD *)a2 = v11;
      if ( v11 || (unsigned int)GetIsEdpEnabled() )
      {
        v12 = CoInitializeEx(0, 0);
        if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147417850 )
        {
          v18 = 0;
          PrintScanBroker = NSecurityLibrary::GetPrintScanBroker(&v18);
          if ( PrintScanBroker >= 0 )
          {
            Token = 0;
            PrintScanBroker = (*(__int64 (__fastcall **)(__int64, void *, HANDLE *))(*(_QWORD *)v18 + 72LL))(
                                v18,
                                TokenHandle,
                                &Token);
            if ( PrintScanBroker >= 0 )
            {
              v19[0] = Token;
              if ( SetThreadToken(0, Token) )
              {
                *(_QWORD *)this = TokenHandle;
                TokenHandle = 0;
              }
              else
              {
                v13 = GetLastError();
                PrintScanBroker = v13;
                if ( v13 > 0 )
                  PrintScanBroker = (unsigned __int16)v13 | 0x80070000;
              }
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v19);
            }
          }
          wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>(&v18);
          if ( v12 >= 0 )
            CoUninitialize();
        }
        else
        {
          PrintScanBroker = v12;
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return (unsigned int)PrintScanBroker;
}

```

## disassembly

```asm
0x1800ce7e0  mov     [rsp-8+arg_10], rbx
0x1800ce7e5  mov     [rsp-8+arg_18], rsi
0x1800ce7ea  push    rbp
0x1800ce7eb  push    rdi
0x1800ce7ec  push    r14
0x1800ce7ee  lea     rbp, [rsp-47h]
0x1800ce7f3  sub     rsp, 0D0h
0x1800ce7fa  mov     rax, cs:__security_cookie
0x1800ce801  xor     rax, rsp
0x1800ce804  mov     [rbp+57h+var_20], rax
0x1800ce808  mov     qword ptr [rcx], 0
0x1800ce80f  xor     ebx, ebx
0x1800ce811  mov     [rbp+57h+TokenHandle], rbx
0x1800ce815  mov     rsi, rdx
0x1800ce818  mov     r14, rcx
0x1800ce81b  mov     dword ptr [rdx], 0
0x1800ce821  call    cs:__imp_GetCurrentThread
0x1800ce827  mov     rcx, rax; ThreadHandle
0x1800ce82a  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800ce82e  lea     edx, [rbx+0Eh]; DesiredAccess
0x1800ce831  lea     r8d, [rbx+1]; OpenAsSelf
0x1800ce835  call    cs:__imp_OpenThreadToken
0x1800ce83b  test    eax, eax
0x1800ce83d  jnz     short loc_1800CE89F
0x1800ce83f  mov     rdi, [rbp+57h+TokenHandle]
0x1800ce843  lea     rax, [rdi-1]
0x1800ce847  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ce84b  ja      short loc_1800CE868
0x1800ce84d  lea     rcx, [rbp+57h+Token]; this
0x1800ce851  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800ce856  mov     rcx, rdi; hObject
0x1800ce859  call    cs:__imp_CloseHandle
0x1800ce85f  lea     rcx, [rbp+57h+Token]; this
0x1800ce863  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800ce868  mov     [rbp+57h+TokenHandle], rbx
0x1800ce86c  call    cs:__imp_GetCurrentThread
0x1800ce872  xor     r8d, r8d; OpenAsSelf
0x1800ce875  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800ce879  mov     rcx, rax; ThreadHandle
0x1800ce87c  lea     edx, [r8+0Eh]; DesiredAccess
0x1800ce880  call    cs:__imp_OpenThreadToken
0x1800ce886  test    eax, eax
0x1800ce888  jnz     short loc_1800CE89F
0x1800ce88a  call    cs:__imp_GetLastError
0x1800ce890  mov     ebx, eax
0x1800ce892  test    eax, eax
0x1800ce894  jle     short loc_1800CE89F
0x1800ce896  movzx   ebx, ax
0x1800ce899  or      ebx, 80070000h
0x1800ce89f  mov     edi, 58h ; 'X'
0x1800ce8a4  lea     rcx, [rbp+57h+TokenInformation]; void *
0x1800ce8a8  mov     r8d, edi; Size
0x1800ce8ab  xor     edx, edx; Val
0x1800ce8ad  call    memset_0
0x1800ce8b2  mov     [rbp+57h+var_A0], edi
0x1800ce8b5  test    ebx, ebx
0x1800ce8b7  js      loc_1800CE9DC
0x1800ce8bd  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800ce8c1  lea     rax, [rbp+57h+var_A0]
0x1800ce8c5  mov     r9d, edi; TokenInformationLength
0x1800ce8c8  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800ce8cd  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800ce8d1  lea     edx, [rdi-3Fh]; TokenInformationClass
0x1800ce8d4  call    cs:__imp_GetTokenInformation
0x1800ce8da  test    eax, eax
0x1800ce8dc  jnz     short loc_1800CE8FB
0x1800ce8de  call    cs:__imp_GetLastError
0x1800ce8e4  mov     ebx, eax
0x1800ce8e6  test    eax, eax
0x1800ce8e8  jle     short loc_1800CE8F3
0x1800ce8ea  movzx   ebx, ax
0x1800ce8ed  or      ebx, 80070000h
0x1800ce8f3  test    ebx, ebx
0x1800ce8f5  js      loc_1800CE9DC
0x1800ce8fb  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x1800ce8ff  mov     edx, 42h ; 'B'; WellKnownSidType
0x1800ce904  call    cs:__imp_IsWellKnownSid
0x1800ce90a  mov     [rsi], eax
0x1800ce90c  test    eax, eax
0x1800ce90e  jnz     short loc_1800CE91E
0x1800ce910  call    cs:__imp_GetIsEdpEnabled
0x1800ce916  test    eax, eax
0x1800ce918  jz      loc_1800CE9DC
0x1800ce91e  xor     edx, edx; dwCoInit
0x1800ce920  xor     ecx, ecx; pvReserved
0x1800ce922  call    cs:__imp_CoInitializeEx
0x1800ce928  mov     ecx, 80000000h
0x1800ce92d  mov     edi, eax
0x1800ce92f  add     eax, ecx
0x1800ce931  test    ecx, eax
0x1800ce933  jnz     short loc_1800CE944
0x1800ce935  cmp     edi, 80010106h
0x1800ce93b  jz      short loc_1800CE944
0x1800ce93d  mov     ebx, edi
0x1800ce93f  jmp     loc_1800CE9DC
0x1800ce944  lea     rcx, [rbp+57h+var_98]
0x1800ce948  mov     [rbp+57h+var_98], 0
0x1800ce950  call    ?GetPrintScanBroker@NSecurityLibrary@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; NSecurityLibrary::GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x1800ce955  mov     ebx, eax
0x1800ce957  test    eax, eax
0x1800ce959  js      short loc_1800CE9C4
0x1800ce95b  mov     rcx, [rbp+57h+var_98]
0x1800ce95f  lea     r8, [rbp+57h+Token]
0x1800ce963  mov     rdx, [rbp+57h+TokenHandle]
0x1800ce967  mov     [rbp+57h+Token], 0
0x1800ce96f  mov     rax, [rcx]
0x1800ce972  mov     rax, [rax+48h]
0x1800ce976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce97b  mov     ebx, eax
0x1800ce97d  test    eax, eax
0x1800ce97f  js      short loc_1800CE9C4
0x1800ce981  mov     rdx, [rbp+57h+Token]; Token
0x1800ce985  xor     ecx, ecx; Thread
0x1800ce987  mov     [rbp+57h+var_90], rdx
0x1800ce98b  call    cs:__imp_SetThreadToken
0x1800ce991  test    eax, eax
0x1800ce993  jz      short loc_1800CE9A6
0x1800ce995  mov     rax, [rbp+57h+TokenHandle]
0x1800ce999  mov     [r14], rax
0x1800ce99c  mov     [rbp+57h+TokenHandle], 0
0x1800ce9a4  jmp     short loc_1800CE9BB
0x1800ce9a6  call    cs:__imp_GetLastError
0x1800ce9ac  mov     ebx, eax
0x1800ce9ae  test    eax, eax
0x1800ce9b0  jle     short loc_1800CE9BB
0x1800ce9b2  movzx   ebx, ax
0x1800ce9b5  or      ebx, 80070000h
0x1800ce9bb  lea     rcx, [rbp+57h+var_90]
0x1800ce9bf  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ce9c4  lea     rcx, [rbp+57h+var_98]
0x1800ce9c8  call    ??1?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy>(void)
0x1800ce9cd  shr     edi, 1Fh
0x1800ce9d0  xor     dil, 1
0x1800ce9d4  jz      short loc_1800CE9DC
0x1800ce9d6  call    cs:__imp_CoUninitialize
0x1800ce9dc  lea     rcx, [rbp+57h+TokenHandle]
0x1800ce9e0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ce9e5  mov     eax, ebx
0x1800ce9e7  mov     rcx, [rbp+57h+var_20]
0x1800ce9eb  xor     rcx, rsp; StackCookie
0x1800ce9ee  call    __security_check_cookie
0x1800ce9f3  lea     r11, [rsp+0E0h+var_10]
0x1800ce9fb  mov     rbx, [r11+30h]
0x1800ce9ff  mov     rsi, [r11+38h]
0x1800cea03  mov     rsp, r11
0x1800cea06  pop     r14
0x1800cea08  pop     rdi
0x1800cea09  pop     rbp
0x1800cea0a  retn
```
