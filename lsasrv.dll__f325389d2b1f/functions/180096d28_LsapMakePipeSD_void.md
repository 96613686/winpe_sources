# LsapMakePipeSD(void * *)

- ea: `0x180096d28`
- end: `0x180097131`
- name: `?LsapMakePipeSD@@YAJPEAPEAX@Z`
- size: `1033`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800aeac4`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x180096d28`
- `0x1800b86d0`
- `0x1800b9304`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180096de5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180096de5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180096dcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180096dcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800970de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800970de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180097090`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180097090`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180096e1c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180096e1c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180096db6`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180096db6`
- `ntdll!RtlAddMandatoryAce` at `0x180097030`
- `ntdll!RtlAddMandatoryAce` at `0x180097030`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180097052`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180097052`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180096f93`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180096f93`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180096e9d`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180096e9d`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180097073`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800970b3`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180097073`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800970b3`
- `ntdll!RtlFreeSid` at `0x1800970ef`
- `ntdll!RtlFreeSid` at `0x1800970ef`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180096fdc`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180096fdc`
- `ntdll!RtlAddAccessAllowedAce` at `0x180096ef2`
- `ntdll!RtlAddAccessAllowedAce` at `0x180096f1f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180096f4c`
- `ntdll!RtlAddAccessAllowedAce` at `0x180096f72`
- `ntdll!RtlAddAccessAllowedAce` at `0x180096ef2`
- `ntdll!RtlAddAccessAllowedAce` at `0x180096f1f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180096f4c`
- `ntdll!RtlAddAccessAllowedAce` at `0x180096f72`
- `ntdll!RtlCreateAcl` at `0x180096ec2`
- `ntdll!RtlCreateAcl` at `0x180096ffe`
- `ntdll!RtlCreateAcl` at `0x180096ec2`
- `ntdll!RtlCreateAcl` at `0x180096ffe`
- `ntdll!RtlLengthSid` at `0x180096e41`
- `ntdll!RtlLengthSid` at `0x180096e53`
- `ntdll!RtlLengthSid` at `0x180096e6d`
- `ntdll!RtlLengthSid` at `0x180096e41`
- `ntdll!RtlLengthSid` at `0x180096e53`
- `ntdll!RtlLengthSid` at `0x180096e6d`

## pseudocode

