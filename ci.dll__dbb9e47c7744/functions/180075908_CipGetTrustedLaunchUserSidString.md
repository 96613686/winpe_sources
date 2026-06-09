# CipGetTrustedLaunchUserSidString

- ea: `0x180075908`
- end: `0x18007599f`
- name: `CipGetTrustedLaunchUserSidString`
- size: `151`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token, PUNICODE_STRING UnicodeString)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18008bc6c`

## callees

- `0x180075908`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180075932`
- `ntoskrnl!RtlInitUnicodeString` at `0x180075932`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075985`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075985`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x18007596b`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x18007596b`
- `ntoskrnl!SeQueryInformationToken` at `0x18007594b`
- `ntoskrnl!SeQueryInformationToken` at `0x18007594b`

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
0x180075908  mov     [rsp+arg_8], rbx
0x18007590d  push    rdi
0x18007590e  sub     rsp, 20h
0x180075912  mov     [rsp+28h+TokenInformation], 0
0x18007591b  mov     rdi, rdx
0x18007591e  mov     rbx, rcx
0x180075921  test    rcx, rcx
0x180075924  jnz     short loc_18007592D
0x180075926  mov     ebx, 0C000000Dh
0x18007592b  jmp     short loc_180075991
0x18007592d  xor     edx, edx; SourceString
0x18007592f  mov     rcx, rdi; DestinationString
0x180075932  call    cs:__imp_RtlInitUnicodeString
0x180075939  nop     dword ptr [rax+rax+00h]
0x18007593e  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x180075943  mov     edx, 1; TokenInformationClass
0x180075948  mov     rcx, rbx; Token
0x18007594b  call    cs:__imp_SeQueryInformationToken
0x180075952  nop     dword ptr [rax+rax+00h]
0x180075957  mov     ebx, eax
0x180075959  test    eax, eax
0x18007595b  js      short loc_180075979
0x18007595d  mov     rdx, [rsp+28h+TokenInformation]
0x180075962  mov     r8b, 1; AllocateDestinationString
0x180075965  mov     rcx, rdi; UnicodeString
0x180075968  mov     rdx, [rdx]; Sid
0x18007596b  call    cs:__imp_RtlConvertSidToUnicodeString
0x180075972  nop     dword ptr [rax+rax+00h]
0x180075977  mov     ebx, eax
0x180075979  mov     rcx, [rsp+28h+TokenInformation]; P
0x18007597e  test    rcx, rcx
0x180075981  jz      short loc_180075991
0x180075983  xor     edx, edx; Tag
0x180075985  call    cs:__imp_ExFreePoolWithTag
0x18007598c  nop     dword ptr [rax+rax+00h]
0x180075991  mov     eax, ebx
0x180075993  mov     rbx, [rsp+28h+arg_8]
0x180075998  add     rsp, 20h
0x18007599c  pop     rdi
0x18007599d  retn
```
