# SampBuildEquivalentNt5Protection

- ea: `0x1803e46c0`
- end: `0x1803e49a6`
- name: `SampBuildEquivalentNt5Protection`
- size: `742`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PACL pSacl, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1803e3d84`

## callees

- `0x18001e090`
- `0x1803e3788`
- `0x1803e4148`
- `0x1803e46c0`
- `0x180453340`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAuditAccessAce` at `0x1803e4810`
- `api-ms-win-security-base-l1-1-0!AddAuditAccessAce` at `0x1803e4810`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1803e490c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1803e490c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1803e4843`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1803e4843`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1803e4754`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1803e4754`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1803e479c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1803e479c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1803e47bc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1803e47bc`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1803e477c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1803e47de`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1803e477c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1803e47de`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1803e491f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1803e491f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1803e4952`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1803e4952`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803e4930`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803e4930`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803e4969`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803e4969`

## pseudocode

```c
__int64 __fastcall SampBuildEquivalentNt5Protection(
        int a1,
        char a2,
        char a3,
        PSID a4,
        void *a5,
        PACL pSacl,
        struct _SAMP_OBJECT *a7,
        HLOCAL *a8,
        DWORD *a9)
{
  PSID v10; // r12
  PACL v11; // r14
  int v14; // ebx
  unsigned int v15; // ebx
  int v16; // edi
  int v17; // edi
  int v18; // edi
  struct _ACE_TABLE_ENTRY near **v19; // rcx
  HLOCAL v20; // rax
  DWORD dwBufferLength; // [rsp+34h] [rbp-CCh] BYREF
  struct _SAMP_OBJECT *v24; // [rsp+38h] [rbp-C8h]
  DWORD *v25; // [rsp+40h] [rbp-C0h]
  _OWORD pSecurityDescriptor[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h]
  struct _ACL v28; // [rsp+70h] [rbp-90h] BYREF
  struct _ACL pAcl; // [rsp+870h] [rbp+770h] BYREF

  v10 = a5;
  v11 = pSacl;
  v24 = a7;
  v27 = 0;
  *a8 = 0;
  *a9 = 0;
  v25 = a9;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  dwBufferLength = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    return (unsigned int)-1073741823;
  v15 = 4;
  if ( !InitializeAcl(&pAcl, 0x800u, 4u) )
    return (unsigned int)-1073741823;
  if ( !a4 )
    a4 = SampAdministratorsAliasSid;
  if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, a4, 0) )
    return (unsigned int)-1073741823;
  if ( !a5 )
    v10 = SampAdministratorsAliasSid;
  if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, v10, 0) )
    return (unsigned int)-1073741823;
  if ( !pSacl )
  {
    if ( !InitializeAcl(&v28, 0x800u, 4u) )
      return (unsigned int)-1073741823;
    if ( !AddAuditAccessAce(&v28, 4u, 0x1070000u, SampWorldSid, 1, 1) )
      return (unsigned int)-1073741823;
    v11 = &v28;
    if ( !(unsigned __int8)AdjustAclSize(&v28) )
      return (unsigned int)-1073741823;
  }
  if ( !SetSecurityDescriptorSacl(pSecurityDescriptor, 1, v11, 0) )
    return (unsigned int)-1073741823;
  if ( a1 )
  {
    v16 = a1 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 && (v18 = v17 - 1) != 0 )
      {
        if ( v18 == 1 )
        {
          if ( a2 )
          {
            v19 = &UserAdminAceTable;
            v15 = 6;
          }
          else if ( a3 )
          {
            v19 = &UserAceTable;
            v15 = 5;
          }
          else
          {
            v19 = &UserNoPwdAceTable;
            v15 = 8;
          }
        }
        else
        {
          v19 = 0;
          v15 = 0;
        }
      }
      else
      {
        v19 = &GroupAceTable;
        if ( a2 )
          v19 = &GroupAdminAceTable;
        v15 = 5 - (a2 != 0);
      }
    }
    else
    {
      v19 = &DomainAceTable;
    }
  }
  else
  {
    v19 = &ServerAceTable;
    v15 = 2;
  }
  v14 = SampCreateNT5Dacl((struct _ACE_TABLE_ENTRY *)v19, v15, v24, &pAcl);
  if ( v14 >= 0 )
  {
    if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, &pAcl, 0) )
    {
      dwBufferLength = GetSecurityDescriptorLength(pSecurityDescriptor);
      v20 = LocalAlloc(0x40u, dwBufferLength);
      *a8 = v20;
      if ( v20 )
      {
        if ( !MakeSelfRelativeSD(pSecurityDescriptor, v20, &dwBufferLength) )
        {
          v14 = -1073741823;
          if ( *a8 )
          {
            LocalFree(*a8);
            *a8 = 0;
          }
        }
        *v25 = dwBufferLength;
      }
      else
      {
        return (unsigned int)-1073741801;
      }
      return (unsigned int)v14;
    }
    return (unsigned int)-1073741823;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1803e46c0  push    rbp
