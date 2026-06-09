# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x100a1aa0`
- end: `0x100a1b57`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CGHPAT_RTL_RUN_ONCE@@PAXPAPAX@Z`
- size: `183`
- prototype: `int __stdcall(_RTL_RUN_ONCE *__formal, void *__formal, void **__formal)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x10067b20`
- `0x100a1aa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x100a1ae2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x100a1ae2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x100a1b02`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x100a1b02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a1b27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a1b2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a1b27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a1b2e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x100a1aef`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x100a1aef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x100a1b1e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x100a1b1e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100a1ac0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100a1ac0`

## pseudocode

```c
int __stdcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        _RTL_RUN_ONCE *__formal,
        void *a2,
        void **a3)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // esi
  IGlobalOptions *ptr; // edx
  unsigned int cbToken; // [esp+8h] [ebp-14h] BYREF
  unsigned int value; // [esp+Ch] [ebp-10h] BYREF
  unsigned int uIsAppContainer; // [esp+10h] [ebp-Ch] BYREF
  void *hToken; // [esp+14h] [ebp-8h] BYREF
  Microsoft::WRL::ComPtr<IGlobalOptions> globalOptions; // [esp+18h] [ebp-4h] BYREF

  globalOptions.ptr_ = 0;
  if ( CoCreateInstance(
         &CLSID_GlobalOptions,
         0,
         1u,
         &_GUID_0000015b_0000_0000_c000_000000000046,
         (LPVOID *)&globalOptions.ptr_) >= 0 )
    ((void (__thiscall *)(HRESULT (__stdcall *)(IGlobalOptions *, tagGLOBALOPT_PROPERTIES, unsigned int *), IGlobalOptions *, int, unsigned int *))globalOptions.ptr_->Query)(
      globalOptions.ptr_->Query,
      globalOptions.ptr_,
      4,
      &value);
  CurrentProcessId = GetCurrentProcessId();
  v4 = OpenProcess(0x1000u, 0, CurrentProcessId);
  if ( v4 )
  {
    if ( OpenProcessToken(v4, 8u, &hToken) )
    {
      uIsAppContainer = 0;
      GetTokenInformation(hToken, TokenIsAppContainer, &uIsAppContainer, 4u, &cbToken);
      CloseHandle(hToken);
    }
    CloseHandle(v4);
  }
  ptr = globalOptions.ptr_;
  if ( globalOptions.ptr_ )
  {
    globalOptions.ptr_ = 0;
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IGlobalOptions *))ptr->Release)(ptr->Release, ptr);
  }
  return 1;
}

```

## disassembly

```asm
0x100a1aa0  mov     edi, edi
0x100a1aa2  push    ebp
0x100a1aa3  mov     ebp, esp
0x100a1aa5  sub     esp, 14h
0x100a1aa8  push    esi
0x100a1aa9  push    edi
0x100a1aaa  lea     eax, [ebp+globalOptions]
0x100a1aad  xor     edi, edi
0x100a1aaf  push    eax; ppv
0x100a1ab0  push    offset __GUID_0000015b_0000_0000_c000_000000000046; riid
0x100a1ab5  push    1; dwClsContext
0x100a1ab7  push    edi; pUnkOuter
0x100a1ab8  push    offset _CLSID_GlobalOptions; rclsid
0x100a1abd  mov     [ebp+globalOptions.ptr_], edi
0x100a1ac0  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x100a1ac6  test    eax, eax
0x100a1ac8  js      short loc_100A1AE2
0x100a1aca  mov     eax, [ebp+globalOptions.ptr_]
0x100a1acd  lea     ecx, [ebp+value]
0x100a1ad0  push    ecx
0x100a1ad1  push    4
0x100a1ad3  push    eax
0x100a1ad4  mov     esi, [eax]
0x100a1ad6  mov     ecx, [esi+10h]; this
0x100a1ad9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a1adf  call    dword ptr [esi+10h]
0x100a1ae2  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x100a1ae8  push    eax; dwProcessId
0x100a1ae9  push    edi; bInheritHandle
0x100a1aea  push    1000h; dwDesiredAccess
0x100a1aef  call    ds:__imp__OpenProcess@12; OpenProcess(x,x,x)
0x100a1af5  mov     esi, eax
0x100a1af7  test    esi, esi
0x100a1af9  jz      short loc_100A1B34
0x100a1afb  lea     eax, [ebp+hToken]
0x100a1afe  push    eax; TokenHandle
0x100a1aff  push    8; DesiredAccess
0x100a1b01  push    esi; ProcessHandle
0x100a1b02  call    ds:__imp__OpenProcessToken@12; OpenProcessToken(x,x,x)
0x100a1b08  test    eax, eax
0x100a1b0a  jz      short loc_100A1B2D
0x100a1b0c  lea     eax, [ebp+cbToken]
0x100a1b0f  mov     [ebp+uIsAppContainer], edi
0x100a1b12  push    eax; ReturnLength
0x100a1b13  push    4; TokenInformationLength
0x100a1b15  lea     eax, [ebp+uIsAppContainer]
0x100a1b18  push    eax; TokenInformation
0x100a1b19  push    1Dh; TokenInformationClass
0x100a1b1b  push    [ebp+hToken]; TokenHandle
0x100a1b1e  call    ds:__imp__GetTokenInformation@20; GetTokenInformation(x,x,x,x,x)
0x100a1b24  push    [ebp+hToken]; hObject
0x100a1b27  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100a1b2d  push    esi; hObject
0x100a1b2e  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100a1b34  mov     edx, [ebp+globalOptions.ptr_]
0x100a1b37  test    edx, edx
0x100a1b39  jz      short loc_100A1B4E
0x100a1b3b  mov     [ebp+globalOptions.ptr_], edi
0x100a1b3e  mov     ecx, [edx]
0x100a1b40  push    edx
0x100a1b41  mov     esi, [ecx+8]
0x100a1b44  mov     ecx, esi; this
0x100a1b46  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a1b4c  call    esi
0x100a1b4e  xor     eax, eax
0x100a1b50  pop     edi
0x100a1b51  inc     eax
0x100a1b52  pop     esi
0x100a1b53  leave
0x100a1b54  retn    0Ch
```
