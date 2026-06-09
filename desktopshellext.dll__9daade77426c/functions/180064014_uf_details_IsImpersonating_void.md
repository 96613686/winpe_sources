# uf::details::IsImpersonating(void)

- ea: `0x180064014`
- end: `0x1800640a3`
- name: `?IsImpersonating@details@uf@@YA_NXZ`
- size: `143`
- prototype: `bool __fastcall(uf::details *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800232a0`
- `0x180060ac4`
- `0x180060c14`
- `0x180066a9c`

## callees

- `0x18001a100`
- `0x18001a18c`
- `0x180064014`
- `0x18006b854`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064050`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006402f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006402f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064046`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064046`

## string_xrefs

- `0x180064070`: `shellcommon\internal\shell\inc\UndockedFlighting\Impersonation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall uf::details::IsImpersonating(uf::details *this)
{
  HANDLE CurrentThread; // rax
  const char *v2; // r9
  bool v4; // bl
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v4;
  }
  else
  {
    if ( GetLastError() != 1008 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x25,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Impersonation.h",
        v2);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x180064014  push    rbx
0x180064016  sub     rsp, 20h
0x18006401a  mov     [rsp+28h+TokenHandle], 0
0x180064023  xor     edx, edx
0x180064025  lea     rcx, [rsp+28h+TokenHandle]
0x18006402a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006402f  call    cs:__imp_GetCurrentThread
0x180064035  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18006403a  mov     edx, 8; DesiredAccess
0x18006403f  lea     r8d, [rdx-7]; OpenAsSelf
0x180064043  mov     rcx, rax; ThreadHandle
0x180064046  call    cs:__imp_OpenThreadToken
0x18006404c  test    eax, eax
0x18006404e  jnz     short loc_180064082
0x180064050  call    cs:__imp_GetLastError
0x180064056  cmp     eax, 3F0h
0x18006405b  jnz     short loc_18006406B
0x18006405d  lea     rcx, [rsp+28h+TokenHandle]
0x180064062  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180064067  xor     al, al
0x180064069  jmp     short loc_18006409D
0x18006406b  mov     rcx, [rsp+28h]; this
0x180064070  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180064077  mov     edx, 25h ; '%'; void *
0x18006407c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180064082  mov     rax, [rsp+28h+TokenHandle]
0x180064087  dec     rax
0x18006408a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006408e  setbe   bl
0x180064091  lea     rcx, [rsp+28h+TokenHandle]
0x180064096  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006409b  mov     al, bl
0x18006409d  add     rsp, 20h
0x1800640a1  pop     rbx
0x1800640a2  retn
```
