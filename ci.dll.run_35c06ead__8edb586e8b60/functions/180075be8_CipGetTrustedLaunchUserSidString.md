# CipGetTrustedLaunchUserSidString

- ea: `0x180075be8`
- end: `0x180075c7f`
- name: `CipGetTrustedLaunchUserSidString`
- size: `151`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token, PUNICODE_STRING UnicodeString)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18009cb40`

## callees

- `0x180075be8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180075c12`
- `ntoskrnl!RtlInitUnicodeString` at `0x180075c12`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075c65`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075c65`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x180075c4b`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x180075c4b`
- `ntoskrnl!SeQueryInformationToken` at `0x180075c2b`
- `ntoskrnl!SeQueryInformationToken` at `0x180075c2b`

## pseudocode

```c
__int64 __fastcall CipGetTrustedLaunchUserSidString(PACCESS_TOKEN Token, PUNICODE_STRING UnicodeString)
{
  NTSTATUS v4; // ebx
  PVOID TokenInformation; // [rsp+30h] [rbp+8h] BYREF

  TokenInformation = 0;
  if ( Token )
  {
    RtlInitUnicodeString(UnicodeString, 0);
    v4 = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
    if ( v4 >= 0 )
      v4 = RtlConvertSidToUnicodeString(UnicodeString, *(PSID *)TokenInformation, 1u);
    if ( TokenInformation )
      ExFreePoolWithTag(TokenInformation, 0);
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
0x180075be8  mov     [rsp+arg_8], rbx
0x180075bed  push    rdi
0x180075bee  sub     rsp, 20h
0x180075bf2  mov     [rsp+28h+TokenInformation], 0
0x180075bfb  mov     rdi, rdx
0x180075bfe  mov     rbx, rcx
0x180075c01  test    rcx, rcx
0x180075c04  jnz     short loc_180075C0D
0x180075c06  mov     ebx, 0C000000Dh
0x180075c0b  jmp     short loc_180075C71
0x180075c0d  xor     edx, edx; SourceString
0x180075c0f  mov     rcx, rdi; DestinationString
0x180075c12  call    cs:__imp_RtlInitUnicodeString
0x180075c19  nop     dword ptr [rax+rax+00h]
0x180075c1e  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x180075c23  mov     edx, 1; TokenInformationClass
0x180075c28  mov     rcx, rbx; Token
0x180075c2b  call    cs:__imp_SeQueryInformationToken
0x180075c32  nop     dword ptr [rax+rax+00h]
0x180075c37  mov     ebx, eax
0x180075c39  test    eax, eax
0x180075c3b  js      short loc_180075C59
0x180075c3d  mov     rdx, [rsp+28h+TokenInformation]
0x180075c42  mov     r8b, 1; AllocateDestinationString
0x180075c45  mov     rcx, rdi; UnicodeString
0x180075c48  mov     rdx, [rdx]; Sid
0x180075c4b  call    cs:__imp_RtlConvertSidToUnicodeString
0x180075c52  nop     dword ptr [rax+rax+00h]
0x180075c57  mov     ebx, eax
0x180075c59  mov     rcx, [rsp+28h+TokenInformation]; P
0x180075c5e  test    rcx, rcx
0x180075c61  jz      short loc_180075C71
0x180075c63  xor     edx, edx; Tag
0x180075c65  call    cs:__imp_ExFreePoolWithTag
0x180075c6c  nop     dword ptr [rax+rax+00h]
0x180075c71  mov     eax, ebx
0x180075c73  mov     rbx, [rsp+28h+arg_8]
0x180075c78  add     rsp, 20h
0x180075c7c  pop     rdi
0x180075c7d  retn
```
