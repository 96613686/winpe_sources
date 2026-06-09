# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::OobeDevicePairingInfo *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18007f980`
- end: `0x18007fa8a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVOobeDevicePairingInfo@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18007f980`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007f9dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007f9dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007fa0f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007fa0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007fa4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007fa55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007fa4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007fa55`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007fa42`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007fa42`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007f9ed`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007f9ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007f9ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007f9ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::OobeDevicePairingInfo *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x18007f980  mov     [rsp-8+arg_0], rbx
0x18007f985  push    rbp
0x18007f986  mov     rbp, rsp
0x18007f989  sub     rsp, 50h
0x18007f98d  mov     [rbp+var_18], 0
0x18007f995  mov     [rbp+var_8], 0
0x18007f99d  lea     rax, [rbp+var_18]
0x18007f9a1  mov     [rsp+50h+ppv], rax; ppv
0x18007f9a6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18007f9ad  xor     edx, edx; pUnkOuter
0x18007f9af  lea     r8d, [rdx+1]; dwClsContext
0x18007f9b3  lea     rcx, CLSID_GlobalOptions; rclsid
0x18007f9ba  call    cs:__imp_CoCreateInstance
0x18007f9c0  test    eax, eax
0x18007f9c2  js      short loc_18007F9DD
0x18007f9c4  mov     rcx, [rbp+var_18]
0x18007f9c8  mov     rax, [rcx]
0x18007f9cb  lea     r8, [rbp+var_8]
0x18007f9cf  mov     edx, 4
0x18007f9d4  mov     rax, [rax+20h]
0x18007f9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f9dd  call    cs:__imp_GetCurrentProcessId
0x18007f9e3  mov     r8d, eax; dwProcessId
0x18007f9e6  xor     edx, edx; bInheritHandle
0x18007f9e8  mov     ecx, 1000h; dwDesiredAccess
0x18007f9ed  call    cs:__imp_OpenProcess
0x18007f9f3  mov     rbx, rax
0x18007f9f6  test    rax, rax
0x18007f9f9  jz      short loc_18007FA5C
0x18007f9fb  mov     [rbp+TokenHandle], 0
0x18007fa03  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18007fa07  mov     edx, 8; DesiredAccess
0x18007fa0c  mov     rcx, rax; ProcessHandle
0x18007fa0f  call    cs:__imp_OpenProcessToken
0x18007fa15  test    eax, eax
0x18007fa17  jz      short loc_18007FA52
0x18007fa19  mov     [rbp+ReturnLength], 0
0x18007fa20  mov     [rbp+TokenInformation], 0
0x18007fa27  lea     rax, [rbp+ReturnLength]
0x18007fa2b  mov     [rsp+50h+ppv], rax; ReturnLength
0x18007fa30  mov     r9d, 4; TokenInformationLength
0x18007fa36  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18007fa3a  lea     edx, [r9+19h]; TokenInformationClass
0x18007fa3e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18007fa42  call    cs:__imp_GetTokenInformation
0x18007fa48  mov     rcx, [rbp+TokenHandle]; hObject
0x18007fa4c  call    cs:__imp_CloseHandle
0x18007fa52  mov     rcx, rbx; hObject
0x18007fa55  call    cs:__imp_CloseHandle
0x18007fa5b  nop
0x18007fa5c  mov     rcx, [rbp+var_18]
0x18007fa60  test    rcx, rcx
0x18007fa63  jz      short loc_18007FA7A
0x18007fa65  mov     [rbp+var_18], 0
0x18007fa6d  mov     rdx, [rcx]
0x18007fa70  mov     rax, [rdx+10h]
0x18007fa74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fa79  nop
0x18007fa7a  mov     eax, 1
0x18007fa7f  mov     rbx, [rsp+50h+arg_0]
0x18007fa84  add     rsp, 50h
0x18007fa88  pop     rbp
0x18007fa89  retn
```
