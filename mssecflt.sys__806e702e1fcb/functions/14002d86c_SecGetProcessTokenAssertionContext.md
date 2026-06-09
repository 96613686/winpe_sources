# SecGetProcessTokenAssertionContext

- ea: `0x14002d86c`
- end: `0x14002d9ae`
- name: `SecGetProcessTokenAssertionContext`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002d9b0`
- `0x140040a08`

## callees

- `0x140011650`
- `0x14002d86c`
- `0x14002e414`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x14002d8c2`
- `ntoskrnl!SeQueryInformationToken` at `0x14002d8f2`
- `ntoskrnl!SeQueryInformationToken` at `0x14002d91b`
- `ntoskrnl!SeQueryInformationToken` at `0x14002d8c2`
- `ntoskrnl!SeQueryInformationToken` at `0x14002d8f2`
- `ntoskrnl!SeQueryInformationToken` at `0x14002d91b`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14002d8a6`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14002d8a6`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14002d95b`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14002d95b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d945`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d97a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d945`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d97a`

## pseudocode

```c
__int64 __fastcall SecGetProcessTokenAssertionContext(struct _KPROCESS *a1, __int64 a2)
{
  PACCESS_TOKEN v3; // rsi
  NTSTATUS v4; // ebx
  PVOID v5; // rcx
  PVOID TokenInformation; // [rsp+20h] [rbp-28h] BYREF
  PVOID P; // [rsp+28h] [rbp-20h] BYREF
  PVOID v9; // [rsp+30h] [rbp-18h] BYREF

  TokenInformation = 0;
  LODWORD(v9) = 0;
  P = 0;
  v3 = PsReferencePrimaryToken(a1);
  v4 = SeQueryInformationToken(v3, TokenPrivileges, &TokenInformation);
  if ( v4 >= 0 )
  {
    _mm_lfence();
    SecTokenPrivilegesToSepTokenPrivileges(TokenInformation, a2 + 8);
    v4 = SeQueryInformationToken(v3, TokenIntegrityLevel, &v9);
    if ( v4 >= 0 )
    {
      _mm_lfence();
      *(_DWORD *)(a2 + 32) = (_DWORD)v9;
      v4 = SeQueryInformationToken(v3, TokenUser, &P);
      if ( v4 >= 0 )
      {
        *(_QWORD *)(a2 + 64) = P;
        *(_QWORD *)a2 = v3;
      }
    }
  }
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v4 < 0 )
  {
    _mm_lfence();
    PsDereferencePrimaryToken(v3);
    v5 = P;
    *(_QWORD *)a2 = 0;
    if ( v5 )
    {
      ExFreePoolWithTag(v5, 0);
      *(_QWORD *)(a2 + 64) = 0;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002d86c  mov     r11, rsp
0x14002d86f  mov     [r11+18h], rbx
0x14002d873  mov     [r11+20h], rsi
0x14002d877  push    rdi
0x14002d878  sub     rsp, 40h
0x14002d87c  mov     rax, cs:__security_cookie
0x14002d883  xor     rax, rsp
0x14002d886  mov     [rsp+48h+var_10], rax
0x14002d88b  mov     rdi, rdx
0x14002d88e  mov     qword ptr [r11-28h], 0
0x14002d896  mov     dword ptr [rsp+48h+var_18], 0
0x14002d89e  mov     qword ptr [r11-20h], 0
0x14002d8a6  call    cs:__imp_PsReferencePrimaryToken
0x14002d8ad  nop     dword ptr [rax+rax+00h]
0x14002d8b2  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14002d8b7  mov     edx, 3; TokenInformationClass
0x14002d8bc  mov     rcx, rax; Token
0x14002d8bf  mov     rsi, rax
0x14002d8c2  call    cs:__imp_SeQueryInformationToken
0x14002d8c9  nop     dword ptr [rax+rax+00h]
0x14002d8ce  mov     ebx, eax
0x14002d8d0  test    eax, eax
0x14002d8d2  js      short loc_14002D939
0x14002d8d4  lfence
0x14002d8d7  mov     rcx, [rsp+48h+TokenInformation]
0x14002d8dc  lea     rdx, [rdi+8]
0x14002d8e0  call    SecTokenPrivilegesToSepTokenPrivileges
0x14002d8e5  lea     r8, [rsp+48h+var_18]; TokenInformation
0x14002d8ea  mov     edx, 19h; TokenInformationClass
0x14002d8ef  mov     rcx, rsi; Token
0x14002d8f2  call    cs:__imp_SeQueryInformationToken
0x14002d8f9  nop     dword ptr [rax+rax+00h]
0x14002d8fe  mov     ebx, eax
0x14002d900  test    eax, eax
0x14002d902  js      short loc_14002D939
0x14002d904  lfence
0x14002d907  mov     eax, dword ptr [rsp+48h+var_18]
0x14002d90b  lea     r8, [rsp+48h+P]; TokenInformation
0x14002d910  mov     edx, 1; TokenInformationClass
0x14002d915  mov     [rdi+20h], eax
0x14002d918  mov     rcx, rsi; Token
0x14002d91b  call    cs:__imp_SeQueryInformationToken
0x14002d922  nop     dword ptr [rax+rax+00h]
0x14002d927  mov     ebx, eax
0x14002d929  test    eax, eax
0x14002d92b  js      short loc_14002D939
0x14002d92d  mov     rax, [rsp+48h+P]
0x14002d932  mov     [rdi+40h], rax
0x14002d936  mov     [rdi], rsi
0x14002d939  mov     rcx, [rsp+48h+TokenInformation]; P
0x14002d93e  test    rcx, rcx
0x14002d941  jz      short loc_14002D951
0x14002d943  xor     edx, edx; Tag
0x14002d945  call    cs:__imp_ExFreePoolWithTag
0x14002d94c  nop     dword ptr [rax+rax+00h]
0x14002d951  test    ebx, ebx
0x14002d953  jns     short loc_14002D98E
0x14002d955  lfence
0x14002d958  mov     rcx, rsi; PrimaryToken
0x14002d95b  call    cs:__imp_PsDereferencePrimaryToken
0x14002d962  nop     dword ptr [rax+rax+00h]
0x14002d967  mov     rcx, [rsp+48h+P]; P
0x14002d96c  mov     qword ptr [rdi], 0
0x14002d973  test    rcx, rcx
0x14002d976  jz      short loc_14002D98E
0x14002d978  xor     edx, edx; Tag
0x14002d97a  call    cs:__imp_ExFreePoolWithTag
0x14002d981  nop     dword ptr [rax+rax+00h]
0x14002d986  mov     qword ptr [rdi+40h], 0
0x14002d98e  mov     eax, ebx
0x14002d990  mov     rcx, [rsp+48h+var_10]
0x14002d995  xor     rcx, rsp; StackCookie
0x14002d998  call    __security_check_cookie
0x14002d99d  mov     rbx, [rsp+48h+arg_10]
0x14002d9a2  mov     rsi, [rsp+48h+arg_18]
0x14002d9a7  add     rsp, 40h
0x14002d9ab  pop     rdi
0x14002d9ac  retn
```
