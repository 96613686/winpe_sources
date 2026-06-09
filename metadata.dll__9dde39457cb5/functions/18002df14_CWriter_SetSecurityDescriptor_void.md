# CWriter::SetSecurityDescriptor(void)

- ea: `0x18002df14`
- end: `0x18002e0cf`
- name: `?SetSecurityDescriptor@CWriter@@AEAAJXZ`
- size: `443`
- prototype: `__int64 __fastcall(CWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d6d0`

## callees

- `0x18002d9cc`
- `0x18002df14`
- `0x1800309d0`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x18002e02f`
- `ADVAPI32!InitializeAcl` at `0x18002e02f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002dfa2`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002dfe5`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002dfa2`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002dfe5`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002e088`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002e088`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002df62`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002df62`
- `ADVAPI32!GetLengthSid` at `0x18002dff9`
- `ADVAPI32!GetLengthSid` at `0x18002e004`
- `ADVAPI32!GetLengthSid` at `0x18002dff9`
- `ADVAPI32!GetLengthSid` at `0x18002e004`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002e04e`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002e068`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002e04e`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002e068`
- `KERNEL32!LocalAlloc` at `0x18002df46`
- `KERNEL32!LocalAlloc` at `0x18002e014`
- `KERNEL32!LocalAlloc` at `0x18002df46`
- `KERNEL32!LocalAlloc` at `0x18002e014`
- `KERNEL32!GetLastError` at `0x18002e092`
- `KERNEL32!GetLastError` at `0x18002e092`

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
  struct _ACL *v8; // rax
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
        v8 = (struct _ACL *)LocalAlloc(0x40u, v7),
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
0x18002df14  push    rbx
0x18002df16  push    rbp
0x18002df17  push    rsi
0x18002df18  push    rdi
0x18002df19  push    r14
0x18002df1b  push    r15
0x18002df1d  sub     rsp, 78h
0x18002df21  mov     rax, cs:__security_cookie
0x18002df28  xor     rax, rsp
0x18002df2b  mov     [rsp+0A8h+var_40], rax
0x18002df30  xor     ebp, ebp
0x18002df32  mov     word ptr [rsp+0A8h+pIdentifierAuthority.Value+4], 500h
0x18002df39  mov     rsi, rcx
0x18002df3c  mov     dword ptr [rsp+0A8h+pIdentifierAuthority.Value], ebp
0x18002df40  lea     edx, [rbp+28h]; uBytes
0x18002df43  lea     ecx, [rbp+40h]; uFlags
0x18002df46  call    cs:__imp_LocalAlloc
0x18002df4c  mov     [rsi+10030h], rax
0x18002df53  test    rax, rax
0x18002df56  jz      loc_18002E092
0x18002df5c  lea     edx, [rbp+1]; dwRevision
0x18002df5f  mov     rcx, rax; pSecurityDescriptor
0x18002df62  call    cs:__imp_InitializeSecurityDescriptor
0x18002df68  test    eax, eax
0x18002df6a  jz      loc_18002E092
0x18002df70  lea     r14, [rsi+10018h]
0x18002df77  xor     r9d, r9d; nSubAuthority1
0x18002df7a  mov     [rsp+0A8h+pSid], r14; pSid
0x18002df7f  lea     r8d, [rbp+12h]; nSubAuthority0
0x18002df83  mov     [rsp+0A8h+nSubAuthority7], ebp; nSubAuthority7
0x18002df87  lea     rcx, [rsp+0A8h+pIdentifierAuthority]; pIdentifierAuthority
0x18002df8c  mov     [rsp+0A8h+nSubAuthority6], ebp; nSubAuthority6
0x18002df90  mov     dl, 1; nSubAuthorityCount
0x18002df92  mov     [rsp+0A8h+nSubAuthority5], ebp; nSubAuthority5
0x18002df96  mov     [rsp+0A8h+nSubAuthority4], ebp; nSubAuthority4
0x18002df9a  mov     [rsp+0A8h+nSubAuthority3], ebp; nSubAuthority3
0x18002df9e  mov     [rsp+0A8h+nSubAuthority2], ebp; nSubAuthority2
0x18002dfa2  call    cs:__imp_AllocateAndInitializeSid
0x18002dfa8  test    eax, eax
0x18002dfaa  jz      loc_18002E092
0x18002dfb0  lea     r15, [rsi+10020h]
0x18002dfb7  mov     r9d, 220h; nSubAuthority1
0x18002dfbd  mov     [rsp+0A8h+pSid], r15; pSid
0x18002dfc2  lea     r8d, [rbp+20h]; nSubAuthority0
0x18002dfc6  mov     [rsp+0A8h+nSubAuthority7], ebp; nSubAuthority7
0x18002dfca  lea     rcx, [rsp+0A8h+pIdentifierAuthority]; pIdentifierAuthority
0x18002dfcf  mov     [rsp+0A8h+nSubAuthority6], ebp; nSubAuthority6
0x18002dfd3  mov     dl, 2; nSubAuthorityCount
0x18002dfd5  mov     [rsp+0A8h+nSubAuthority5], ebp; nSubAuthority5
0x18002dfd9  mov     [rsp+0A8h+nSubAuthority4], ebp; nSubAuthority4
0x18002dfdd  mov     [rsp+0A8h+nSubAuthority3], ebp; nSubAuthority3
0x18002dfe1  mov     [rsp+0A8h+nSubAuthority2], ebp; nSubAuthority2
0x18002dfe5  call    cs:__imp_AllocateAndInitializeSid
0x18002dfeb  test    eax, eax
0x18002dfed  jz      loc_18002E092
0x18002dff3  mov     rcx, [r14]; pSid
0x18002dff6  mov     rdi, [r15]
0x18002dff9  call    cs:__imp_GetLengthSid
0x18002dfff  mov     rcx, rdi; pSid
0x18002e002  mov     ebx, eax
0x18002e004  call    cs:__imp_GetLengthSid
0x18002e00a  add     eax, 1Ch
0x18002e00d  lea     ecx, [rbp+40h]; uFlags
0x18002e010  add     ebx, eax
0x18002e012  mov     edx, ebx; uBytes
0x18002e014  call    cs:__imp_LocalAlloc
0x18002e01a  mov     [rsi+10028h], rax
0x18002e021  test    rax, rax
0x18002e024  jz      short loc_18002E092
0x18002e026  lea     r8d, [rbp+2]; dwAclRevision
0x18002e02a  mov     edx, ebx; nAclLength
0x18002e02c  mov     rcx, rax; pAcl
0x18002e02f  call    cs:__imp_InitializeAcl
0x18002e035  test    eax, eax
0x18002e037  jz      short loc_18002E092
0x18002e039  mov     r9, [r14]; pSid
0x18002e03c  lea     edx, [rbp+2]; dwAceRevision
0x18002e03f  mov     rcx, [rsi+10028h]; pAcl
0x18002e046  mov     ebx, 1F01FFh
0x18002e04b  mov     r8d, ebx; AccessMask
0x18002e04e  call    cs:__imp_AddAccessAllowedAce
0x18002e054  test    eax, eax
0x18002e056  jz      short loc_18002E092
0x18002e058  mov     r9, [r15]; pSid
0x18002e05b  lea     edx, [rbp+2]; dwAceRevision
0x18002e05e  mov     rcx, [rsi+10028h]; pAcl
0x18002e065  mov     r8d, ebx; AccessMask
0x18002e068  call    cs:__imp_AddAccessAllowedAce
0x18002e06e  test    eax, eax
0x18002e070  jz      short loc_18002E092
0x18002e072  mov     r8, [rsi+10028h]; pDacl
0x18002e079  lea     edx, [rbp+1]; bDaclPresent
0x18002e07c  mov     rcx, [rsi+10030h]; pSecurityDescriptor
0x18002e083  xor     r9d, r9d; bDaclDefaulted
0x18002e086  mov     ebx, ebp
0x18002e088  call    cs:__imp_SetSecurityDescriptorDacl
0x18002e08e  test    eax, eax
0x18002e090  jnz     short loc_18002E0B3
0x18002e092  call    cs:__imp_GetLastError
0x18002e098  mov     ebx, eax
0x18002e09a  test    eax, eax
0x18002e09c  jle     short loc_18002E0A7
0x18002e09e  movzx   ebx, ax
0x18002e0a1  or      ebx, 80070000h
0x18002e0a7  test    ebx, ebx
0x18002e0a9  jns     short loc_18002E0B3
0x18002e0ab  mov     rcx, rsi; this
0x18002e0ae  call    ?FreeSecurityRelatedMembers@CWriter@@AEAAXXZ; CWriter::FreeSecurityRelatedMembers(void)
0x18002e0b3  mov     eax, ebx
0x18002e0b5  mov     rcx, [rsp+0A8h+var_40]
0x18002e0ba  xor     rcx, rsp; StackCookie
0x18002e0bd  call    __security_check_cookie
0x18002e0c2  add     rsp, 78h
0x18002e0c6  pop     r15
0x18002e0c8  pop     r14
0x18002e0ca  pop     rdi
0x18002e0cb  pop     rsi
0x18002e0cc  pop     rbp
0x18002e0cd  pop     rbx
0x18002e0ce  retn
```
