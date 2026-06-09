# CSystemAndUserDescriptor::CSystemAndUserDescriptor(void *,ulong,long *)

- ea: `0x180017d10`
- end: `0x180017e8d`
- name: `??0CSystemAndUserDescriptor@@QEAA@PEAXKPEAJ@Z`
- size: `381`
- prototype: `CSystemAndUserDescriptor *__fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, HANDLE TokenHandle, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007604`
- `0x180009f84`

## callees

- `0x180017d10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e63`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180017e59`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180017e59`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017d5a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017daa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017d5a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017daa`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180017e16`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180017e32`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180017e16`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180017e32`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017dbf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017dce`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017dbf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017dce`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180017dfa`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180017dfa`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180017e40`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180017e40`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017de0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017de0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CSystemAndUserDescriptor *__fastcall CSystemAndUserDescriptor::CSystemAndUserDescriptor(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        HANDLE TokenHandle,
        __int64 a3,
        unsigned int *a4)
{
  void *v7; // rax
  unsigned int v8; // ebx
  DWORD LengthSid; // ebx
  DWORD v10; // ebx
  struct _ACL *v11; // rax
  signed int LastError; // eax
  SIZE_T cb; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(cb) = 0;
  *((_QWORD *)pSecurityDescriptor + 5) = 0;
  *((_QWORD *)pSecurityDescriptor + 6) = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&cb) && GetLastError() != 122 )
    goto LABEL_9;
  v7 = CoTaskMemAlloc((unsigned int)cb);
  *((_QWORD *)pSecurityDescriptor + 5) = v7;
  if ( !v7 )
  {
    v8 = -2147024882;
    goto LABEL_11;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v7, cb, (PDWORD)&cb) )
    goto LABEL_9;
  LengthSid = GetLengthSid(qword_1800626F0);
  v10 = GetLengthSid(**((PSID **)pSecurityDescriptor + 5)) + 24 + LengthSid;
  v11 = (struct _ACL *)LocalAlloc(0x40u, v10);
  *((_QWORD *)pSecurityDescriptor + 6) = v11;
  if ( !v11
    || (InitializeAcl(v11, v10, 2u),
        AddAccessAllowedAce(*((PACL *)pSecurityDescriptor + 6), 2u, 0x10000000u, qword_1800626F0),
        AddAccessAllowedAce(*((PACL *)pSecurityDescriptor + 6), 2u, 0xC0000000, **((PSID **)pSecurityDescriptor + 5)),
        !InitializeSecurityDescriptor(pSecurityDescriptor, 1u))
    || (v8 = 0, !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, *((PACL *)pSecurityDescriptor + 6), 0)) )
  {
LABEL_9:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_11:
  *a4 = v8;
  return (CSystemAndUserDescriptor *)pSecurityDescriptor;
}

```

## disassembly

