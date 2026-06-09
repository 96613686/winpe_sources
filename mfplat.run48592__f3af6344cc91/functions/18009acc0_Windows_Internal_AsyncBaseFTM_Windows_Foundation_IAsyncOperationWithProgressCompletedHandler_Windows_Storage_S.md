# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18009acc0`
- end: `0x18009adc8`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `264`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18009acc0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009ad4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009ad4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009ad1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009ad1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ad8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ad95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ad8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ad95`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18009ad2d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18009ad2d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009acfa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009acfa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009ad82`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009ad82`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x18009acc0  mov     [rsp-8+arg_0], rbx
0x18009acc5  push    rbp
0x18009acc6  mov     rbp, rsp
0x18009acc9  sub     rsp, 50h
0x18009accd  xor     edx, edx; pUnkOuter
0x18009accf  mov     [rbp+var_18], 0
0x18009acd7  lea     rax, [rbp+var_18]
0x18009acdb  mov     [rbp+var_8], 0
0x18009ace3  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18009acea  mov     [rsp+50h+ppv], rax; ppv
0x18009acef  lea     rcx, CLSID_GlobalOptions; rclsid
0x18009acf6  lea     r8d, [rdx+1]; dwClsContext
0x18009acfa  call    cs:__imp_CoCreateInstance
0x18009ad00  test    eax, eax
0x18009ad02  js      short loc_18009AD1D
0x18009ad04  mov     rcx, [rbp+var_18]
0x18009ad08  lea     r8, [rbp+var_8]
0x18009ad0c  mov     edx, 4
0x18009ad11  mov     rax, [rcx]
0x18009ad14  mov     rax, [rax+20h]
0x18009ad18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad1d  call    cs:__imp_GetCurrentProcessId
0x18009ad23  xor     edx, edx; bInheritHandle
0x18009ad25  mov     ecx, 1000h; dwDesiredAccess
0x18009ad2a  mov     r8d, eax; dwProcessId
0x18009ad2d  call    cs:__imp_OpenProcess
0x18009ad33  mov     rbx, rax
0x18009ad36  test    rax, rax
0x18009ad39  jz      short loc_18009AD9B
0x18009ad3b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18009ad3f  mov     [rbp+TokenHandle], 0
0x18009ad47  mov     edx, 8; DesiredAccess
0x18009ad4c  mov     rcx, rax; ProcessHandle
0x18009ad4f  call    cs:__imp_OpenProcessToken
0x18009ad55  test    eax, eax
0x18009ad57  jz      short loc_18009AD92
0x18009ad59  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18009ad5d  lea     rax, [rbp+ReturnLength]
0x18009ad61  mov     r9d, 4; TokenInformationLength
0x18009ad67  mov     [rbp+ReturnLength], 0
0x18009ad6e  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18009ad72  mov     [rbp+TokenInformation], 0
0x18009ad79  mov     [rsp+50h+ppv], rax; ReturnLength
0x18009ad7e  lea     edx, [r9+19h]; TokenInformationClass
0x18009ad82  call    cs:__imp_GetTokenInformation
0x18009ad88  mov     rcx, [rbp+TokenHandle]; hObject
0x18009ad8c  call    cs:__imp_CloseHandle
0x18009ad92  mov     rcx, rbx; hObject
0x18009ad95  call    cs:__imp_CloseHandle
0x18009ad9b  mov     rcx, [rbp+var_18]
0x18009ad9f  test    rcx, rcx
0x18009ada2  jz      short loc_18009ADB8
0x18009ada4  mov     [rbp+var_18], 0
0x18009adac  mov     rdx, [rcx]
0x18009adaf  mov     rax, [rdx+10h]
0x18009adb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009adb8  mov     rbx, [rsp+50h+arg_0]
0x18009adbd  mov     eax, 1
0x18009adc2  add     rsp, 50h
0x18009adc6  pop     rbp
0x18009adc7  retn
```
