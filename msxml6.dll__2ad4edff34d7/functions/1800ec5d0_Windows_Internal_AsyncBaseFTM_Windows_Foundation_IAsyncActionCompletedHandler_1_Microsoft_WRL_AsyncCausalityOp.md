# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800ec5d0`
- end: `0x1800ec6d8`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `264`
- prototype: `int __fastcall(_RTL_RUN_ONCE *__formal, void *__formal, void **__formal)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ec5d0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ec65f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ec65f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ec62d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ec62d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec69c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec6a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec69c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec6a5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ec63d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ec63d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ec692`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ec692`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ec60a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ec60a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        _RTL_RUN_ONCE *__formal,
        void *a2,
        void **a3)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  IGlobalOptions *ptr; // rcx
  unsigned int uIsAppContainer; // [rsp+30h] [rbp-20h] BYREF
  Microsoft::WRL::ComPtr<IGlobalOptions> globalOptions; // [rsp+38h] [rbp-18h] BYREF
  void *hToken; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 value; // [rsp+48h] [rbp-8h] BYREF
  unsigned int cbToken; // [rsp+78h] [rbp+28h] BYREF

  globalOptions.ptr_ = 0;
  value = 0;
  if ( CoCreateInstance(
         &CLSID_GlobalOptions,
         0,
         1u,
         &GUID_0000015b_0000_0000_c000_000000000046,
         (LPVOID *)&globalOptions.ptr_) >= 0 )
    globalOptions.ptr_->Query(globalOptions.ptr_, COMGLB_RO_SETTINGS, &value);
  CurrentProcessId = GetCurrentProcessId();
  v4 = OpenProcess(0x1000u, 0, CurrentProcessId);
  v5 = v4;
  if ( v4 )
  {
    hToken = 0;
    if ( OpenProcessToken(v4, 8u, &hToken) )
    {
      cbToken = 0;
      uIsAppContainer = 0;
      GetTokenInformation(hToken, TokenIsAppContainer, &uIsAppContainer, 4u, &cbToken);
      CloseHandle(hToken);
    }
    CloseHandle(v5);
  }
  ptr = globalOptions.ptr_;
  if ( globalOptions.ptr_ )
  {
    globalOptions.ptr_ = 0;
    ptr->Release(ptr);
  }
  return 1;
}

```

## disassembly

```asm
0x1800ec5d0  mov     [rsp-8+arg_0], rbx
0x1800ec5d5  push    rbp
0x1800ec5d6  mov     rbp, rsp
0x1800ec5d9  sub     rsp, 50h
0x1800ec5dd  xor     edx, edx; pUnkOuter
0x1800ec5df  mov     [rbp+globalOptions.ptr_], 0
0x1800ec5e7  lea     rax, [rbp+globalOptions]
0x1800ec5eb  mov     [rbp+value], 0
0x1800ec5f3  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800ec5fa  mov     [rsp+50h+ppv], rax; ppv
0x1800ec5ff  lea     __formal, CLSID_GlobalOptions; rclsid
0x1800ec606  lea     r8d, [rdx+1]; dwClsContext
0x1800ec60a  call    cs:__imp_CoCreateInstance
0x1800ec610  test    eax, eax
0x1800ec612  js      short loc_1800EC62D
0x1800ec614  mov     __formal, [rbp+globalOptions.ptr_]
0x1800ec618  lea     r8, [rbp+value]
0x1800ec61c  mov     edx, 4
0x1800ec621  mov     rax, [__formal]
0x1800ec624  mov     rax, [rax+20h]
0x1800ec628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec62d  call    cs:__imp_GetCurrentProcessId
0x1800ec633  xor     edx, edx; bInheritHandle
0x1800ec635  mov     ecx, 1000h; dwDesiredAccess
0x1800ec63a  mov     r8d, eax; dwProcessId
0x1800ec63d  call    cs:__imp_OpenProcess
0x1800ec643  mov     rbx, rax
0x1800ec646  test    rax, rax
0x1800ec649  jz      short loc_1800EC6AB
0x1800ec64b  lea     r8, [rbp+hToken]; TokenHandle
0x1800ec64f  mov     [rbp+hToken], 0
0x1800ec657  mov     edx, 8; DesiredAccess
0x1800ec65c  mov     __formal, rax; ProcessHandle
0x1800ec65f  call    cs:__imp_OpenProcessToken
0x1800ec665  test    eax, eax
0x1800ec667  jz      short loc_1800EC6A2
0x1800ec669  mov     __formal, [rbp+hToken]; TokenHandle
0x1800ec66d  lea     rax, [rbp+cbToken]
0x1800ec671  mov     r9d, 4; TokenInformationLength
0x1800ec677  mov     [rbp+cbToken], 0
0x1800ec67e  lea     r8, [rbp+uIsAppContainer]; TokenInformation
0x1800ec682  mov     [rbp+uIsAppContainer], 0
0x1800ec689  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800ec68e  lea     edx, [r9+19h]; TokenInformationClass
0x1800ec692  call    cs:__imp_GetTokenInformation
0x1800ec698  mov     __formal, [rbp+hToken]; hObject
0x1800ec69c  call    cs:__imp_CloseHandle
0x1800ec6a2  mov     __formal, rbx; hObject
0x1800ec6a5  call    cs:__imp_CloseHandle
0x1800ec6ab  mov     __formal, [rbp+globalOptions.ptr_]
0x1800ec6af  test    __formal, __formal
0x1800ec6b2  jz      short loc_1800EC6C8
0x1800ec6b4  mov     [rbp+globalOptions.ptr_], 0
0x1800ec6bc  mov     rdx, [__formal]
0x1800ec6bf  mov     rax, [rdx+10h]
0x1800ec6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec6c8  mov     rbx, [rsp+50h+arg_0]
0x1800ec6cd  mov     eax, 1
0x1800ec6d2  add     rsp, 50h
0x1800ec6d6  pop     rbp
0x1800ec6d7  retn
```