```asm
0x180017d10  mov     rax, rsp
0x180017d13  mov     [rax+8], rbx
0x180017d17  mov     [rax+10h], rsi
0x180017d1b  mov     [rax+18h], r8d
0x180017d1f  push    rdi
0x180017d20  sub     rsp, 30h
0x180017d24  mov     rbx, rdx
0x180017d27  mov     dword ptr [rax+18h], 0
0x180017d2e  mov     rsi, r9
0x180017d31  mov     qword ptr [rcx+28h], 0
0x180017d39  xor     r9d, r9d; TokenInformationLength
0x180017d3c  mov     qword ptr [rcx+30h], 0
0x180017d44  mov     rdi, rcx
0x180017d47  lea     rax, [rax+18h]
0x180017d4b  xor     r8d, r8d; TokenInformation
0x180017d4e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180017d53  mov     rcx, rbx; TokenHandle
0x180017d56  lea     edx, [r9+1]; TokenInformationClass
0x180017d5a  call    cs:__imp_GetTokenInformation
0x180017d60  test    eax, eax
0x180017d62  jnz     short loc_180017D73
0x180017d64  call    cs:__imp_GetLastError
0x180017d6a  cmp     eax, 7Ah ; 'z'
0x180017d6d  jnz     loc_180017E63
0x180017d73  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x180017d77  call    cs:__imp_CoTaskMemAlloc
0x180017d7d  mov     [rdi+28h], rax
0x180017d81  test    rax, rax
0x180017d84  jnz     short loc_180017D90
0x180017d86  mov     ebx, 8007000Eh
0x180017d8b  jmp     loc_180017E78
0x180017d90  mov     r9d, dword ptr [rsp+38h+cb]; TokenInformationLength
0x180017d95  lea     rcx, [rsp+38h+cb]
0x180017d9a  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180017d9f  mov     r8, rax; TokenInformation
0x180017da2  mov     rcx, rbx; TokenHandle
0x180017da5  mov     edx, 1; TokenInformationClass
0x180017daa  call    cs:__imp_GetTokenInformation
0x180017db0  test    eax, eax
0x180017db2  jz      loc_180017E63
0x180017db8  lea     rcx, qword_1800626F0; pSid
0x180017dbf  call    cs:__imp_GetLengthSid
0x180017dc5  mov     rcx, [rdi+28h]
0x180017dc9  mov     ebx, eax
0x180017dcb  mov     rcx, [rcx]; pSid
0x180017dce  call    cs:__imp_GetLengthSid
0x180017dd4  add     eax, 18h
0x180017dd7  mov     ecx, 40h ; '@'; uFlags
0x180017ddc  add     ebx, eax
0x180017dde  mov     edx, ebx; uBytes
0x180017de0  call    cs:__imp_LocalAlloc
0x180017de6  mov     [rdi+30h], rax
0x180017dea  test    rax, rax
0x180017ded  jz      short loc_180017E63
0x180017def  mov     r8d, 2; dwAclRevision
0x180017df5  mov     edx, ebx; nAclLength
0x180017df7  mov     rcx, rax; pAcl
0x180017dfa  call    cs:__imp_InitializeAcl
0x180017e00  mov     rcx, [rdi+30h]; pAcl
0x180017e04  lea     r9, qword_1800626F0; pSid
0x180017e0b  mov     edx, 2; dwAceRevision
0x180017e10  mov     r8d, 10000000h; AccessMask
0x180017e16  call    cs:__imp_AddAccessAllowedAce
0x180017e1c  mov     r9, [rdi+28h]
0x180017e20  mov     edx, 2; dwAceRevision
0x180017e25  mov     rcx, [rdi+30h]; pAcl
0x180017e29  mov     r8d, 0C0000000h; AccessMask
0x180017e2f  mov     r9, [r9]; pSid
0x180017e32  call    cs:__imp_AddAccessAllowedAce
0x180017e38  mov     edx, 1; dwRevision
0x180017e3d  mov     rcx, rdi; pSecurityDescriptor
0x180017e40  call    cs:__imp_InitializeSecurityDescriptor
0x180017e46  test    eax, eax
0x180017e48  jz      short loc_180017E63
0x180017e4a  mov     r8, [rdi+30h]; pDacl
0x180017e4e  xor     ebx, ebx
0x180017e50  xor     r9d, r9d; bDaclDefaulted
0x180017e53  mov     rcx, rdi; pSecurityDescriptor
0x180017e56  lea     edx, [rbx+1]; bDaclPresent
0x180017e59  call    cs:__imp_SetSecurityDescriptorDacl
0x180017e5f  test    eax, eax
0x180017e61  jnz     short loc_180017E78
0x180017e63  call    cs:__imp_GetLastError
0x180017e69  mov     ebx, eax
0x180017e6b  test    eax, eax
0x180017e6d  jle     short loc_180017E78
0x180017e6f  movzx   ebx, ax
0x180017e72  or      ebx, 80070000h
0x180017e78  mov     [rsi], ebx
0x180017e7a  mov     rax, rdi
0x180017e7d  mov     rbx, [rsp+38h+arg_0]
0x180017e82  mov     rsi, [rsp+38h+arg_8]
0x180017e87  add     rsp, 30h
0x180017e8b  pop     rdi
0x180017e8c  retn
```
