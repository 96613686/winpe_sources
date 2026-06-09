# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x1800ae518`
- end: `0x1800ae62e`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `278`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ac75c`
- `0x1800c5d38`
- `0x1800cb564`
- `0x1800cd870`
- `0x1800cf144`

## callees

- `0x180008618`
- `0x180009ab4`
- `0x1800ae518`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae5df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae600`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae5df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae600`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ae546`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ae546`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ae580`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ae5cd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ae580`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ae5cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ae55d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ae55d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae5bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ae5e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ae5e8`

## string_xrefs

- `0x1800ae594`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(HANDLE Token, void **a2)
{
  unsigned int v2; // ebx
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  unsigned int LastError; // eax
  char *v9; // rcx
  void *v10; // rdi
  void *v11; // rbp
  DWORD v12; // r14d
  wil::details::in1diag3 *v13; // rcx
  void *TokenHandle; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v7 = 450;
LABEL_6:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wi"
                                "l\\token_helpers.h",
                  v6);
    v9 = (char *)TokenHandle;
    v2 = LastError;
    goto LABEL_13;
  }
  if ( !SetThreadToken(0, Token) )
  {
    v7 = 454;
    goto LABEL_6;
  }
  v10 = *a2;
  v9 = 0;
  v11 = TokenHandle;
  TokenHandle = 0;
  if ( v10 != (void *)-1LL )
  {
    v12 = GetLastError();
    if ( !SetThreadToken(0, v10) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
    if ( v10 )
      CloseHandle(v10);
    SetLastError(v12);
    v9 = (char *)TokenHandle;
  }
  *a2 = v11;
LABEL_13:
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  return v2;
}

```

## disassembly

```asm
0x1800ae518  mov     [rsp+arg_10], rbx
0x1800ae51d  mov     [rsp+arg_18], rbp
0x1800ae522  push    rsi
0x1800ae523  push    rdi
0x1800ae524  push    r14
0x1800ae526  sub     rsp, 30h
0x1800ae52a  mov     rax, cs:__security_cookie
0x1800ae531  xor     rax, rsp
0x1800ae534  mov     [rsp+48h+var_20], rax
0x1800ae539  xor     ebx, ebx
0x1800ae53b  mov     rsi, rdx
0x1800ae53e  mov     [rsp+48h+TokenHandle], rbx
0x1800ae543  mov     rdi, rcx
0x1800ae546  call    cs:__imp_GetCurrentThread
0x1800ae54c  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800ae551  mov     edx, 0F01FFh; DesiredAccess
0x1800ae556  mov     rcx, rax; ThreadHandle
0x1800ae559  lea     r8d, [rbx+1]; OpenAsSelf
0x1800ae55d  call    cs:__imp_OpenThreadToken
0x1800ae563  test    eax, eax
0x1800ae565  jnz     short loc_1800AE57B
0x1800ae567  call    cs:__imp_GetLastError
0x1800ae56d  cmp     eax, 3F0h
0x1800ae572  jz      short loc_1800AE57B
0x1800ae574  mov     edx, 1C2h
0x1800ae579  jmp     short loc_1800AE58F
0x1800ae57b  mov     rdx, rdi; Token
0x1800ae57e  xor     ecx, ecx; Thread
0x1800ae580  call    cs:__imp_SetThreadToken
0x1800ae586  test    eax, eax
0x1800ae588  jnz     short loc_1800AE5A9
0x1800ae58a  mov     edx, 1C6h; void *
0x1800ae58f  mov     rcx, [rsp+48h]; this
0x1800ae594  lea     r8, aCW1SPackagesMi_6; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800ae59b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ae5a0  mov     rcx, [rsp+48h+TokenHandle]
0x1800ae5a5  mov     ebx, eax
0x1800ae5a7  jmp     short loc_1800AE5F6
0x1800ae5a9  mov     rdi, [rsi]
0x1800ae5ac  mov     rcx, rbx
0x1800ae5af  mov     rbp, [rsp+48h+TokenHandle]
0x1800ae5b4  mov     [rsp+48h+TokenHandle], rbx
0x1800ae5b9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800ae5bd  jz      short loc_1800AE5F3
0x1800ae5bf  call    cs:__imp_GetLastError
0x1800ae5c5  mov     rdx, rdi; Token
0x1800ae5c8  xor     ecx, ecx; Thread
0x1800ae5ca  mov     r14d, eax
0x1800ae5cd  call    cs:__imp_SetThreadToken
0x1800ae5d3  test    eax, eax
0x1800ae5d5  jz      short loc_1800AE628
0x1800ae5d7  test    rdi, rdi
0x1800ae5da  jz      short loc_1800AE5E5
0x1800ae5dc  mov     rcx, rdi; hObject
0x1800ae5df  call    cs:__imp_CloseHandle
0x1800ae5e5  mov     ecx, r14d; dwErrCode
0x1800ae5e8  call    cs:__imp_SetLastError
0x1800ae5ee  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800ae5f3  mov     [rsi], rbp
0x1800ae5f6  lea     rax, [rcx-1]
0x1800ae5fa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ae5fe  ja      short loc_1800AE606
0x1800ae600  call    cs:__imp_CloseHandle
0x1800ae606  mov     eax, ebx
0x1800ae608  mov     rcx, [rsp+48h+var_20]
0x1800ae60d  xor     rcx, rsp; StackCookie
0x1800ae610  call    __security_check_cookie
0x1800ae615  mov     rbx, [rsp+48h+arg_10]
0x1800ae61a  mov     rbp, [rsp+48h+arg_18]
0x1800ae61f  add     rsp, 30h
0x1800ae623  pop     r14
0x1800ae625  pop     rdi
0x1800ae626  pop     rsi
0x1800ae627  retn
0x1800ae628  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
