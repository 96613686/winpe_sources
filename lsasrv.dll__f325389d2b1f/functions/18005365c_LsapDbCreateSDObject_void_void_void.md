# LsapDbCreateSDObject(void *,void *,void * *)

- ea: `0x18005365c`
- end: `0x180053cd8`
- name: `?LsapDbCreateSDObject@@YAJPEAX0PEAPEAX@Z`
- size: `1660`
- prototype: `__int64 __fastcall(void *, void *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180053558`
- `0x18010c5f0`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x18005365c`
- `0x180054110`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x180053772`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180053772`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800539d7`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800539d7`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800539b5`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800539b5`
- `ntdll!RtlFreeHeap` at `0x180053cb7`
- `ntdll!RtlFreeHeap` at `0x180053cb7`
- `ntdll!RtlNewSecurityObject` at `0x180053a7f`
- `ntdll!RtlNewSecurityObject` at `0x180053a7f`
- `ntdll!NtOpenProcessToken` at `0x180053757`
- `ntdll!NtOpenProcessToken` at `0x180053757`
- `ntdll!NtClose` at `0x18005371a`
- `ntdll!NtClose` at `0x180053b2c`
- `ntdll!NtClose` at `0x18005371a`
- `ntdll!NtClose` at `0x180053b2c`
- `ntdll!NtOpenProcess` at `0x1800536d9`
- `ntdll!NtOpenProcess` at `0x1800536d9`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800538d4`
- `ntdll!RtlAddAccessAllowedAce` at `0x18005390b`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053b97`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053bc6`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053bf5`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053c24`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053c53`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053c8d`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800538d4`
- `ntdll!RtlAddAccessAllowedAce` at `0x18005390b`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053b97`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053bc6`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053bf5`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053c24`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053c53`
- `ntdll!RtlAddAccessAllowedAce` at `0x180053c8d`
- `ntdll!RtlCreateAcl` at `0x180053893`
- `ntdll!RtlCreateAcl` at `0x180053893`
- `ntdll!RtlLengthSid` at `0x180053839`
- `ntdll!RtlLengthSid` at `0x18005384c`
- `ntdll!RtlLengthSid` at `0x180053aa8`
- `ntdll!RtlLengthSid` at `0x180053acd`
- `ntdll!RtlLengthSid` at `0x180053af2`
- `ntdll!RtlLengthSid` at `0x180053b15`
- `ntdll!RtlLengthSid` at `0x180053b4b`
- `ntdll!RtlLengthSid` at `0x180053b6e`
- `ntdll!RtlLengthSid` at `0x180053839`
- `ntdll!RtlLengthSid` at `0x18005384c`
- `ntdll!RtlLengthSid` at `0x180053aa8`
- `ntdll!RtlLengthSid` at `0x180053acd`
- `ntdll!RtlLengthSid` at `0x180053af2`
- `ntdll!RtlLengthSid` at `0x180053b15`
- `ntdll!RtlLengthSid` at `0x180053b4b`
- `ntdll!RtlLengthSid` at `0x180053b6e`

## pseudocode

