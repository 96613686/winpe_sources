# GetUserSidForProcess(_EPROCESS *,void * *)

- ea: `0x18000ed64`
- end: `0x18000ee4e`
- name: `?GetUserSidForProcess@@YAJPEAU_EPROCESS@@PEAPEAX@Z`
- size: `234`
- prototype: `__int64 __fastcall(struct _EPROCESS *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180045030`
- `0x180045420`

## callees

- `0x18000aee8`
- `0x18000ed64`
- `0x18000ff20`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x18000edff`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x18000edff`
- `ntoskrnl!SeQueryInformationToken` at `0x18000edae`
- `ntoskrnl!SeQueryInformationToken` at `0x18000edae`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x18000edf1`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x18000edf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ee16`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ee34`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ee16`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ee34`

## pseudocode

```c
__int64 __fastcall GetUserSidForProcess(struct _EPROCESS *a1, void **a2)
{
  void *v2; // rbx
  NTSTATUS v4; // edi
  void *ImpersonationOrPrimaryToken; // rsi
  unsigned __int8 v7; // [rsp+50h] [rbp+30h] BYREF
  PVOID TokenInformation; // [rsp+60h] [rbp+40h] BYREF
  void *v9; // [rsp+68h] [rbp+48h] BYREF

  v2 = 0;
  TokenInformation = 0;
  v7 = 0;
  v9 = 0;
  if ( a1 )
  {
    ImpersonationOrPrimaryToken = GetImpersonationOrPrimaryToken(a1, &v7);
    v4 = SeQueryInformationToken(ImpersonationOrPrimaryToken, TokenUser, &TokenInformation);
    if ( v4 >= 0 )
    {
      v4 = DuplicateSid(*(PSID *)TokenInformation, &v9);
      if ( v4 < 0 )
        v2 = v9;
      else
        *a2 = v9;
    }
    if ( ImpersonationOrPrimaryToken )
    {
      if ( v7 )
        PsDereferenceImpersonationToken(ImpersonationOrPrimaryToken);
      else
        PsDereferencePrimaryToken(ImpersonationOrPrimaryToken);
    }
    if ( TokenInformation )
    {
      ExFreePoolWithTag(TokenInformation, 0);
      TokenInformation = 0;
    }
    if ( v2 )
      ExFreePoolWithTag(v2, 0);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ed64  push    rbp
0x18000ed66  push    rbx
0x18000ed67  push    rsi
0x18000ed68  push    rdi
0x18000ed69  push    r14
0x18000ed6b  mov     rbp, rsp
0x18000ed6e  sub     rsp, 20h
0x18000ed72  xor     ebx, ebx
0x18000ed74  mov     [rbp+TokenInformation], 0
0x18000ed7c  mov     [rbp+arg_0], 0
0x18000ed80  mov     r14, rdx
0x18000ed83  mov     [rbp+arg_18], rbx
0x18000ed87  test    rcx, rcx
0x18000ed8a  jnz     short loc_18000ED96
0x18000ed8c  mov     edi, 0C000000Dh
0x18000ed91  jmp     loc_18000EE40
0x18000ed96  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x18000ed9a  call    ?GetImpersonationOrPrimaryToken@@YAPEAXPEAU_EPROCESS@@PEAE@Z; GetImpersonationOrPrimaryToken(_EPROCESS *,uchar *)
0x18000ed9f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000eda3  mov     edx, 1; TokenInformationClass
0x18000eda8  mov     rcx, rax; Token
0x18000edab  mov     rsi, rax
0x18000edae  call    cs:__imp_SeQueryInformationToken
0x18000edb5  nop     dword ptr [rax+rax+00h]
0x18000edba  mov     edi, eax
0x18000edbc  test    eax, eax
0x18000edbe  js      short loc_18000EDE3
0x18000edc0  mov     rcx, [rbp+TokenInformation]
0x18000edc4  lea     rdx, [rbp+arg_18]; void **
0x18000edc8  mov     rcx, [rcx]; SourceSid
0x18000edcb  call    ?DuplicateSid@@YAJPEAXPEAPEAX@Z; DuplicateSid(void *,void * *)
0x18000edd0  mov     edi, eax
0x18000edd2  test    eax, eax
0x18000edd4  js      short loc_18000EDDF
0x18000edd6  mov     rax, [rbp+arg_18]
0x18000edda  mov     [r14], rax
0x18000eddd  jmp     short loc_18000EDE3
0x18000eddf  mov     rbx, [rbp+arg_18]
0x18000ede3  test    rsi, rsi
0x18000ede6  jz      short loc_18000EE0B
0x18000ede8  cmp     [rbp+arg_0], 0
0x18000edec  mov     rcx, rsi; PrimaryToken
0x18000edef  jz      short loc_18000EDFF
0x18000edf1  call    cs:__imp_PsDereferenceImpersonationToken
0x18000edf8  nop     dword ptr [rax+rax+00h]
0x18000edfd  jmp     short loc_18000EE0B
0x18000edff  call    cs:__imp_PsDereferencePrimaryToken
0x18000ee06  nop     dword ptr [rax+rax+00h]
0x18000ee0b  mov     rcx, [rbp+TokenInformation]; P
0x18000ee0f  test    rcx, rcx
0x18000ee12  jz      short loc_18000EE2A
0x18000ee14  xor     edx, edx; Tag
0x18000ee16  call    cs:__imp_ExFreePoolWithTag
0x18000ee1d  nop     dword ptr [rax+rax+00h]
0x18000ee22  mov     [rbp+TokenInformation], 0
0x18000ee2a  test    rbx, rbx
0x18000ee2d  jz      short loc_18000EE40
0x18000ee2f  xor     edx, edx; Tag
0x18000ee31  mov     rcx, rbx; P
0x18000ee34  call    cs:__imp_ExFreePoolWithTag
0x18000ee3b  nop     dword ptr [rax+rax+00h]
0x18000ee40  mov     eax, edi
0x18000ee42  add     rsp, 20h
0x18000ee46  pop     r14
0x18000ee48  pop     rdi
0x18000ee49  pop     rsi
0x18000ee4a  pop     rbx
0x18000ee4b  pop     rbp
0x18000ee4c  retn
```
