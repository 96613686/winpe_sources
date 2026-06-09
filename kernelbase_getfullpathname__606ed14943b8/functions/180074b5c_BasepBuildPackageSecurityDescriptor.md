# BasepBuildPackageSecurityDescriptor

- ea: `0x180074b5c`
- end: `0x1800751d8`
- name: `BasepBuildPackageSecurityDescriptor`
- size: `1660`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR SecurityDescriptor@<rcx>, PSID Sid@<rdx>, PSID Sid1@<r8>, PSECURITY_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180073a2c`

## callees

- `0x180074b5c`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x180074f58`
- `ntdll!RtlSubAuthoritySid` at `0x180074f58`
- `ntdll!RtlEqualSid` at `0x180074cd8`
- `ntdll!RtlEqualSid` at `0x180074cd8`
- `ntdll!RtlGetAce` at `0x180074cbd`
- `ntdll!RtlGetAce` at `0x180074d78`
- `ntdll!RtlGetAce` at `0x180074dcb`
- `ntdll!RtlGetAce` at `0x180074cbd`
- `ntdll!RtlGetAce` at `0x180074d78`
- `ntdll!RtlGetAce` at `0x180074dcb`
- `ntdll!RtlQueryInformationAcl` at `0x180074c33`
- `ntdll!RtlQueryInformationAcl` at `0x180074c58`
- `ntdll!RtlQueryInformationAcl` at `0x180074c33`
- `ntdll!RtlQueryInformationAcl` at `0x180074c58`
- `ntdll!RtlSubAuthorityCountSid` at `0x180074f3e`
- `ntdll!RtlSubAuthorityCountSid` at `0x180074f3e`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180074c0f`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180074c0f`
- `ntdll!RtlCreateAcl` at `0x180074d58`
- `ntdll!RtlCreateAcl` at `0x180074d58`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180074e6b`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180074ea0`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180074ed2`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180074f02`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800751b4`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180074e6b`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180074ea0`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180074ed2`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180074f02`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800751b4`
- `ntdll!RtlAddAce` at `0x180074da5`
- `ntdll!RtlAddAce` at `0x180074da5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180074bec`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180074bec`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800750c8`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800750c8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180074fbf`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180075024`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180075086`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180074fbf`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180075024`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180075086`
- `ntdll!RtlLengthSid` at `0x180074c71`
- `ntdll!RtlLengthSid` at `0x180074cf7`
- `ntdll!RtlLengthSid` at `0x180074fdb`
- `ntdll!RtlLengthSid` at `0x180075040`
- `ntdll!RtlLengthSid` at `0x18007509f`
- `ntdll!RtlLengthSid` at `0x180074c71`
- `ntdll!RtlLengthSid` at `0x180074cf7`
- `ntdll!RtlLengthSid` at `0x180074fdb`
- `ntdll!RtlLengthSid` at `0x180075040`
- `ntdll!RtlLengthSid` at `0x18007509f`
- `ntdll!RtlFreeHeap` at `0x180074f2a`
- `ntdll!RtlFreeHeap` at `0x1800750f7`
- `ntdll!RtlFreeHeap` at `0x18007511c`
- `ntdll!RtlFreeHeap` at `0x180075141`
- `ntdll!RtlFreeHeap` at `0x180074f2a`
- `ntdll!RtlFreeHeap` at `0x1800750f7`
- `ntdll!RtlFreeHeap` at `0x18007511c`
- `ntdll!RtlFreeHeap` at `0x180075141`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180074df3`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180074df3`
- `ntdll!RtlAddAccessAllowedAce` at `0x180074e41`
- `ntdll!RtlAddAccessAllowedAce` at `0x18007518a`
- `ntdll!RtlAddAccessAllowedAce` at `0x180074e41`
- `ntdll!RtlAddAccessAllowedAce` at `0x18007518a`
- `ntdll!RtlAllocateHeap` at `0x180074d28`
- `ntdll!RtlAllocateHeap` at `0x180074d28`

## pseudocode

