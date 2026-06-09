# LsaBuildComputerGroupsSecurityDescriptor(void)

- ea: `0x18010144c`
- end: `0x1801016ba`
- name: `?LsaBuildComputerGroupsSecurityDescriptor@@YAJXZ`
- size: `622`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180103240`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x1800b86d0`
- `0x18010144c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801014e8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801014e8`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1801015fc`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1801015fc`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18010161e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18010161e`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18010164b`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18010164b`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18010166b`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180101696`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18010166b`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180101696`
- `ntdll!RtlAddAccessAllowedAce` at `0x1801015d8`
- `ntdll!RtlAddAccessAllowedAce` at `0x1801015d8`
- `ntdll!RtlCreateAcl` at `0x1801015a6`
- `ntdll!RtlCreateAcl` at `0x1801015a6`
- `ntdll!RtlLengthSid` at `0x18010156c`
- `ntdll!RtlLengthSid` at `0x18010156c`

## pseudocode

```c
__int64 LsaBuildComputerGroupsSecurityDescriptor(void)
{
  __int64 result; // rax
  struct _RTL_BALANCED_NODE *v1; // rsi
  struct _ACL *v2; // rdi
  __int64 i; // rbx
  void *v4; // rax
  void *v5; // rdx
  NTSTATUS Acl; // ebx
  __int64 k; // r14
  struct _RTL_BALANCED_NODE *v8; // rcx
  __int64 v9; // rbx
  ULONG v10; // r14d
  ULONG v11; // eax
  struct _ACL *v12; // rax
  __int64 j; // r14
  struct _RTL_BALANCED_NODE *v14; // rax
  ULONG BufferLength; // [rsp+20h] [rbp-60h] BYREF
  DWORD cbSid; // [rsp+24h] [rbp-5Ch] BYREF
  WELL_KNOWN_SID_TYPE WellKnownSidType[4]; // [rsp+28h] [rbp-58h]
  _OWORD SecurityDescriptor[2]; // [rsp+38h] [rbp-48h] BYREF
  struct _RTL_BALANCED_NODE *v19; // [rsp+58h] [rbp-28h]
  PSID Sid[2]; // [rsp+60h] [rbp-20h]
  __int64 v21; // [rsp+70h] [rbp-10h]

  result = 0;
  WellKnownSidType[0] = WinAccountComputersSid;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v19 = 0;
  BufferLength = 0;
  cbSid = 68;
  v21 = 0;
  *(_OWORD *)Sid = 0;
  WellKnownSidType[1] = WinAccountControllersSid;
  WellKnownSidType[2] = WinAccountReadonlyControllersSid;
  if ( g_LsapComputerGroupsSD )
    return result;
  v1 = 0;
  v2 = 0;
  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    cbSid = 68;
    v4 = (void *)LsapAllocate(68);
    Sid[i] = v4;
    if ( !v4 || !CreateWellKnownSid(WellKnownSidType[i], LsapPrimaryDomainSid, v4, &cbSid) )
      goto LABEL_7;
  }
  v9 = 0;
  v10 = 8;
  do
  {
    v11 = RtlLengthSid(Sid[v9++]);
    v10 += v11 + 8;
  }
  while ( v9 != 3 );
  v12 = (struct _ACL *)LsapAllocate(v10);
  v2 = v12;
  if ( !v12 )
    goto LABEL_7;
  Acl = RtlCreateAcl(v12, v10, 2u);
  if ( Acl >= 0 )
  {
    for ( j = 0; (unsigned int)j < 3; j = (unsigned int)(j + 1) )
    {
      Acl = RtlAddAccessAllowedAce(v2, 2u, 0x801u, Sid[j]);
      if ( Acl < 0 )
        goto LABEL_8;
    }
    Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    if ( Acl >= 0 )
    {
      Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v2, 0);
      if ( Acl >= 0 )
      {
        v2 = 0;
        Acl = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, *((PSID *)WellKnownSids + 90), 0);
        if ( Acl >= 0 )
        {
          RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
          v14 = (struct _RTL_BALANCED_NODE *)LsapAllocate(BufferLength);
          v1 = v14;
          if ( v14 )
          {
            Acl = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v14, &BufferLength);
            if ( Acl >= 0 )
            {
              g_LsapComputerGroupsSD = v1;
              v1 = 0;
              goto LABEL_12;
            }
            goto LABEL_8;
          }
LABEL_7:
          Acl = -1073741801;
        }
      }
    }
  }
