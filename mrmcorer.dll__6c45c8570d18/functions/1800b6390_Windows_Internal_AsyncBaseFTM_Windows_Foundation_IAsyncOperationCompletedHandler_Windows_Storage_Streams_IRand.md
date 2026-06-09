# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800b6390`
- end: `0x1800b649a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800b6390`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b641f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b641f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b63ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b63ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b645c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b6465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b645c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b6465`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b63fd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b63fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b63ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b63ca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b6452`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b6452`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1800b6390  mov     [rsp-8+arg_0], rbx
0x1800b6395  push    rbp
0x1800b6396  mov     rbp, rsp
0x1800b6399  sub     rsp, 50h
0x1800b639d  mov     [rbp+var_18], 0
0x1800b63a5  mov     [rbp+var_8], 0
0x1800b63ad  lea     rax, [rbp+var_18]
0x1800b63b1  mov     [rsp+50h+ppv], rax; ppv
0x1800b63b6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800b63bd  xor     edx, edx; pUnkOuter
0x1800b63bf  lea     r8d, [rdx+1]; dwClsContext
0x1800b63c3  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800b63ca  call    cs:__imp_CoCreateInstance
0x1800b63d0  test    eax, eax
0x1800b63d2  js      short loc_1800B63ED
0x1800b63d4  mov     rcx, [rbp+var_18]
0x1800b63d8  mov     rax, [rcx]
0x1800b63db  lea     r8, [rbp+var_8]
0x1800b63df  mov     edx, 4
0x1800b63e4  mov     rax, [rax+20h]
0x1800b63e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b63ed  call    cs:__imp_GetCurrentProcessId
0x1800b63f3  mov     r8d, eax; dwProcessId
0x1800b63f6  xor     edx, edx; bInheritHandle
0x1800b63f8  mov     ecx, 1000h; dwDesiredAccess
0x1800b63fd  call    cs:__imp_OpenProcess
0x1800b6403  mov     rbx, rax
0x1800b6406  test    rax, rax
0x1800b6409  jz      short loc_1800B646C
0x1800b640b  mov     [rbp+TokenHandle], 0
0x1800b6413  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800b6417  mov     edx, 8; DesiredAccess
0x1800b641c  mov     rcx, rax; ProcessHandle
0x1800b641f  call    cs:__imp_OpenProcessToken
0x1800b6425  test    eax, eax
0x1800b6427  jz      short loc_1800B6462
0x1800b6429  mov     [rbp+ReturnLength], 0
0x1800b6430  mov     [rbp+TokenInformation], 0
0x1800b6437  lea     rax, [rbp+ReturnLength]
0x1800b643b  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800b6440  mov     r9d, 4; TokenInformationLength
0x1800b6446  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800b644a  lea     edx, [r9+19h]; TokenInformationClass
0x1800b644e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800b6452  call    cs:__imp_GetTokenInformation
0x1800b6458  mov     rcx, [rbp+TokenHandle]; hObject
0x1800b645c  call    cs:__imp_CloseHandle
0x1800b6462  mov     rcx, rbx; hObject
0x1800b6465  call    cs:__imp_CloseHandle
0x1800b646b  nop
0x1800b646c  mov     rcx, [rbp+var_18]
0x1800b6470  test    rcx, rcx
0x1800b6473  jz      short loc_1800B648A
0x1800b6475  mov     [rbp+var_18], 0
0x1800b647d  mov     rdx, [rcx]
0x1800b6480  mov     rax, [rdx+10h]
0x1800b6484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6489  nop
0x1800b648a  mov     eax, 1
0x1800b648f  mov     rbx, [rsp+50h+arg_0]
0x1800b6494  add     rsp, 50h
0x1800b6498  pop     rbp
0x1800b6499  retn
```
