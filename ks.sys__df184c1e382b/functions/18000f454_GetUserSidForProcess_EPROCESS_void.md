# GetUserSidForProcess(_EPROCESS *,void * *)

- ea: `0x18000f454`
- end: `0x18000f53e`
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
- `0x18000f454`
- `0x18000ff34`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x18000f4ef`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x18000f4ef`
- `ntoskrnl!SeQueryInformationToken` at `0x18000f49e`
- `ntoskrnl!SeQueryInformationToken` at `0x18000f49e`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x18000f4e1`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x18000f4e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f506`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f524`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f506`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f524`

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
0x18000f454  push    rbp
0x18000f456  push    rbx
0x18000f457  push    rsi
0x18000f458  push    rdi
0x18000f459  push    r14
0x18000f45b  mov     rbp, rsp
0x18000f45e  sub     rsp, 20h
0x18000f462  xor     ebx, ebx
0x18000f464  mov     [rbp+TokenInformation], 0
0x18000f46c  mov     [rbp+arg_0], 0
0x18000f470  mov     r14, rdx
0x18000f473  mov     [rbp+arg_18], rbx
0x18000f477  test    rcx, rcx
0x18000f47a  jnz     short loc_18000F486
0x18000f47c  mov     edi, 0C000000Dh
0x18000f481  jmp     loc_18000F530
0x18000f486  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x18000f48a  call    ?GetImpersonationOrPrimaryToken@@YAPEAXPEAU_EPROCESS@@PEAE@Z; GetImpersonationOrPrimaryToken(_EPROCESS *,uchar *)
0x18000f48f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000f493  mov     edx, 1; TokenInformationClass
0x18000f498  mov     rcx, rax; Token
0x18000f49b  mov     rsi, rax
0x18000f49e  call    cs:__imp_SeQueryInformationToken
0x18000f4a5  nop     dword ptr [rax+rax+00h]
0x18000f4aa  mov     edi, eax
0x18000f4ac  test    eax, eax
0x18000f4ae  js      short loc_18000F4D3
0x18000f4b0  mov     rcx, [rbp+TokenInformation]
0x18000f4b4  lea     rdx, [rbp+arg_18]; void **
0x18000f4b8  mov     rcx, [rcx]; SourceSid
0x18000f4bb  call    ?DuplicateSid@@YAJPEAXPEAPEAX@Z; DuplicateSid(void *,void * *)
0x18000f4c0  mov     edi, eax
0x18000f4c2  test    eax, eax
0x18000f4c4  js      short loc_18000F4CF
0x18000f4c6  mov     rax, [rbp+arg_18]
0x18000f4ca  mov     [r14], rax
0x18000f4cd  jmp     short loc_18000F4D3
0x18000f4cf  mov     rbx, [rbp+arg_18]
0x18000f4d3  test    rsi, rsi
0x18000f4d6  jz      short loc_18000F4FB
0x18000f4d8  cmp     [rbp+arg_0], 0
0x18000f4dc  mov     rcx, rsi; PrimaryToken
0x18000f4df  jz      short loc_18000F4EF
0x18000f4e1  call    cs:__imp_PsDereferenceImpersonationToken
0x18000f4e8  nop     dword ptr [rax+rax+00h]
0x18000f4ed  jmp     short loc_18000F4FB
0x18000f4ef  call    cs:__imp_PsDereferencePrimaryToken
0x18000f4f6  nop     dword ptr [rax+rax+00h]
0x18000f4fb  mov     rcx, [rbp+TokenInformation]; P
0x18000f4ff  test    rcx, rcx
0x18000f502  jz      short loc_18000F51A
0x18000f504  xor     edx, edx; Tag
0x18000f506  call    cs:__imp_ExFreePoolWithTag
0x18000f50d  nop     dword ptr [rax+rax+00h]
0x18000f512  mov     [rbp+TokenInformation], 0
0x18000f51a  test    rbx, rbx
0x18000f51d  jz      short loc_18000F530
0x18000f51f  xor     edx, edx; Tag
0x18000f521  mov     rcx, rbx; P
0x18000f524  call    cs:__imp_ExFreePoolWithTag
0x18000f52b  nop     dword ptr [rax+rax+00h]
0x18000f530  mov     eax, edi
0x18000f532  add     rsp, 20h
0x18000f536  pop     r14
0x18000f538  pop     rdi
0x18000f539  pop     rsi
0x18000f53a  pop     rbx
0x18000f53b  pop     rbp
0x18000f53c  retn
```