```c
__int64 __fastcall LsapDbCreateSDObject(void *a1, int *a2, void **a3)
{
  ULONG v3; // r12d
  struct _ACL *v5; // rdi
  struct _RTL_BALANCED_NODE *v6; // r14
  void *v7; // rdx
  NTSTATUS Acl; // ebx
  PVOID *v9; // rsi
  ULONG v11; // r13d
  ULONG v12; // r15d
  void *v13; // rdi
  ULONG v14; // ebx
  ULONG v15; // eax
  ULONG v16; // ebx
  struct _ACL *v17; // rax
  ACCESS_MASK v18; // r8d
  ACCESS_MASK v19; // r8d
  ACCESS_MASK v20; // r8d
  ACCESS_MASK v21; // r8d
  ACCESS_MASK v22; // r8d
  struct _RTL_BALANCED_NODE *v23; // rax
  __int64 v24; // rax
  ULONG v25; // [rsp+30h] [rbp-59h]
  void *ProcessHandle; // [rsp+38h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-49h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v29; // [rsp+68h] [rbp-21h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-19h] BYREF
  unsigned int v32; // [rsp+F8h] [rbp+6Fh] BYREF
  PSECURITY_DESCRIPTOR *NewDescriptor; // [rsp+100h] [rbp+77h]
  ULONG v34; // [rsp+108h] [rbp+7Fh]

  NewDescriptor = a3;
  v3 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a3 = 0;
  ProcessHandle = 0;
  v29 = 0;
  TokenHandle = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v5 = 0;
  v6 = 0;
  Acl = NtOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, &NtCurrentTeb()->ClientId);
  if ( Acl < 0 )
    goto LABEL_2;
  Acl = NtOpenProcessToken(ProcessHandle, 8u, &TokenHandle);
  if ( Acl < 0 )
    goto LABEL_2;
  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( Acl < 0 )
    goto LABEL_2;
  if ( *((_DWORD *)&LsapDbState + 22 * a2[26] + 156) )
    v32 = RtlLengthSid(*((PSID *)WellKnownSids + 108)) + 12;
  else
    v32 = 0;
  if ( *((_DWORD *)&LsapDbState + 22 * a2[26] + 157) )
    v34 = RtlLengthSid(*((PSID *)WellKnownSids + 156)) + 12;
  else
    v34 = 0;
  if ( *((_DWORD *)&LsapDbState + 22 * a2[26] + 158) )
    v25 = RtlLengthSid(*((PSID *)WellKnownSids + 162)) + 12;
  else
    v25 = 0;
  if ( *((_DWORD *)&LsapDbState + 22 * a2[26] + 159) )
    v11 = RtlLengthSid(*((PSID *)WellKnownSids + 168)) + 12;
  else
    v11 = 0;
  if ( *((_DWORD *)&LsapDbState + 22 * a2[26] + 161) )
    v3 = RtlLengthSid(*((PSID *)WellKnownSids + 288)) + 12;
  if ( *((_DWORD *)&LsapDbState + 22 * a2[26] + 161) )
    v12 = RtlLengthSid(*((PSID *)WellKnownSids + 450)) + 40;
  else
    v12 = 28;
  v13 = (void *)*((_QWORD *)WellKnownSids + 96);
  v14 = v12 + RtlLengthSid(*((PSID *)WellKnownSids + 6));
  v15 = RtlLengthSid(v13);
  v16 = v3 + v11 + v25 + v34 + v32 + v15 + v14;
  v17 = (struct _ACL *)LsapAllocate(v16);
  v5 = v17;
  if ( !v17 )
    goto LABEL_29;
  Acl = RtlCreateAcl(v17, v16, 2u);
  if ( Acl < 0 )
    goto LABEL_2;
  Acl = RtlAddAccessAllowedAce(v5, 2u, *((_DWORD *)&LsapDbState + 22 * a2[26] + 154), *((PSID *)WellKnownSids + 96));
  if ( Acl < 0 )
    goto LABEL_2;
  Acl = RtlAddAccessAllowedAce(v5, 2u, *((_DWORD *)&LsapDbState + 22 * a2[26] + 155), *((PSID *)WellKnownSids + 6));
  if ( Acl < 0 )
    goto LABEL_2;
  v18 = *((_DWORD *)&LsapDbState + 22 * a2[26] + 156);
  if ( v18 )
  {
    Acl = RtlAddAccessAllowedAce(v5, 2u, v18, *((PSID *)WellKnownSids + 108));
    if ( Acl < 0 )
      goto LABEL_2;
  }
  v19 = *((_DWORD *)&LsapDbState + 22 * a2[26] + 157);
  if ( v19 )
  {
    Acl = RtlAddAccessAllowedAce(v5, 2u, v19, *((PSID *)WellKnownSids + 156));
    if ( Acl < 0 )
      goto LABEL_2;
  }
  v20 = *((_DWORD *)&LsapDbState + 22 * a2[26] + 158);
  if ( v20 )
  {
    Acl = RtlAddAccessAllowedAce(v5, 2u, v20, *((PSID *)WellKnownSids + 162));
    if ( Acl < 0 )
      goto LABEL_2;
  }
  v21 = *((_DWORD *)&LsapDbState + 22 * a2[26] + 159);
  if ( v21 )
  {
    Acl = RtlAddAccessAllowedAce(v5, 2u, v21, *((PSID *)WellKnownSids + 168));
    if ( Acl < 0 )
      goto LABEL_2;
  }
  v22 = *((_DWORD *)&LsapDbState + 22 * a2[26] + 161);
  if ( v22 )
  {
    Acl = RtlAddAccessAllowedAce(v5, 2u, v22, *((PSID *)WellKnownSids + 288));
    if ( Acl < 0 )
      goto LABEL_2;
    Acl = RtlAddAccessAllowedAce(v5, 2u, *((_DWORD *)&LsapDbState + 22 * a2[26] + 161), *((PSID *)WellKnownSids + 450));
    if ( Acl < 0 )
      goto LABEL_2;
  }
  Acl = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, *(&LsapDbState + 11 * a2[26] + 81), 0);
  if ( Acl < 0 )
    goto LABEL_2;
  Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v5, 0);
  if ( Acl < 0 )
    goto LABEL_2;
  if ( !a1 )
  {
LABEL_44:
    v24 = a2[26];
    v9 = NewDescriptor;
    Acl = RtlNewSecurityObject(
            v6,
            SecurityDescriptor,
            NewDescriptor,
            0,
            TokenHandle,
            (PGENERIC_MAPPING)&qword_18019F3B8[11 * v24]);
    if ( Acl >= 0 )
      goto LABEL_5;
    goto LABEL_3;
  }
  v32 = 0;
  Acl = LsapDbReadAttributeObject(a1, &LsapDbNames, 0, &v32);
  if ( Acl < 0 )
    goto LABEL_2;
  v23 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v32);
  v6 = v23;
  if ( v23 )
  {
    Acl = LsapDbReadAttributeObject(a1, &LsapDbNames, v23, &v32);
    if ( Acl < 0 )
      goto LABEL_2;
    goto LABEL_44;
  }
LABEL_29:
  Acl = -1073741670;
LABEL_2:
  v9 = NewDescriptor;
LABEL_3:
  if ( *v9 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v9);
    *v9 = 0;
  }
LABEL_5:
  if ( v6 )
    LsapSubProv_FreeRoutine(v6, v7);
  if ( v5 )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v5, v7);
  if ( ProcessHandle )
    NtClose(ProcessHandle);
  if ( TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x18005365c  mov     [rsp-8+NewDescriptor], r8
0x180053661  mov     [rsp-8+arg_0], rcx
0x180053666  push    rbp
0x180053667  push    rbx
0x180053668  push    rsi
0x180053669  push    rdi
0x18005366a  push    r12
0x18005366c  push    r13
0x18005366e  push    r14
0x180053670  push    r15
0x180053672  lea     rbp, [rsp-1Fh]
0x180053677  sub     rsp, 0A8h
0x18005367e  xor     r12d, r12d
0x180053681  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180053689  xorps   xmm0, xmm0
0x18005368c  mov     [r8], r12
0x18005368f  xor     ecx, ecx
0x180053691  mov     [rbp+57h+ProcessHandle], r12
0x180053695  mov     [rbp+57h+var_78], rcx
0x180053699  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005369d  mov     [rbp+57h+TokenHandle], r12
0x1800536a1  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1800536a5  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r12
0x1800536a9  mov     rsi, rdx
0x1800536ac  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1800536b0  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1800536b4  mov     edx, 400h; DesiredAccess
0x1800536b9  movups  [rbp+57h+var_88], xmm0
0x1800536bd  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x1800536c1  mov     edi, r12d
0x1800536c4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800536c9  mov     r9, gs:30h
0x1800536d2  mov     r14d, r12d
0x1800536d5  add     r9, 40h ; '@'; ClientId
0x1800536d9  call    cs:__imp_NtOpenProcess
0x1800536e0  nop     dword ptr [rax+rax+00h]
0x1800536e5  mov     ebx, eax
0x1800536e7  test    eax, eax
0x1800536e9  jns     short loc_18005374A
0x1800536eb  mov     rsi, [rbp+57h+NewDescriptor]
0x1800536ef  mov     r8, [rsi]; P
0x1800536f2  test    r8, r8
0x1800536f5  jnz     loc_180053CA8
0x1800536fb  test    r14, r14
0x1800536fe  jnz     loc_180053CCB
0x180053704  test    rdi, rdi
0x180053707  jz      short loc_180053711
0x180053709  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x18005370c  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180053711  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x180053715  test    rcx, rcx
0x180053718  jz      short loc_180053726
0x18005371a  call    cs:__imp_NtClose
0x180053721  nop     dword ptr [rax+rax+00h]
0x180053726  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18005372a  test    rcx, rcx
0x18005372d  jnz     loc_180053B2C
0x180053733  mov     eax, ebx
0x180053735  add     rsp, 0A8h
0x18005373c  pop     r15
0x18005373e  pop     r14
0x180053740  pop     r13
0x180053742  pop     r12
0x180053744  pop     rdi
0x180053745  pop     rsi
0x180053746  pop     rbx
0x180053747  pop     rbp
0x180053748  retn
0x18005374a  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x18005374e  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180053752  mov     edx, 8; DesiredAccess
0x180053757  call    cs:__imp_NtOpenProcessToken
0x18005375e  nop     dword ptr [rax+rax+00h]
0x180053763  mov     ebx, eax
0x180053765  test    eax, eax
0x180053767  js      short loc_1800536EB
0x180053769  mov     edx, 1; Revision
0x18005376e  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180053772  call    cs:__imp_RtlCreateSecurityDescriptor
0x180053779  nop     dword ptr [rax+rax+00h]
0x18005377e  mov     ebx, eax
0x180053780  test    eax, eax
0x180053782  js      loc_1800536EB
0x180053788  movsxd  rax, dword ptr [rsi+68h]
0x18005378c  lea     rbx, ?LsapDbState@@3U_LSAP_DB_STATE@@A; _LSAP_DB_STATE LsapDbState
0x180053793  imul    rcx, rax, 58h ; 'X'
0x180053797  cmp     [rcx+rbx+270h], r12d
0x18005379f  jnz     loc_180053B07
0x1800537a5  mov     [rbp+57h+arg_8], r12d
0x1800537a9  movsxd  rax, dword ptr [rsi+68h]
0x1800537ad  imul    rcx, rax, 58h ; 'X'
0x1800537b1  cmp     [rcx+rbx+274h], r12d
0x1800537b9  jnz     loc_180053A9A
0x1800537bf  mov     [rbp+57h+arg_18], r12d
0x1800537c3  movsxd  rax, dword ptr [rsi+68h]
0x1800537c7  imul    rcx, rax, 58h ; 'X'
0x1800537cb  cmp     [rcx+rbx+278h], r12d
0x1800537d3  jnz     loc_180053ABF
0x1800537d9  mov     [rbp+57h+var_B0], r12d
0x1800537dd  movsxd  rax, dword ptr [rsi+68h]
0x1800537e1  imul    rcx, rax, 58h ; 'X'
0x1800537e5  cmp     [rcx+rbx+27Ch], r12d
0x1800537ed  jnz     loc_180053B3D
0x1800537f3  mov     r13d, r12d
0x1800537f6  movsxd  rax, dword ptr [rsi+68h]
0x1800537fa  imul    rcx, rax, 58h ; 'X'
0x1800537fe  cmp     [rcx+rbx+284h], r12d
0x180053806  jnz     loc_180053AE4
0x18005380c  movsxd  rax, dword ptr [rsi+68h]
0x180053810  imul    rcx, rax, 58h ; 'X'
0x180053814  cmp     [rcx+rbx+284h], edi
0x18005381b  jnz     loc_180053B60
0x180053821  mov     r15d, 1Ch
0x180053827  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005382e  mov     rdi, [rcx+300h]
0x180053835  mov     rcx, [rcx+30h]; Sid
0x180053839  call    cs:__imp_RtlLengthSid
0x180053840  nop     dword ptr [rax+rax+00h]
0x180053845  mov     rcx, rdi; Sid
0x180053848  lea     ebx, [r15+rax]
0x18005384c  call    cs:__imp_RtlLengthSid
0x180053853  nop     dword ptr [rax+rax+00h]
0x180053858  add     ebx, eax
0x18005385a  add     ebx, [rbp+57h+arg_8]
0x18005385d  add     ebx, [rbp+57h+arg_18]
0x180053860  add     ebx, [rbp+57h+var_B0]
0x180053863  add     ebx, r13d
0x180053866  add     ebx, r12d
0x180053869  mov     ecx, ebx
0x18005386b  call    LsapAllocate
0x180053870  xor     r12d, r12d
0x180053873  mov     rdi, rax
0x180053876  test    rax, rax
0x180053879  jnz     short loc_180053885
0x18005387b  mov     ebx, 0C000009Ah
0x180053880  jmp     loc_1800536EB
0x180053885  mov     r13d, 2
0x18005388b  mov     edx, ebx; AclSize
0x18005388d  mov     r8d, r13d; AclRevision
0x180053890  mov     rcx, rdi; Acl
0x180053893  call    cs:__imp_RtlCreateAcl
0x18005389a  nop     dword ptr [rax+rax+00h]
0x18005389f  mov     ebx, eax
0x1800538a1  test    eax, eax
0x1800538a3  js      loc_1800536EB
0x1800538a9  movsxd  rax, dword ptr [rsi+68h]
0x1800538ad  lea     r15, ?LsapDbState@@3U_LSAP_DB_STATE@@A; _LSAP_DB_STATE LsapDbState
0x1800538b4  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800538bb  mov     edx, r13d; Revision
0x1800538be  imul    r8, rax, 58h ; 'X'
0x1800538c2  mov     r9, [r9+300h]; Sid
0x1800538c9  mov     rcx, rdi; Acl
0x1800538cc  mov     r8d, [r8+r15+268h]; AccessMask
0x1800538d4  call    cs:__imp_RtlAddAccessAllowedAce
0x1800538db  nop     dword ptr [rax+rax+00h]
0x1800538e0  mov     ebx, eax
0x1800538e2  test    eax, eax
0x1800538e4  js      loc_1800536EB
0x1800538ea  movsxd  rax, dword ptr [rsi+68h]
0x1800538ee  mov     edx, r13d; Revision
0x1800538f1  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800538f8  mov     rcx, rdi; Acl
0x1800538fb  imul    r8, rax, 58h ; 'X'
0x1800538ff  mov     r9, [r9+30h]; Sid
0x180053903  mov     r8d, [r8+r15+26Ch]; AccessMask
0x18005390b  call    cs:__imp_RtlAddAccessAllowedAce
0x180053912  nop     dword ptr [rax+rax+00h]
0x180053917  mov     ebx, eax
0x180053919  test    eax, eax
0x18005391b  js      loc_1800536EB
0x180053921  movsxd  rax, dword ptr [rsi+68h]
0x180053925  imul    rcx, rax, 58h ; 'X'
0x180053929  mov     r8d, [rcx+r15+270h]; AccessMask
0x180053931  test    r8d, r8d
0x180053934  jnz     loc_180053B83
0x18005393a  movsxd  rax, dword ptr [rsi+68h]
0x18005393e  imul    rcx, rax, 58h ; 'X'
0x180053942  mov     r8d, [rcx+r15+274h]; AccessMask
0x18005394a  test    r8d, r8d
0x18005394d  jnz     loc_180053BB2
0x180053953  movsxd  rax, dword ptr [rsi+68h]
0x180053957  imul    rcx, rax, 58h ; 'X'
0x18005395b  mov     r8d, [rcx+r15+278h]; AccessMask
0x180053963  test    r8d, r8d
0x180053966  jnz     loc_180053BE1
0x18005396c  movsxd  rax, dword ptr [rsi+68h]
0x180053970  imul    rcx, rax, 58h ; 'X'
0x180053974  mov     r8d, [rcx+r15+27Ch]; AccessMask
0x18005397c  test    r8d, r8d
0x18005397f  jnz     loc_180053C10
0x180053985  movsxd  rax, dword ptr [rsi+68h]
0x180053989  imul    rcx, rax, 58h ; 'X'
0x18005398d  mov     r8d, [rcx+r15+284h]; AccessMask
0x180053995  test    r8d, r8d
0x180053998  jnz     loc_180053C3F
0x18005399e  movsxd  rax, dword ptr [rsi+68h]
0x1800539a2  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800539a6  imul    rdx, rax, 58h ; 'X'
0x1800539aa  xor     r8d, r8d; OwnerDefaulted
0x1800539ad  mov     rdx, [rdx+r15+288h]; Owner
0x1800539b5  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1800539bc  nop     dword ptr [rax+rax+00h]
0x1800539c1  mov     ebx, eax
0x1800539c3  test    eax, eax
0x1800539c5  js      loc_1800536EB
0x1800539cb  xor     r9d, r9d; DaclDefaulted
0x1800539ce  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800539d2  mov     r8, rdi; Dacl
0x1800539d5  mov     dl, 1; DaclPresent
0x1800539d7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800539de  nop     dword ptr [rax+rax+00h]
0x1800539e3  mov     ebx, eax
0x1800539e5  test    eax, eax
0x1800539e7  js      loc_1800536EB
0x1800539ed  mov     r15, [rbp+57h+arg_0]
0x1800539f1  test    r15, r15
0x1800539f4  jz      short loc_180053A4E
0x1800539f6  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x1800539fa  mov     [rbp+57h+arg_8], r12d
0x1800539fe  xor     r8d, r8d; void *
0x180053a01  lea     rdx, ?LsapDbNames@@3PAU_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x180053a08  mov     rcx, r15; void *
0x180053a0b  call    ?LsapDbReadAttributeObject@@YAJPEAXPEAU_UNICODE_STRING@@0PEAK@Z; LsapDbReadAttributeObject(void *,_UNICODE_STRING *,void *,ulong *)
0x180053a10  mov     ebx, eax
0x180053a12  test    eax, eax
0x180053a14  js      loc_1800536EB
0x180053a1a  mov     ecx, [rbp+57h+arg_8]
0x180053a1d  call    LsapAllocate
0x180053a22  mov     r14, rax
0x180053a25  test    rax, rax
0x180053a28  jz      loc_18005387B
0x180053a2e  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x180053a32  mov     r8, rax; void *
0x180053a35  lea     rdx, ?LsapDbNames@@3PAU_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x180053a3c  mov     rcx, r15; void *
0x180053a3f  call    ?LsapDbReadAttributeObject@@YAJPEAXPEAU_UNICODE_STRING@@0PEAK@Z; LsapDbReadAttributeObject(void *,_UNICODE_STRING *,void *,ulong *)
0x180053a44  mov     ebx, eax
0x180053a46  test    eax, eax
0x180053a48  js      loc_1800536EB
0x180053a4e  movsxd  rax, dword ptr [rsi+68h]
0x180053a52  lea     rdx, [rbp+57h+SecurityDescriptor]; CreatorDescriptor
0x180053a56  mov     rsi, [rbp+57h+NewDescriptor]
0x180053a5a  xor     r9d, r9d; IsDirectoryObject
0x180053a5d  imul    rcx, rax, 58h ; 'X'
0x180053a61  lea     rax, qword_18019F3B8
0x180053a68  mov     r8, rsi; NewDescriptor
0x180053a6b  add     rcx, rax
0x180053a6e  mov     rax, [rbp+57h+TokenHandle]
0x180053a72  mov     [rsp+0E0h+GenericMapping], rcx; GenericMapping
0x180053a77  mov     rcx, r14; ParentDescriptor
0x180053a7a  mov     [rsp+0E0h+Token], rax; Token
0x180053a7f  call    cs:__imp_RtlNewSecurityObject
0x180053a86  nop     dword ptr [rax+rax+00h]
0x180053a8b  mov     ebx, eax
0x180053a8d  test    eax, eax
0x180053a8f  jns     loc_1800536FB
0x180053a95  jmp     loc_1800536EF
0x180053a9a  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180053aa1  mov     rcx, [rcx+4E0h]; Sid
0x180053aa8  call    cs:__imp_RtlLengthSid
0x180053aaf  nop     dword ptr [rax+rax+00h]
0x180053ab4  add     eax, 0Ch
0x180053ab7  mov     [rbp+57h+arg_18], eax
0x180053aba  jmp     loc_1800537C3
0x180053abf  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180053ac6  mov     rcx, [rcx+510h]; Sid
0x180053acd  call    cs:__imp_RtlLengthSid
0x180053ad4  nop     dword ptr [rax+rax+00h]
0x180053ad9  add     eax, 0Ch
0x180053adc  mov     [rbp+57h+var_B0], eax
0x180053adf  jmp     loc_1800537DD
0x180053ae4  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180053aeb  mov     rcx, [rcx+900h]; Sid
0x180053af2  call    cs:__imp_RtlLengthSid
0x180053af9  nop     dword ptr [rax+rax+00h]
0x180053afe  lea     r12d, [rax+0Ch]
0x180053b02  jmp     loc_18005380C
0x180053b07  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180053b0e  mov     rcx, [rcx+360h]; Sid
0x180053b15  call    cs:__imp_RtlLengthSid
0x180053b1c  nop     dword ptr [rax+rax+00h]
0x180053b21  add     eax, 0Ch
0x180053b24  mov     [rbp+57h+arg_8], eax
0x180053b27  jmp     loc_1800537A9
0x180053b2c  call    cs:__imp_NtClose
0x180053b33  nop     dword ptr [rax+rax+00h]
0x180053b38  jmp     loc_180053733
0x180053b3d  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180053b44  mov     rcx, [rcx+540h]; Sid
0x180053b4b  call    cs:__imp_RtlLengthSid
0x180053b52  nop     dword ptr [rax+rax+00h]
0x180053b57  lea     r13d, [rax+0Ch]
0x180053b5b  jmp     loc_1800537F6
0x180053b60  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180053b67  mov     rcx, [rcx+0E10h]; Sid
0x180053b6e  call    cs:__imp_RtlLengthSid
0x180053b75  nop     dword ptr [rax+rax+00h]
0x180053b7a  lea     r15d, [rax+28h]
0x180053b7e  jmp     loc_180053827
0x180053b83  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
  ... truncated ...
```