LABEL_8:
  for ( k = 0; k != 3; ++k )
  {
    v8 = (struct _RTL_BALANCED_NODE *)Sid[k];
    if ( v8 )
      LsapSubProv_FreeRoutine(v8, v5);
  }
LABEL_12:
  if ( v19 )
    LsapSubProv_FreeRoutine(v19, v5);
  if ( v2 )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v2, v5);
  if ( v1 )
    LsapSubProv_FreeRoutine(v1, v5);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x18010144c  push    rbp
0x18010144e  push    rbx
0x18010144f  push    rsi
0x180101450  push    rdi
0x180101451  push    r14
0x180101453  mov     rbp, rsp
0x180101456  sub     rsp, 80h
0x18010145d  mov     rax, cs:__security_cookie
0x180101464  xor     rax, rsp
0x180101467  mov     [rbp+var_8], rax
0x18010146b  xor     eax, eax
0x18010146d  mov     [rbp+WellKnownSidType], 2Ch ; ','
0x180101474  cmp     cs:?g_LsapComputerGroupsSD@@3PEAXEA, rax; void * g_LsapComputerGroupsSD
0x18010147b  xorps   xmm0, xmm0
0x18010147e  movups  [rbp+SecurityDescriptor], xmm0
0x180101482  mov     [rbp+var_28], rax
0x180101486  lea     r14d, [rax+44h]
0x18010148a  mov     [rbp+BufferLength], eax
0x18010148d  mov     [rbp+cbSid], r14d
0x180101491  movups  [rbp+var_38], xmm0
0x180101495  mov     [rbp+var_10], rax
0x180101499  movups  xmmword ptr [rbp+Sid], xmm0
0x18010149d  mov     [rbp+var_54], 2Dh ; '-'
0x1801014a4  mov     [rbp+var_50], 4Bh ; 'K'
0x1801014ab  jnz     loc_180101546
0x1801014b1  xor     esi, esi
0x1801014b3  xor     edi, edi
0x1801014b5  xor     ebx, ebx
0x1801014b7  cmp     ebx, 3
0x1801014ba  jnb     loc_180101561
0x1801014c0  mov     rcx, r14
0x1801014c3  mov     [rbp+cbSid], r14d
0x1801014c7  call    LsapAllocate
0x1801014cc  mov     [rbp+rbx*8+Sid], rax
0x1801014d1  test    rax, rax
0x1801014d4  jz      short loc_1801014FC
0x1801014d6  mov     rdx, cs:?LsapPrimaryDomainSid@@3PEAXEA; DomainSid
0x1801014dd  lea     r9, [rbp+cbSid]; cbSid
0x1801014e1  mov     ecx, [rbp+rbx*4+WellKnownSidType]; WellKnownSidType
0x1801014e5  mov     r8, rax; pSid
0x1801014e8  call    cs:__imp_CreateWellKnownSid
0x1801014ef  nop     dword ptr [rax+rax+00h]
0x1801014f4  test    eax, eax
0x1801014f6  jz      short loc_1801014FC
0x1801014f8  inc     ebx
0x1801014fa  jmp     short loc_1801014B7
0x1801014fc  mov     ebx, 0C0000017h
0x180101501  xor     r14d, r14d
0x180101504  mov     rcx, [rbp+r14*8+Sid]; struct _RTL_BALANCED_NODE *
0x180101509  test    rcx, rcx
0x18010150c  jz      short loc_180101513
0x18010150e  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180101513  inc     r14
0x180101516  cmp     r14, 3
0x18010151a  jnz     short loc_180101504
0x18010151c  mov     rcx, [rbp+var_28]; struct _RTL_BALANCED_NODE *
0x180101520  test    rcx, rcx
0x180101523  jz      short loc_18010152A
0x180101525  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18010152a  test    rdi, rdi
0x18010152d  jz      short loc_180101537
0x18010152f  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x180101532  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180101537  test    rsi, rsi
0x18010153a  jz      short loc_180101544
0x18010153c  mov     rcx, rsi; struct _RTL_BALANCED_NODE *
0x18010153f  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180101544  mov     eax, ebx
0x180101546  mov     rcx, [rbp+var_8]
0x18010154a  xor     rcx, rsp; StackCookie
0x18010154d  call    __security_check_cookie
0x180101552  add     rsp, 80h
0x180101559  pop     r14
0x18010155b  pop     rdi
0x18010155c  pop     rsi
0x18010155d  pop     rbx
0x18010155e  pop     rbp
0x18010155f  retn
0x180101561  xor     ebx, ebx
0x180101563  lea     r14d, [rbx+8]
0x180101567  mov     rcx, [rbp+rbx*8+Sid]; Sid
0x18010156c  call    cs:__imp_RtlLengthSid
0x180101573  nop     dword ptr [rax+rax+00h]
0x180101578  add     r14d, 8
0x18010157c  inc     rbx
0x18010157f  add     r14d, eax
0x180101582  cmp     rbx, 3
0x180101586  jnz     short loc_180101567
0x180101588  mov     ecx, r14d
0x18010158b  call    LsapAllocate
0x180101590  mov     rdi, rax
0x180101593  test    rax, rax
0x180101596  jz      loc_1801014FC
0x18010159c  lea     r8d, [rbx-1]; AclRevision
0x1801015a0  mov     edx, r14d; AclSize
0x1801015a3  mov     rcx, rax; Acl
0x1801015a6  call    cs:__imp_RtlCreateAcl
0x1801015ad  nop     dword ptr [rax+rax+00h]
0x1801015b2  mov     ebx, eax
0x1801015b4  test    eax, eax
0x1801015b6  js      loc_180101501
0x1801015bc  xor     r14d, r14d
0x1801015bf  cmp     r14d, 3
0x1801015c3  jnb     short loc_1801015F3
0x1801015c5  mov     r9, [rbp+r14*8+Sid]; Sid
0x1801015ca  mov     edx, 2; Revision
0x1801015cf  mov     r8d, 801h; AccessMask
0x1801015d5  mov     rcx, rdi; Acl
0x1801015d8  call    cs:__imp_RtlAddAccessAllowedAce
0x1801015df  nop     dword ptr [rax+rax+00h]
0x1801015e4  mov     ebx, eax
0x1801015e6  test    eax, eax
0x1801015e8  js      loc_180101501
0x1801015ee  inc     r14d
0x1801015f1  jmp     short loc_1801015BF
0x1801015f3  mov     edx, 1; Revision
0x1801015f8  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801015fc  call    cs:__imp_RtlCreateSecurityDescriptor
0x180101603  nop     dword ptr [rax+rax+00h]
0x180101608  mov     ebx, eax
0x18010160a  test    eax, eax
0x18010160c  js      loc_180101501
0x180101612  xor     r9d, r9d; DaclDefaulted
0x180101615  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180101619  mov     r8, rdi; Dacl
0x18010161c  mov     dl, 1; DaclPresent
0x18010161e  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180101625  nop     dword ptr [rax+rax+00h]
0x18010162a  mov     ebx, eax
0x18010162c  test    eax, eax
0x18010162e  js      loc_180101501
0x180101634  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18010163b  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18010163f  xor     r8d, r8d; OwnerDefaulted
0x180101642  xor     edi, edi
0x180101644  mov     rdx, [rdx+2D0h]; Owner
0x18010164b  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180101652  nop     dword ptr [rax+rax+00h]
0x180101657  mov     ebx, eax
0x180101659  test    eax, eax
0x18010165b  js      loc_180101501
0x180101661  lea     r8, [rbp+BufferLength]; BufferLength
0x180101665  xor     edx, edx; SelfRelativeSecurityDescriptor
0x180101667  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18010166b  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180101672  nop     dword ptr [rax+rax+00h]
0x180101677  mov     ecx, [rbp+BufferLength]
0x18010167a  call    LsapAllocate
0x18010167f  mov     rsi, rax
0x180101682  test    rax, rax
0x180101685  jz      loc_1801014FC
0x18010168b  lea     r8, [rbp+BufferLength]; BufferLength
0x18010168f  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x180101692  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180101696  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18010169d  nop     dword ptr [rax+rax+00h]
0x1801016a2  mov     ebx, eax
0x1801016a4  test    eax, eax
0x1801016a6  js      loc_180101501
0x1801016ac  mov     cs:?g_LsapComputerGroupsSD@@3PEAXEA, rsi; void * g_LsapComputerGroupsSD
0x1801016b3  xor     esi, esi
0x1801016b5  jmp     loc_18010151C
```
