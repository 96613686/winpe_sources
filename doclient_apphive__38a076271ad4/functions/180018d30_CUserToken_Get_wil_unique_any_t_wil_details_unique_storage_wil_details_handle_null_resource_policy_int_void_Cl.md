# CUserToken::Get(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x180018d30`
- end: `0x180018edc`
- name: `?Get@CUserToken@@QEAAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005ee0`
- `0x180006000`

## callees

- `0x180008450`
- `0x180008618`
- `0x18000a4e0`
- `0x180018d30`
- `0x180018ee4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018d61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018e22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018d61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018d69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018d69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e2a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180018dd4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180018dd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018ded`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018ded`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018e72`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180018d7f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180018d7f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018dbb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018dbb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180018e4e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180018e4e`

## string_xrefs

- `0x180018e93`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180018eba`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180018e5d`: `C:\__w\1\s\src\DeliveryOptimization\dll\UserToken.cpp`

## pseudocode

```c
__int64 __fastcall CUserToken::Get(__int64 a1, void **a2)
{
  void *v2; // rbp
  unsigned int v3; // edi
  DWORD LastError; // ebx
  unsigned int v7; // r8d
  const char *v8; // r9
  HANDLE v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // r8d
  const char *v12; // r9
  DWORD v13; // eax
  const char *v14; // r9
  void *v15; // rbp
  DWORD v16; // ebx
  const char *v17; // r9
  __int64 v19; // [rsp+38h] [rbp-40h] BYREF
  HANDLE hEvent; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = *a2;
  v3 = 0;
  if ( *a2 && v2 != (void *)-1LL )
  {
    LastError = GetLastError();
    CloseHandle(v2);
    SetLastError(LastError);
  }
  *a2 = 0;
  if ( _InterlockedCompareExchange8((volatile signed __int8 *)(a1 + 24), 0, 1) == 1 )
  {
    if ( !ResetEvent(*(HANDLE *)a1) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CC, v7, v8);
    v9 = *(HANDLE *)a1;
    if ( !*(_QWORD *)a1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xABC,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    v10 = *(_QWORD *)(a1 + 32);
    v19 = a1;
    hEvent = v9;
    COrderedTaskExecutor::QueueTask__CUserToken::_AsyncRefresh_::_2_::_lambda_1___(v10, &v19);
    if ( hEvent && !SetEvent(hEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9C7, v11, v12);
  }
  v13 = WaitForSingleObjectEx(*(HANDLE *)a1, 0x7D0u, 0);
  if ( v13 != 258 && v13 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xAD8,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v14);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 16));
  if ( ((*(_QWORD *)(a1 + 8) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v15 = *a2;
    if ( *a2 && v15 != (void *)-1LL )
    {
      v16 = GetLastError();
      CloseHandle(v15);
      SetLastError(v16);
    }
    *a2 = 0;
    if ( !DuplicateTokenEx(*(HANDLE *)(a1 + 8), 0xEu, 0, SecurityImpersonation, TokenImpersonation, a2) )
      v3 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x29,
             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\UserToken.cpp",
             v17);
  }
  else
  {
    v3 = -2147023728;
  }
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 16));
  return v3;
}

