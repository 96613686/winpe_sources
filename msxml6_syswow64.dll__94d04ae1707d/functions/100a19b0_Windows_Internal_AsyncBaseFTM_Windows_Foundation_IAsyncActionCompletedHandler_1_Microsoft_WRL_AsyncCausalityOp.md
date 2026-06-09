# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x100a19b0`
- end: `0x100a1a67`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CGHPAT_RTL_RUN_ONCE@@PAXPAPAX@Z`
- size: `183`
- prototype: `int __stdcall(_RTL_RUN_ONCE *__formal, void *__formal, void **__formal)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x10067bc0`
- `0x100a19b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x100a19f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x100a19f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x100a1a12`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x100a1a12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a1a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a1a3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a1a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a1a3e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x100a19ff`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x100a19ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x100a1a2e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x100a1a2e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100a19d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100a19d0`

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
0x100a19b0  mov     edi, edi
0x100a19b2  push    ebp
0x100a19b3  mov     ebp, esp
0x100a19b5  sub     esp, 14h
0x100a19b8  push    esi
0x100a19b9  push    edi
0x100a19ba  lea     eax, [ebp+globalOptions]
0x100a19bd  xor     edi, edi
0x100a19bf  push    eax; ppv
0x100a19c0  push    offset __GUID_0000015b_0000_0000_c000_000000000046; riid
0x100a19c5  push    1; dwClsContext
0x100a19c7  push    edi; pUnkOuter
0x100a19c8  push    offset _CLSID_GlobalOptions; rclsid
0x100a19cd  mov     [ebp+globalOptions.ptr_], edi
0x100a19d0  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x100a19d6  test    eax, eax
0x100a19d8  js      short loc_100A19F2
0x100a19da  mov     eax, [ebp+globalOptions.ptr_]
0x100a19dd  lea     ecx, [ebp+value]
0x100a19e0  push    ecx
0x100a19e1  push    4
0x100a19e3  push    eax
0x100a19e4  mov     esi, [eax]
0x100a19e6  mov     ecx, [esi+10h]; this
0x100a19e9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a19ef  call    dword ptr [esi+10h]
0x100a19f2  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x100a19f8  push    eax; dwProcessId
0x100a19f9  push    edi; bInheritHandle
0x100a19fa  push    1000h; dwDesiredAccess
0x100a19ff  call    ds:__imp__OpenProcess@12; OpenProcess(x,x,x)
0x100a1a05  mov     esi, eax
0x100a1a07  test    esi, esi
0x100a1a09  jz      short loc_100A1A44
0x100a1a0b  lea     eax, [ebp+hToken]
0x100a1a0e  push    eax; TokenHandle
0x100a1a0f  push    8; DesiredAccess
0x100a1a11  push    esi; ProcessHandle
0x100a1a12  call    ds:__imp__OpenProcessToken@12; OpenProcessToken(x,x,x)
0x100a1a18  test    eax, eax
0x100a1a1a  jz      short loc_100A1A3D
0x100a1a1c  lea     eax, [ebp+cbToken]
0x100a1a1f  mov     [ebp+uIsAppContainer], edi
0x100a1a22  push    eax; ReturnLength
0x100a1a23  push    4; TokenInformationLength
0x100a1a25  lea     eax, [ebp+uIsAppContainer]
0x100a1a28  push    eax; TokenInformation
0x100a1a29  push    1Dh; TokenInformationClass
0x100a1a2b  push    [ebp+hToken]; TokenHandle
0x100a1a2e  call    ds:__imp__GetTokenInformation@20; GetTokenInformation(x,x,x,x,x)
0x100a1a34  push    [ebp+hToken]; hObject
0x100a1a37  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100a1a3d  push    esi; hObject
0x100a1a3e  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100a1a44  mov     edx, [ebp+globalOptions.ptr_]
0x100a1a47  test    edx, edx
0x100a1a49  jz      short loc_100A1A5E
0x100a1a4b  mov     [ebp+globalOptions.ptr_], edi
0x100a1a4e  mov     ecx, [edx]
0x100a1a50  push    edx
0x100a1a51  mov     esi, [ecx+8]
0x100a1a54  mov     ecx, esi; this
0x100a1a56  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a1a5c  call    esi
0x100a1a5e  xor     eax, eax
0x100a1a60  pop     edi
0x100a1a61  inc     eax
0x100a1a62  pop     esi
0x100a1a63  leave
0x100a1a64  retn    0Ch
```
