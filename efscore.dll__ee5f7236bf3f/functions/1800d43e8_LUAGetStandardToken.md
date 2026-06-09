# LUAGetStandardToken

- ea: `0x1800d43e8`
- end: `0x1800d4507`
- name: `LUAGetStandardToken`
- size: `287`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003e348`
- `0x1800ac870`

## callees

- `0x1800d43ac`
- `0x1800d43e8`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x1800d44d2`
- `ntdll!NtDuplicateToken` at `0x1800d44d2`
- `ntdll!NtQueryInformationToken` at `0x1800d4451`
- `ntdll!NtQueryInformationToken` at `0x1800d4483`
- `ntdll!NtQueryInformationToken` at `0x1800d44af`
- `ntdll!NtQueryInformationToken` at `0x1800d44f2`
- `ntdll!NtQueryInformationToken` at `0x1800d4451`
- `ntdll!NtQueryInformationToken` at `0x1800d4483`
- `ntdll!NtQueryInformationToken` at `0x1800d44af`
- `ntdll!NtQueryInformationToken` at `0x1800d44f2`

## pseudocode

```c
__int64 __fastcall LUAGetStandardToken(HANDLE TokenHandle, PHANDLE NewTokenHandle)
{
  NTSTATUS v5; // ecx
  TOKEN_TYPE TokenType; // [rsp+30h] [rbp-10h] BYREF
  void *v7; // [rsp+38h] [rbp-8h] BYREF
  ULONG ReturnLength; // [rsp+68h] [rbp+28h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+30h] BYREF
  int v10; // [rsp+78h] [rbp+38h] BYREF

  ReturnLength = 0;
  TokenType = 0;
  v10 = 0;
  TokenInformation = 0;
  v7 = 0;
  *NewTokenHandle = 0;
  if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    return 3221225474LL;
  v5 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v5 >= 0 )
  {
    if ( TokenInformation == 3 )
      goto LABEL_8;
    if ( TokenInformation != 1 )
    {
      v5 = NtQueryInformationToken(TokenHandle, TokenLinkedToken, &v7, 8u, &ReturnLength);
      if ( v5 >= 0 )
        *NewTokenHandle = v7;
      return (unsigned int)v5;
    }
    v5 = NtQueryInformationToken(TokenHandle, TokenElevation, &v10, 4u, &ReturnLength);
    if ( v5 >= 0 && !v10 )
    {
LABEL_8:
      v5 = NtQueryInformationToken(TokenHandle, TokenType, &TokenType, 4u, &ReturnLength);
      if ( v5 >= 0 )
        return (unsigned int)NtDuplicateToken(TokenHandle, 0, 0, 0, TokenType, NewTokenHandle);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800d43e8  push    rbp
0x1800d43ea  push    rbx
0x1800d43eb  push    rdi
0x1800d43ec  mov     rbp, rsp
0x1800d43ef  sub     rsp, 40h
0x1800d43f3  mov     rdi, rdx
0x1800d43f6  mov     [rbp+arg_8], 0
0x1800d43fd  mov     rbx, rcx
0x1800d4400  mov     [rbp+TokenType], 0
0x1800d4407  mov     [rbp+arg_18], 0
0x1800d440e  mov     [rbp+TokenInformation], 0
0x1800d4415  mov     [rbp+var_8], 0
0x1800d441d  mov     qword ptr [rdx], 0
0x1800d4424  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x1800d4429  test    eax, eax
0x1800d442b  jnz     short loc_1800D4437
0x1800d442d  mov     eax, 0C0000002h
0x1800d4432  jmp     loc_1800D44DC
0x1800d4437  mov     r9d, 4; TokenInformationLength
0x1800d443d  lea     rax, [rbp+arg_8]
0x1800d4441  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800d4445  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800d444a  mov     rcx, rbx; TokenHandle
0x1800d444d  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800d4451  call    cs:__imp_NtQueryInformationToken
0x1800d4457  mov     ecx, eax
0x1800d4459  test    eax, eax
0x1800d445b  js      short loc_1800D44DA
0x1800d445d  cmp     [rbp+TokenInformation], 3
0x1800d4461  jz      short loc_1800D4495
0x1800d4463  cmp     [rbp+TokenInformation], 1
0x1800d4467  lea     rax, [rbp+arg_8]
0x1800d446b  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800d4470  mov     rcx, rbx; TokenHandle
0x1800d4473  jnz     short loc_1800D44E4
0x1800d4475  mov     r9d, 4; TokenInformationLength
0x1800d447b  lea     r8, [rbp+arg_18]; TokenInformation
0x1800d447f  lea     edx, [r9+10h]; TokenInformationClass
0x1800d4483  call    cs:__imp_NtQueryInformationToken
0x1800d4489  mov     ecx, eax
0x1800d448b  test    eax, eax
0x1800d448d  js      short loc_1800D44DA
0x1800d448f  cmp     [rbp+arg_18], 0
0x1800d4493  jnz     short loc_1800D44DA
0x1800d4495  mov     r9d, 4; TokenInformationLength
0x1800d449b  lea     rax, [rbp+arg_8]
0x1800d449f  lea     r8, [rbp+TokenType]; TokenInformation
0x1800d44a3  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800d44a8  mov     rcx, rbx; TokenHandle
0x1800d44ab  lea     edx, [r9+4]; TokenInformationClass
0x1800d44af  call    cs:__imp_NtQueryInformationToken
0x1800d44b5  mov     ecx, eax
0x1800d44b7  test    eax, eax
0x1800d44b9  js      short loc_1800D44DA
0x1800d44bb  mov     eax, [rbp+TokenType]
0x1800d44be  xor     r9d, r9d; EffectiveOnly
0x1800d44c1  mov     [rsp+40h+NewTokenHandle], rdi; NewTokenHandle
0x1800d44c6  xor     r8d, r8d; ObjectAttributes
0x1800d44c9  xor     edx, edx; DesiredAccess
0x1800d44cb  mov     dword ptr [rsp+40h+ReturnLength], eax; TokenType
0x1800d44cf  mov     rcx, rbx; ExistingTokenHandle
0x1800d44d2  call    cs:__imp_NtDuplicateToken
0x1800d44d8  mov     ecx, eax
0x1800d44da  mov     eax, ecx
0x1800d44dc  add     rsp, 40h
0x1800d44e0  pop     rdi
0x1800d44e1  pop     rbx
0x1800d44e2  pop     rbp
0x1800d44e3  retn
0x1800d44e4  mov     r9d, 8; TokenInformationLength
0x1800d44ea  lea     r8, [rbp+var_8]; TokenInformation
0x1800d44ee  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800d44f2  call    cs:__imp_NtQueryInformationToken
0x1800d44f8  mov     ecx, eax
0x1800d44fa  test    eax, eax
0x1800d44fc  js      short loc_1800D44DA
0x1800d44fe  mov     rax, [rbp+var_8]
0x1800d4502  mov     [rdi], rax
0x1800d4505  jmp     short loc_1800D44DA
```
