# GetWorldReadableSecurityDescriptor

- ea: `0x18001d774`
- end: `0x18001d8c8`
- name: `GetWorldReadableSecurityDescriptor`
- size: `340`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001cb50`

## callees

- `0x18000173c`
- `0x18000178c`
- `0x18001d208`
- `0x18001d774`
- `0x1800273b0`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAce` at `0x18001d829`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001d844`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001d85d`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001d829`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001d844`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001d85d`
- `ADVAPI32!InitializeAcl` at `0x18001d80c`
- `ADVAPI32!InitializeAcl` at `0x18001d80c`
- `ADVAPI32!GetLengthSid` at `0x18001d7cb`
- `ADVAPI32!GetLengthSid` at `0x18001d7d6`
- `ADVAPI32!GetLengthSid` at `0x18001d7e3`
- `ADVAPI32!GetLengthSid` at `0x18001d7cb`
- `ADVAPI32!GetLengthSid` at `0x18001d7d6`
- `ADVAPI32!GetLengthSid` at `0x18001d7e3`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18001d871`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18001d871`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18001d886`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18001d886`
- `mqsec!MQSec_GetAnonymousSid` at `0x18001d7bf`
- `mqsec!MQSec_GetAnonymousSid` at `0x18001d7bf`
- `mqsec!MQSec_GetWorldSid` at `0x18001d7b6`
- `mqsec!MQSec_GetWorldSid` at `0x18001d7b6`

## pseudocode

```c
__int64 __fastcall GetWorldReadableSecurityDescriptor(PSECURITY_DESCRIPTOR pSecurityDescriptor, ACL **a2)
{
  ACL *v3; // rbx
  void *WorldSid; // r14
  void *AnonymousSid; // r15
  DWORD LengthSid; // edi
  DWORD v8; // edi
  DWORD v9; // edi
  ACL *v10; // rax
  unsigned int v11; // edi
  _BYTE pSid[128]; // [rsp+20h] [rbp-B8h] BYREF

  v3 = 0;
  *a2 = 0;
  if ( !(unsigned int)GetCurrentUserSid(pSid) )
    goto LABEL_10;
  WorldSid = MQSec_GetWorldSid();
  AnonymousSid = MQSec_GetAnonymousSid();
  LengthSid = GetLengthSid(AnonymousSid);
  v8 = GetLengthSid(WorldSid) + LengthSid;
  v9 = GetLengthSid(pSid) + 32 + v8;
  v10 = (ACL *)operator new(v9);
  v3 = v10;
  if ( !v10 )
    goto LABEL_10;
  if ( InitializeAcl(v10, v9, 2u)
    && AddAccessAllowedAce(v3, 2u, 0xF003Fu, pSid)
    && AddAccessAllowedAce(v3, 2u, 0x2002Fu, WorldSid)
    && AddAccessAllowedAce(v3, 2u, 4u, AnonymousSid)
    && (v11 = 1, InitializeSecurityDescriptor(pSecurityDescriptor, 1u))
    && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v3, 0) )
  {
    *a2 = v3;
  }
  else
  {
LABEL_10:
    v11 = 0;
    operator delete(v3);
  }
  return v11;
}