```c
NTSTATUS __fastcall BasepBuildPackageSecurityDescriptor(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        PSID Sid,
        PSID Sid1,
        char a4,
        PSECURITY_DESCRIPTOR SecurityDescriptora)
{
  ULONG v5; // esi
  NTSTATUS result; // eax
  NTSTATUS Acl; // ebx
  ULONG v12; // eax
  int v13; // r12d
  int v14; // edi
  int v15; // r13d
  int v16; // r15d
  ULONG i; // ebx
  char v18; // r14
  ULONG v19; // ebx
  ACL *Heap; // rax
  ACL *v21; // rdi
  ULONG j; // ebx
  char *v23; // rsi
  PSID_IDENTIFIER_AUTHORITY v24; // rax
  int v25; // ecx
  PSID v26; // rsi
  PSID v27; // rsi
  ULONG AclRevision; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+64h] [rbp-6Dh] BYREF
  unsigned __int8 DaclPresent[3]; // [rsp+65h] [rbp-6Ch] BYREF
  int v31; // [rsp+68h] [rbp-69h]
  unsigned __int16 v32; // [rsp+6Ch] [rbp-65h]
  PACL Dacl; // [rsp+70h] [rbp-61h] BYREF
  PVOID Ace; // [rsp+78h] [rbp-59h] BYREF
  PSID P; // [rsp+80h] [rbp-51h] BYREF
  PSID v36; // [rsp+88h] [rbp-49h] BYREF
  PSID v37; // [rsp+90h] [rbp-41h] BYREF
  int v38; // [rsp+98h] [rbp-39h]
  PVOID AceList; // [rsp+A0h] [rbp-31h] BYREF
  PSID Sida; // [rsp+A8h] [rbp-29h]
  PSID pSid; // [rsp+B0h] [rbp-21h]
  PSECURITY_DESCRIPTOR v42; // [rsp+B8h] [rbp-19h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C0h] [rbp-11h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v44; // [rsp+C8h] [rbp-9h] BYREF
  __int64 Information; // [rsp+D0h] [rbp-1h] BYREF
  int v46; // [rsp+D8h] [rbp+7h]

  v5 = 0;
  pSid = Sid;
  Sida = Sid1;
  Information = 0;
  v46 = 0;
  v42 = SecurityDescriptora;
  AceList = 0;
  AclRevision = 0;
  Ace = 0;
  Dacl = 0;
  DaclDefaulted = 0;
  DaclPresent[0] = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v44.Value = 0;
  *(_WORD *)&v44.Value[4] = 256;
  P = 0;
  v37 = 0;
  v36 = 0;
  result = RtlCreateSecurityDescriptor(SecurityDescriptora, 1u);
  if ( result < 0 )
    return result;
  result = RtlGetDaclSecurityDescriptor(SecurityDescriptor, DaclPresent, &Dacl, &DaclDefaulted);
  if ( result < 0 )
    return result;
  Acl = RtlQueryInformationAcl(Dacl, &Information, 0xCu, AclSizeInformation);
  if ( Acl >= 0 )
  {
    Acl = RtlQueryInformationAcl(Dacl, &AclRevision, 4u, AclRevisionInformation);
    if ( Acl >= 0 )
    {
      v12 = RtlLengthSid(Sid);
      v13 = HIDWORD(Information) + 2 * v12;
      v38 = a4 & 1;
      if ( (a4 & 1) != 0 )
      {
        Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &P);
        if ( Acl < 0 )
          goto LABEL_49;
        v14 = 1;
        v5 = RtlLengthSid(P);
      }
      else
      {
        v14 = 0;
      }
      v15 = a4 & 4;
      if ( (a4 & 4) != 0 )
      {
        Acl = RtlAllocateAndInitializeSid(&v44, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v36);
        if ( Acl < 0 )
          goto LABEL_49;
        ++v14;
        v5 += RtlLengthSid(v36);
      }
      v16 = a4 & 2;
      if ( !v16 )
        goto LABEL_9;
      Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v37);
      if ( Acl >= 0 )
      {
        ++v14;
        v5 += RtlLengthSid(v37);
LABEL_9:
        for ( i = 0; ; ++i )
        {
          if ( i >= (unsigned int)Information || RtlGetAce(Dacl, i, &Ace) < 0 )
          {
            v18 = 0;
            v14 += 2;
            v5 += 2 * RtlLengthSid(Sida);
            goto LABEL_15;
          }
          if ( RtlEqualSid(Sid1, (char *)Ace + 8) )
            break;
        }
        v18 = 1;
LABEL_15:
        v19 = (v5 + v13 + 19 + 8 * v14) & 0xFFFFFFFC;
        Heap = (ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
        v21 = Heap;
        if ( !Heap )
          return -1073741801;
        memset_0(Heap, 0, v19);
        Acl = RtlCreateAcl(v21, v19, AclRevision);
        if ( Acl < 0 )
          goto LABEL_34;
        Acl = RtlGetAce(Dacl, 0, &AceList);
        if ( Acl < 0 )
          goto LABEL_34;
        Acl = RtlAddAce(v21, AclRevision, 0, AceList, HIDWORD(Information) - 8);
        if ( Acl < 0 )
          goto LABEL_34;
        for ( j = 0; j < (unsigned int)Information; ++j )
        {
          if ( RtlGetAce(v21, j, &Ace) < 0 )
            break;
          v23 = (char *)Ace + 8;
          v31 = 0;
          v32 = 1280;
          v24 = RtlIdentifierAuthoritySid((char *)Ace + 8);
          v25 = -*(_DWORD *)v24->Value;
          if ( !*(_DWORD *)v24->Value )
            v25 = v32 - *(unsigned __int16 *)&v24->Value[4];
          if ( !v25
            && *RtlSubAuthorityCountSid(v23) == 3
            && *RtlSubAuthoritySid(v23, 0) == 5
            && (*((_BYTE *)Ace + 1) & 8) == 0 )
          {
            *((_DWORD *)Ace + 1) = 983055;
          }
        }
        if ( !v18 )
        {
          v27 = Sida;
          Acl = RtlAddAccessAllowedAce(v21, AclRevision, 0xF000Fu, Sida);
          if ( Acl < 0 )
            goto LABEL_34;
          Acl = RtlAddAccessAllowedAceEx(v21, AclRevision, 0xBu, 0x10000000u, v27);
          if ( Acl < 0 )
            goto LABEL_34;
        }
        if ( (v26 = pSid, Acl = RtlAddAccessAllowedAce(v21, AclRevision, 0xF000Fu, pSid), Acl < 0)
          || (Acl = RtlAddAccessAllowedAceEx(v21, AclRevision, 0xBu, 0x10000000u, v26), Acl < 0)
          || v38 && (Acl = RtlAddAccessAllowedAceEx(v21, AclRevision, 0xBu, 0x10000000u, P), Acl < 0)
          || v15 && (Acl = RtlAddAccessAllowedAceEx(v21, AclRevision, 0xBu, 0xA0000000, v36), Acl < 0)
          || v16 && (Acl = RtlAddAccessAllowedAceEx(v21, AclRevision, 0xBu, 0xA0000000, v37), Acl < 0)
          || (Acl = RtlSetDaclSecurityDescriptor(v42, 1u, v21, 0), Acl < 0) )
        {
LABEL_34:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
        }
      }
    }
  }
LABEL_49:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v36 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v36);
  if ( v37 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
  return Acl;
}

```

