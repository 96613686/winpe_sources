# CSystemAndUserDescriptor::CSystemAndUserDescriptor(void *,ulong,long *)

- ea: `0x180031504`
- end: `0x180031681`
- name: `??0CSystemAndUserDescriptor@@QEAA@PEAXKPEAJ@Z`
- size: `381`
- prototype: `CSystemAndUserDescriptor *__fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, HANDLE TokenHandle, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000a654`
- `0x18000e7e0`

## callees

- `0x180031504`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031657`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180031634`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180031634`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003154e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003159e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003154e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003159e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800315b3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800315c2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800315b3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800315c2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800315ee`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800315ee`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18003160a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180031626`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18003160a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180031626`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003164d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003164d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800315d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800315d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003156b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003156b`

## pseudocode

```c
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
  LengthSid = GetLengthSid(qword_180063748);
  v10 = GetLengthSid(**((PSID **)pSecurityDescriptor + 5)) + 24 + LengthSid;
  v11 = (struct _ACL *)LocalAlloc(0x40u, v10);
  *((_QWORD *)pSecurityDescriptor + 6) = v11;
  if ( !v11
    || (InitializeAcl(v11, v10, 2u),
        AddAccessAllowedAce(*((PACL *)pSecurityDescriptor + 6), 2u, 0x10000000u, qword_180063748),
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
0x180031504  mov     rax, rsp
0x180031507  mov     [rax+8], rbx
0x18003150b  mov     [rax+10h], rsi
0x18003150f  mov     [rax+18h], r8d
0x180031513  push    rdi
0x180031514  sub     rsp, 30h
0x180031518  mov     rbx, rdx
0x18003151b  mov     dword ptr [rax+18h], 0
0x180031522  mov     rsi, r9
0x180031525  mov     qword ptr [rcx+28h], 0
0x18003152d  xor     r9d, r9d; TokenInformationLength
0x180031530  mov     qword ptr [rcx+30h], 0
0x180031538  mov     rdi, rcx
0x18003153b  lea     rax, [rax+18h]
0x18003153f  xor     r8d, r8d; TokenInformation
0x180031542  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180031547  mov     rcx, rbx; TokenHandle
0x18003154a  lea     edx, [r9+1]; TokenInformationClass
0x18003154e  call    cs:__imp_GetTokenInformation
0x180031554  test    eax, eax
0x180031556  jnz     short loc_180031567
0x180031558  call    cs:__imp_GetLastError
0x18003155e  cmp     eax, 7Ah ; 'z'
0x180031561  jnz     loc_180031657
0x180031567  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x18003156b  call    cs:__imp_CoTaskMemAlloc
0x180031571  mov     [rdi+28h], rax
0x180031575  test    rax, rax
0x180031578  jnz     short loc_180031584
0x18003157a  mov     ebx, 8007000Eh
0x18003157f  jmp     loc_18003166C
0x180031584  mov     r9d, dword ptr [rsp+38h+cb]; TokenInformationLength
0x180031589  lea     rcx, [rsp+38h+cb]
0x18003158e  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180031593  mov     r8, rax; TokenInformation
0x180031596  mov     rcx, rbx; TokenHandle
0x180031599  mov     edx, 1; TokenInformationClass
0x18003159e  call    cs:__imp_GetTokenInformation
0x1800315a4  test    eax, eax
0x1800315a6  jz      loc_180031657
0x1800315ac  lea     rcx, qword_180063748; pSid
0x1800315b3  call    cs:__imp_GetLengthSid
0x1800315b9  mov     rcx, [rdi+28h]
0x1800315bd  mov     ebx, eax
0x1800315bf  mov     rcx, [rcx]; pSid
0x1800315c2  call    cs:__imp_GetLengthSid
0x1800315c8  add     eax, 18h
0x1800315cb  mov     ecx, 40h ; '@'; uFlags
0x1800315d0  add     ebx, eax
0x1800315d2  mov     edx, ebx; uBytes
0x1800315d4  call    cs:__imp_LocalAlloc
0x1800315da  mov     [rdi+30h], rax
0x1800315de  test    rax, rax
0x1800315e1  jz      short loc_180031657
0x1800315e3  mov     r8d, 2; dwAclRevision
0x1800315e9  mov     edx, ebx; nAclLength
0x1800315eb  mov     rcx, rax; pAcl
0x1800315ee  call    cs:__imp_InitializeAcl
0x1800315f4  mov     rcx, [rdi+30h]; pAcl
0x1800315f8  lea     r9, qword_180063748; pSid
0x1800315ff  mov     edx, 2; dwAceRevision
0x180031604  mov     r8d, 10000000h; AccessMask
0x18003160a  call    cs:__imp_AddAccessAllowedAce
0x180031610  mov     r9, [rdi+28h]
0x180031614  mov     edx, 2; dwAceRevision
0x180031619  mov     rcx, [rdi+30h]; pAcl
0x18003161d  mov     r8d, 0C0000000h; AccessMask
0x180031623  mov     r9, [r9]; pSid
0x180031626  call    cs:__imp_AddAccessAllowedAce
0x18003162c  mov     edx, 1; dwRevision
0x180031631  mov     rcx, rdi; pSecurityDescriptor
0x180031634  call    cs:__imp_InitializeSecurityDescriptor
0x18003163a  test    eax, eax
0x18003163c  jz      short loc_180031657
0x18003163e  mov     r8, [rdi+30h]; pDacl
0x180031642  xor     ebx, ebx
0x180031644  xor     r9d, r9d; bDaclDefaulted
0x180031647  mov     rcx, rdi; pSecurityDescriptor
0x18003164a  lea     edx, [rbx+1]; bDaclPresent
0x18003164d  call    cs:__imp_SetSecurityDescriptorDacl
0x180031653  test    eax, eax
0x180031655  jnz     short loc_18003166C
0x180031657  call    cs:__imp_GetLastError
0x18003165d  mov     ebx, eax
0x18003165f  test    eax, eax
0x180031661  jle     short loc_18003166C
0x180031663  movzx   ebx, ax
0x180031666  or      ebx, 80070000h
0x18003166c  mov     [rsi], ebx
0x18003166e  mov     rax, rdi
0x180031671  mov     rbx, [rsp+38h+arg_0]
0x180031676  mov     rsi, [rsp+38h+arg_8]
0x18003167b  add     rsp, 30h
0x18003167f  pop     rdi
0x180031680  retn
```
