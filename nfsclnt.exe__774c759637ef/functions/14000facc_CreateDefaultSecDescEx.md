# CreateDefaultSecDescEx

- ea: `0x14000facc`
- end: `0x14000fc95`
- name: `CreateDefaultSecDescEx`
- size: `457`
- prototype: `__int64 __fastcall(void **, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000664c`
- `0x14000fe8c`

## callees

- `0x1400016e2`
- `0x1400016ee`
- `0x14000facc`
- `0x14000fce8`
- `0x14000fd50`
- `0x14001830e`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000fc01`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000fc01`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000fbe5`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000fbe5`
- `ADVAPI32!InitializeAcl` at `0x14000fb66`
- `ADVAPI32!InitializeAcl` at `0x14000fb66`
- `ADVAPI32!GetLengthSid` at `0x14000fb12`
- `ADVAPI32!GetLengthSid` at `0x14000fb21`
- `ADVAPI32!GetLengthSid` at `0x14000fb37`
- `ADVAPI32!GetLengthSid` at `0x14000fb12`
- `ADVAPI32!GetLengthSid` at `0x14000fb21`
- `ADVAPI32!GetLengthSid` at `0x14000fb37`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x14000fc10`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x14000fc10`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000fb89`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000fba7`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000fbc9`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000fb89`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000fba7`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000fbc9`
- `ADVAPI32!MakeSelfRelativeSD` at `0x14000fc4e`
- `ADVAPI32!MakeSelfRelativeSD` at `0x14000fc4e`

## pseudocode

