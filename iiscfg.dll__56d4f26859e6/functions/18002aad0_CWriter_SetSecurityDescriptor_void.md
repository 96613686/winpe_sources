# CWriter::SetSecurityDescriptor(void)

- ea: `0x18002aad0`
- end: `0x18002ac8b`
- name: `?SetSecurityDescriptor@CWriter@@AEAAJXZ`
- size: `443`
- prototype: `__int64 __fastcall(CWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a458`

## callees

- `0x18002a664`
- `0x18002aad0`
- `0x18002e110`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18002ab02`
- `KERNEL32!LocalAlloc` at `0x18002abd0`
- `KERNEL32!LocalAlloc` at `0x18002ab02`
- `KERNEL32!LocalAlloc` at `0x18002abd0`
- `KERNEL32!GetLastError` at `0x18002ac4e`
- `KERNEL32!GetLastError` at `0x18002ac4e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002ab1e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002ab1e`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002ac44`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002ac44`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002ac0a`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002ac24`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002ac0a`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002ac24`
- `ADVAPI32!InitializeAcl` at `0x18002abeb`
- `ADVAPI32!InitializeAcl` at `0x18002abeb`
- `ADVAPI32!GetLengthSid` at `0x18002abb5`
- `ADVAPI32!GetLengthSid` at `0x18002abc0`
- `ADVAPI32!GetLengthSid` at `0x18002abb5`
- `ADVAPI32!GetLengthSid` at `0x18002abc0`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002ab5e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002aba1`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002ab5e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002aba1`

## pseudocode

```c
__int64 __fastcall CWriter::SetSecurityDescriptor(CWriter *this)
{
  HLOCAL v2; // rax
  PSID *v3; // r14
  PSID *v4; // r15
  PSID v5; // rdi
  DWORD LengthSid; // ebx
  DWORD v7; // ebx
  ACL *v8; // rax
  signed int v9; // ebx
  signed int LastError; // eax
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-48h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v2 = LocalAlloc(0x40u, 0x28u);
  *((_QWORD *)this + 8198) = v2;
  if ( !v2 )
    goto LABEL_10;
  if ( !InitializeSecurityDescriptor(v2, 1u) )
    goto LABEL_10;
  v3 = (PSID *)((char *)this + 65560);
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, (PSID *)this + 8195)
    || (v4 = (PSID *)((char *)this + 65568),
        !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, (PSID *)this + 8196))
    || (v5 = *v4,
        LengthSid = GetLengthSid(*v3),
        v7 = GetLengthSid(v5) + 28 + LengthSid,
        v8 = (ACL *)LocalAlloc(0x40u, v7),
        (*((_QWORD *)this + 8197) = v8) == 0)
    || !InitializeAcl(v8, v7, 2u)
    || !AddAccessAllowedAce(*((PACL *)this + 8197), 2u, 0x1F01FFu, *v3)
    || !AddAccessAllowedAce(*((PACL *)this + 8197), 2u, 0x1F01FFu, *v4)
    || (v9 = 0, !SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 8198), 1, *((PACL *)this + 8197), 0)) )
  {
LABEL_10:
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      CWriter::FreeSecurityRelatedMembers(this);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002aad0  push    rbx
0x18002aad2  push    rbp
0x18002aad3  push    rsi
0x18002aad4  push    rdi
0x18002aad5  push    r14
0x18002aad7  push    r15
0x18002aad9  sub     rsp, 78h
0x18002aadd  mov     rax, cs:__security_cookie
0x18002aae4  xor     rax, rsp
0x18002aae7  mov     [rsp+0A8h+var_40], rax
0x18002aaec  xor     ebp, ebp
0x18002aaee  mov     word ptr [rsp+0A8h+pIdentifierAuthority.Value+4], 500h
0x18002aaf5  mov     rsi, rcx
0x18002aaf8  mov     dword ptr [rsp+0A8h+pIdentifierAuthority.Value], ebp
0x18002aafc  lea     edx, [rbp+28h]; uBytes
0x18002aaff  lea     ecx, [rbp+40h]; uFlags
0x18002ab02  call    cs:__imp_LocalAlloc
0x18002ab08  mov     [rsi+10030h], rax
0x18002ab0f  test    rax, rax
0x18002ab12  jz      loc_18002AC4E
0x18002ab18  lea     edx, [rbp+1]; dwRevision
0x18002ab1b  mov     rcx, rax; pSecurityDescriptor
0x18002ab1e  call    cs:__imp_InitializeSecurityDescriptor
0x18002ab24  test    eax, eax
0x18002ab26  jz      loc_18002AC4E
0x18002ab2c  lea     r14, [rsi+10018h]
0x18002ab33  xor     r9d, r9d; nSubAuthority1
0x18002ab36  mov     [rsp+0A8h+pSid], r14; pSid
0x18002ab3b  lea     r8d, [rbp+12h]; nSubAuthority0
0x18002ab3f  mov     [rsp+0A8h+nSubAuthority7], ebp; nSubAuthority7
0x18002ab43  lea     rcx, [rsp+0A8h+pIdentifierAuthority]; pIdentifierAuthority
0x18002ab48  mov     [rsp+0A8h+nSubAuthority6], ebp; nSubAuthority6
0x18002ab4c  mov     dl, 1; nSubAuthorityCount
0x18002ab4e  mov     [rsp+0A8h+nSubAuthority5], ebp; nSubAuthority5
0x18002ab52  mov     [rsp+0A8h+nSubAuthority4], ebp; nSubAuthority4
0x18002ab56  mov     [rsp+0A8h+nSubAuthority3], ebp; nSubAuthority3
0x18002ab5a  mov     [rsp+0A8h+nSubAuthority2], ebp; nSubAuthority2
0x18002ab5e  call    cs:__imp_AllocateAndInitializeSid
0x18002ab64  test    eax, eax
0x18002ab66  jz      loc_18002AC4E
0x18002ab6c  lea     r15, [rsi+10020h]
0x18002ab73  mov     r9d, 220h; nSubAuthority1
0x18002ab79  mov     [rsp+0A8h+pSid], r15; pSid
0x18002ab7e  lea     r8d, [rbp+20h]; nSubAuthority0
0x18002ab82  mov     [rsp+0A8h+nSubAuthority7], ebp; nSubAuthority7
0x18002ab86  lea     rcx, [rsp+0A8h+pIdentifierAuthority]; pIdentifierAuthority
0x18002ab8b  mov     [rsp+0A8h+nSubAuthority6], ebp; nSubAuthority6
0x18002ab8f  mov     dl, 2; nSubAuthorityCount
0x18002ab91  mov     [rsp+0A8h+nSubAuthority5], ebp; nSubAuthority5
0x18002ab95  mov     [rsp+0A8h+nSubAuthority4], ebp; nSubAuthority4
0x18002ab99  mov     [rsp+0A8h+nSubAuthority3], ebp; nSubAuthority3
0x18002ab9d  mov     [rsp+0A8h+nSubAuthority2], ebp; nSubAuthority2
0x18002aba1  call    cs:__imp_AllocateAndInitializeSid
0x18002aba7  test    eax, eax
0x18002aba9  jz      loc_18002AC4E
0x18002abaf  mov     rcx, [r14]; pSid
0x18002abb2  mov     rdi, [r15]
0x18002abb5  call    cs:__imp_GetLengthSid
0x18002abbb  mov     rcx, rdi; pSid
0x18002abbe  mov     ebx, eax
0x18002abc0  call    cs:__imp_GetLengthSid
0x18002abc6  add     eax, 1Ch
0x18002abc9  lea     ecx, [rbp+40h]; uFlags
0x18002abcc  add     ebx, eax
0x18002abce  mov     edx, ebx; uBytes
0x18002abd0  call    cs:__imp_LocalAlloc
0x18002abd6  mov     [rsi+10028h], rax
0x18002abdd  test    rax, rax
0x18002abe0  jz      short loc_18002AC4E
0x18002abe2  lea     r8d, [rbp+2]; dwAclRevision
0x18002abe6  mov     edx, ebx; nAclLength
0x18002abe8  mov     rcx, rax; pAcl
0x18002abeb  call    cs:__imp_InitializeAcl
0x18002abf1  test    eax, eax
0x18002abf3  jz      short loc_18002AC4E
0x18002abf5  mov     r9, [r14]; pSid
0x18002abf8  lea     edx, [rbp+2]; dwAceRevision
0x18002abfb  mov     rcx, [rsi+10028h]; pAcl
0x18002ac02  mov     ebx, 1F01FFh
0x18002ac07  mov     r8d, ebx; AccessMask
0x18002ac0a  call    cs:__imp_AddAccessAllowedAce
0x18002ac10  test    eax, eax
0x18002ac12  jz      short loc_18002AC4E
0x18002ac14  mov     r9, [r15]; pSid
0x18002ac17  lea     edx, [rbp+2]; dwAceRevision
0x18002ac1a  mov     rcx, [rsi+10028h]; pAcl
0x18002ac21  mov     r8d, ebx; AccessMask
0x18002ac24  call    cs:__imp_AddAccessAllowedAce
0x18002ac2a  test    eax, eax
0x18002ac2c  jz      short loc_18002AC4E
0x18002ac2e  mov     r8, [rsi+10028h]; pDacl
0x18002ac35  lea     edx, [rbp+1]; bDaclPresent
0x18002ac38  mov     rcx, [rsi+10030h]; pSecurityDescriptor
0x18002ac3f  xor     r9d, r9d; bDaclDefaulted
0x18002ac42  mov     ebx, ebp
0x18002ac44  call    cs:__imp_SetSecurityDescriptorDacl
0x18002ac4a  test    eax, eax
0x18002ac4c  jnz     short loc_18002AC6F
0x18002ac4e  call    cs:__imp_GetLastError
0x18002ac54  mov     ebx, eax
0x18002ac56  test    eax, eax
0x18002ac58  jle     short loc_18002AC63
0x18002ac5a  movzx   ebx, ax
0x18002ac5d  or      ebx, 80070000h
0x18002ac63  test    ebx, ebx
0x18002ac65  jns     short loc_18002AC6F
0x18002ac67  mov     rcx, rsi; this
0x18002ac6a  call    ?FreeSecurityRelatedMembers@CWriter@@AEAAXXZ; CWriter::FreeSecurityRelatedMembers(void)
0x18002ac6f  mov     eax, ebx
0x18002ac71  mov     rcx, [rsp+0A8h+var_40]
0x18002ac76  xor     rcx, rsp; StackCookie
0x18002ac79  call    __security_check_cookie
0x18002ac7e  add     rsp, 78h
0x18002ac82  pop     r15
0x18002ac84  pop     r14
0x18002ac86  pop     rdi
0x18002ac87  pop     rsi
0x18002ac88  pop     rbp
0x18002ac89  pop     rbx
0x18002ac8a  retn
```
