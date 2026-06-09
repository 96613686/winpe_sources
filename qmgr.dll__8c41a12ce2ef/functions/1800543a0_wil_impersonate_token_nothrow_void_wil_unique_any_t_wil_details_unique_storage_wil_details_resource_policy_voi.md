# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x1800543a0`
- end: `0x18005448f`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `239`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005aba0`
- `0x1800deb70`
- `0x1800dec30`
- `0x1800dedb0`
- `0x1800dee90`
- `0x1800def40`
- `0x1800df220`
- `0x1800ea4a8`
- `0x1800f5088`

## callees

- `0x180011760`
- `0x1800543a0`
- `0x180086674`
- `0x1800959c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800543b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800543b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800543d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800543d2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800543e1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800543e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005442e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005442e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054468`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005447a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005447a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054487`

## string_xrefs

- `0x18005444c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(HANDLE Token, void **a2)
{
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  char *v6; // rcx
  void *v7; // rbp
  void *v8; // rsi
  __int64 v10; // rdx
  unsigned int LastError; // ebx
  DWORD v12; // ebx
  void *v13; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v10 = 450;
LABEL_11:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v5);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return LastError;
  }
  if ( !SetThreadToken(0, Token) )
  {
    v10 = 454;
    goto LABEL_11;
  }
  v6 = 0;
  v7 = TokenHandle;
  v8 = *a2;
  TokenHandle = 0;
  if ( v8 != (void *)-1LL )
  {
    v12 = GetLastError();
    wil::details::RevertImpersonateToken(v8, v13);
    SetLastError(v12);
    v6 = (char *)TokenHandle;
  }
  *a2 = v7;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return 0;
}

```

## disassembly

```asm
0x1800543a0  mov     [rsp+arg_18], rbx
0x1800543a5  push    rdi
0x1800543a6  sub     rsp, 20h
0x1800543aa  mov     rdi, rdx
0x1800543ad  mov     [rsp+28h+TokenHandle], 0
0x1800543b6  mov     rbx, rcx
0x1800543b9  call    cs:__imp_GetCurrentThread
0x1800543bf  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800543c4  mov     edx, 0F01FFh; DesiredAccess
0x1800543c9  mov     rcx, rax; ThreadHandle
0x1800543cc  mov     r8d, 1; OpenAsSelf
0x1800543d2  call    cs:__imp_OpenThreadToken
0x1800543d8  test    eax, eax
0x1800543da  jz      short loc_18005442E
0x1800543dc  mov     rdx, rbx; Token
0x1800543df  xor     ecx, ecx; Thread
0x1800543e1  call    cs:__imp_SetThreadToken
0x1800543e7  test    eax, eax
0x1800543e9  jz      short loc_180054442
0x1800543eb  mov     [rsp+28h+arg_0], rbp
0x1800543f0  xor     ecx, ecx; hObject
0x1800543f2  mov     rbp, [rsp+28h+TokenHandle]
0x1800543f7  mov     [rsp+28h+arg_8], rsi
0x1800543fc  mov     rsi, [rdi]
0x1800543ff  mov     [rsp+28h+TokenHandle], rcx
0x180054404  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180054408  jnz     short loc_180054468
0x18005440a  mov     rsi, [rsp+28h+arg_8]
0x18005440f  lea     rax, [rcx-1]
0x180054413  mov     [rdi], rbp
0x180054416  mov     rbp, [rsp+28h+arg_0]
0x18005441b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005441f  jbe     short loc_180054487
0x180054421  xor     eax, eax
0x180054423  mov     rbx, [rsp+28h+arg_18]
0x180054428  add     rsp, 20h
0x18005442c  pop     rdi
0x18005442d  retn
0x18005442e  call    cs:__imp_GetLastError
0x180054434  cmp     eax, 3F0h
0x180054439  jz      short loc_1800543DC
0x18005443b  mov     edx, 1C2h
0x180054440  jmp     short loc_180054447
0x180054442  mov     edx, 1C6h; void *
0x180054447  mov     rcx, [rsp+28h]; this
0x18005444c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180054453  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180054458  lea     rcx, [rsp+28h+TokenHandle]
0x18005445d  mov     ebx, eax
0x18005445f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180054464  mov     eax, ebx
0x180054466  jmp     short loc_180054423
0x180054468  call    cs:__imp_GetLastError
0x18005446e  mov     rcx, rsi; Token
0x180054471  mov     ebx, eax
0x180054473  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180054478  mov     ecx, ebx; dwErrCode
0x18005447a  call    cs:__imp_SetLastError
0x180054480  mov     rcx, [rsp+28h+TokenHandle]
0x180054485  jmp     short loc_18005440A
0x180054487  call    cs:__imp_CloseHandle
0x18005448d  jmp     short loc_180054421
```
