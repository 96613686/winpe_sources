# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::CancelUpdateAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180026420`
- end: `0x18002652a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?CancelUpdateAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180026420`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800264af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800264af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002647d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002647d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800264e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800264e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002645a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002645a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002648d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002648d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::CancelUpdateAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180026420  mov     [rsp-8+arg_0], rbx
0x180026425  push    rbp
0x180026426  mov     rbp, rsp
0x180026429  sub     rsp, 50h
0x18002642d  mov     [rbp+var_18], 0
0x180026435  mov     [rbp+var_8], 0
0x18002643d  lea     rax, [rbp+var_18]
0x180026441  mov     [rsp+50h+ppv], rax; ppv
0x180026446  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18002644d  xor     edx, edx; pUnkOuter
0x18002644f  lea     r8d, [rdx+1]; dwClsContext
0x180026453  lea     rcx, CLSID_GlobalOptions; rclsid
0x18002645a  call    cs:__imp_CoCreateInstance
0x180026460  test    eax, eax
0x180026462  js      short loc_18002647D
0x180026464  mov     rcx, [rbp+var_18]
0x180026468  mov     rax, [rcx]
0x18002646b  lea     r8, [rbp+var_8]
0x18002646f  mov     edx, 4
0x180026474  mov     rax, [rax+20h]
0x180026478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002647d  call    cs:__imp_GetCurrentProcessId
0x180026483  mov     r8d, eax; dwProcessId
0x180026486  xor     edx, edx; bInheritHandle
0x180026488  mov     ecx, 1000h; dwDesiredAccess
0x18002648d  call    cs:__imp_OpenProcess
0x180026493  mov     rbx, rax
0x180026496  test    rax, rax
0x180026499  jz      short loc_1800264FC
0x18002649b  mov     [rbp+TokenHandle], 0
0x1800264a3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800264a7  mov     edx, 8; DesiredAccess
0x1800264ac  mov     rcx, rax; ProcessHandle
0x1800264af  call    cs:__imp_OpenProcessToken
0x1800264b5  test    eax, eax
0x1800264b7  jz      short loc_1800264F2
0x1800264b9  mov     [rbp+ReturnLength], 0
0x1800264c0  mov     [rbp+TokenInformation], 0
0x1800264c7  lea     rax, [rbp+ReturnLength]
0x1800264cb  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800264d0  mov     r9d, 4; TokenInformationLength
0x1800264d6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800264da  lea     edx, [r9+19h]; TokenInformationClass
0x1800264de  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800264e2  call    cs:__imp_GetTokenInformation
0x1800264e8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800264ec  call    cs:__imp_CloseHandle
0x1800264f2  mov     rcx, rbx; hObject
0x1800264f5  call    cs:__imp_CloseHandle
0x1800264fb  nop
0x1800264fc  mov     rcx, [rbp+var_18]
0x180026500  test    rcx, rcx
0x180026503  jz      short loc_18002651A
0x180026505  mov     [rbp+var_18], 0
0x18002650d  mov     rdx, [rcx]
0x180026510  mov     rax, [rdx+10h]
0x180026514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026519  nop
0x18002651a  mov     eax, 1
0x18002651f  mov     rbx, [rsp+50h+arg_0]
0x180026524  add     rsp, 50h
0x180026528  pop     rbp
0x180026529  retn
```