```c
__int64 __fastcall CreateDefaultSecDescEx(void **a1, __int64 a2, __int64 a3, __int64 a4)
{
  DWORD v4; // esi
  __int64 result; // rax
  unsigned int v7; // ebp
  DWORD LengthSid; // edi
  DWORD v9; // edi
  struct _ACL *v10; // rbx
  DWORD SecurityDescriptorLength; // esi
  void *v12; // rax
  void *v13; // rdi
  _OWORD pSecurityDescriptor[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v15; // [rsp+40h] [rbp-48h]
  DWORD dwBufferLength; // [rsp+A8h] [rbp+20h] BYREF

  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v4 = a3;
  v15 = 0;
  dwBufferLength = 0;
  result = InitializeStandardSids(a1, a2, a3, a4, 0);
  if ( (_DWORD)result )
  {
    v7 = 0;
    LengthSid = GetLengthSid(pSid);
    v9 = GetLengthSid(qword_140021BA8) + LengthSid + 24;
    if ( v4 )
      v9 += GetLengthSid(qword_140021BB0) + 8;
    v10 = (struct _ACL *)malloc_0(v9);
    if ( v10
      && (*v10 = 0, InitializeAcl(v10, v9, 2u))
      && AddAccessAllowedAce(v10, 2u, 0x10000000u, pSid)
      && AddAccessAllowedAce(v10, 2u, 0x10000000u, qword_140021BA8)
      && (!v4 || AddAccessAllowedAce(v10, 2u, v4, qword_140021BB0))
      && InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v10, 0)
      && (SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor),
          dwBufferLength = SecurityDescriptorLength,
          v12 = malloc_0(SecurityDescriptorLength),
          *a1 = v12,
          (v13 = v12) != 0) )
    {
      memset_0(v12, 0, SecurityDescriptorLength);
      if ( MakeSelfRelativeSD(pSecurityDescriptor, v13, &dwBufferLength) )
      {
        v7 = 1;
      }
      else if ( *a1 )
      {
        free_0(*a1);
        *a1 = 0;
      }
      FreeStandardSids();
    }
    else
    {
      FreeStandardSids();
      if ( !v10 )
        return v7;
    }
    free_0(v10);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x14000facc  mov     r11, rsp
0x14000facf  mov     [r11+20h], r9b
0x14000fad3  push    rbx
0x14000fad4  push    rbp
0x14000fad5  push    rsi
0x14000fad6  push    rdi
0x14000fad7  push    r14
0x14000fad9  push    r15
0x14000fadb  sub     rsp, 58h
0x14000fadf  xorps   xmm0, xmm0
0x14000fae2  xor     eax, eax
0x14000fae4  movups  [rsp+88h+pSecurityDescriptor], xmm0
0x14000fae9  mov     esi, r8d
0x14000faec  mov     r14, rcx
0x14000faef  movups  [rsp+88h+var_58], xmm0
0x14000faf4  mov     [r11-48h], rax
0x14000faf8  mov     [r11+20h], eax
0x14000fafc  call    InitializeStandardSids
0x14000fb01  test    eax, eax
0x14000fb03  jz      loc_14000FC88
0x14000fb09  mov     rcx, cs:pSid; pSid
0x14000fb10  xor     ebp, ebp
0x14000fb12  call    cs:__imp_GetLengthSid
0x14000fb18  mov     rcx, cs:qword_140021BA8; pSid
0x14000fb1f  mov     edi, eax
0x14000fb21  call    cs:__imp_GetLengthSid
0x14000fb27  add     edi, 18h
0x14000fb2a  add     edi, eax
0x14000fb2c  test    esi, esi
0x14000fb2e  jz      short loc_14000FB42
0x14000fb30  mov     rcx, cs:qword_140021BB0; pSid
0x14000fb37  call    cs:__imp_GetLengthSid
0x14000fb3d  add     edi, 8
0x14000fb40  add     edi, eax
0x14000fb42  mov     ecx, edi; Size
0x14000fb44  call    malloc_0
0x14000fb49  mov     rbx, rax
0x14000fb4c  test    rax, rax
0x14000fb4f  jz      loc_14000FC74
0x14000fb55  xor     eax, eax
0x14000fb57  mov     edx, edi; nAclLength
0x14000fb59  mov     rcx, rbx; pAcl
0x14000fb5c  mov     [rbx], rax
0x14000fb5f  lea     r15d, [rax+2]
0x14000fb63  mov     r8d, r15d; dwAclRevision
0x14000fb66  call    cs:__imp_InitializeAcl
0x14000fb6c  test    eax, eax
0x14000fb6e  jz      loc_14000FC74
0x14000fb74  mov     r9, cs:pSid; pSid
0x14000fb7b  mov     edi, 10000000h
0x14000fb80  mov     r8d, edi; AccessMask
0x14000fb83  mov     edx, r15d; dwAceRevision
0x14000fb86  mov     rcx, rbx; pAcl
0x14000fb89  call    cs:__imp_AddAccessAllowedAce
0x14000fb8f  test    eax, eax
0x14000fb91  jz      loc_14000FC74
0x14000fb97  mov     r9, cs:qword_140021BA8; pSid
0x14000fb9e  mov     r8d, edi; AccessMask
0x14000fba1  mov     edx, r15d; dwAceRevision
0x14000fba4  mov     rcx, rbx; pAcl
0x14000fba7  call    cs:__imp_AddAccessAllowedAce
0x14000fbad  test    eax, eax
0x14000fbaf  jz      loc_14000FC74
0x14000fbb5  test    esi, esi
0x14000fbb7  jz      short loc_14000FBD7
0x14000fbb9  mov     r9, cs:qword_140021BB0; pSid
0x14000fbc0  mov     r8d, esi; AccessMask
0x14000fbc3  mov     edx, r15d; dwAceRevision
0x14000fbc6  mov     rcx, rbx; pAcl
0x14000fbc9  call    cs:__imp_AddAccessAllowedAce
0x14000fbcf  test    eax, eax
0x14000fbd1  jz      loc_14000FC74
0x14000fbd7  mov     r15d, 1
0x14000fbdd  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x14000fbe2  mov     edx, r15d; dwRevision
0x14000fbe5  call    cs:__imp_InitializeSecurityDescriptor
0x14000fbeb  test    eax, eax
0x14000fbed  jz      loc_14000FC74
0x14000fbf3  xor     r9d, r9d; bDaclDefaulted
0x14000fbf6  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x14000fbfb  mov     r8, rbx; pDacl
0x14000fbfe  mov     edx, r15d; bDaclPresent
0x14000fc01  call    cs:__imp_SetSecurityDescriptorDacl
0x14000fc07  test    eax, eax
0x14000fc09  jz      short loc_14000FC74
0x14000fc0b  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x14000fc10  call    cs:__imp_GetSecurityDescriptorLength
0x14000fc16  mov     esi, eax
0x14000fc18  mov     ecx, eax; Size
0x14000fc1a  mov     [rsp+88h+dwBufferLength], esi
0x14000fc21  call    malloc_0
0x14000fc26  mov     [r14], rax
0x14000fc29  mov     rdi, rax
0x14000fc2c  test    rax, rax
0x14000fc2f  jz      short loc_14000FC74
0x14000fc31  mov     r8d, esi; Size
0x14000fc34  xor     edx, edx; Val
0x14000fc36  mov     rcx, rax; void *
0x14000fc39  call    memset_0
0x14000fc3e  lea     r8, [rsp+88h+dwBufferLength]; lpdwBufferLength
0x14000fc46  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x14000fc49  lea     rcx, [rsp+88h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x14000fc4e  call    cs:__imp_MakeSelfRelativeSD
0x14000fc54  test    eax, eax
0x14000fc56  jnz     short loc_14000FC6F
0x14000fc58  mov     rcx, [r14]; Block
0x14000fc5b  test    rcx, rcx
0x14000fc5e  jz      short loc_14000FC68
0x14000fc60  call    free_0
0x14000fc65  mov     [r14], rbp
0x14000fc68  call    FreeStandardSids
0x14000fc6d  jmp     short loc_14000FC7E
0x14000fc6f  mov     ebp, r15d
0x14000fc72  jmp     short loc_14000FC68
0x14000fc74  call    FreeStandardSids
0x14000fc79  test    rbx, rbx
0x14000fc7c  jz      short loc_14000FC86
0x14000fc7e  mov     rcx, rbx; Block
0x14000fc81  call    free_0
0x14000fc86  mov     eax, ebp
0x14000fc88  add     rsp, 58h
0x14000fc8c  pop     r15
0x14000fc8e  pop     r14
0x14000fc90  pop     rdi
0x14000fc91  pop     rsi
0x14000fc92  pop     rbp
0x14000fc93  pop     rbx
0x14000fc94  retn
```
