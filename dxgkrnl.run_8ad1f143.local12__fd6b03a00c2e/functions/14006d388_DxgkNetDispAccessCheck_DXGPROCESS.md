# DxgkNetDispAccessCheck(DXGPROCESS *)

- ea: `0x14006d388`
- end: `0x14006d669`
- name: `?DxgkNetDispAccessCheck@@YAJPEAVDXGPROCESS@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(struct DXGPROCESS *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14020dde0`
- `0x14020e0f0`
- `0x14020e350`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140046d28`
- `0x14006d388`
- `0x1400a0bd0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14006d3b9`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14006d3b9`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14006d3ec`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14006d3ec`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14006d410`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14006d410`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14006d421`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14006d421`
- `ntoskrnl!RtlInitializeSid` at `0x14006d464`
- `ntoskrnl!RtlInitializeSid` at `0x14006d464`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d475`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d48f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d4a9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d4c3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d4dd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d4f7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d475`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d48f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d4a9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d4c3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d4dd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006d4f7`
- `ntoskrnl!RtlLengthSid` at `0x14006d50c`
- `ntoskrnl!RtlLengthSid` at `0x14006d50c`
- `ntoskrnl!RtlCreateAcl` at `0x14006d541`
- `ntoskrnl!RtlCreateAcl` at `0x14006d541`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006d568`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006d568`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14006d58a`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14006d58a`
- `ntoskrnl!SeAccessCheck` at `0x14006d605`
- `ntoskrnl!SeAccessCheck` at `0x14006d605`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006d628`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006d628`

## pseudocode

```c
__int64 __fastcall DxgkNetDispAccessCheck(struct DXGPROCESS *this)
{
  NTSTATUS Acl; // ebx
  ULONG v3; // eax
  void *v4; // rax
  void *v5; // rsi
  ULONG v6; // ebx
  struct _ACL *v7; // rax
  struct _ACL *v8; // rdi
  BOOLEAN v9; // al
  int AccessStatus; // [rsp+50h] [rbp-39h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-35h] BYREF
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+58h] [rbp-31h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+78h] [rbp-11h] BYREF
  __int64 v15; // [rsp+98h] [rbp+Fh]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A0h] [rbp+17h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+A8h] [rbp+1Fh] BYREF

  if ( this )
  {
    Acl = 0;
    if ( g_OSTestSigningEnabled )
    {
      if ( !(unsigned int)PsGetCurrentProcessSessionId() )
        return (unsigned int)Acl;
    }
    if ( !DXGPROCESS::IsRemoteConnection(this) )
      return (unsigned int)Acl;
  }
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  v15 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  v3 = RtlLengthRequiredSid(6u);
  v4 = (void *)operator new[](v3, 1265072196, 256);
  v5 = v4;
  if ( v4 )
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    RtlInitializeSid(v4, &IdentifierAuthority, 6u);
    *RtlSubAuthoritySid(v5, 0) = 80;
    *RtlSubAuthoritySid(v5, 1u) = 1495648203;
    *RtlSubAuthoritySid(v5, 2u) = -1791465185;
    *RtlSubAuthoritySid(v5, 3u) = 1597754693;
    *RtlSubAuthoritySid(v5, 4u) = -849792585;
    *RtlSubAuthoritySid(v5, 5u) = 1316708627;
    v6 = RtlLengthSid(v5) + 20;
    v7 = (struct _ACL *)operator new[](v6, 1265072196, 256);
    v8 = v7;
    if ( v7 )
    {
      Acl = RtlCreateAcl(v7, v6, 2u);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v8, 2u, 0x1F0000u, v5);
        if ( Acl >= 0 )
        {
          Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v8, 0);
          if ( Acl >= 0 )
          {
            GenericMapping.GenericAll = 2031616;
            GenericMapping.GenericRead = 0x20000;
            GenericMapping.GenericWrite = 0x20000;
            GenericMapping.GenericExecute = 0x20000;
            GrantedAccess = 0;
            AccessStatus = 0;
            v9 = SeAccessCheck(
                   SecurityDescriptor,
                   &SubjectContext,
                   0,
                   0x1F0000u,
                   0,
                   0,
                   &GenericMapping,
                   1,
                   &GrantedAccess,
                   &AccessStatus);
            Acl = AccessStatus;
            if ( v9 )
              Acl = 0;
          }
        }
      }
      goto LABEL_15;
    }
  }
  else
  {
    v8 = 0;
  }
  Acl = -1073741801;