0x1803e46c2  push    rbx
0x1803e46c3  push    rsi
0x1803e46c4  push    rdi
0x1803e46c5  push    r12
0x1803e46c7  push    r13
0x1803e46c9  push    r14
0x1803e46cb  push    r15
0x1803e46cd  lea     rbp, [rsp-0F88h]
0x1803e46d5  mov     eax, 1088h
0x1803e46da  call    _alloca_probe
0x1803e46df  sub     rsp, rax
0x1803e46e2  mov     rax, cs:__security_cookie
0x1803e46e9  xor     rax, rsp
0x1803e46ec  mov     [rbp+0FC0h+var_50], rax
0x1803e46f3  mov     rax, [rbp+0FC0h+arg_30]
0x1803e46fa  mov     edi, ecx
0x1803e46fc  mov     r15, [rbp+0FC0h+arg_38]
0x1803e4703  xor     ecx, ecx
0x1803e4705  mov     r12, [rbp+0FC0h+arg_20]
0x1803e470c  xor     ebx, ebx
0x1803e470e  mov     r14, [rbp+0FC0h+pSacl]
0x1803e4715  xorps   xmm0, xmm0
0x1803e4718  mov     [rsp+10C0h+var_1088], rax
0x1803e471d  mov     sil, dl
0x1803e4720  mov     rax, [rbp+0FC0h+arg_40]
0x1803e4727  lea     edx, [rcx+1]; dwRevision
0x1803e472a  mov     [rsp+10C0h+var_1058], rcx
0x1803e472f  mov     r13, r9
0x1803e4732  mov     [r15], rbx
0x1803e4735  lea     rcx, [rsp+10C0h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e473a  mov     [rsp+10C0h+var_1090], r8b
0x1803e473f  mov     [rax], ebx
0x1803e4741  mov     [rsp+10C0h+var_1080], rax
0x1803e4746  movups  [rsp+10C0h+pSecurityDescriptor], xmm0
0x1803e474b  mov     [rsp+10C0h+dwBufferLength], ebx
0x1803e474f  movups  [rsp+10C0h+var_1068], xmm0
0x1803e4754  call    cs:__imp_InitializeSecurityDescriptor
0x1803e475a  test    eax, eax
0x1803e475c  jnz     short loc_1803E4768
0x1803e475e  mov     ebx, 0C0000001h
0x1803e4763  jmp     loc_1803E4981
0x1803e4768  mov     ebx, 4
0x1803e476d  lea     rcx, [rbp+0FC0h+pAcl]; pAcl
0x1803e4774  mov     r8d, ebx; dwAclRevision
0x1803e4777  mov     edx, 800h; nAclLength
0x1803e477c  call    cs:__imp_InitializeAcl
0x1803e4782  test    eax, eax
0x1803e4784  jz      short loc_1803E475E
0x1803e4786  test    r13, r13
0x1803e4789  lea     rcx, [rsp+10C0h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e478e  cmovz   r13, cs:SampAdministratorsAliasSid
0x1803e4796  xor     r8d, r8d; bOwnerDefaulted
0x1803e4799  mov     rdx, r13; pOwner
0x1803e479c  call    cs:__imp_SetSecurityDescriptorOwner
0x1803e47a2  test    eax, eax
0x1803e47a4  jz      short loc_1803E475E
0x1803e47a6  test    r12, r12
0x1803e47a9  lea     rcx, [rsp+10C0h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e47ae  cmovz   r12, cs:SampAdministratorsAliasSid
0x1803e47b6  xor     r8d, r8d; bGroupDefaulted
0x1803e47b9  mov     rdx, r12; pGroup
0x1803e47bc  call    cs:__imp_SetSecurityDescriptorGroup
0x1803e47c2  test    eax, eax
0x1803e47c4  jz      short loc_1803E475E
0x1803e47c6  test    r14, r14
0x1803e47c9  jz      short loc_1803E47D1
0x1803e47cb  lea     r12d, [rbx-3]
0x1803e47cf  jmp     short loc_1803E4835
0x1803e47d1  mov     r8d, ebx; dwAclRevision
0x1803e47d4  lea     rcx, [rsp+10C0h+var_1050]; pAcl
0x1803e47d9  mov     edx, 800h; nAclLength
0x1803e47de  call    cs:__imp_InitializeAcl
0x1803e47e4  test    eax, eax
0x1803e47e6  jz      loc_1803E475E
0x1803e47ec  mov     r9, cs:SampWorldSid; pSid
0x1803e47f3  lea     rcx, [rsp+10C0h+var_1050]; pAcl
0x1803e47f8  mov     r12d, 1
0x1803e47fe  mov     r8d, 1070000h; dwAccessMask
0x1803e4804  mov     [rsp+10C0h+bAuditFailure], r12d; bAuditFailure
0x1803e4809  mov     edx, ebx; dwAceRevision
0x1803e480b  mov     [rsp+10C0h+bAuditSuccess], r12d; bAuditSuccess
0x1803e4810  call    cs:__imp_AddAuditAccessAce
0x1803e4816  test    eax, eax
0x1803e4818  jz      loc_1803E475E
0x1803e481e  lea     rcx, [rsp+10C0h+var_1050]
0x1803e4823  lea     r14, [rsp+10C0h+var_1050]
0x1803e4828  call    AdjustAclSize
0x1803e482d  test    al, al
0x1803e482f  jz      loc_1803E475E
0x1803e4835  xor     r9d, r9d; bSaclDefaulted
0x1803e4838  lea     rcx, [rsp+10C0h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e483d  mov     r8, r14; pSacl
0x1803e4840  mov     edx, r12d; bSaclPresent
0x1803e4843  call    cs:__imp_SetSecurityDescriptorSacl
0x1803e4849  test    eax, eax
0x1803e484b  jz      loc_1803E475E
0x1803e4851  test    edi, edi
0x1803e4853  jz      short loc_1803E48D1
0x1803e4855  sub     edi, 1
0x1803e4858  jz      short loc_1803E48C8
0x1803e485a  sub     edi, 1
0x1803e485d  jz      short loc_1803E48A5
0x1803e485f  sub     edi, 1
0x1803e4862  jz      short loc_1803E48A5
0x1803e4864  cmp     edi, 1
0x1803e4867  jz      short loc_1803E486F
0x1803e4869  xor     ecx, ecx
0x1803e486b  xor     ebx, ebx
0x1803e486d  jmp     short loc_1803E48DD
0x1803e486f  test    sil, sil
0x1803e4872  jnz     short loc_1803E4897
0x1803e4874  cmp     [rsp+10C0h+var_1090], sil
0x1803e4879  jnz     short loc_1803E4889
0x1803e487b  lea     rcx, ?UserNoPwdAceTable@@3PAU_ACE_TABLE_ENTRY@@A; _ACE_TABLE_ENTRY near * UserNoPwdAceTable
0x1803e4882  mov     ebx, 8
0x1803e4887  jmp     short loc_1803E48DD
0x1803e4889  lea     rcx, ?UserAceTable@@3PAU_ACE_TABLE_ENTRY@@A; _ACE_TABLE_ENTRY near * UserAceTable
0x1803e4890  mov     ebx, 5
0x1803e4895  jmp     short loc_1803E48DD
0x1803e4897  lea     rcx, ?UserAdminAceTable@@3PAU_ACE_TABLE_ENTRY@@A; _ACE_TABLE_ENTRY near * UserAdminAceTable
0x1803e489e  mov     ebx, 6
0x1803e48a3  jmp     short loc_1803E48DD
0x1803e48a5  test    sil, sil
0x1803e48a8  lea     rax, ?GroupAdminAceTable@@3PAU_ACE_TABLE_ENTRY@@A; _ACE_TABLE_ENTRY near * GroupAdminAceTable
0x1803e48af  lea     rcx, ?GroupAceTable@@3PAU_ACE_TABLE_ENTRY@@A; _ACE_TABLE_ENTRY near * GroupAceTable
0x1803e48b6  mov     ebx, 5
0x1803e48bb  cmovnz  rcx, rax
0x1803e48bf  neg     sil
0x1803e48c2  sbb     eax, eax
0x1803e48c4  add     ebx, eax
0x1803e48c6  jmp     short loc_1803E48DD
0x1803e48c8  lea     rcx, ?DomainAceTable@@3PAU_ACE_TABLE_ENTRY@@A; _ACE_TABLE_ENTRY near * DomainAceTable
0x1803e48cf  jmp     short loc_1803E48DD
0x1803e48d1  lea     rcx, ?ServerAceTable@@3PAU_ACE_TABLE_ENTRY@@A; struct _ACE_TABLE_ENTRY *
0x1803e48d8  mov     ebx, 2
0x1803e48dd  mov     r8, [rsp+10C0h+var_1088]; struct _SAMP_OBJECT *
0x1803e48e2  lea     r9, [rbp+0FC0h+pAcl]; struct _ACL *
0x1803e48e9  mov     edx, ebx; unsigned int
0x1803e48eb  call    ?SampCreateNT5Dacl@@YAJPEAU_ACE_TABLE_ENTRY@@KPEAU_SAMP_OBJECT@@PEAU_ACL@@@Z; SampCreateNT5Dacl(_ACE_TABLE_ENTRY *,ulong,_SAMP_OBJECT *,_ACL *)
0x1803e48f0  mov     ebx, eax
0x1803e48f2  test    eax, eax
0x1803e48f4  js      loc_1803E4981
0x1803e48fa  xor     r9d, r9d; bDaclDefaulted
0x1803e48fd  lea     r8, [rbp+0FC0h+pAcl]; pDacl
0x1803e4904  mov     edx, r12d; bDaclPresent
0x1803e4907  lea     rcx, [rsp+10C0h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e490c  call    cs:__imp_SetSecurityDescriptorDacl
0x1803e4912  test    eax, eax
0x1803e4914  jz      loc_1803E475E
0x1803e491a  lea     rcx, [rsp+10C0h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e491f  call    cs:__imp_GetSecurityDescriptorLength
0x1803e4925  mov     edx, eax; uBytes
0x1803e4927  mov     ecx, 40h ; '@'; uFlags
0x1803e492c  mov     [rsp+10C0h+dwBufferLength], edx
0x1803e4930  call    cs:__imp_LocalAlloc
0x1803e4936  mov     [r15], rax
0x1803e4939  test    rax, rax
0x1803e493c  jnz     short loc_1803E4945
0x1803e493e  mov     ebx, 0C0000017h
0x1803e4943  jmp     short loc_1803E4981
0x1803e4945  lea     r8, [rsp+10C0h+dwBufferLength]; lpdwBufferLength
0x1803e494a  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1803e494d  lea     rcx, [rsp+10C0h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1803e4952  call    cs:__imp_MakeSelfRelativeSD
0x1803e4958  test    eax, eax
0x1803e495a  jnz     short loc_1803E4976
0x1803e495c  mov     rcx, [r15]; hMem
0x1803e495f  mov     ebx, 0C0000001h
0x1803e4964  test    rcx, rcx
0x1803e4967  jz      short loc_1803E4976
0x1803e4969  call    cs:__imp_LocalFree
0x1803e496f  mov     qword ptr [r15], 0
0x1803e4976  mov     rcx, [rsp+10C0h+var_1080]
0x1803e497b  mov     eax, [rsp+10C0h+dwBufferLength]
0x1803e497f  mov     [rcx], eax
0x1803e4981  mov     eax, ebx
0x1803e4983  mov     rcx, [rbp+0FC0h+var_50]
0x1803e498a  xor     rcx, rsp; StackCookie
0x1803e498d  call    __security_check_cookie
0x1803e4992  add     rsp, 1088h
0x1803e4999  pop     r15
0x1803e499b  pop     r14
0x1803e499d  pop     r13
0x1803e499f  pop     r12
0x1803e49a1  pop     rdi
0x1803e49a2  pop     rsi
0x1803e49a3  pop     rbx
0x1803e49a4  pop     rbp
0x1803e49a5  retn
```
