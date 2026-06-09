# PrincipalHasWriteAccess

- ea: `0x14000aaf4`
- end: `0x14000abb8`
- name: `PrincipalHasWriteAccess`
- size: `196`
- prototype: `__int64 __fastcall(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009a08`

## callees

- `0x14000aaf4`

## import_xrefs

- `AUTHZ!AuthzAccessCheck` at `0x14000ab83`
- `AUTHZ!AuthzAccessCheck` at `0x14000ab83`

## pseudocode

```c
__int64 __fastcall PrincipalHasWriteAccess(
        AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  unsigned int v2; // ebx
  struct _AUTHZ_ACCESS_REPLY v4; // [rsp+58h] [rbp+7h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+78h] [rbp+27h] BYREF
  int v6; // [rsp+C8h] [rbp+77h] BYREF
  int v7; // [rsp+D0h] [rbp+7Fh] BYREF

  v2 = 0;
  *(_QWORD *)&pRequest.DesiredAccess = 0x2000000;
  v4.GrantedAccessMask = (PACCESS_MASK)&v6;
  v4.Error = (PDWORD)&v7;
  *(_QWORD *)&v4.ResultListLength = 1;
  v4.SaclEvaluationResults = 0;
  v6 = 0;
  v7 = 0;
  memset(&pRequest.PrincipalSelfSid, 0, 32);
  if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &v4, 0) )
    return (*v4.GrantedAccessMask & 0x500D0000) != 0;
  return v2;
}

```

## disassembly

```asm
0x14000aaf4  mov     r11, rsp
0x14000aaf7  mov     [r11+8], rbx
0x14000aafb  mov     [r11+10h], rsi
0x14000aaff  mov     [r11+18h], r8d
0x14000ab03  push    rbp
0x14000ab04  lea     rbp, [r11-5Fh]
0x14000ab08  sub     rsp, 0A0h
0x14000ab0f  xor     ebx, ebx
0x14000ab11  mov     qword ptr [rbp+57h+pRequest.DesiredAccess], 2000000h
0x14000ab19  mov     [r11-68h], rbx
0x14000ab1d  lea     rax, [rbp+57h+arg_10]
0x14000ab21  mov     [rbp+57h+var_48], rax
0x14000ab25  lea     r8, [rbp+57h+pRequest]; pRequest
0x14000ab29  lea     rax, [rbp+57h+arg_18]
0x14000ab2d  mov     qword ptr [rbp+57h+pRequest.ObjectTypeListLength], 0
0x14000ab35  mov     [rbp+57h+var_38], rax
0x14000ab39  lea     esi, [rbx+1]
0x14000ab3c  lea     rax, [rbp+57h+var_50]
0x14000ab40  mov     [rbp+57h+var_50], 1
0x14000ab48  mov     [r11-70h], rax
0x14000ab4c  xorps   xmm0, xmm0
0x14000ab4f  mov     [rsp+0A0h+OptionalSecurityDescriptorCount], ebx; OptionalSecurityDescriptorCount
0x14000ab53  xor     r9d, r9d; hAuditEvent
0x14000ab56  mov     [r11-80h], rbx
0x14000ab5a  mov     [rsp+0A0h+pSecurityDescriptor], rdx; pSecurityDescriptor
0x14000ab5f  mov     rdx, rcx; hAuthzClientContext
0x14000ab62  xor     ecx, ecx; Flags
0x14000ab64  mov     [rbp+57h+var_40], 0
0x14000ab6c  mov     [rbp+57h+arg_10], 0
0x14000ab73  mov     [rbp+57h+arg_18], 0
0x14000ab7a  movdqu  xmmword ptr [rbp+57h+pRequest.PrincipalSelfSid], xmm0
0x14000ab7f  mov     [rbp+57h+pRequest.OptionalArguments], rbx
0x14000ab83  call    cs:__imp_AuthzAccessCheck
0x14000ab8a  nop     dword ptr [rax+rax+00h]
0x14000ab8f  test    eax, eax
0x14000ab91  jz      short loc_14000ABA0
0x14000ab93  mov     rcx, [rbp+57h+var_48]
0x14000ab97  test    dword ptr [rcx], 500D0000h
0x14000ab9d  cmovnz  ebx, esi
0x14000aba0  lea     r11, [rsp+0A0h+var_s0]
0x14000aba8  mov     eax, ebx
0x14000abaa  mov     rbx, [r11+10h]
0x14000abae  mov     rsi, [r11+18h]
0x14000abb2  mov     rsp, r11
0x14000abb5  pop     rbp
0x14000abb6  retn
```