LABEL_15:
  SeReleaseSubjectContext(&SubjectContext);
  if ( v5 )
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v5);
  if ( v8 )
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v8);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14006d388  push    rbp
0x14006d38a  push    rbx
0x14006d38b  push    rsi
0x14006d38c  push    rdi
0x14006d38d  lea     rbp, [rsp-3Fh]
0x14006d392  sub     rsp, 0C8h
0x14006d399  mov     rax, cs:__security_cookie
0x14006d3a0  xor     rax, rsp
0x14006d3a3  mov     [rbp+57h+var_28], rax
0x14006d3a7  mov     rdi, rcx
0x14006d3aa  test    rcx, rcx
0x14006d3ad  jz      short loc_14006D3DD
0x14006d3af  xor     ebx, ebx
0x14006d3b1  cmp     cs:?g_OSTestSigningEnabled@@3EA, bl; uchar g_OSTestSigningEnabled
0x14006d3b7  jz      short loc_14006D3CD
0x14006d3b9  call    cs:__imp_PsGetCurrentProcessSessionId
0x14006d3c0  nop     dword ptr [rax+rax+00h]
0x14006d3c5  test    eax, eax
0x14006d3c7  jz      loc_14006D64E
0x14006d3cd  mov     rcx, rdi; this
0x14006d3d0  call    ?IsRemoteConnection@DXGPROCESS@@QEBAEXZ; DXGPROCESS::IsRemoteConnection(void)
0x14006d3d5  test    al, al
0x14006d3d7  jz      loc_14006D64E
0x14006d3dd  xorps   xmm0, xmm0
0x14006d3e0  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14006d3e4  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x14006d3e8  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x14006d3ec  call    cs:__imp_SeCaptureSubjectContext
0x14006d3f3  nop     dword ptr [rax+rax+00h]
0x14006d3f8  xor     eax, eax
0x14006d3fa  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14006d3fe  xorps   xmm0, xmm0
0x14006d401  mov     [rbp+57h+var_48], rax
0x14006d405  movups  [rbp+57h+SecurityDescriptor], xmm0
0x14006d409  lea     edx, [rax+1]; Revision
0x14006d40c  movups  [rbp+57h+var_58], xmm0
0x14006d410  call    cs:__imp_RtlCreateSecurityDescriptor
0x14006d417  nop     dword ptr [rax+rax+00h]
0x14006d41c  mov     ecx, 6; SubAuthorityCount
0x14006d421  call    cs:__imp_RtlLengthRequiredSid
0x14006d428  nop     dword ptr [rax+rax+00h]
0x14006d42d  mov     edi, 100h
0x14006d432  mov     ecx, eax
0x14006d434  mov     r8d, edi
0x14006d437  mov     edx, 4B677844h
0x14006d43c  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14006d441  mov     rsi, rax
0x14006d444  test    rax, rax
0x14006d447  jz      loc_14006D61D
0x14006d44d  mov     r8b, 6; SubAuthorityCount
0x14006d450  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x14006d457  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14006d45b  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x14006d461  mov     rcx, rax; Sid
0x14006d464  call    cs:__imp_RtlInitializeSid
0x14006d46b  nop     dword ptr [rax+rax+00h]
0x14006d470  xor     edx, edx; SubAuthority
0x14006d472  mov     rcx, rsi; Sid
0x14006d475  call    cs:__imp_RtlSubAuthoritySid
0x14006d47c  nop     dword ptr [rax+rax+00h]
0x14006d481  mov     edx, 1; SubAuthority
0x14006d486  mov     rcx, rsi; Sid
0x14006d489  mov     dword ptr [rax], 50h ; 'P'
0x14006d48f  call    cs:__imp_RtlSubAuthoritySid
0x14006d496  nop     dword ptr [rax+rax+00h]
0x14006d49b  mov     edx, 2; SubAuthority
0x14006d4a0  mov     rcx, rsi; Sid
0x14006d4a3  mov     dword ptr [rax], 5925C7CBh
0x14006d4a9  call    cs:__imp_RtlSubAuthoritySid
0x14006d4b0  nop     dword ptr [rax+rax+00h]
0x14006d4b5  mov     edx, 3; SubAuthority
0x14006d4ba  mov     rcx, rsi; Sid
0x14006d4bd  mov     dword ptr [rax], 9538691Fh
0x14006d4c3  call    cs:__imp_RtlSubAuthoritySid
0x14006d4ca  nop     dword ptr [rax+rax+00h]
0x14006d4cf  mov     edx, 4; SubAuthority
0x14006d4d4  mov     rcx, rsi; Sid
0x14006d4d7  mov     dword ptr [rax], 5F3BCD45h
0x14006d4dd  call    cs:__imp_RtlSubAuthoritySid
0x14006d4e4  nop     dword ptr [rax+rax+00h]
0x14006d4e9  mov     edx, 5; SubAuthority
0x14006d4ee  mov     rcx, rsi; Sid
0x14006d4f1  mov     dword ptr [rax], 0CD5931B7h
0x14006d4f7  call    cs:__imp_RtlSubAuthoritySid
0x14006d4fe  nop     dword ptr [rax+rax+00h]
0x14006d503  mov     rcx, rsi; Sid
0x14006d506  mov     dword ptr [rax], 4E7B6113h
0x14006d50c  call    cs:__imp_RtlLengthSid
0x14006d513  nop     dword ptr [rax+rax+00h]
0x14006d518  mov     r8d, edi
0x14006d51b  mov     edx, 4B677844h
0x14006d520  lea     ebx, [rax+14h]
0x14006d523  mov     ecx, ebx
0x14006d525  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14006d52a  mov     rdi, rax
0x14006d52d  test    rax, rax
0x14006d530  jz      loc_14006D61F
0x14006d536  mov     r8d, 2; AclRevision
0x14006d53c  mov     edx, ebx; AclLength
0x14006d53e  mov     rcx, rax; Acl
0x14006d541  call    cs:__imp_RtlCreateAcl
0x14006d548  nop     dword ptr [rax+rax+00h]
0x14006d54d  mov     ebx, eax
0x14006d54f  test    eax, eax
0x14006d551  js      loc_14006D624
0x14006d557  mov     r9, rsi; Sid
0x14006d55a  mov     edx, 2; AceRevision
0x14006d55f  mov     r8d, 1F0000h; AccessMask
0x14006d565  mov     rcx, rdi; Acl
0x14006d568  call    cs:__imp_RtlAddAccessAllowedAce
0x14006d56f  nop     dword ptr [rax+rax+00h]
0x14006d574  mov     ebx, eax
0x14006d576  test    eax, eax
0x14006d578  js      loc_14006D624
0x14006d57e  xor     r9d, r9d; DaclDefaulted
0x14006d581  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14006d585  mov     r8, rdi; Dacl
0x14006d588  mov     dl, 1; DaclPresent
0x14006d58a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14006d591  nop     dword ptr [rax+rax+00h]
0x14006d596  mov     ebx, eax
0x14006d598  test    eax, eax
0x14006d59a  js      loc_14006D624
0x14006d5a0  mov     eax, 20000h
0x14006d5a5  mov     [rbp+57h+var_38.GenericAll], 1F0000h
0x14006d5ac  mov     [rbp+57h+var_38.GenericRead], eax
0x14006d5af  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x14006d5b3  mov     [rbp+57h+var_38.GenericWrite], eax
0x14006d5b6  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14006d5ba  mov     [rbp+57h+var_38.GenericExecute], eax
0x14006d5bd  mov     r9d, 1F0000h; DesiredAccess
0x14006d5c3  lea     rax, [rbp+57h+var_90]
0x14006d5c7  mov     [rbp+57h+var_8C], 0
0x14006d5ce  mov     [rsp+0E0h+AccessStatus], rax; AccessStatus
0x14006d5d3  xor     r8d, r8d; SubjectContextLocked
0x14006d5d6  lea     rax, [rbp+57h+var_8C]
0x14006d5da  mov     [rbp+57h+var_90], 0
0x14006d5e1  mov     [rsp+0E0h+GrantedAccess], rax; GrantedAccess
0x14006d5e6  lea     rax, [rbp+57h+var_38]
0x14006d5ea  mov     [rsp+0E0h+AccessMode], 1; AccessMode
0x14006d5ef  mov     [rsp+0E0h+GenericMapping], rax; GenericMapping
0x14006d5f4  mov     [rsp+0E0h+Privileges], 0; Privileges
0x14006d5fd  mov     [rsp+0E0h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14006d605  call    cs:__imp_SeAccessCheck
0x14006d60c  nop     dword ptr [rax+rax+00h]
0x14006d611  mov     ebx, [rbp+57h+var_90]
0x14006d614  xor     ecx, ecx
0x14006d616  test    al, al
0x14006d618  cmovnz  ebx, ecx
0x14006d61b  jmp     short loc_14006D624
0x14006d61d  xor     edi, edi
0x14006d61f  mov     ebx, 0C0000017h
0x14006d624  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14006d628  call    cs:__imp_SeReleaseSubjectContext
0x14006d62f  nop     dword ptr [rax+rax+00h]
0x14006d634  test    rsi, rsi
0x14006d637  jz      short loc_14006D641
0x14006d639  mov     rcx, rsi; void *
0x14006d63c  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14006d641  test    rdi, rdi
0x14006d644  jz      short loc_14006D64E
0x14006d646  mov     rcx, rdi; void *
0x14006d649  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14006d64e  mov     eax, ebx
0x14006d650  mov     rcx, [rbp+57h+var_28]
0x14006d654  xor     rcx, rsp; StackCookie
0x14006d657  call    __security_check_cookie
0x14006d65c  add     rsp, 0C8h
0x14006d663  pop     rdi
0x14006d664  pop     rsi
0x14006d665  pop     rbx
0x14006d666  pop     rbp
0x14006d667  retn
```
