# EEL_GetUserSidStringForToken

- ea: `0x14005a17c`
- end: `0x14005a1fc`
- name: `EEL_GetUserSidStringForToken`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140059fcc`

## callees

- `0x14000c230`
- `0x14005a17c`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14005a1d6`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14005a1d6`
- `ntoskrnl!ZwQueryInformationToken` at `0x14005a1bb`
- `ntoskrnl!ZwQueryInformationToken` at `0x14005a1bb`

## pseudocode

```c
int __fastcall EEL_GetUserSidStringForToken(void *a1, struct _UNICODE_STRING *a2)
{
  int result; // eax
  ULONG ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  ReturnLength[0] = 0;
  result = ZwQueryInformationToken(a1, TokenUser, TokenInformation, 0x54u, ReturnLength);
  if ( result >= 0 )
    return RtlConvertSidToUnicodeString(a2, TokenInformation[0], 1u);
  return result;
}

```

## disassembly

```asm
0x14005a17c  push    rbx
0x14005a17e  sub     rsp, 0B0h
0x14005a185  mov     rax, cs:__security_cookie
0x14005a18c  xor     rax, rsp
0x14005a18f  mov     [rsp+0B8h+var_18], rax
0x14005a197  mov     r9d, 54h ; 'T'; TokenInformationLength
0x14005a19d  mov     [rsp+0B8h+var_88], 0
0x14005a1a5  mov     rbx, rdx
0x14005a1a8  lea     rax, [rsp+0B8h+var_88]
0x14005a1ad  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x14005a1b2  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x14005a1b7  lea     edx, [r9-53h]; TokenInformationClass
0x14005a1bb  call    cs:__imp_ZwQueryInformationToken
0x14005a1c2  nop     dword ptr [rax+rax+00h]
0x14005a1c7  test    eax, eax
0x14005a1c9  js      short loc_14005A1E2
0x14005a1cb  mov     rdx, [rsp+0B8h+TokenInformation]; Sid
0x14005a1d0  mov     r8b, 1; AllocateDestinationString
0x14005a1d3  mov     rcx, rbx; UnicodeString
0x14005a1d6  call    cs:__imp_RtlConvertSidToUnicodeString
0x14005a1dd  nop     dword ptr [rax+rax+00h]
0x14005a1e2  mov     rcx, [rsp+0B8h+var_18]
0x14005a1ea  xor     rcx, rsp; StackCookie
0x14005a1ed  call    __security_check_cookie
0x14005a1f2  add     rsp, 0B0h
0x14005a1f9  pop     rbx
0x14005a1fa  retn
```
