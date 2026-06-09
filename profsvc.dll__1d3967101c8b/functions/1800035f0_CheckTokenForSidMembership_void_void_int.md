# CheckTokenForSidMembership(void *,void *,int *)

- ea: `0x1800035f0`
- end: `0x1800036cf`
- name: `?CheckTokenForSidMembership@@YAJPEAX0PEAH@Z`
- size: `223`
- prototype: `__int64 __fastcall(void *, void *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003a54`

## callees

- `0x1800035f0`
- `0x18000a9b8`
- `0x18002db38`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036c7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000362a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000362a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000363f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000363f`

## string_xrefs

- `0x18000366a`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x1800036a6`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`

## pseudocode

```c
__int64 __fastcall CheckTokenForSidMembership(void *a1, void *a2, int *a3)
{
  const char *v5; // r9
  const char *v6; // r9
  unsigned int v8; // ebx
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  TokenHandle = 0;
  if ( DuplicateTokenEx(a1, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
  {
    if ( CheckTokenMembership(TokenHandle, a2, a3) )
    {
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x5F,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
                    v6);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return LastError;
    }
  }
  else
  {
    v8 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x5A,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
           v5);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v8;
  }
}

```

## disassembly

```asm
0x1800035f0  mov     [rsp+arg_0], rbx
0x1800035f5  push    rdi
0x1800035f6  sub     rsp, 30h
0x1800035fa  xor     eax, eax
0x1800035fc  mov     rbx, r8
0x1800035ff  mov     [r8], eax
0x180003602  mov     rdi, rdx
0x180003605  mov     [rsp+38h+TokenHandle], rax
0x18000360a  mov     r9d, 2; ImpersonationLevel
0x180003610  lea     rax, [rsp+38h+TokenHandle]
0x180003615  xor     r8d, r8d; lpTokenAttributes
0x180003618  mov     [rsp+38h+phNewToken], rax; phNewToken
0x18000361d  mov     edx, 0Ch; dwDesiredAccess
0x180003622  mov     [rsp+38h+TokenType], 2; TokenType
0x18000362a  call    cs:__imp_DuplicateTokenEx
0x180003630  test    eax, eax
0x180003632  jz      short loc_180003665
0x180003634  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180003639  mov     r8, rbx; IsMember
0x18000363c  mov     rdx, rdi; SidToCheck
0x18000363f  call    cs:__imp_CheckTokenMembership
0x180003645  test    eax, eax
0x180003647  jz      short loc_1800036A1
0x180003649  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18000364e  lea     rax, [rcx-1]
0x180003652  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003656  jbe     short loc_1800036C7
0x180003658  xor     eax, eax
0x18000365a  mov     rbx, [rsp+38h+arg_0]
0x18000365f  add     rsp, 30h
0x180003663  pop     rdi
0x180003664  retn
0x180003665  mov     rcx, [rsp+38h]; this
0x18000366a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x180003671  mov     edx, 5Ah ; 'Z'; void *
0x180003676  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000367b  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180003680  mov     ebx, eax
0x180003682  lea     rdx, [rcx-1]
0x180003686  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000368a  jbe     short loc_180003699
0x18000368c  mov     eax, ebx
0x18000368e  mov     rbx, [rsp+38h+arg_0]
0x180003693  add     rsp, 30h
0x180003697  pop     rdi
0x180003698  retn
0x180003699  call    cs:__imp_CloseHandle
0x18000369f  jmp     short loc_18000368C
0x1800036a1  mov     rcx, [rsp+38h]; this
0x1800036a6  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800036ad  mov     edx, 5Fh ; '_'; void *
0x1800036b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800036b7  lea     rcx, [rsp+38h+TokenHandle]
0x1800036bc  mov     ebx, eax
0x1800036be  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800036c3  mov     eax, ebx
0x1800036c5  jmp     short loc_18000365A
0x1800036c7  call    cs:__imp_CloseHandle
0x1800036cd  jmp     short loc_180003658
```
