# CheckTokenForSidMembership(void *,void *,int *)

- ea: `0x180003650`
- end: `0x18000374c`
- name: `?CheckTokenForSidMembership@@YAJPEAX0PEAH@Z`
- size: `252`
- prototype: `int(void *, void *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003b44`

## callees

- `0x180003650`
- `0x1800084bc`
- `0x18002df48`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003707`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000373b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003707`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000373b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000368a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000368a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800036a5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800036a5`

## string_xrefs

- `0x1800036d7`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x18000371a`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`

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
0x180003650  mov     [rsp+arg_0], rbx
0x180003655  push    rdi
0x180003656  sub     rsp, 30h
0x18000365a  xor     eax, eax
0x18000365c  mov     rbx, r8
0x18000365f  mov     [r8], eax
0x180003662  mov     rdi, rdx
0x180003665  mov     [rsp+38h+TokenHandle], rax
0x18000366a  mov     r9d, 2; ImpersonationLevel
0x180003670  lea     rax, [rsp+38h+TokenHandle]
0x180003675  xor     r8d, r8d; lpTokenAttributes
0x180003678  mov     [rsp+38h+phNewToken], rax; phNewToken
0x18000367d  mov     edx, 0Ch; dwDesiredAccess
0x180003682  mov     [rsp+38h+TokenType], 2; TokenType
0x18000368a  call    cs:__imp_DuplicateTokenEx
0x180003691  nop     dword ptr [rax+rax+00h]
0x180003696  test    eax, eax
0x180003698  jz      short loc_1800036D2
0x18000369a  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18000369f  mov     r8, rbx; IsMember
0x1800036a2  mov     rdx, rdi; SidToCheck
0x1800036a5  call    cs:__imp_CheckTokenMembership
0x1800036ac  nop     dword ptr [rax+rax+00h]
0x1800036b1  test    eax, eax
0x1800036b3  jz      short loc_180003715
0x1800036b5  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800036ba  lea     rax, [rcx-1]
0x1800036be  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800036c2  jbe     short loc_18000373B
0x1800036c4  xor     eax, eax
0x1800036c6  mov     rbx, [rsp+38h+arg_0]
0x1800036cb  add     rsp, 30h
0x1800036cf  pop     rdi
0x1800036d0  retn
0x1800036d2  mov     rcx, [rsp+38h]; this
0x1800036d7  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800036de  mov     edx, 5Ah ; 'Z'; void *
0x1800036e3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800036e8  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800036ed  mov     ebx, eax
0x1800036ef  lea     rdx, [rcx-1]
0x1800036f3  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800036f7  jbe     short loc_180003707
0x1800036f9  mov     eax, ebx
0x1800036fb  mov     rbx, [rsp+38h+arg_0]
0x180003700  add     rsp, 30h
0x180003704  pop     rdi
0x180003705  retn
0x180003707  call    cs:__imp_CloseHandle
0x18000370e  nop     dword ptr [rax+rax+00h]
0x180003713  jmp     short loc_1800036F9
0x180003715  mov     rcx, [rsp+38h]; this
0x18000371a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x180003721  mov     edx, 5Fh ; '_'; void *
0x180003726  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000372b  lea     rcx, [rsp+38h+TokenHandle]
0x180003730  mov     ebx, eax
0x180003732  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180003737  mov     eax, ebx
0x180003739  jmp     short loc_1800036C6
0x18000373b  call    cs:__imp_CloseHandle
0x180003742  nop     dword ptr [rax+rax+00h]
0x180003747  jmp     loc_1800036C4
```
