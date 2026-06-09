# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800ee810`
- end: `0x1800ee943`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `307`
- prototype: `int __fastcall(_RTL_RUN_ONCE *__formal, void *__formal, void **__formal)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ee810`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ee8b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ee8b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ee873`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ee873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee8fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee909`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee8fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee909`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ee889`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ee889`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ee8ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ee8ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ee84a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ee84a`

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
0x1800ee810  mov     [rsp-8+arg_0], rbx
0x1800ee815  push    rbp
0x1800ee816  mov     rbp, rsp
0x1800ee819  sub     rsp, 50h
0x1800ee81d  xor     edx, edx; pUnkOuter
0x1800ee81f  mov     [rbp+globalOptions.ptr_], 0
0x1800ee827  lea     rax, [rbp+globalOptions]
0x1800ee82b  mov     [rbp+value], 0
0x1800ee833  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800ee83a  mov     [rsp+50h+ppv], rax; ppv
0x1800ee83f  lea     __formal, CLSID_GlobalOptions; rclsid
0x1800ee846  lea     r8d, [rdx+1]; dwClsContext
0x1800ee84a  call    cs:__imp_CoCreateInstance
0x1800ee851  nop     dword ptr [rax+rax+00h]
0x1800ee856  test    eax, eax
0x1800ee858  js      short loc_1800EE873
0x1800ee85a  mov     __formal, [rbp+globalOptions.ptr_]
0x1800ee85e  lea     r8, [rbp+value]
0x1800ee862  mov     edx, 4
0x1800ee867  mov     rax, [__formal]
0x1800ee86a  mov     rax, [rax+20h]
0x1800ee86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee873  call    cs:__imp_GetCurrentProcessId
0x1800ee87a  nop     dword ptr [rax+rax+00h]
0x1800ee87f  xor     edx, edx; bInheritHandle
0x1800ee881  mov     ecx, 1000h; dwDesiredAccess
0x1800ee886  mov     r8d, eax; dwProcessId
0x1800ee889  call    cs:__imp_OpenProcess
0x1800ee890  nop     dword ptr [rax+rax+00h]
0x1800ee895  mov     rbx, rax
0x1800ee898  test    rax, rax
0x1800ee89b  jz      short loc_1800EE915
0x1800ee89d  lea     r8, [rbp+hToken]; TokenHandle
0x1800ee8a1  mov     [rbp+hToken], 0
0x1800ee8a9  mov     edx, 8; DesiredAccess
0x1800ee8ae  mov     __formal, rax; ProcessHandle
0x1800ee8b1  call    cs:__imp_OpenProcessToken
0x1800ee8b8  nop     dword ptr [rax+rax+00h]
0x1800ee8bd  test    eax, eax
0x1800ee8bf  jz      short loc_1800EE906
0x1800ee8c1  mov     __formal, [rbp+hToken]; TokenHandle
0x1800ee8c5  lea     rax, [rbp+cbToken]
0x1800ee8c9  mov     r9d, 4; TokenInformationLength
0x1800ee8cf  mov     [rbp+cbToken], 0
0x1800ee8d6  lea     r8, [rbp+uIsAppContainer]; TokenInformation
0x1800ee8da  mov     [rbp+uIsAppContainer], 0
0x1800ee8e1  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800ee8e6  lea     edx, [r9+19h]; TokenInformationClass
0x1800ee8ea  call    cs:__imp_GetTokenInformation
0x1800ee8f1  nop     dword ptr [rax+rax+00h]
0x1800ee8f6  mov     __formal, [rbp+hToken]; hObject
0x1800ee8fa  call    cs:__imp_CloseHandle
0x1800ee901  nop     dword ptr [rax+rax+00h]
0x1800ee906  mov     __formal, rbx; hObject
0x1800ee909  call    cs:__imp_CloseHandle
0x1800ee910  nop     dword ptr [rax+rax+00h]
0x1800ee915  mov     __formal, [rbp+globalOptions.ptr_]
0x1800ee919  test    __formal, __formal
0x1800ee91c  jz      short loc_1800EE932
0x1800ee91e  mov     [rbp+globalOptions.ptr_], 0
0x1800ee926  mov     rdx, [__formal]
0x1800ee929  mov     rax, [rdx+10h]
0x1800ee92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee932  mov     rbx, [rsp+50h+arg_0]
0x1800ee937  mov     eax, 1
0x1800ee93c  add     rsp, 50h
0x1800ee940  pop     rbp
0x1800ee941  retn
```
