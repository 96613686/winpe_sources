# _CheckUserAccessForChangePassword(void *,void *)

- ea: `0x1800f9dd4`
- end: `0x1800fa216`
- name: `?_CheckUserAccessForChangePassword@@YAJPEAX0@Z`
- size: `1090`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800fa3d8`

## callees

- `0x180011278`
- `0x180078a74`
- `0x1800b86d0`
- `0x1800bbbfc`
- `0x1800f9dd4`

## import_xrefs

- `ntdll!NtCreateToken` at `0x1800fa0a6`
- `ntdll!NtCreateToken` at `0x1800fa0a6`
- `ntdll!RtlFreeHeap` at `0x1800fa1e5`
- `ntdll!RtlFreeHeap` at `0x1800fa1e5`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800f9ecd`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800f9ecd`
- `ntdll!NtAccessCheck` at `0x1800fa11f`
- `ntdll!NtAccessCheck` at `0x1800fa11f`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800fa00a`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800fa00a`
- `ntdll!NtClose` at `0x1800fa1c0`
- `ntdll!NtClose` at `0x1800fa1c0`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800f9f4d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800f9f4d`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrQuerySecurityObject` at `0x1800f9ea0`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrQuerySecurityObject` at `0x1800f9ea0`

## pseudocode

```c
__int64 __fastcall _CheckUserAccessForChangePassword(void *a1, void *a2)
{
  NTSTATUS DaclSecurityDescriptor; // ebx
  LsaHandleCache *v5; // rcx
  __int64 v6; // rdx
  void *v7; // rcx
  unsigned __int8 DaclPresent; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 DaclDefaulted[3]; // [rsp+71h] [rbp-8Fh] BYREF
  int AccessStatus; // [rsp+74h] [rbp-8Ch] BYREF
  void *v12; // [rsp+78h] [rbp-88h] BYREF
  PSID P; // [rsp+80h] [rbp-80h] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp-78h] BYREF
  ULONG ReturnLength; // [rsp+8Ch] [rbp-74h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  PACL Dacl; // [rsp+98h] [rbp-68h] BYREF
  struct _TOKEN_PRIMARY_GROUP TokenPrimaryGroup; // [rsp+A0h] [rbp-60h] BYREF
  union _LARGE_INTEGER ExpirationTime; // [rsp+A8h] [rbp-58h] BYREF
  struct _LUID AuthenticationId; // [rsp+B0h] [rbp-50h] BYREF
  struct _TOKEN_USER TokenUser; // [rsp+B8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-8h] BYREF
  int v24; // [rsp+100h] [rbp+0h]
  struct _GENERIC_MAPPING GenericMapping; // [rsp+108h] [rbp+8h] BYREF
  struct _TOKEN_GROUPS TokenGroups; // [rsp+118h] [rbp+18h] BYREF
  struct _TOKEN_PRIVILEGES TokenPrivileges; // [rsp+130h] [rbp+30h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+140h] [rbp+40h] BYREF

  AuthenticationId = (struct _LUID)999LL;
  AccessStatus = 0;
  DaclPresent = 0;
  Dacl = 0;
  DaclDefaulted[0] = 0;
  TokenUser = 0;
  TokenPrimaryGroup.PrimaryGroup = 0;
  memset(&TokenGroups, 0, sizeof(TokenGroups));
  TokenPrivileges = 0;
  v23 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v24 = 0;
  ExpirationTime.QuadPart = 0;
  GrantedAccess = 0;
  v12 = 0;
  P = 0;
  ReturnLength = 256;
  GenericMapping.GenericRead = 131866;
  GenericMapping.GenericWrite = 131140;
  GenericMapping.GenericExecute = 131137;
  GenericMapping.GenericAll = 985087;
  TokenHandle = (void *)-1LL;
  if ( !(unsigned __int8)IsSamIDecodeClaimsBlobPresent() )
  {
    DaclSecurityDescriptor = -1073741637;
    goto LABEL_29;
  }
  DaclSecurityDescriptor = SamrQuerySecurityObject(a1, 7, &v12);
  if ( DaclSecurityDescriptor < 0 )
  {
LABEL_29:
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 20;
      goto LABEL_32;
    }
    goto LABEL_33;
  }
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(
                             *((PSECURITY_DESCRIPTOR *)v12 + 1),
                             &DaclPresent,
                             &Dacl,
                             DaclDefaulted);
  if ( DaclSecurityDescriptor >= 0 )
  {
    if ( !DaclPresent || !Dacl )
    {
      DaclSecurityDescriptor = 0;
      goto LABEL_33;
    }
    DaclSecurityDescriptor = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &P);
    if ( DaclSecurityDescriptor >= 0 )
    {
      ObjectAttributes.SecurityQualityOfService = &v23;
      TokenGroups.Groups[0].Sid = P;
      TokenPrimaryGroup.PrimaryGroup = P;
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      ObjectAttributes.SecurityDescriptor = 0;
      LOWORD(v24) = 256;
      v23 = 0x10000000CLL;
      TokenUser.User.Sid = a2;
      TokenUser.User.Attributes = 0;
      TokenGroups.GroupCount = 1;
      TokenGroups.Groups[0].Attributes = 7;
      TokenPrivileges.PrivilegeCount = 0;
      ExpirationTime.LowPart = 0x7FFFFFF;
      if ( TokenSource.SourceName[0]
        || (TokenSource.SourceName[0] = 69,
            *(_WORD *)&TokenSource.SourceName[1] = 29537,
            DaclSecurityDescriptor = NtAllocateLocallyUniqueId(&TokenSource.SourceIdentifier),
            DaclSecurityDescriptor >= 0) )
      {
        DaclSecurityDescriptor = NtCreateToken(
                                   &TokenHandle,
                                   0xF01FFu,
                                   &ObjectAttributes,
                                   TokenImpersonation,
                                   &AuthenticationId,
                                   &ExpirationTime,
                                   &TokenUser,
                                   &TokenGroups,
                                   &TokenPrivileges,
                                   0,
                                   &TokenPrimaryGroup,
                                   0,
                                   &TokenSource);
        if ( DaclSecurityDescriptor >= 0 )
        {
          DaclSecurityDescriptor = NtAccessCheck(
                                     *((PSECURITY_DESCRIPTOR *)v12 + 1),
                                     TokenHandle,
                                     0x40u,
                                     &GenericMapping,
                                     &PrivilegeSet,
                                     &ReturnLength,
                                     &GrantedAccess,
                                     &AccessStatus);
          if ( DaclSecurityDescriptor >= 0 )
          {
            DaclSecurityDescriptor = AccessStatus;
            goto LABEL_33;
          }
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 25;
            goto LABEL_32;
          }
        }
        else
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 24;
            goto LABEL_32;
          }
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 23;
          goto LABEL_32;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 22;
        goto LABEL_32;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 21;
LABEL_32:
      WPP_SF_d(
        *((_QWORD *)v5 + 2),
        v6,
        WPP_545c8b7f486339e055cd0f4d1a7ce3f2_Traceguids,
        (unsigned int)DaclSecurityDescriptor);
    }
  }
LABEL_33:
  v7 = v12;
  if ( v12 )
  {
    if ( *((_QWORD *)v12 + 1) )
    {
      LsapSamExtFreeVoid(*((void **)v12 + 1));
      v7 = v12;
    }
    LsapSamExtFreeVoid(v7);
  }
  if ( TokenHandle != (void *)-1LL )
    NtClose(TokenHandle);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x1800f9dd4  mov     [rsp-8+arg_10], rbx
0x1800f9dd9  push    rbp
0x1800f9dda  push    rsi
0x1800f9ddb  push    rdi
0x1800f9ddc  lea     rbp, [rsp-150h]
0x1800f9de4  sub     rsp, 250h
0x1800f9deb  mov     rax, cs:__security_cookie
0x1800f9df2  xor     rax, rsp
0x1800f9df5  mov     [rbp+160h+var_20], rax
0x1800f9dfc  xor     esi, esi
0x1800f9dfe  mov     qword ptr [rbp+160h+AuthenticationId.LowPart], 3E7h
0x1800f9e06  xorps   xmm1, xmm1
0x1800f9e09  mov     [rsp+260h+AccessStatus], esi
0x1800f9e0d  xor     eax, eax
0x1800f9e0f  mov     [rsp+260h+DaclPresent], sil
0x1800f9e14  xorps   xmm0, xmm0
0x1800f9e17  mov     [rbp+160h+Dacl], rsi
0x1800f9e1b  mov     [rsp+260h+DaclDefaulted], sil
0x1800f9e20  mov     rdi, rdx
0x1800f9e23  movups  xmmword ptr [rbp+160h+TokenUser.User.Sid], xmm0
0x1800f9e27  mov     [rbp+160h+TokenPrimaryGroup.PrimaryGroup], rsi
0x1800f9e2b  mov     rbx, rcx
0x1800f9e2e  movups  xmmword ptr [rbp+160h+TokenGroups.GroupCount], xmm1
0x1800f9e32  mov     qword ptr [rbp+160h+TokenGroups.Groups.Attributes], rax
0x1800f9e36  movups  xmmword ptr [rbp+160h+TokenPrivileges.PrivilegeCount], xmm0
0x1800f9e3a  mov     [rbp+160h+var_168], rax
0x1800f9e3e  movups  xmmword ptr [rbp+160h+ObjectAttributes.Length], xmm1
0x1800f9e42  mov     [rbp+160h+var_160], eax
0x1800f9e45  movups  xmmword ptr [rbp+160h+ObjectAttributes.ObjectName], xmm1
0x1800f9e49  mov     qword ptr [rbp+160h+ExpirationTime], rsi
0x1800f9e4d  movups  xmmword ptr [rbp+160h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800f9e51  mov     [rbp+160h+GrantedAccess], esi
0x1800f9e54  mov     [rsp+260h+var_1E8], rsi
0x1800f9e59  mov     [rbp+160h+P], rsi
0x1800f9e5d  mov     [rbp+160h+ReturnLength], 100h
0x1800f9e64  mov     [rbp+160h+GenericMapping.GenericRead], 2031Ah
0x1800f9e6b  mov     [rbp+160h+GenericMapping.GenericWrite], 20044h
0x1800f9e72  mov     [rbp+160h+GenericMapping.GenericExecute], 20041h
0x1800f9e79  mov     [rbp+160h+GenericMapping.GenericAll], 0F07FFh
0x1800f9e80  mov     [rbp+160h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800f9e88  call    IsSamIDecodeClaimsBlobPresent
0x1800f9e8d  test    al, al
0x1800f9e8f  jz      loc_1800FA15B
0x1800f9e95  lea     r8, [rsp+260h+var_1E8]
0x1800f9e9a  mov     rcx, rbx
0x1800f9e9d  lea     edx, [rsi+7]
0x1800f9ea0  call    cs:__imp_SamrQuerySecurityObject
0x1800f9ea7  nop     dword ptr [rax+rax+00h]
0x1800f9eac  mov     ebx, eax
0x1800f9eae  test    eax, eax
0x1800f9eb0  js      loc_1800FA160
0x1800f9eb6  mov     rcx, [rsp+260h+var_1E8]
0x1800f9ebb  lea     r9, [rsp+260h+DaclDefaulted]; DaclDefaulted
0x1800f9ec0  lea     r8, [rbp+160h+Dacl]; Dacl
0x1800f9ec4  lea     rdx, [rsp+260h+DaclPresent]; DaclPresent
0x1800f9ec9  mov     rcx, [rcx+8]; SecurityDescriptor
0x1800f9ecd  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1800f9ed4  nop     dword ptr [rax+rax+00h]
0x1800f9ed9  mov     ebx, eax
0x1800f9edb  test    eax, eax
0x1800f9edd  jns     short loc_1800F9F08
0x1800f9edf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9ee6  lea     rax, WPP_GLOBAL_Control
0x1800f9eed  cmp     rcx, rax
0x1800f9ef0  jz      loc_1800FA191
0x1800f9ef6  test    byte ptr [rcx+1Ch], 1
0x1800f9efa  jz      loc_1800FA191
0x1800f9f00  lea     edx, [rsi+15h]
0x1800f9f03  jmp     loc_1800FA17E
0x1800f9f08  cmp     [rsp+260h+DaclPresent], sil
0x1800f9f0d  jz      loc_1800FA157
0x1800f9f13  cmp     [rbp+160h+Dacl], rsi
0x1800f9f17  jz      loc_1800FA157
0x1800f9f1d  lea     rax, [rbp+160h+P]
0x1800f9f21  xor     r9d, r9d; SubAuthority1
0x1800f9f24  mov     [rsp+260h+Sid], rax; Sid
0x1800f9f29  lea     rcx, IdentifierAuthority; IdentifierAuthority
0x1800f9f30  mov     [rsp+260h+SubAuthority7], esi; SubAuthority7
0x1800f9f34  xor     r8d, r8d; SubAuthority0
0x1800f9f37  mov     [rsp+260h+SubAuthority6], esi; SubAuthority6
0x1800f9f3b  mov     dl, 1; SubAuthorityCount
0x1800f9f3d  mov     [rsp+260h+SubAuthority5], esi; SubAuthority5
0x1800f9f41  mov     [rsp+260h+SubAuthority4], esi; SubAuthority4
0x1800f9f45  mov     [rsp+260h+SubAuthority3], esi; SubAuthority3
0x1800f9f49  mov     [rsp+260h+SubAuthority2], esi; SubAuthority2
0x1800f9f4d  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800f9f54  nop     dword ptr [rax+rax+00h]
0x1800f9f59  mov     ebx, eax
0x1800f9f5b  test    eax, eax
0x1800f9f5d  jns     short loc_1800F9F8A
0x1800f9f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9f66  lea     rax, WPP_GLOBAL_Control
0x1800f9f6d  cmp     rcx, rax
0x1800f9f70  jz      loc_1800FA191
0x1800f9f76  test    byte ptr [rcx+1Ch], 1
0x1800f9f7a  jz      loc_1800FA191
0x1800f9f80  mov     edx, 16h
0x1800f9f85  jmp     loc_1800FA17E
0x1800f9f8a  cmp     cs:TokenSource.SourceName, sil
0x1800f9f91  lea     rax, [rbp+160h+var_168]
0x1800f9f95  mov     [rbp+160h+ObjectAttributes.SecurityQualityOfService], rax
0x1800f9f99  mov     rax, [rbp+160h+P]
0x1800f9f9d  mov     [rbp+160h+TokenGroups.Groups.Sid], rax
0x1800f9fa1  mov     [rbp+160h+TokenPrimaryGroup.PrimaryGroup], rax
0x1800f9fa5  mov     [rbp+160h+ObjectAttributes.Length], 30h ; '0'
0x1800f9fac  mov     [rbp+160h+ObjectAttributes.RootDirectory], rsi
0x1800f9fb0  mov     [rbp+160h+ObjectAttributes.Attributes], esi
0x1800f9fb3  mov     [rbp+160h+ObjectAttributes.ObjectName], rsi
0x1800f9fb7  mov     [rbp+160h+ObjectAttributes.SecurityDescriptor], rsi
0x1800f9fbb  mov     dword ptr [rbp+160h+var_168+4], 1
0x1800f9fc2  mov     word ptr [rbp+160h+var_160], 100h
0x1800f9fc8  mov     dword ptr [rbp+160h+var_168], 0Ch
0x1800f9fcf  mov     [rbp+160h+TokenUser.User.Sid], rdi
0x1800f9fd3  mov     [rbp+160h+TokenUser.User.Attributes], esi
0x1800f9fd6  mov     [rbp+160h+TokenGroups.GroupCount], 1
0x1800f9fdd  mov     [rbp+160h+TokenGroups.Groups.Attributes], 7
0x1800f9fe4  mov     [rbp+160h+TokenPrivileges.PrivilegeCount], esi
0x1800f9fe7  mov     dword ptr [rbp+160h+ExpirationTime], 7FFFFFFh
0x1800f9fee  jnz     short loc_1800FA047
0x1800f9ff0  mov     eax, 7361h
0x1800f9ff5  mov     cs:TokenSource.SourceName, 45h ; 'E'
0x1800f9ffc  lea     rcx, TokenSource.SourceIdentifier; LocallyUniqueId
0x1800fa003  mov     word ptr cs:TokenSource.SourceName+1, ax
0x1800fa00a  call    cs:__imp_NtAllocateLocallyUniqueId
0x1800fa011  nop     dword ptr [rax+rax+00h]
0x1800fa016  mov     ebx, eax
0x1800fa018  test    eax, eax
0x1800fa01a  jns     short loc_1800FA047
0x1800fa01c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa023  lea     rax, WPP_GLOBAL_Control
0x1800fa02a  cmp     rcx, rax
0x1800fa02d  jz      loc_1800FA191
0x1800fa033  test    byte ptr [rcx+1Ch], 1
0x1800fa037  jz      loc_1800FA191
0x1800fa03d  mov     edx, 17h
0x1800fa042  jmp     loc_1800FA17E
0x1800fa047  lea     rax, TokenSource
0x1800fa04e  mov     r9d, 2; TokenType
0x1800fa054  mov     [rsp+260h+TokenSource], rax; TokenSource
0x1800fa059  lea     r8, [rbp+160h+ObjectAttributes]; ObjectAttributes
0x1800fa05d  mov     [rsp+260h+TokenDefaultDacl], rsi; TokenDefaultDacl
0x1800fa062  lea     rax, [rbp+160h+TokenPrimaryGroup]
0x1800fa066  mov     [rsp+260h+Sid], rax; TokenPrimaryGroup
0x1800fa06b  lea     rcx, [rbp+160h+TokenHandle]; TokenHandle
0x1800fa06f  mov     qword ptr [rsp+260h+SubAuthority7], rsi; TokenOwner
0x1800fa074  lea     rax, [rbp+160h+TokenPrivileges]
0x1800fa078  mov     qword ptr [rsp+260h+SubAuthority6], rax; TokenPrivileges
0x1800fa07d  mov     edx, 0F01FFh; DesiredAccess
0x1800fa082  lea     rax, [rbp+160h+TokenGroups]
0x1800fa086  mov     qword ptr [rsp+260h+SubAuthority5], rax; TokenGroups
0x1800fa08b  lea     rax, [rbp+160h+TokenUser]
0x1800fa08f  mov     qword ptr [rsp+260h+SubAuthority4], rax; TokenUser
0x1800fa094  lea     rax, [rbp+160h+ExpirationTime]
0x1800fa098  mov     qword ptr [rsp+260h+SubAuthority3], rax; ExpirationTime
0x1800fa09d  lea     rax, [rbp+160h+AuthenticationId]
0x1800fa0a1  mov     qword ptr [rsp+260h+SubAuthority2], rax; AuthenticationId
0x1800fa0a6  call    cs:__imp_NtCreateToken
0x1800fa0ad  nop     dword ptr [rax+rax+00h]
0x1800fa0b2  mov     ebx, eax
0x1800fa0b4  test    eax, eax
0x1800fa0b6  jns     short loc_1800FA0E3
0x1800fa0b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa0bf  lea     rax, WPP_GLOBAL_Control
0x1800fa0c6  cmp     rcx, rax
0x1800fa0c9  jz      loc_1800FA191
0x1800fa0cf  test    byte ptr [rcx+1Ch], 1
0x1800fa0d3  jz      loc_1800FA191
0x1800fa0d9  mov     edx, 18h
0x1800fa0de  jmp     loc_1800FA17E
0x1800fa0e3  mov     rcx, [rsp+260h+var_1E8]
0x1800fa0e8  lea     rax, [rsp+260h+AccessStatus]
0x1800fa0ed  mov     rdx, [rbp+160h+TokenHandle]; ClientToken
0x1800fa0f1  lea     r9, [rbp+160h+GenericMapping]; GenericMapping
0x1800fa0f5  mov     qword ptr [rsp+260h+SubAuthority5], rax; AccessStatus
0x1800fa0fa  mov     r8d, 40h ; '@'; DesiredAccess
0x1800fa100  lea     rax, [rbp+160h+GrantedAccess]
0x1800fa104  mov     rcx, [rcx+8]; SecurityDescriptor
0x1800fa108  mov     qword ptr [rsp+260h+SubAuthority4], rax; GrantedAccess
0x1800fa10d  lea     rax, [rbp+160h+ReturnLength]
0x1800fa111  mov     qword ptr [rsp+260h+SubAuthority3], rax; ReturnLength
0x1800fa116  lea     rax, [rbp+160h+PrivilegeSet]
0x1800fa11a  mov     qword ptr [rsp+260h+SubAuthority2], rax; PrivilegeSet
0x1800fa11f  call    cs:__imp_NtAccessCheck
0x1800fa126  nop     dword ptr [rax+rax+00h]
0x1800fa12b  mov     ebx, eax
0x1800fa12d  test    eax, eax
0x1800fa12f  jns     short loc_1800FA151
0x1800fa131  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa138  lea     rax, WPP_GLOBAL_Control
0x1800fa13f  cmp     rcx, rax
0x1800fa142  jz      short loc_1800FA191
0x1800fa144  test    byte ptr [rcx+1Ch], 1
0x1800fa148  jz      short loc_1800FA191
0x1800fa14a  mov     edx, 19h
0x1800fa14f  jmp     short loc_1800FA17E
0x1800fa151  mov     ebx, [rsp+260h+AccessStatus]
0x1800fa155  jmp     short loc_1800FA191
0x1800fa157  mov     ebx, esi
0x1800fa159  jmp     short loc_1800FA191
0x1800fa15b  mov     ebx, 0C00000BBh
0x1800fa160  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa167  lea     rax, WPP_GLOBAL_Control
0x1800fa16e  cmp     rcx, rax
0x1800fa171  jz      short loc_1800FA191
0x1800fa173  test    byte ptr [rcx+1Ch], 1
0x1800fa177  jz      short loc_1800FA191
0x1800fa179  mov     edx, 14h
0x1800fa17e  mov     rcx, [rcx+10h]
0x1800fa182  lea     r8, WPP_545c8b7f486339e055cd0f4d1a7ce3f2_Traceguids
0x1800fa189  mov     r9d, ebx
0x1800fa18c  call    WPP_SF_d
0x1800fa191  mov     rcx, [rsp+260h+var_1E8]
0x1800fa196  test    rcx, rcx
0x1800fa199  jz      short loc_1800FA1B6
0x1800fa19b  mov     rax, [rcx+8]
0x1800fa19f  test    rax, rax
0x1800fa1a2  jz      short loc_1800FA1B1
0x1800fa1a4  mov     rcx, rax; void *
0x1800fa1a7  call    ?LsapSamExtFreeVoid@@YAXPEAX@Z; LsapSamExtFreeVoid(void *)
0x1800fa1ac  mov     rcx, [rsp+260h+var_1E8]; void *
0x1800fa1b1  call    ?LsapSamExtFreeVoid@@YAXPEAX@Z; LsapSamExtFreeVoid(void *)
0x1800fa1b6  mov     rcx, [rbp+160h+TokenHandle]; Handle
0x1800fa1ba  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800fa1be  jz      short loc_1800FA1CC
0x1800fa1c0  call    cs:__imp_NtClose
0x1800fa1c7  nop     dword ptr [rax+rax+00h]
0x1800fa1cc  cmp     [rbp+160h+P], rsi
0x1800fa1d0  jz      short loc_1800FA1F1
0x1800fa1d2  mov     rcx, gs:60h
0x1800fa1db  xor     edx, edx; Flags
0x1800fa1dd  mov     r8, [rbp+160h+P]; P
0x1800fa1e1  mov     rcx, [rcx+30h]; HeapHandle
0x1800fa1e5  call    cs:__imp_RtlFreeHeap
0x1800fa1ec  nop     dword ptr [rax+rax+00h]
0x1800fa1f1  mov     eax, ebx
0x1800fa1f3  mov     rcx, [rbp+160h+var_20]
0x1800fa1fa  xor     rcx, rsp; StackCookie
0x1800fa1fd  call    __security_check_cookie
0x1800fa202  mov     rbx, [rsp+260h+arg_10]
0x1800fa20a  add     rsp, 250h
0x1800fa211  pop     rdi
0x1800fa212  pop     rsi
0x1800fa213  pop     rbp
0x1800fa214  retn
```
