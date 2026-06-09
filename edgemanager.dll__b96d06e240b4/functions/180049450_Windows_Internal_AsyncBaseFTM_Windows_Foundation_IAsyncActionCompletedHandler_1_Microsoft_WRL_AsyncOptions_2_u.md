# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncOptions<2,&ushort const near * const CoreWebViewComponentCallbackOnEngagementStateChangeOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180049450`
- end: `0x18004955a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncOptions@$01$1?CoreWebViewComponentCallbackOnEngagementStateChangeOpName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180049450`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800494ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800494ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800494df`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800494df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004951c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049525`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004951c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049525`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800494bd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800494bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180049512`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180049512`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004948a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004948a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncOptions<2,&unsigned short const near * const CoreWebViewComponentCallbackOnEngagementStateChangeOpName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180049450  mov     [rsp-8+arg_0], rbx
0x180049455  push    rbp
0x180049456  mov     rbp, rsp
0x180049459  sub     rsp, 50h
0x18004945d  mov     [rbp+var_18], 0
0x180049465  mov     [rbp+var_8], 0
0x18004946d  lea     rax, [rbp+var_18]
0x180049471  mov     [rsp+50h+ppv], rax; ppv
0x180049476  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18004947d  xor     edx, edx; pUnkOuter
0x18004947f  lea     r8d, [rdx+1]; dwClsContext
0x180049483  lea     rcx, CLSID_GlobalOptions; rclsid
0x18004948a  call    cs:__imp_CoCreateInstance
0x180049490  test    eax, eax
0x180049492  js      short loc_1800494AD
0x180049494  mov     rcx, [rbp+var_18]
0x180049498  mov     rax, [rcx]
0x18004949b  lea     r8, [rbp+var_8]
0x18004949f  mov     edx, 4
0x1800494a4  mov     rax, [rax+20h]
0x1800494a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494ad  call    cs:__imp_GetCurrentProcessId
0x1800494b3  mov     r8d, eax; dwProcessId
0x1800494b6  xor     edx, edx; bInheritHandle
0x1800494b8  mov     ecx, 1000h; dwDesiredAccess
0x1800494bd  call    cs:__imp_OpenProcess
0x1800494c3  mov     rbx, rax
0x1800494c6  test    rax, rax
0x1800494c9  jz      short loc_18004952C
0x1800494cb  mov     [rbp+TokenHandle], 0
0x1800494d3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800494d7  mov     edx, 8; DesiredAccess
0x1800494dc  mov     rcx, rax; ProcessHandle
0x1800494df  call    cs:__imp_OpenProcessToken
0x1800494e5  test    eax, eax
0x1800494e7  jz      short loc_180049522
0x1800494e9  mov     [rbp+ReturnLength], 0
0x1800494f0  mov     [rbp+TokenInformation], 0
0x1800494f7  lea     rax, [rbp+ReturnLength]
0x1800494fb  mov     [rsp+50h+ppv], rax; ReturnLength
0x180049500  mov     r9d, 4; TokenInformationLength
0x180049506  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18004950a  lea     edx, [r9+19h]; TokenInformationClass
0x18004950e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180049512  call    cs:__imp_GetTokenInformation
0x180049518  mov     rcx, [rbp+TokenHandle]; hObject
0x18004951c  call    cs:__imp_CloseHandle
0x180049522  mov     rcx, rbx; hObject
0x180049525  call    cs:__imp_CloseHandle
0x18004952b  nop
0x18004952c  mov     rcx, [rbp+var_18]
0x180049530  test    rcx, rcx
0x180049533  jz      short loc_18004954A
0x180049535  mov     [rbp+var_18], 0
0x18004953d  mov     rdx, [rcx]
0x180049540  mov     rax, [rdx+10h]
0x180049544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049549  nop
0x18004954a  mov     eax, 1
0x18004954f  mov     rbx, [rsp+50h+arg_0]
0x180049554  add     rsp, 50h
0x180049558  pop     rbp
0x180049559  retn
```
