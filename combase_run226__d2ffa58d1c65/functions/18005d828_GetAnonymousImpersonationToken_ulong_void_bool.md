# GetAnonymousImpersonationToken(ulong,void * *,bool *)

- ea: `0x18005d828`
- end: `0x18005d8e5`
- name: `?GetAnonymousImpersonationToken@@YAJKPEAPEAXPEA_N@Z`
- size: `189`
- prototype: `HRESULT __fastcall(unsigned int anonymousImpersonationToken, void **impersonatedAnonymousToken, bool *access)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005d488`

## callees

- `0x18000712c`
- `0x18003cf8c`
- `0x18005d828`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005d848`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005d863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005d848`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005d863`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005d87a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005d87a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005d884`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005d8d2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005d884`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005d8d2`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x18005d851`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x18005d851`

## string_xrefs

- `0x18005d8a0`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18005d8bf`: `onecore\com\combase\dcomrem\security.cxx`

## pseudocode

```c
HRESULT __fastcall GetAnonymousImpersonationToken(
        unsigned int anonymousImpersonationToken,
        void **impersonatedAnonymousToken,
        bool *access)
{
  HANDLE CurrentThread; // rax
  HANDLE v6; // rax
  __int64 v7; // rcx
  HRESULT LastError; // ebx
  __int64 v10; // rcx
  void *retaddr; // [rsp+28h] [rbp+0h]

  *impersonatedAnonymousToken = 0;
  if ( access )
    *access = 0;
  CurrentThread = GetCurrentThread();
  if ( !ImpersonateAnonymousToken(CurrentThread) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, 0xB0Au, "onecore\\com\\combase\\dcomrem\\security.cxx");
  if ( access )
    *access = 1;
  v6 = GetCurrentThread();
  if ( OpenThreadToken(v6, 0x20008u, 1, impersonatedAnonymousToken) )
  {
    if ( !RevertToSelf() )
      MicrosoftTelemetryAssertTriggeredNoArgs(v7);
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  0xB12u,
                  "onecore\\com\\combase\\dcomrem\\security.cxx");
    if ( !RevertToSelf() )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10);
    return LastError;
  }
}

```

## disassembly

```asm
0x18005d828  mov     [rsp+arg_0], rbx
0x18005d82d  push    rdi
0x18005d82e  sub     rsp, 20h
0x18005d832  mov     qword ptr [anonymousImpersonationToken], 0
0x18005d839  mov     rbx, impersonatedAnonymousToken
0x18005d83c  mov     rdi, anonymousImpersonationToken
0x18005d83f  test    impersonatedAnonymousToken, impersonatedAnonymousToken
0x18005d842  jz      short loc_18005D848
0x18005d844  mov     byte ptr [impersonatedAnonymousToken], 0
0x18005d848  call    cs:__imp_GetCurrentThread
0x18005d84e  mov     rcx, rax; ThreadHandle
0x18005d851  call    cs:__imp_ImpersonateAnonymousToken
0x18005d857  test    eax, eax
0x18005d859  jz      short loc_18005D89B
0x18005d85b  test    rbx, rbx
0x18005d85e  jz      short loc_18005D863
0x18005d860  mov     byte ptr [rbx], 1
0x18005d863  call    cs:__imp_GetCurrentThread
0x18005d869  mov     r9, rdi; TokenHandle
0x18005d86c  mov     edx, 20008h; DesiredAccess
0x18005d871  mov     rcx, rax; ThreadHandle
0x18005d874  mov     r8d, 1; OpenAsSelf
0x18005d87a  call    cs:__imp_OpenThreadToken
0x18005d880  test    eax, eax
0x18005d882  jz      short loc_18005D8BA
0x18005d884  call    cs:__imp_RevertToSelf
0x18005d88a  test    eax, eax
0x18005d88c  jz      short loc_18005D8B3
0x18005d88e  xor     eax, eax
0x18005d890  mov     rbx, [rsp+28h+arg_0]
0x18005d895  add     rsp, 20h
0x18005d899  pop     rdi
0x18005d89a  retn
0x18005d89b  mov     rcx, [rsp+28h]; callerReturnAddress
0x18005d8a0  lea     impersonatedAnonymousToken, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18005d8a7  mov     edx, 0B0Ah; lineNumber
0x18005d8ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005d8b1  jmp     short loc_18005D890
0x18005d8b3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "RevertToSelf()")
0x18005d8b8  jmp     short loc_18005D88E
0x18005d8ba  mov     rcx, [rsp+28h]; callerReturnAddress
0x18005d8bf  lea     impersonatedAnonymousToken, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18005d8c6  mov     edx, 0B12h; lineNumber
0x18005d8cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005d8d0  mov     ebx, eax
0x18005d8d2  call    cs:__imp_RevertToSelf
0x18005d8d8  test    eax, eax
0x18005d8da  jnz     short loc_18005D8E1
0x18005d8dc  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "RevertToSelf()")
0x18005d8e1  mov     eax, ebx
0x18005d8e3  jmp     short loc_18005D890
```
