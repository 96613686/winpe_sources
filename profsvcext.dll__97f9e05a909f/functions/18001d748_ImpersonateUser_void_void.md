# ImpersonateUser(void *,void * *)

- ea: `0x18001d748`
- end: `0x18001d843`
- name: `?ImpersonateUser@@YAJPEAXPEAPEAX@Z`
- size: `251`
- prototype: `__int64 __fastcall(HANDLE hToken, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013aac`

## callees

- `0x18000547c`
- `0x180006a9c`
- `0x180011454`
- `0x18001a46c`
- `0x18001d748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d79b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d79b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d778`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d778`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d791`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d791`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001d7e8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001d7e8`

## string_xrefs

- `0x18001d7c4`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001d7f7`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ImpersonateUser(HANDLE hToken, void **a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *v8; // r9
  void *v9; // rax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 != -2147023888 && (v6 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        (const char *)v6,
        v10);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v6;
    }
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x2D,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
           v8);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v6;
  }
  v9 = TokenHandle;
  TokenHandle = 0;
  *a2 = v9;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18001d748  mov     rax, rsp
0x18001d74b  mov     [rax+8], rbx
0x18001d74f  mov     [rax+18h], rsi
0x18001d753  push    rdi; int
0x18001d754  sub     rsp, 20h
0x18001d758  mov     rdi, rdx
0x18001d75b  mov     rsi, rcx
0x18001d75e  mov     qword ptr [rdx], 0
0x18001d765  mov     qword ptr [rax+10h], 0
0x18001d76d  xor     edx, edx
0x18001d76f  lea     rcx, [rax+10h]
0x18001d773  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001d778  call    cs:__imp_GetCurrentThread
0x18001d77e  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001d783  mov     edx, 2000Ch; DesiredAccess
0x18001d788  mov     r8d, 1; OpenAsSelf
0x18001d78e  mov     rcx, rax; ThreadHandle
0x18001d791  call    cs:__imp_OpenThreadToken
0x18001d797  test    eax, eax
0x18001d799  jnz     short loc_18001D7E5
0x18001d79b  call    cs:__imp_GetLastError
0x18001d7a1  mov     ebx, eax
0x18001d7a3  test    eax, eax
0x18001d7a5  jle     short loc_18001D7B0
0x18001d7a7  movzx   ebx, ax
0x18001d7aa  or      ebx, 80070000h
0x18001d7b0  cmp     ebx, 800703F0h
0x18001d7b6  jz      short loc_18001D7E5
0x18001d7b8  test    ebx, ebx
0x18001d7ba  jns     short loc_18001D7E5
0x18001d7bc  mov     rcx, [rsp+28h]; this
0x18001d7c1  mov     r9d, ebx; char *
0x18001d7c4  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d7cb  mov     edx, 2Ah ; '*'; void *
0x18001d7d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d7d5  nop
0x18001d7d6  lea     rcx, [rsp+28h+TokenHandle]
0x18001d7db  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d7e0  nop
0x18001d7e1  mov     eax, ebx
0x18001d7e3  jmp     short loc_18001D833
0x18001d7e5  mov     rcx, rsi; hToken
0x18001d7e8  call    cs:__imp_ImpersonateLoggedOnUser
0x18001d7ee  test    eax, eax
0x18001d7f0  jnz     short loc_18001D815
0x18001d7f2  mov     rcx, [rsp+28h]; this
0x18001d7f7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d7fe  lea     edx, [rax+2Dh]; void *
0x18001d801  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d806  mov     ebx, eax
0x18001d808  lea     rcx, [rsp+28h+TokenHandle]
0x18001d80d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d812  nop
0x18001d813  jmp     short loc_18001D7E1
0x18001d815  mov     rax, [rsp+28h+TokenHandle]
0x18001d81a  mov     [rsp+28h+TokenHandle], 0
0x18001d823  mov     [rdi], rax
0x18001d826  lea     rcx, [rsp+28h+TokenHandle]
0x18001d82b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d830  nop
0x18001d831  xor     eax, eax
0x18001d833  mov     rbx, [rsp+28h+arg_0]
0x18001d838  mov     rsi, [rsp+28h+arg_10]
0x18001d83d  add     rsp, 20h
0x18001d841  pop     rdi
0x18001d842  retn
```
