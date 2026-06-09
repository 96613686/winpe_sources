# GetMyOwnToken(void * *)

- ea: `0x180016f5c`
- end: `0x180017099`
- name: `?GetMyOwnToken@@YAJPEAPEAX@Z`
- size: `317`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017364`
- `0x1800179fc`

## callees

- `0x180016f5c`
- `0x180026da8`
- `0x18002aef0`
- `0x18002d2d8`
- `0x18002db38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017053`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001703c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001703c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016ffe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017083`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016ffe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017083`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180016f76`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180016f76`
- `ntdll!RtlAdjustPrivilege` at `0x180016fd9`
- `ntdll!RtlAdjustPrivilege` at `0x18001701b`
- `ntdll!RtlAdjustPrivilege` at `0x180016fd9`
- `ntdll!RtlAdjustPrivilege` at `0x18001701b`

## string_xrefs

- `0x180016f7c`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetMyOwnToken(PHANDLE TokenHandle)
{
  const char *v2; // r9
  int LastError; // eax
  char v4; // bl
  unsigned int v5; // edi
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  int v9; // eax
  HANDLE CurrentThread; // rax
  const char *v11; // r9
  unsigned int v12; // ebx
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v15; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int8 OldValue; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int8 v17; // [rsp+58h] [rbp+20h] BYREF

  v15 = 0;
  if ( ImpersonateSelf(SecurityImpersonation) )
  {
    v15 = 1;
    v4 = 1;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3D5,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
                  v2);
    v4 = 0;
    v5 = LastError;
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x404,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
        (const char *)(unsigned int)LastError,
        v13);
      return v5;
    }
  }
  OldValue = 0;
  v7 = RtlAdjustPrivilege(0x12u, 1u, 1u, &OldValue);
  if ( v7 < 0 )
  {
    v5 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x407,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
           (const char *)(unsigned int)v7,
           v13);
    if ( v4 )
      RevertToSelf();
    return v5;
  }
  v17 = 0;
  v8 = RtlAdjustPrivilege(0x11u, 1u, 1u, &v17);
  if ( v8 < 0 )
  {
    v9 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x40A,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
           (const char *)(unsigned int)v8,
           v13);
LABEL_13:
    v12 = v9;
    CAutoImpersonateSelf::ResetImpersonation((CAutoImpersonateSelf *)&v15);
    return v12;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, TokenHandle) )
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x40C,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
           v11);
    goto LABEL_13;
  }
  if ( v4 )
    RevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x180016f5c  mov     [rsp+arg_0], rbx
0x180016f61  push    rsi
0x180016f62  push    rdi
0x180016f63  push    r14; int
0x180016f65  sub     rsp, 20h
0x180016f69  mov     rsi, rcx
0x180016f6c  mov     [rsp+38h+arg_8], 0
0x180016f71  mov     ecx, 2; ImpersonationLevel
0x180016f76  call    cs:__imp_ImpersonateSelf
0x180016f7c  lea     r14, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016f83  test    eax, eax
0x180016f85  jnz     short loc_180016FBD
0x180016f87  mov     rcx, [rsp+38h]; this
0x180016f8c  mov     r8, r14; unsigned int
0x180016f8f  mov     edx, 3D5h; void *
0x180016f94  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016f99  xor     bl, bl
0x180016f9b  mov     edi, eax
0x180016f9d  test    eax, eax
0x180016f9f  jns     short loc_180016FC4
0x180016fa1  mov     rcx, [rsp+38h]; this
0x180016fa6  mov     r9d, eax; char *
0x180016fa9  mov     r8, r14; unsigned int
0x180016fac  mov     edx, 404h; void *
0x180016fb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016fb6  mov     eax, edi
0x180016fb8  jmp     loc_18001708B
0x180016fbd  mov     [rsp+38h+arg_8], 1
0x180016fc2  mov     bl, 1
0x180016fc4  mov     r8b, 1; ForThread
0x180016fc7  mov     [rsp+38h+OldValue], 0
0x180016fcc  mov     dl, r8b; NewValue
0x180016fcf  lea     r9, [rsp+38h+OldValue]; OldValue
0x180016fd4  mov     ecx, 12h; Privilege
0x180016fd9  call    cs:__imp_RtlAdjustPrivilege
0x180016fdf  test    eax, eax
0x180016fe1  jns     short loc_180017006
0x180016fe3  mov     rcx, [rsp+38h]; this
0x180016fe8  mov     r9d, eax; char *
0x180016feb  mov     r8, r14; unsigned int
0x180016fee  mov     edx, 407h; void *
0x180016ff3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180016ff8  mov     edi, eax
0x180016ffa  test    bl, bl
0x180016ffc  jz      short loc_180016FB6
0x180016ffe  call    cs:__imp_RevertToSelf
0x180017004  jmp     short loc_180016FB6
0x180017006  mov     r8b, 1; ForThread
0x180017009  mov     [rsp+38h+arg_18], 0
0x18001700e  mov     dl, r8b; NewValue
0x180017011  lea     r9, [rsp+38h+arg_18]; OldValue
0x180017016  mov     ecx, 11h; Privilege
0x18001701b  call    cs:__imp_RtlAdjustPrivilege
0x180017021  test    eax, eax
0x180017023  jns     short loc_18001703C
0x180017025  mov     rcx, [rsp+38h]; this
0x18001702a  mov     r9d, eax; char *
0x18001702d  mov     r8, r14; unsigned int
0x180017030  mov     edx, 40Ah; void *
0x180017035  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001703a  jmp     short loc_18001706F
0x18001703c  call    cs:__imp_GetCurrentThread
0x180017042  mov     r9, rsi; TokenHandle
0x180017045  mov     edx, 2000Ch; DesiredAccess
0x18001704a  mov     rcx, rax; ThreadHandle
0x18001704d  mov     r8d, 1; OpenAsSelf
0x180017053  call    cs:__imp_OpenThreadToken
0x180017059  test    eax, eax
0x18001705b  jnz     short loc_18001707F
0x18001705d  mov     rcx, [rsp+38h]; this
0x180017062  mov     r8, r14; unsigned int
0x180017065  mov     edx, 40Ch; void *
0x18001706a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001706f  lea     rcx, [rsp+38h+arg_8]; this
0x180017074  mov     ebx, eax
0x180017076  call    ?ResetImpersonation@CAutoImpersonateSelf@@AEAAXXZ; CAutoImpersonateSelf::ResetImpersonation(void)
0x18001707b  mov     eax, ebx
0x18001707d  jmp     short loc_18001708B
0x18001707f  test    bl, bl
0x180017081  jz      short loc_180017089
0x180017083  call    cs:__imp_RevertToSelf
0x180017089  xor     eax, eax
0x18001708b  mov     rbx, [rsp+38h+arg_0]
0x180017090  add     rsp, 20h
0x180017094  pop     r14
0x180017096  pop     rdi
0x180017097  pop     rsi
0x180017098  retn
```
