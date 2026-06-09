# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x1800c1c64`
- end: `0x1800c1d18`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `180`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c1c10`

## callees

- `0x18005c5bc`
- `0x180065598`
- `0x180071a34`
- `0x1800c1c64`
- `0x1800c3440`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1cac`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c1cc5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c1cc5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c1ca2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c1ca2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c1c89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c1c89`

## string_xrefs

- `0x1800c1cd9`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(HANDLE Token, __int64 a2)
{
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // ebx
  void *v8; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, Token) )
    {
      v8 = TokenHandle;
      TokenHandle = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::reset(
        a2,
        v8);
      LastError = 0;
      goto LABEL_8;
    }
    v6 = 454;
  }
  else
  {
    v6 = 450;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v6,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                v5);
LABEL_8:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800c1c64  mov     [rsp+arg_0], rbx
0x1800c1c69  push    rdi
0x1800c1c6a  sub     rsp, 20h
0x1800c1c6e  mov     rbx, rdx
0x1800c1c71  mov     [rsp+28h+TokenHandle], 0
0x1800c1c7a  mov     rdi, rcx
0x1800c1c7d  xor     edx, edx
0x1800c1c7f  lea     rcx, [rsp+28h+TokenHandle]
0x1800c1c84  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c1c89  call    cs:__imp_GetCurrentThread
0x1800c1c8f  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800c1c94  mov     edx, 0F01FFh; DesiredAccess
0x1800c1c99  mov     rcx, rax; ThreadHandle
0x1800c1c9c  mov     r8d, 1; OpenAsSelf
0x1800c1ca2  call    cs:__imp_OpenThreadToken
0x1800c1ca8  test    eax, eax
0x1800c1caa  jnz     short loc_1800C1CC0
0x1800c1cac  call    cs:__imp_GetLastError
0x1800c1cb2  cmp     eax, 3F0h
0x1800c1cb7  jz      short loc_1800C1CC0
0x1800c1cb9  mov     edx, 1C2h
0x1800c1cbe  jmp     short loc_1800C1CD4
0x1800c1cc0  mov     rdx, rdi; Token
0x1800c1cc3  xor     ecx, ecx; Thread
0x1800c1cc5  call    cs:__imp_SetThreadToken
0x1800c1ccb  test    eax, eax
0x1800c1ccd  jnz     short loc_1800C1CE9
0x1800c1ccf  mov     edx, 1C6h; void *
0x1800c1cd4  mov     rcx, [rsp+28h]; this
0x1800c1cd9  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c1ce0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c1ce5  mov     ebx, eax
0x1800c1ce7  jmp     short loc_1800C1D01
0x1800c1ce9  mov     rdx, [rsp+28h+TokenHandle]
0x1800c1cee  mov     rcx, rbx
0x1800c1cf1  mov     [rsp+28h+TokenHandle], 0
0x1800c1cfa  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::reset(void *)
0x1800c1cff  xor     ebx, ebx
0x1800c1d01  lea     rcx, [rsp+28h+TokenHandle]
0x1800c1d06  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c1d0b  mov     eax, ebx
0x1800c1d0d  mov     rbx, [rsp+28h+arg_0]
0x1800c1d12  add     rsp, 20h
0x1800c1d16  pop     rdi
0x1800c1d17  retn
```
