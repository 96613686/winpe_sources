# DxgkNetDispAccessCheck(DXGPROCESS *)

- ea: `0x14006ce28`
- end: `0x14006d109`
- name: `?DxgkNetDispAccessCheck@@YAJPEAVDXGPROCESS@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(struct DXGPROCESS *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14020b790`
- `0x14020baa0`
- `0x14020bd00`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140046ac8`
- `0x14006ce28`
- `0x1400a0100`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14006ce59`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14006ce59`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14006ce8c`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14006ce8c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14006ceb0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14006ceb0`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14006cec1`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14006cec1`
- `ntoskrnl!RtlInitializeSid` at `0x14006cf04`
- `ntoskrnl!RtlInitializeSid` at `0x14006cf04`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf15`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf2f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf49`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf63`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf7d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf97`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf15`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf2f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf49`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf63`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf7d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14006cf97`
- `ntoskrnl!RtlLengthSid` at `0x14006cfac`
- `ntoskrnl!RtlLengthSid` at `0x14006cfac`
- `ntoskrnl!RtlCreateAcl` at `0x14006cfe1`
- `ntoskrnl!RtlCreateAcl` at `0x14006cfe1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006d008`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006d008`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14006d02a`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14006d02a`
- `ntoskrnl!SeAccessCheck` at `0x14006d0a5`
- `ntoskrnl!SeAccessCheck` at `0x14006d0a5`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006d0c8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006d0c8`

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
0x14006ce28  push    rbp
0x14006ce2a  push    rbx
0x14006ce2b  push    rsi
0x14006ce2c  push    rdi
0x14006ce2d  lea     rbp, [rsp-3Fh]
0x14006ce32  sub     rsp, 0C8h
0x14006ce39  mov     rax, cs:__security_cookie
0x14006ce40  xor     rax, rsp
0x14006ce43  mov     [rbp+57h+var_28], rax
0x14006ce47  mov     rdi, rcx
0x14006ce4a  test    rcx, rcx
0x14006ce4d  jz      short loc_14006CE7D
0x14006ce4f  xor     ebx, ebx
0x14006ce51  cmp     cs:?g_OSTestSigningEnabled@@3EA, bl; uchar g_OSTestSigningEnabled
0x14006ce57  jz      short loc_14006CE6D
0x14006ce59  call    cs:__imp_PsGetCurrentProcessSessionId
0x14006ce60  nop     dword ptr [rax+rax+00h]
0x14006ce65  test    eax, eax
0x14006ce67  jz      loc_14006D0EE
0x14006ce6d  mov     rcx, rdi; this
0x14006ce70  call    ?IsRemoteConnection@DXGPROCESS@@QEBAEXZ; DXGPROCESS::IsRemoteConnection(void)
0x14006ce75  test    al, al
0x14006ce77  jz      loc_14006D0EE
0x14006ce7d  xorps   xmm0, xmm0
0x14006ce80  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14006ce84  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x14006ce88  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x14006ce8c  call    cs:__imp_SeCaptureSubjectContext
0x14006ce93  nop     dword ptr [rax+rax+00h]
0x14006ce98  xor     eax, eax
0x14006ce9a  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14006ce9e  xorps   xmm0, xmm0
0x14006cea1  mov     [rbp+57h+var_48], rax
0x14006cea5  movups  [rbp+57h+SecurityDescriptor], xmm0
0x14006cea9  lea     edx, [rax+1]; Revision
0x14006ceac  movups  [rbp+57h+var_58], xmm0
0x14006ceb0  call    cs:__imp_RtlCreateSecurityDescriptor
0x14006ceb7  nop     dword ptr [rax+rax+00h]
0x14006cebc  mov     ecx, 6; SubAuthorityCount
0x14006cec1  call    cs:__imp_RtlLengthRequiredSid
0x14006cec8  nop     dword ptr [rax+rax+00h]
0x14006cecd  mov     edi, 100h
0x14006ced2  mov     ecx, eax
0x14006ced4  mov     r8d, edi
0x14006ced7  mov     edx, 4B677844h
0x14006cedc  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14006cee1  mov     rsi, rax
0x14006cee4  test    rax, rax
0x14006cee7  jz      loc_14006D0BD
0x14006ceed  mov     r8b, 6; SubAuthorityCount
0x14006cef0  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x14006cef7  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14006cefb  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x14006cf01  mov     rcx, rax; Sid
0x14006cf04  call    cs:__imp_RtlInitializeSid
0x14006cf0b  nop     dword ptr [rax+rax+00h]
0x14006cf10  xor     edx, edx; SubAuthority
0x14006cf12  mov     rcx, rsi; Sid
0x14006cf15  call    cs:__imp_RtlSubAuthoritySid
0x14006cf1c  nop     dword ptr [rax+rax+00h]
0x14006cf21  mov     edx, 1; SubAuthority
0x14006cf26  mov     rcx, rsi; Sid
0x14006cf29  mov     dword ptr [rax], 50h ; 'P'
0x14006cf2f  call    cs:__imp_RtlSubAuthoritySid
0x14006cf36  nop     dword ptr [rax+rax+00h]
0x14006cf3b  mov     edx, 2; SubAuthority
0x14006cf40  mov     rcx, rsi; Sid
0x14006cf43  mov     dword ptr [rax], 5925C7CBh
0x14006cf49  call    cs:__imp_RtlSubAuthoritySid
0x14006cf50  nop     dword ptr [rax+rax+00h]
0x14006cf55  mov     edx, 3; SubAuthority
0x14006cf5a  mov     rcx, rsi; Sid
0x14006cf5d  mov     dword ptr [rax], 9538691Fh
0x14006cf63  call    cs:__imp_RtlSubAuthoritySid
0x14006cf6a  nop     dword ptr [rax+rax+00h]
0x14006cf6f  mov     edx, 4; SubAuthority
0x14006cf74  mov     rcx, rsi; Sid
0x14006cf77  mov     dword ptr [rax], 5F3BCD45h
0x14006cf7d  call    cs:__imp_RtlSubAuthoritySid
0x14006cf84  nop     dword ptr [rax+rax+00h]
0x14006cf89  mov     edx, 5; SubAuthority
0x14006cf8e  mov     rcx, rsi; Sid
0x14006cf91  mov     dword ptr [rax], 0CD5931B7h
0x14006cf97  call    cs:__imp_RtlSubAuthoritySid
0x14006cf9e  nop     dword ptr [rax+rax+00h]
0x14006cfa3  mov     rcx, rsi; Sid
0x14006cfa6  mov     dword ptr [rax], 4E7B6113h
0x14006cfac  call    cs:__imp_RtlLengthSid
0x14006cfb3  nop     dword ptr [rax+rax+00h]
0x14006cfb8  mov     r8d, edi
0x14006cfbb  mov     edx, 4B677844h
0x14006cfc0  lea     ebx, [rax+14h]
0x14006cfc3  mov     ecx, ebx
0x14006cfc5  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14006cfca  mov     rdi, rax
0x14006cfcd  test    rax, rax
0x14006cfd0  jz      loc_14006D0BF
0x14006cfd6  mov     r8d, 2; AclRevision
0x14006cfdc  mov     edx, ebx; AclLength
0x14006cfde  mov     rcx, rax; Acl
0x14006cfe1  call    cs:__imp_RtlCreateAcl
0x14006cfe8  nop     dword ptr [rax+rax+00h]
0x14006cfed  mov     ebx, eax
0x14006cfef  test    eax, eax
0x14006cff1  js      loc_14006D0C4
0x14006cff7  mov     r9, rsi; Sid
0x14006cffa  mov     edx, 2; AceRevision
0x14006cfff  mov     r8d, 1F0000h; AccessMask
0x14006d005  mov     rcx, rdi; Acl
0x14006d008  call    cs:__imp_RtlAddAccessAllowedAce
0x14006d00f  nop     dword ptr [rax+rax+00h]
0x14006d014  mov     ebx, eax
0x14006d016  test    eax, eax
0x14006d018  js      loc_14006D0C4
0x14006d01e  xor     r9d, r9d; DaclDefaulted
0x14006d021  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14006d025  mov     r8, rdi; Dacl
0x14006d028  mov     dl, 1; DaclPresent
0x14006d02a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14006d031  nop     dword ptr [rax+rax+00h]
0x14006d036  mov     ebx, eax
0x14006d038  test    eax, eax
0x14006d03a  js      loc_14006D0C4
0x14006d040  mov     eax, 20000h
0x14006d045  mov     [rbp+57h+var_38.GenericAll], 1F0000h
0x14006d04c  mov     [rbp+57h+var_38.GenericRead], eax
0x14006d04f  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x14006d053  mov     [rbp+57h+var_38.GenericWrite], eax
0x14006d056  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14006d05a  mov     [rbp+57h+var_38.GenericExecute], eax
0x14006d05d  mov     r9d, 1F0000h; DesiredAccess
0x14006d063  lea     rax, [rbp+57h+var_90]
0x14006d067  mov     [rbp+57h+var_8C], 0
0x14006d06e  mov     [rsp+0E0h+AccessStatus], rax; AccessStatus
0x14006d073  xor     r8d, r8d; SubjectContextLocked
0x14006d076  lea     rax, [rbp+57h+var_8C]
0x14006d07a  mov     [rbp+57h+var_90], 0
0x14006d081  mov     [rsp+0E0h+GrantedAccess], rax; GrantedAccess
0x14006d086  lea     rax, [rbp+57h+var_38]
0x14006d08a  mov     [rsp+0E0h+AccessMode], 1; AccessMode
0x14006d08f  mov     [rsp+0E0h+GenericMapping], rax; GenericMapping
0x14006d094  mov     [rsp+0E0h+Privileges], 0; Privileges
0x14006d09d  mov     [rsp+0E0h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14006d0a5  call    cs:__imp_SeAccessCheck
0x14006d0ac  nop     dword ptr [rax+rax+00h]
0x14006d0b1  mov     ebx, [rbp+57h+var_90]
0x14006d0b4  xor     ecx, ecx
0x14006d0b6  test    al, al
0x14006d0b8  cmovnz  ebx, ecx
0x14006d0bb  jmp     short loc_14006D0C4
0x14006d0bd  xor     edi, edi
0x14006d0bf  mov     ebx, 0C0000017h
0x14006d0c4  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14006d0c8  call    cs:__imp_SeReleaseSubjectContext
0x14006d0cf  nop     dword ptr [rax+rax+00h]
0x14006d0d4  test    rsi, rsi
0x14006d0d7  jz      short loc_14006D0E1
0x14006d0d9  mov     rcx, rsi; void *
0x14006d0dc  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14006d0e1  test    rdi, rdi
0x14006d0e4  jz      short loc_14006D0EE
0x14006d0e6  mov     rcx, rdi; void *
0x14006d0e9  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14006d0ee  mov     eax, ebx
0x14006d0f0  mov     rcx, [rbp+57h+var_28]
0x14006d0f4  xor     rcx, rsp; StackCookie
0x14006d0f7  call    __security_check_cookie
0x14006d0fc  add     rsp, 0C8h
0x14006d103  pop     rdi
0x14006d104  pop     rsi
0x14006d105  pop     rbx
0x14006d106  pop     rbp
0x14006d107  retn
```
