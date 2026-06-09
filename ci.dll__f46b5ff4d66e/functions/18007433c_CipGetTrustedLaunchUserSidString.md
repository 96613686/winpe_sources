# CipGetTrustedLaunchUserSidString

- ea: `0x18007433c`
- end: `0x1800743d3`
- name: `CipGetTrustedLaunchUserSidString`
- size: `151`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token, PUNICODE_STRING UnicodeString)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18008a63c`

## callees

- `0x18007433c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180074366`
- `ntoskrnl!RtlInitUnicodeString` at `0x180074366`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800743b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800743b9`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x18007439f`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x18007439f`
- `ntoskrnl!SeQueryInformationToken` at `0x18007437f`
- `ntoskrnl!SeQueryInformationToken` at `0x18007437f`

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
0x18007433c  mov     [rsp+arg_8], rbx
0x180074341  push    rdi
0x180074342  sub     rsp, 20h
0x180074346  mov     [rsp+28h+TokenInformation], 0
0x18007434f  mov     rdi, rdx
0x180074352  mov     rbx, rcx
0x180074355  test    rcx, rcx
0x180074358  jnz     short loc_180074361
0x18007435a  mov     ebx, 0C000000Dh
0x18007435f  jmp     short loc_1800743C5
0x180074361  xor     edx, edx; SourceString
0x180074363  mov     rcx, rdi; DestinationString
0x180074366  call    cs:__imp_RtlInitUnicodeString
0x18007436d  nop     dword ptr [rax+rax+00h]
0x180074372  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x180074377  mov     edx, 1; TokenInformationClass
0x18007437c  mov     rcx, rbx; Token
0x18007437f  call    cs:__imp_SeQueryInformationToken
0x180074386  nop     dword ptr [rax+rax+00h]
0x18007438b  mov     ebx, eax
0x18007438d  test    eax, eax
0x18007438f  js      short loc_1800743AD
0x180074391  mov     rdx, [rsp+28h+TokenInformation]
0x180074396  mov     r8b, 1; AllocateDestinationString
0x180074399  mov     rcx, rdi; UnicodeString
0x18007439c  mov     rdx, [rdx]; Sid
0x18007439f  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800743a6  nop     dword ptr [rax+rax+00h]
0x1800743ab  mov     ebx, eax
0x1800743ad  mov     rcx, [rsp+28h+TokenInformation]; P
0x1800743b2  test    rcx, rcx
0x1800743b5  jz      short loc_1800743C5
0x1800743b7  xor     edx, edx; Tag
0x1800743b9  call    cs:__imp_ExFreePoolWithTag
0x1800743c0  nop     dword ptr [rax+rax+00h]
0x1800743c5  mov     eax, ebx
0x1800743c7  mov     rbx, [rsp+28h+arg_8]
0x1800743cc  add     rsp, 20h
0x1800743d0  pop     rdi
0x1800743d1  retn
```