```c
__int64 __fastcall LsapMakePipeSD(void **a1)
{
  struct _RTL_BALANCED_NODE *v2; // rax
  struct _RTL_BALANCED_NODE *v3; // rsi
  struct _ACL *v5; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  HANDLE CurrentProcess; // rax
  void *v8; // rbx
  ULONG v9; // r14d
  ULONG v10; // r14d
  ULONG v11; // r14d
  HLOCAL v12; // rax
  void *v13; // r14
  void *v14; // rdx
  void *v15; // rdx
  void *SubAuthority3; // [rsp+28h] [rbp-D8h]
  ULONG BufferLength; // [rsp+60h] [rbp-A0h] BYREF
  DWORD TokenInformationLength; // [rsp+64h] [rbp-9Ch] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+80h] [rbp-80h] BYREF
  struct _ACL Acl; // [rsp+E0h] [rbp-20h] BYREF

  TokenInformationLength = 76;
  TokenHandle = 0;
  BufferLength = 0;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  memset_0(&Acl, 0, 0x200u);
  v2 = (struct _RTL_BALANCED_NODE *)LsapAllocate(40);
  v3 = v2;
  if ( !v2 )
    return 3221225495LL;
  v5 = 0;
  SecurityDescriptor = RtlCreateSecurityDescriptor(v2, 1u);
  if ( SecurityDescriptor >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
      goto LABEL_5;
    if ( !GetTokenInformation(
            TokenHandle,
            TokenOwner,
            TokenInformation,
            TokenInformationLength,
            &TokenInformationLength) )
      goto LABEL_5;
    v8 = (void *)*((_QWORD *)WellKnownSids + 108);
    v9 = RtlLengthSid(*((PSID *)WellKnownSids + 336));
    v10 = RtlLengthSid(v8) + v9;
    v11 = RtlLengthSid(*((PSID *)WellKnownSids + 6)) + 124 + v10;
    v5 = (struct _ACL *)LsapAllocate(v11);
    if ( !v5 )
      goto LABEL_5;
    SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v3, TokenInformation[0], 0);
    if ( SecurityDescriptor < 0 )
      goto LABEL_25;
    SecurityDescriptor = RtlCreateAcl(v5, v11, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_25;
    SecurityDescriptor = RtlAddAccessAllowedAce(v5, 2u, 0x12019Bu, *((PSID *)WellKnownSids + 6));
    if ( SecurityDescriptor < 0 )
      goto LABEL_25;
    SecurityDescriptor = RtlAddAccessAllowedAce(v5, 2u, 0x12019Bu, *((PSID *)WellKnownSids + 108));
    if ( SecurityDescriptor < 0 )
      goto LABEL_25;
    SecurityDescriptor = RtlAddAccessAllowedAce(v5, 2u, 0x12019Bu, *((PSID *)WellKnownSids + 336));
    if ( SecurityDescriptor < 0 )
      goto LABEL_25;
    SecurityDescriptor = RtlAddAccessAllowedAce(v5, 2u, 0x1F01FFu, TokenInformation[0]);
    if ( SecurityDescriptor < 0 )
      goto LABEL_25;
    if ( RtlSetDaclSecurityDescriptor(v3, 1u, v5, 0) < 0 )
    {
LABEL_5:
      SecurityDescriptor = -1073741801;
      goto LABEL_25;
    }
    SecurityDescriptor = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( SecurityDescriptor >= 0 )
    {
      SecurityDescriptor = RtlCreateAcl(&Acl, 0x200u, 2u);
      if ( SecurityDescriptor >= 0 )
      {
        LODWORD(SubAuthority3) = 1;
        SecurityDescriptor = RtlAddMandatoryAce(&Acl, 2u, 0, (ULONG)Sid, 0x11u, SubAuthority3);
        if ( SecurityDescriptor >= 0 )
        {
          SecurityDescriptor = RtlSetSaclSecurityDescriptor(v3, 1u, &Acl, 0);
          if ( SecurityDescriptor >= 0 )
          {
            BufferLength = 0;
            SecurityDescriptor = RtlMakeSelfRelativeSD(v3, 0, &BufferLength);
            if ( SecurityDescriptor != -1073741789 )
            {
              if ( SecurityDescriptor >= 0 )
                SecurityDescriptor = -1073741595;
              goto LABEL_25;
            }
            v12 = LocalAlloc(0x40u, BufferLength);
            v13 = v12;
            if ( v12 )
            {
              SecurityDescriptor = RtlMakeSelfRelativeSD(v3, v12, &BufferLength);
              if ( SecurityDescriptor >= 0 )
                *a1 = v13;
              goto LABEL_25;
            }
            goto LABEL_5;
          }
        }
      }
    }
  }
LABEL_25:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  RtlFreeSid(Sid);
  LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v5, v14);
  LsapSubProv_FreeRoutine(v3, v15);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x180096d28  push    rbp
0x180096d2a  push    rbx
0x180096d2b  push    rsi
0x180096d2c  push    rdi
0x180096d2d  push    r12
0x180096d2f  push    r13
0x180096d31  push    r14
0x180096d33  push    r15
0x180096d35  lea     rbp, [rsp-1F8h]
0x180096d3d  sub     rsp, 2F8h
0x180096d44  mov     rax, cs:__security_cookie
0x180096d4b  xor     rax, rsp
0x180096d4e  mov     [rbp+230h+var_50], rax
0x180096d55  xor     r12d, r12d
0x180096d58  mov     [rsp+330h+TokenInformationLength], 4Ch ; 'L'
0x180096d60  mov     r15, rcx
0x180096d63  mov     [rsp+330h+TokenHandle], r12
0x180096d68  lea     rcx, [rbp+230h+Acl]; void *
0x180096d6c  mov     [rsp+330h+BufferLength], r12d
0x180096d71  xor     edx, edx; Val
0x180096d73  mov     [rsp+330h+var_2C0], r12
0x180096d78  mov     r8d, 200h; Size
0x180096d7e  mov     dword ptr [rsp+330h+IdentifierAuthority.Value], r12d
0x180096d83  mov     word ptr [rsp+330h+IdentifierAuthority.Value+4], 1000h
0x180096d8a  call    memset_0
0x180096d8f  lea     ecx, [r12+28h]
0x180096d94  call    LsapAllocate
0x180096d99  mov     rsi, rax
0x180096d9c  test    rax, rax
0x180096d9f  jnz     short loc_180096DAB
0x180096da1  mov     eax, 0C0000017h
0x180096da6  jmp     loc_18009710D
0x180096dab  mov     edx, 1; Revision
0x180096db0  mov     rcx, rsi; SecurityDescriptor
0x180096db3  mov     rdi, r12
0x180096db6  call    cs:__imp_RtlCreateSecurityDescriptor
0x180096dbd  nop     dword ptr [rax+rax+00h]
0x180096dc2  mov     ebx, eax
0x180096dc4  test    eax, eax
0x180096dc6  js      loc_1800970D4
0x180096dcc  call    cs:__imp_GetCurrentProcess
0x180096dd3  nop     dword ptr [rax+rax+00h]
0x180096dd8  lea     r8, [rsp+330h+TokenHandle]; TokenHandle
0x180096ddd  mov     edx, 20008h; DesiredAccess
0x180096de2  mov     rcx, rax; ProcessHandle
0x180096de5  call    cs:__imp_OpenProcessToken
0x180096dec  nop     dword ptr [rax+rax+00h]
0x180096df1  test    eax, eax
0x180096df3  jnz     short loc_180096DFF
0x180096df5  mov     ebx, 0C0000017h
0x180096dfa  jmp     loc_1800970D4
0x180096dff  mov     r9d, [rsp+330h+TokenInformationLength]; TokenInformationLength
0x180096e04  lea     rax, [rsp+330h+TokenInformationLength]
0x180096e09  mov     rcx, [rsp+330h+TokenHandle]; TokenHandle
0x180096e0e  lea     r8, [rbp+230h+TokenInformation]; TokenInformation
0x180096e12  mov     edx, 4; TokenInformationClass
0x180096e17  mov     [rsp+330h+ReturnLength], rax; ReturnLength
0x180096e1c  call    cs:__imp_GetTokenInformation
0x180096e23  nop     dword ptr [rax+rax+00h]
0x180096e28  test    eax, eax
0x180096e2a  jz      short loc_180096DF5
0x180096e2c  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180096e33  mov     rcx, [rax+0A80h]; Sid
0x180096e3a  mov     rbx, [rax+360h]
0x180096e41  call    cs:__imp_RtlLengthSid
0x180096e48  nop     dword ptr [rax+rax+00h]
0x180096e4d  mov     rcx, rbx; Sid
0x180096e50  mov     r14d, eax
0x180096e53  call    cs:__imp_RtlLengthSid
0x180096e5a  nop     dword ptr [rax+rax+00h]
0x180096e5f  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180096e66  add     r14d, eax
0x180096e69  mov     rcx, [rcx+30h]; Sid
0x180096e6d  call    cs:__imp_RtlLengthSid
0x180096e74  nop     dword ptr [rax+rax+00h]
0x180096e79  add     eax, 7Ch ; '|'
0x180096e7c  add     r14d, eax
0x180096e7f  mov     ecx, r14d
0x180096e82  call    LsapAllocate
0x180096e87  mov     rdi, rax
0x180096e8a  test    rax, rax
0x180096e8d  jz      loc_180096DF5
0x180096e93  mov     rdx, [rbp+230h+TokenInformation]; Owner
0x180096e97  xor     r8d, r8d; OwnerDefaulted
0x180096e9a  mov     rcx, rsi; SecurityDescriptor
0x180096e9d  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180096ea4  nop     dword ptr [rax+rax+00h]
0x180096ea9  mov     ebx, eax
0x180096eab  test    eax, eax
0x180096ead  js      loc_1800970D4
0x180096eb3  mov     r13d, 2
0x180096eb9  mov     edx, r14d; AclSize
0x180096ebc  mov     r8d, r13d; AclRevision
0x180096ebf  mov     rcx, rdi; Acl
0x180096ec2  call    cs:__imp_RtlCreateAcl
0x180096ec9  nop     dword ptr [rax+rax+00h]
0x180096ece  mov     ebx, eax
0x180096ed0  test    eax, eax
0x180096ed2  js      loc_1800970D4
0x180096ed8  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180096edf  mov     r14d, 12019Bh
0x180096ee5  mov     r8d, r14d; AccessMask
0x180096ee8  mov     edx, r13d; Revision
0x180096eeb  mov     rcx, rdi; Acl
0x180096eee  mov     r9, [r9+30h]; Sid
0x180096ef2  call    cs:__imp_RtlAddAccessAllowedAce
0x180096ef9  nop     dword ptr [rax+rax+00h]
0x180096efe  mov     ebx, eax
0x180096f00  test    eax, eax
0x180096f02  js      loc_1800970D4
0x180096f08  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180096f0f  mov     r8d, r14d; AccessMask
0x180096f12  mov     edx, r13d; Revision
0x180096f15  mov     rcx, rdi; Acl
0x180096f18  mov     r9, [r9+360h]; Sid
0x180096f1f  call    cs:__imp_RtlAddAccessAllowedAce
0x180096f26  nop     dword ptr [rax+rax+00h]
0x180096f2b  mov     ebx, eax
0x180096f2d  test    eax, eax
0x180096f2f  js      loc_1800970D4
0x180096f35  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180096f3c  mov     r8d, r14d; AccessMask
0x180096f3f  mov     edx, r13d; Revision
0x180096f42  mov     rcx, rdi; Acl
0x180096f45  mov     r9, [r9+0A80h]; Sid
0x180096f4c  call    cs:__imp_RtlAddAccessAllowedAce
0x180096f53  nop     dword ptr [rax+rax+00h]
0x180096f58  mov     ebx, eax
0x180096f5a  test    eax, eax
0x180096f5c  js      loc_1800970D4
0x180096f62  mov     r9, [rbp+230h+TokenInformation]; Sid
0x180096f66  mov     r8d, 1F01FFh; AccessMask
0x180096f6c  mov     edx, r13d; Revision
0x180096f6f  mov     rcx, rdi; Acl
0x180096f72  call    cs:__imp_RtlAddAccessAllowedAce
0x180096f79  nop     dword ptr [rax+rax+00h]
0x180096f7e  mov     ebx, eax
0x180096f80  test    eax, eax
0x180096f82  js      loc_1800970D4
0x180096f88  xor     r9d, r9d; DaclDefaulted
0x180096f8b  mov     r8, rdi; Dacl
0x180096f8e  mov     dl, 1; DaclPresent
0x180096f90  mov     rcx, rsi; SecurityDescriptor
0x180096f93  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180096f9a  nop     dword ptr [rax+rax+00h]
0x180096f9f  test    eax, eax
0x180096fa1  js      loc_180096DF5
0x180096fa7  lea     rax, [rsp+330h+var_2C0]
0x180096fac  xor     r9d, r9d; SubAuthority1
0x180096faf  mov     [rsp+330h+Sid], rax; Sid
0x180096fb4  lea     rcx, [rsp+330h+IdentifierAuthority]; IdentifierAuthority
0x180096fb9  mov     [rsp+330h+SubAuthority7], r12d; SubAuthority7
0x180096fbe  xor     r8d, r8d; SubAuthority0
0x180096fc1  mov     [rsp+330h+SubAuthority6], r12d; SubAuthority6
0x180096fc6  mov     dl, 1; SubAuthorityCount
0x180096fc8  mov     [rsp+330h+SubAuthority5], r12d; SubAuthority5
0x180096fcd  mov     [rsp+330h+SubAuthority4], r12d; SubAuthority4
0x180096fd2  mov     dword ptr [rsp+330h+SubAuthority3], r12d; SubAuthority3
0x180096fd7  mov     dword ptr [rsp+330h+ReturnLength], r12d; SubAuthority2
0x180096fdc  call    cs:__imp_RtlAllocateAndInitializeSid
0x180096fe3  nop     dword ptr [rax+rax+00h]
0x180096fe8  mov     ebx, eax
0x180096fea  test    eax, eax
0x180096fec  js      loc_1800970D4
0x180096ff2  mov     r8d, r13d; AclRevision
0x180096ff5  lea     rcx, [rbp+230h+Acl]; Acl
0x180096ff9  mov     edx, 200h; AclSize
0x180096ffe  call    cs:__imp_RtlCreateAcl
0x180097005  nop     dword ptr [rax+rax+00h]
0x18009700a  mov     ebx, eax
0x18009700c  test    eax, eax
0x18009700e  js      loc_1800970D4
0x180097014  mov     r9, [rsp+330h+var_2C0]; MandatoryFlags
0x180097019  lea     rcx, [rbp+230h+Acl]; Acl
0x18009701d  mov     dword ptr [rsp+330h+SubAuthority3], 1; LabelSid
0x180097025  xor     r8d, r8d; Flags
0x180097028  mov     edx, r13d; Revision
0x18009702b  mov     byte ptr [rsp+330h+ReturnLength], 11h; AceType
0x180097030  call    cs:__imp_RtlAddMandatoryAce
0x180097037  nop     dword ptr [rax+rax+00h]
0x18009703c  mov     ebx, eax
0x18009703e  test    eax, eax
0x180097040  js      loc_1800970D4
0x180097046  xor     r9d, r9d; SaclDefaulted
0x180097049  lea     r8, [rbp+230h+Acl]; Sacl
0x18009704d  mov     dl, 1; SaclPresent
0x18009704f  mov     rcx, rsi; SecurityDescriptor
0x180097052  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x180097059  nop     dword ptr [rax+rax+00h]
0x18009705e  mov     ebx, eax
0x180097060  test    eax, eax
0x180097062  js      short loc_1800970D4
0x180097064  lea     r8, [rsp+330h+BufferLength]; BufferLength
0x180097069  mov     [rsp+330h+BufferLength], r12d
0x18009706e  xor     edx, edx; SelfRelativeSD
0x180097070  mov     rcx, rsi; AbsoluteSD
0x180097073  call    cs:__imp_RtlMakeSelfRelativeSD
0x18009707a  nop     dword ptr [rax+rax+00h]
0x18009707f  mov     ebx, eax
0x180097081  cmp     eax, 0C0000023h
0x180097086  jnz     short loc_1800970CA
0x180097088  mov     edx, [rsp+330h+BufferLength]; uBytes
0x18009708c  lea     ecx, [r13+3Eh]; uFlags
0x180097090  call    cs:__imp_LocalAlloc
0x180097097  nop     dword ptr [rax+rax+00h]
0x18009709c  mov     r14, rax
0x18009709f  test    rax, rax
0x1800970a2  jz      loc_180096DF5
0x1800970a8  lea     r8, [rsp+330h+BufferLength]; BufferLength
0x1800970ad  mov     rdx, rax; SelfRelativeSD
0x1800970b0  mov     rcx, rsi; AbsoluteSD
0x1800970b3  call    cs:__imp_RtlMakeSelfRelativeSD
0x1800970ba  nop     dword ptr [rax+rax+00h]
0x1800970bf  mov     ebx, eax
0x1800970c1  test    eax, eax
0x1800970c3  js      short loc_1800970D4
0x1800970c5  mov     [r15], r14
0x1800970c8  jmp     short loc_1800970D4
0x1800970ca  test    ebx, ebx
0x1800970cc  mov     eax, 0C00000E5h
0x1800970d1  cmovns  ebx, eax
0x1800970d4  mov     rcx, [rsp+330h+TokenHandle]; hObject
0x1800970d9  test    rcx, rcx
0x1800970dc  jz      short loc_1800970EA
0x1800970de  call    cs:__imp_CloseHandle
0x1800970e5  nop     dword ptr [rax+rax+00h]
0x1800970ea  mov     rcx, [rsp+330h+var_2C0]; Sid
0x1800970ef  call    cs:__imp_RtlFreeSid
0x1800970f6  nop     dword ptr [rax+rax+00h]
0x1800970fb  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x1800970fe  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180097103  mov     rcx, rsi; struct _RTL_BALANCED_NODE *
0x180097106  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18009710b  mov     eax, ebx
0x18009710d  mov     rcx, [rbp+230h+var_50]
0x180097114  xor     rcx, rsp; StackCookie
0x180097117  call    __security_check_cookie
0x18009711c  add     rsp, 2F8h
0x180097123  pop     r15
0x180097125  pop     r14
0x180097127  pop     r13
0x180097129  pop     r12
0x18009712b  pop     rdi
0x18009712c  pop     rsi
0x18009712d  pop     rbx
0x18009712e  pop     rbp
0x18009712f  retn
```