```

## disassembly

```asm
0x180018d30  mov     [rsp+arg_10], rbx
0x180018d35  push    rbp
0x180018d36  push    rsi
0x180018d37  push    rdi
0x180018d38  push    r14
0x180018d3a  push    r15
0x180018d3c  sub     rsp, 50h
0x180018d40  mov     rbp, [rdx]
0x180018d43  xor     edi, edi
0x180018d45  mov     r14, rdx
0x180018d48  mov     rsi, rcx
0x180018d4b  test    rbp, rbp
0x180018d4e  jz      short loc_180018D6F
0x180018d50  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180018d54  jz      short loc_180018D6F
0x180018d56  call    cs:__imp_GetLastError
0x180018d5c  mov     rcx, rbp; hObject
0x180018d5f  mov     ebx, eax
0x180018d61  call    cs:__imp_CloseHandle
0x180018d67  mov     ecx, ebx; dwErrCode
0x180018d69  call    cs:__imp_SetLastError
0x180018d6f  mov     [r14], rdi
0x180018d72  mov     al, 1
0x180018d74  lock cmpxchg [rsi+18h], dil
0x180018d7a  jnz     short loc_180018DC9
0x180018d7c  mov     rcx, [rsi]; hEvent
0x180018d7f  call    cs:__imp_ResetEvent
0x180018d85  test    eax, eax
0x180018d87  jz      loc_180018EA5
0x180018d8d  mov     rax, [rsi]
0x180018d90  test    rax, rax
0x180018d93  jz      loc_180018EB5
0x180018d99  mov     rcx, [rsi+20h]
0x180018d9d  lea     rdx, [rsp+78h+var_40]
0x180018da2  mov     [rsp+78h+var_40], rsi
0x180018da7  mov     [rsp+78h+hEvent], rax
0x180018dac  call    COrderedTaskExecutor__QueueTask__CUserToken___AsyncRefresh____2____lambda_1___
0x180018db1  mov     rcx, [rsp+78h+hEvent]; hEvent
0x180018db6  test    rcx, rcx
0x180018db9  jz      short loc_180018DC9
0x180018dbb  call    cs:__imp_SetEvent
0x180018dc1  test    eax, eax
0x180018dc3  jz      loc_180018ECC
0x180018dc9  mov     rcx, [rsi]; hHandle
0x180018dcc  xor     r8d, r8d; bAlertable
0x180018dcf  mov     edx, 7D0h; dwMilliseconds
0x180018dd4  call    cs:__imp_WaitForSingleObjectEx
0x180018dda  cmp     eax, 102h
0x180018ddf  jz      short loc_180018DE9
0x180018de1  test    eax, eax
0x180018de3  jnz     loc_180018E8E
0x180018de9  lea     rcx, [rsi+10h]; SRWLock
0x180018ded  call    cs:__imp_AcquireSRWLockShared
0x180018df3  mov     rax, [rsi+8]
0x180018df7  inc     rax
0x180018dfa  test    rax, 0FFFFFFFFFFFFFFFEh
0x180018e00  jnz     short loc_180018E09
0x180018e02  mov     edi, 80070490h
0x180018e07  jmp     short loc_180018E6E
0x180018e09  mov     rbp, [r14]
0x180018e0c  test    rbp, rbp
0x180018e0f  jz      short loc_180018E30
0x180018e11  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180018e15  jz      short loc_180018E30
0x180018e17  call    cs:__imp_GetLastError
0x180018e1d  mov     rcx, rbp; hObject
0x180018e20  mov     ebx, eax
0x180018e22  call    cs:__imp_CloseHandle
0x180018e28  mov     ecx, ebx; dwErrCode
0x180018e2a  call    cs:__imp_SetLastError
0x180018e30  mov     r9d, 2; ImpersonationLevel
0x180018e36  mov     [r14], rdi
0x180018e39  mov     rcx, [rsi+8]; hExistingToken
0x180018e3d  xor     r8d, r8d; lpTokenAttributes
0x180018e40  mov     [rsp+78h+phNewToken], r14; phNewToken
0x180018e45  mov     [rsp+78h+TokenType], r9d; TokenType
0x180018e4a  lea     edx, [r9+0Ch]; dwDesiredAccess
0x180018e4e  call    cs:__imp_DuplicateTokenEx
0x180018e54  test    eax, eax
0x180018e56  jnz     short loc_180018E6E
0x180018e58  mov     rcx, [rsp+78h]; this
0x180018e5d  lea     r8, aCW1SSrcDeliver_94; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180018e64  lea     edx, [rax+29h]; void *
0x180018e67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018e6c  mov     edi, eax
0x180018e6e  lea     rcx, [rsi+10h]; SRWLock
0x180018e72  call    cs:__imp_ReleaseSRWLockShared
0x180018e78  mov     rbx, [rsp+78h+arg_10]
0x180018e80  mov     eax, edi
0x180018e82  add     rsp, 50h
0x180018e86  pop     r15
0x180018e88  pop     r14
0x180018e8a  pop     rdi
0x180018e8b  pop     rsi
0x180018e8c  pop     rbp
0x180018e8d  retn
0x180018e8e  mov     rcx, [rsp+78h]; this
0x180018e93  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180018e9a  mov     edx, 0AD8h; void *
0x180018e9f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180018ea5  mov     rcx, [rsp+78h]; this
0x180018eaa  mov     edx, 9CCh; void *
0x180018eaf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018eb5  mov     rcx, [rsp+78h]; this
0x180018eba  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180018ec1  mov     edx, 0ABCh; void *
0x180018ec6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180018ecc  mov     rcx, [rsp+78h]; this
0x180018ed1  mov     edx, 9C7h; void *
0x180018ed6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