## disassembly

```asm
0x180074b5c  mov     [rsp-8+arg_18], rbx
0x180074b61  push    rbp
0x180074b62  push    rsi
0x180074b63  push    rdi
0x180074b64  push    r12
0x180074b66  push    r13
0x180074b68  push    r14
0x180074b6a  push    r15
0x180074b6c  lea     rbp, [rsp-1Fh]
0x180074b71  sub     rsp, 0F0h
0x180074b78  mov     rax, cs:__security_cookie
0x180074b7f  xor     rax, rsp
0x180074b82  mov     [rbp+4Fh+var_40], rax
0x180074b86  mov     rax, [rbp+4Fh+SecurityDescriptor]
0x180074b8a  xor     esi, esi
0x180074b8c  mov     rbx, rcx
0x180074b8f  mov     [rbp+4Fh+pSid], rdx
0x180074b93  xor     ecx, ecx
0x180074b95  mov     [rbp+4Fh+Sid], r8
0x180074b99  mov     rdi, rdx
0x180074b9c  mov     [rbp+4Fh+Information], rcx
0x180074ba0  mov     [rbp+4Fh+var_48], ecx
0x180074ba3  lea     r13d, [rsi+1]
0x180074ba7  mov     edx, r13d; Revision
0x180074baa  mov     [rbp+4Fh+var_68], rax
0x180074bae  mov     rcx, rax; SecurityDescriptor
0x180074bb1  mov     [rbp+4Fh+AceList], rsi
0x180074bb5  mov     r15d, r9d
0x180074bb8  mov     [rbp+4Fh+AclRevision], esi
0x180074bbb  mov     r14, r8
0x180074bbe  mov     [rbp+4Fh+Ace], rsi
0x180074bc2  mov     [rbp+4Fh+Dacl], rsi
0x180074bc6  mov     [rbp+4Fh+DaclDefaulted], sil
0x180074bca  mov     [rbp+4Fh+DaclPresent], sil
0x180074bce  mov     dword ptr [rbp+4Fh+IdentifierAuthority.Value], esi
0x180074bd1  mov     word ptr [rbp+4Fh+IdentifierAuthority.Value+4], 500h
0x180074bd7  mov     dword ptr [rbp+4Fh+var_58.Value], esi
0x180074bda  mov     word ptr [rbp+4Fh+var_58.Value+4], 100h
0x180074be0  mov     [rbp+4Fh+P], rsi
0x180074be4  mov     [rbp+4Fh+var_90], rsi
0x180074be8  mov     [rbp+4Fh+var_98], rsi
0x180074bec  call    cs:__imp_RtlCreateSecurityDescriptor
0x180074bf3  nop     dword ptr [rax+rax+00h]
0x180074bf8  test    eax, eax
0x180074bfa  js      loc_18007514F
0x180074c00  lea     r9, [rbp+4Fh+DaclDefaulted]; DaclDefaulted
0x180074c04  mov     rcx, rbx; SecurityDescriptor
0x180074c07  lea     r8, [rbp+4Fh+Dacl]; Dacl
0x180074c0b  lea     rdx, [rbp+4Fh+DaclPresent]; DaclPresent
0x180074c0f  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180074c16  nop     dword ptr [rax+rax+00h]
0x180074c1b  test    eax, eax
0x180074c1d  js      loc_18007514F
0x180074c23  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x180074c27  lea     r9d, [rsi+2]; InformationClass
0x180074c2b  lea     r8d, [rsi+0Ch]; InformationLength
0x180074c2f  lea     rdx, [rbp+4Fh+Information]; Information
0x180074c33  call    cs:__imp_RtlQueryInformationAcl
0x180074c3a  nop     dword ptr [rax+rax+00h]
0x180074c3f  mov     ebx, eax
0x180074c41  test    eax, eax
0x180074c43  js      loc_1800750DE
0x180074c49  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x180074c4d  lea     r8d, [rsi+4]; InformationLength
0x180074c51  mov     r9d, r13d; InformationClass
0x180074c54  lea     rdx, [rbp+4Fh+AclRevision]; Information
0x180074c58  call    cs:__imp_RtlQueryInformationAcl
0x180074c5f  nop     dword ptr [rax+rax+00h]
0x180074c64  mov     ebx, eax
0x180074c66  test    eax, eax
0x180074c68  js      loc_1800750DE
0x180074c6e  mov     rcx, rdi; Sid
0x180074c71  call    cs:__imp_RtlLengthSid
0x180074c78  nop     dword ptr [rax+rax+00h]
0x180074c7d  mov     ecx, dword ptr [rbp+4Fh+Information+4]
0x180074c80  lea     r12d, [rcx+rax*2]
0x180074c84  mov     eax, r15d
0x180074c87  and     eax, r13d
0x180074c8a  mov     [rbp+4Fh+var_88], eax
0x180074c8d  jnz     loc_180075053
0x180074c93  mov     edi, esi
0x180074c95  mov     r13d, r15d
0x180074c98  and     r13d, 4
0x180074c9c  jnz     loc_180074FF5
0x180074ca2  and     r15d, 2
0x180074ca6  jnz     loc_180074F8F
0x180074cac  xor     ebx, ebx
0x180074cae  cmp     ebx, dword ptr [rbp+4Fh+Information]
0x180074cb1  jnb     short loc_180074CF0
0x180074cb3  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x180074cb7  lea     r8, [rbp+4Fh+Ace]; Ace
0x180074cbb  mov     edx, ebx; AceIndex
0x180074cbd  call    cs:__imp_RtlGetAce
0x180074cc4  nop     dword ptr [rax+rax+00h]
0x180074cc9  test    eax, eax
0x180074ccb  js      short loc_180074CF0
0x180074ccd  mov     rdx, [rbp+4Fh+Ace]
0x180074cd1  mov     rcx, r14; Sid1
0x180074cd4  add     rdx, 8; Sid2
0x180074cd8  call    cs:__imp_RtlEqualSid
0x180074cdf  nop     dword ptr [rax+rax+00h]
0x180074ce4  test    al, al
0x180074ce6  jnz     loc_180074F87
0x180074cec  inc     ebx
0x180074cee  jmp     short loc_180074CAE
0x180074cf0  mov     rcx, [rbp+4Fh+Sid]; Sid
0x180074cf4  xor     r14b, r14b
0x180074cf7  call    cs:__imp_RtlLengthSid
0x180074cfe  nop     dword ptr [rax+rax+00h]
0x180074d03  add     edi, 2
0x180074d06  lea     esi, [rsi+rax*2]
0x180074d09  mov     rcx, gs:60h
0x180074d12  lea     ebx, [r12+13h]
0x180074d17  lea     ebx, [rbx+rdi*8]
0x180074d1a  xor     edx, edx; Flags
0x180074d1c  add     ebx, esi
0x180074d1e  and     ebx, 0FFFFFFFCh
0x180074d21  mov     rcx, [rcx+30h]; HeapHandle
0x180074d25  mov     r8d, ebx; Size
0x180074d28  call    cs:__imp_RtlAllocateHeap
0x180074d2f  nop     dword ptr [rax+rax+00h]
0x180074d34  xor     esi, esi
0x180074d36  mov     rdi, rax
0x180074d39  test    rax, rax
0x180074d3c  jz      loc_1800750B2
0x180074d42  mov     r8d, ebx; Size
0x180074d45  xor     edx, edx; Val
0x180074d47  mov     rcx, rax; void *
0x180074d4a  call    memset_0
0x180074d4f  mov     r8d, [rbp+4Fh+AclRevision]; AclRevision
0x180074d53  mov     edx, ebx; AclSize
0x180074d55  mov     rcx, rdi; Acl
0x180074d58  call    cs:__imp_RtlCreateAcl
0x180074d5f  nop     dword ptr [rax+rax+00h]
0x180074d64  mov     ebx, eax
0x180074d66  test    eax, eax
0x180074d68  js      loc_180074F18
0x180074d6e  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x180074d72  lea     r8, [rbp+4Fh+AceList]; Ace
0x180074d76  xor     edx, edx; AceIndex
0x180074d78  call    cs:__imp_RtlGetAce
0x180074d7f  nop     dword ptr [rax+rax+00h]
0x180074d84  mov     ebx, eax
0x180074d86  test    eax, eax
0x180074d88  js      loc_180074F18
0x180074d8e  mov     eax, dword ptr [rbp+4Fh+Information+4]
0x180074d91  xor     r8d, r8d; StartingAceIndex
0x180074d94  mov     r9, [rbp+4Fh+AceList]; AceList
0x180074d98  add     eax, 0FFFFFFF8h
0x180074d9b  mov     edx, [rbp+4Fh+AclRevision]; AceRevision
0x180074d9e  mov     rcx, rdi; Acl
0x180074da1  mov     [rsp+120h+AceListLength], eax; AceListLength
0x180074da5  call    cs:__imp_RtlAddAce
0x180074dac  nop     dword ptr [rax+rax+00h]
0x180074db1  mov     ebx, eax
0x180074db3  test    eax, eax
0x180074db5  js      loc_180074F18
0x180074dbb  mov     ebx, esi
0x180074dbd  cmp     dword ptr [rbp+4Fh+Information], esi
0x180074dc0  jbe     short loc_180074E1F
0x180074dc2  lea     r8, [rbp+4Fh+Ace]; Ace
0x180074dc6  mov     edx, ebx; AceIndex
0x180074dc8  mov     rcx, rdi; Acl
0x180074dcb  call    cs:__imp_RtlGetAce
0x180074dd2  nop     dword ptr [rax+rax+00h]
0x180074dd7  test    eax, eax
0x180074dd9  js      short loc_180074E1F
0x180074ddb  mov     rsi, [rbp+4Fh+Ace]
0x180074ddf  xor     r12d, r12d
0x180074de2  add     rsi, 8
0x180074de6  mov     [rbp+4Fh+var_B8], r12d
0x180074dea  mov     rcx, rsi; Sid
0x180074ded  mov     [rbp+4Fh+var_B4], 500h
0x180074df3  call    cs:__imp_RtlIdentifierAuthoritySid
0x180074dfa  nop     dword ptr [rax+rax+00h]
0x180074dff  mov     ecx, r12d
0x180074e02  sub     ecx, [rax]
0x180074e04  jnz     short loc_180074E10
0x180074e06  movzx   ecx, [rbp+4Fh+var_B4]
0x180074e0a  movzx   eax, word ptr [rax+4]
0x180074e0e  sub     ecx, eax
0x180074e10  test    ecx, ecx
0x180074e12  jz      loc_180074F3B
0x180074e18  inc     ebx
0x180074e1a  cmp     ebx, dword ptr [rbp+4Fh+Information]
0x180074e1d  jb      short loc_180074DC2
0x180074e1f  mov     r12d, 0Bh
0x180074e25  test    r14b, r14b
0x180074e28  jz      loc_180075177
0x180074e2e  mov     rsi, [rbp+4Fh+pSid]
0x180074e32  mov     r8d, 0F000Fh; AccessMask
0x180074e38  mov     edx, [rbp+4Fh+AclRevision]; Revision
0x180074e3b  mov     r9, rsi; Sid
0x180074e3e  mov     rcx, rdi; Acl
0x180074e41  call    cs:__imp_RtlAddAccessAllowedAce
0x180074e48  nop     dword ptr [rax+rax+00h]
0x180074e4d  mov     ebx, eax
0x180074e4f  test    eax, eax
0x180074e51  js      loc_180074FEE
0x180074e57  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x180074e5a  mov     r9d, 10000000h; AccessMask
0x180074e60  mov     r8d, r12d; AceFlags
0x180074e63  mov     qword ptr [rsp+120h+AceListLength], rsi; pSid
0x180074e68  mov     rcx, rdi; pAcl
0x180074e6b  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180074e72  nop     dword ptr [rax+rax+00h]
0x180074e77  xor     esi, esi
0x180074e79  mov     ebx, eax
0x180074e7b  test    eax, eax
0x180074e7d  js      loc_180074F18
0x180074e83  cmp     [rbp+4Fh+var_88], esi
0x180074e86  jz      short loc_180074EB2
0x180074e88  mov     rax, [rbp+4Fh+P]
0x180074e8c  mov     r9d, 10000000h; AccessMask
0x180074e92  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x180074e95  mov     r8d, r12d; AceFlags
0x180074e98  mov     rcx, rdi; pAcl
0x180074e9b  mov     qword ptr [rsp+120h+AceListLength], rax; pSid
0x180074ea0  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180074ea7  nop     dword ptr [rax+rax+00h]
0x180074eac  mov     ebx, eax
0x180074eae  test    eax, eax
0x180074eb0  js      short loc_180074F18
0x180074eb2  mov     r14d, 0A0000000h
0x180074eb8  test    r13d, r13d
0x180074ebb  jz      short loc_180074EE4
0x180074ebd  mov     rax, [rbp+4Fh+var_98]
0x180074ec1  mov     r9d, r14d; AccessMask
0x180074ec4  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x180074ec7  mov     r8d, r12d; AceFlags
0x180074eca  mov     rcx, rdi; pAcl
0x180074ecd  mov     qword ptr [rsp+120h+AceListLength], rax; pSid
0x180074ed2  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180074ed9  nop     dword ptr [rax+rax+00h]
0x180074ede  mov     ebx, eax
0x180074ee0  test    eax, eax
0x180074ee2  js      short loc_180074F18
0x180074ee4  test    r15d, r15d
0x180074ee7  jz      loc_1800750BC
0x180074eed  mov     rax, [rbp+4Fh+var_90]
0x180074ef1  mov     r9d, r14d; AccessMask
0x180074ef4  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x180074ef7  mov     r8d, r12d; AceFlags
0x180074efa  mov     rcx, rdi; pAcl
0x180074efd  mov     qword ptr [rsp+120h+AceListLength], rax; pSid
0x180074f02  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180074f09  nop     dword ptr [rax+rax+00h]
0x180074f0e  mov     ebx, eax
0x180074f10  test    eax, eax
0x180074f12  jns     loc_1800750BC
0x180074f18  mov     rcx, gs:60h
0x180074f21  mov     r8, rdi; P
0x180074f24  xor     edx, edx; Flags
0x180074f26  mov     rcx, [rcx+30h]; HeapHandle
0x180074f2a  call    cs:__imp_RtlFreeHeap
0x180074f31  nop     dword ptr [rax+rax+00h]
0x180074f36  jmp     loc_1800750DE
0x180074f3b  mov     rcx, rsi; Sid
0x180074f3e  call    cs:__imp_RtlSubAuthorityCountSid
0x180074f45  nop     dword ptr [rax+rax+00h]
0x180074f4a  cmp     byte ptr [rax], 3
0x180074f4d  jnz     loc_180074E18
0x180074f53  xor     edx, edx; SubAuthority
0x180074f55  mov     rcx, rsi; Sid
0x180074f58  call    cs:__imp_RtlSubAuthoritySid
0x180074f5f  nop     dword ptr [rax+rax+00h]
0x180074f64  cmp     dword ptr [rax], 5
0x180074f67  jnz     loc_180074E18
0x180074f6d  mov     rax, [rbp+4Fh+Ace]
0x180074f71  test    byte ptr [rax+1], 8
0x180074f75  jnz     loc_180074E18
0x180074f7b  mov     dword ptr [rax+4], 0F000Fh
0x180074f82  jmp     loc_180074E18
0x180074f87  mov     r14b, 1
0x180074f8a  jmp     loc_180074D09
0x180074f8f  lea     rax, [rbp+4Fh+var_90]
0x180074f93  xor     r9d, r9d; SubAuthority1
0x180074f96  mov     [rsp+120h+var_D0], rax; Sid
0x180074f9b  lea     rcx, [rbp+4Fh+IdentifierAuthority]; IdentifierAuthority
0x180074f9f  xor     eax, eax
0x180074fa1  mov     dl, 1; SubAuthorityCount
0x180074fa3  mov     [rsp+120h+SubAuthority7], eax; SubAuthority7
0x180074fa7  mov     [rsp+120h+SubAuthority6], eax; SubAuthority6
0x180074fab  mov     [rsp+120h+SubAuthority5], eax; SubAuthority5
0x180074faf  mov     [rsp+120h+SubAuthority4], eax; SubAuthority4
0x180074fb3  lea     r8d, [rax+0Ch]; SubAuthority0
0x180074fb7  mov     [rsp+120h+SubAuthority3], eax; SubAuthority3
0x180074fbb  mov     [rsp+120h+AceListLength], eax; SubAuthority2
0x180074fbf  call    cs:__imp_RtlAllocateAndInitializeSid
0x180074fc6  nop     dword ptr [rax+rax+00h]
0x180074fcb  mov     ebx, eax
0x180074fcd  test    eax, eax
0x180074fcf  js      loc_1800751D1
0x180074fd5  mov     rcx, [rbp+4Fh+var_90]; Sid
0x180074fd9  inc     edi
0x180074fdb  call    cs:__imp_RtlLengthSid
0x180074fe2  nop     dword ptr [rax+rax+00h]
0x180074fe7  add     esi, eax
0x180074fe9  jmp     loc_180074CAC
0x180074fee  xor     esi, esi
  ... truncated ...
```