```

## disassembly

```asm
0x18001d774  mov     [rsp+arg_10], rbx
0x18001d779  push    rbp
0x18001d77a  push    rsi
0x18001d77b  push    rdi
0x18001d77c  push    r14
0x18001d77e  push    r15
0x18001d780  sub     rsp, 0B0h
0x18001d787  mov     rax, cs:__security_cookie
0x18001d78e  xor     rax, rsp
0x18001d791  mov     [rsp+0D8h+var_38], rax
0x18001d799  mov     rbp, rcx
0x18001d79c  xor     ebx, ebx
0x18001d79e  lea     rcx, [rsp+0D8h+pSid]; pDestinationSid
0x18001d7a3  mov     [rdx], rbx
0x18001d7a6  mov     rsi, rdx
0x18001d7a9  call    GetCurrentUserSid
0x18001d7ae  test    eax, eax
0x18001d7b0  jz      loc_18001D895
0x18001d7b6  call    cs:__imp_?MQSec_GetWorldSid@@YAPEAXXZ; MQSec_GetWorldSid(void)
0x18001d7bc  mov     r14, rax
0x18001d7bf  call    cs:__imp_?MQSec_GetAnonymousSid@@YAPEAXXZ; MQSec_GetAnonymousSid(void)
0x18001d7c5  mov     rcx, rax; pSid
0x18001d7c8  mov     r15, rax
0x18001d7cb  call    cs:__imp_GetLengthSid
0x18001d7d1  mov     rcx, r14; pSid
0x18001d7d4  mov     edi, eax
0x18001d7d6  call    cs:__imp_GetLengthSid
0x18001d7dc  lea     rcx, [rsp+0D8h+pSid]; pSid
0x18001d7e1  add     edi, eax
0x18001d7e3  call    cs:__imp_GetLengthSid
0x18001d7e9  add     eax, 20h ; ' '
0x18001d7ec  add     edi, eax
0x18001d7ee  mov     ecx, edi; Size
0x18001d7f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d7f5  mov     rbx, rax
0x18001d7f8  test    rax, rax
0x18001d7fb  jz      loc_18001D895
0x18001d801  mov     r8d, 2; dwAclRevision
0x18001d807  mov     edx, edi; nAclLength
0x18001d809  mov     rcx, rax; pAcl
0x18001d80c  call    cs:__imp_InitializeAcl
0x18001d812  test    eax, eax
0x18001d814  jz      short loc_18001D895
0x18001d816  lea     r9, [rsp+0D8h+pSid]; pSid
0x18001d81b  mov     edx, 2; dwAceRevision
0x18001d820  mov     r8d, 0F003Fh; AccessMask
0x18001d826  mov     rcx, rbx; pAcl
0x18001d829  call    cs:__imp_AddAccessAllowedAce
0x18001d82f  test    eax, eax
0x18001d831  jz      short loc_18001D895
0x18001d833  mov     r9, r14; pSid
0x18001d836  mov     edx, 2; dwAceRevision
0x18001d83b  mov     r8d, 2002Fh; AccessMask
0x18001d841  mov     rcx, rbx; pAcl
0x18001d844  call    cs:__imp_AddAccessAllowedAce
0x18001d84a  test    eax, eax
0x18001d84c  jz      short loc_18001D895
0x18001d84e  mov     edx, 2; dwAceRevision
0x18001d853  mov     r9, r15; pSid
0x18001d856  mov     rcx, rbx; pAcl
0x18001d859  lea     r8d, [rdx+2]; AccessMask
0x18001d85d  call    cs:__imp_AddAccessAllowedAce
0x18001d863  test    eax, eax
0x18001d865  jz      short loc_18001D895
0x18001d867  mov     edi, 1
0x18001d86c  mov     rcx, rbp; pSecurityDescriptor
0x18001d86f  mov     edx, edi; dwRevision
0x18001d871  call    cs:__imp_InitializeSecurityDescriptor
0x18001d877  test    eax, eax
0x18001d879  jz      short loc_18001D895
0x18001d87b  xor     r9d, r9d; bDaclDefaulted
0x18001d87e  mov     r8, rbx; pDacl
0x18001d881  mov     edx, edi; bDaclPresent
0x18001d883  mov     rcx, rbp; pSecurityDescriptor
0x18001d886  call    cs:__imp_SetSecurityDescriptorDacl
0x18001d88c  test    eax, eax
0x18001d88e  jz      short loc_18001D895
0x18001d890  mov     [rsi], rbx
0x18001d893  jmp     short loc_18001D89F
0x18001d895  xor     edi, edi
0x18001d897  mov     rcx, rbx; Block
0x18001d89a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d89f  mov     eax, edi
0x18001d8a1  mov     rcx, [rsp+0D8h+var_38]
0x18001d8a9  xor     rcx, rsp; StackCookie
0x18001d8ac  call    __security_check_cookie
0x18001d8b1  mov     rbx, [rsp+0D8h+arg_10]
0x18001d8b9  add     rsp, 0B0h
0x18001d8c0  pop     r15
0x18001d8c2  pop     r14
0x18001d8c4  pop     rdi
0x18001d8c5  pop     rsi
0x18001d8c6  pop     rbp
0x18001d8c7  retn
```
