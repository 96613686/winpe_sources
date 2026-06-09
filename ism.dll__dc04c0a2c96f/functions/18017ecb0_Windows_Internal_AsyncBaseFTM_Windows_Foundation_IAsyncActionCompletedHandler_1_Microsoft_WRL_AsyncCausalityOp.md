# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SetAllConstantsForInputTypeToDefaultAsyncCasualityName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18017ecb0`
- end: `0x18017edba`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?SetAllConstantsForInputTypeToDefaultAsyncCasualityName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18017ecb0`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18017ed0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18017ed0d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18017ed3f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18017ed3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017ed7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017ed85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017ed7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017ed85`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18017ecea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18017ecea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18017ed72`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18017ed72`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18017ed1d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18017ed1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SetAllConstantsForInputTypeToDefaultAsyncCasualityName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  LPVOID v6; // rcx
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  __int64 v11; // [rsp+48h] [rbp-8h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+28h] BYREF

  ppv = 0;
  v11 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v11);
  CurrentProcessId = GetCurrentProcessId();
  v4 = OpenProcess(0x1000u, 0, CurrentProcessId);
  v5 = v4;
  if ( v4 )
  {
    TokenHandle = 0;
    if ( OpenProcessToken(v4, 8u, &TokenHandle) )
    {
      ReturnLength = 0;
      TokenInformation = 0;
      GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
      CloseHandle(TokenHandle);
    }
    CloseHandle(v5);
  }
  v6 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return 1;
}

```

## disassembly

```asm
0x18017ecb0  mov     [rsp-8+arg_0], rbx
0x18017ecb5  push    rbp
0x18017ecb6  mov     rbp, rsp
0x18017ecb9  sub     rsp, 50h
0x18017ecbd  mov     [rbp+var_18], 0
0x18017ecc5  mov     [rbp+var_8], 0
0x18017eccd  lea     rax, [rbp+var_18]
0x18017ecd1  mov     [rsp+50h+ppv], rax; ppv
0x18017ecd6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18017ecdd  xor     edx, edx; pUnkOuter
0x18017ecdf  lea     r8d, [rdx+1]; dwClsContext
0x18017ece3  lea     rcx, CLSID_GlobalOptions; rclsid
0x18017ecea  call    cs:__imp_CoCreateInstance
0x18017ecf0  test    eax, eax
0x18017ecf2  js      short loc_18017ED0D
0x18017ecf4  mov     rcx, [rbp+var_18]
0x18017ecf8  mov     rax, [rcx]
0x18017ecfb  lea     r8, [rbp+var_8]
0x18017ecff  mov     edx, 4
0x18017ed04  mov     rax, [rax+20h]
0x18017ed08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ed0d  call    cs:__imp_GetCurrentProcessId
0x18017ed13  mov     r8d, eax; dwProcessId
0x18017ed16  xor     edx, edx; bInheritHandle
0x18017ed18  mov     ecx, 1000h; dwDesiredAccess
0x18017ed1d  call    cs:__imp_OpenProcess
0x18017ed23  mov     rbx, rax
0x18017ed26  test    rax, rax
0x18017ed29  jz      short loc_18017ED8C
0x18017ed2b  mov     [rbp+TokenHandle], 0
0x18017ed33  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18017ed37  mov     edx, 8; DesiredAccess
0x18017ed3c  mov     rcx, rax; ProcessHandle
0x18017ed3f  call    cs:__imp_OpenProcessToken
0x18017ed45  test    eax, eax
0x18017ed47  jz      short loc_18017ED82
0x18017ed49  mov     [rbp+ReturnLength], 0
0x18017ed50  mov     [rbp+TokenInformation], 0
0x18017ed57  lea     rax, [rbp+ReturnLength]
0x18017ed5b  mov     [rsp+50h+ppv], rax; ReturnLength
0x18017ed60  mov     r9d, 4; TokenInformationLength
0x18017ed66  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18017ed6a  lea     edx, [r9+19h]; TokenInformationClass
0x18017ed6e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18017ed72  call    cs:__imp_GetTokenInformation
0x18017ed78  mov     rcx, [rbp+TokenHandle]; hObject
0x18017ed7c  call    cs:__imp_CloseHandle
0x18017ed82  mov     rcx, rbx; hObject
0x18017ed85  call    cs:__imp_CloseHandle
0x18017ed8b  nop
0x18017ed8c  mov     rcx, [rbp+var_18]
0x18017ed90  test    rcx, rcx
0x18017ed93  jz      short loc_18017EDAA
0x18017ed95  mov     [rbp+var_18], 0
0x18017ed9d  mov     rdx, [rcx]
0x18017eda0  mov     rax, [rdx+10h]
0x18017eda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017eda9  nop
0x18017edaa  mov     eax, 1
0x18017edaf  mov     rbx, [rsp+50h+arg_0]
0x18017edb4  add     rsp, 50h
0x18017edb8  pop     rbp
0x18017edb9  retn
```
