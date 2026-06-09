# CreateDBWinMutex

- ea: `0x180071c10`
- end: `0x1800720f4`
- name: `CreateDBWinMutex`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c7fd0`

## callees

- `0x18004b9d0`
- `0x180071c10`
- `0x180072100`
- `0x180072360`
- `0x180072e90`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180071f97`
- `ntdll!RtlInitUnicodeString` at `0x180071f97`
- `ntdll!RtlSetLastWin32Error` at `0x180072028`
- `ntdll!RtlSetLastWin32Error` at `0x180072028`
- `ntdll!RtlFreeSid` at `0x180072052`
- `ntdll!RtlFreeSid` at `0x180072068`
- `ntdll!RtlFreeSid` at `0x18007207e`
- `ntdll!RtlFreeSid` at `0x180072094`
- `ntdll!RtlFreeSid` at `0x180072052`
- `ntdll!RtlFreeSid` at `0x180072068`
- `ntdll!RtlFreeSid` at `0x18007207e`
- `ntdll!RtlFreeSid` at `0x180072094`
- `ntdll!RtlCreateAcl` at `0x180071e31`
- `ntdll!RtlCreateAcl` at `0x180071f0e`
- `ntdll!RtlCreateAcl` at `0x180071e31`
- `ntdll!RtlCreateAcl` at `0x180071f0e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180071db9`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180071db9`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180071ec6`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180071ec6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180071cbb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180071d09`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180071d51`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180071d9c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180071cbb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180071d09`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180071d51`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180071d9c`
- `ntdll!RtlLengthSid` at `0x180071dda`
- `ntdll!RtlLengthSid` at `0x180071ded`
- `ntdll!RtlLengthSid` at `0x180071e00`
- `ntdll!RtlLengthSid` at `0x180071edf`
- `ntdll!RtlLengthSid` at `0x180071dda`
- `ntdll!RtlLengthSid` at `0x180071ded`
- `ntdll!RtlLengthSid` at `0x180071e00`
- `ntdll!RtlLengthSid` at `0x180071edf`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180071f5f`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180071f5f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180071e58`
- `ntdll!RtlAddAccessAllowedAce` at `0x180071e7f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180071ea6`
- `ntdll!RtlAddAccessAllowedAce` at `0x180071e58`
- `ntdll!RtlAddAccessAllowedAce` at `0x180071e7f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180071ea6`
- `ntdll!RtlAddMandatoryAce` at `0x180071f3f`
- `ntdll!RtlAddMandatoryAce` at `0x180071f3f`
- `ntdll!NtCreateMutant` at `0x180072007`
- `ntdll!NtCreateMutant` at `0x180072007`

## pseudocode

```c
HANDLE CreateDBWinMutex()
{
  ACL *v0; // rdi
  ACL *v1; // rbx
  HANDLE v2; // r14
  ULONG v3; // esi
  ULONG v4; // esi
  ULONG v5; // esi
  ACL *v6; // rax
  SIZE_T v7; // rsi
  ACL *v8; // rax
  NTSTATUS NamedObjectDirectory; // eax
  ULONG v10; // ecx
  void *SubAuthority3; // [rsp+30h] [rbp-D8h]
  PSID Sid; // [rsp+68h] [rbp-A0h] BYREF
  PSID v14; // [rsp+70h] [rbp-98h] BYREF
  PSID v15; // [rsp+78h] [rbp-90h] BYREF
  PSID v16; // [rsp+80h] [rbp-88h] BYREF
  void *v17; // [rsp+88h] [rbp-80h] BYREF
  HANDLE MutantHandle; // [rsp+90h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-10h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+100h] [rbp-8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v24; // [rsp+108h] [rbp+0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v25; // [rsp+110h] [rbp+8h] BYREF

  v22 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v24.Value = 0;
  *(_DWORD *)v25.Value = 0;
  v0 = 0;
  v1 = 0;
  v2 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_WORD *)&v24.Value[4] = 256;
  *(_WORD *)&v25.Value[4] = 4096;
  Sid = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid) >= 0
    && RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v14) >= 0
    && RtlAllocateAndInitializeSid(&v24, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v15) >= 0
    && RtlAllocateAndInitializeSid(&v25, 1u, 0x1000u, 0, 0, 0, 0, 0, 0, 0, &v16) >= 0
    && RtlCreateSecurityDescriptor(SecurityDescriptor, 1u) >= 0 )
  {
    v3 = RtlLengthSid(v15);
    v4 = RtlLengthSid(v14) + v3;
    v5 = RtlLengthSid(Sid) + 32 + v4;
    v6 = (ACL *)GlobalAlloc(0, v5);
    v0 = v6;
    if ( v6 )
    {
      if ( RtlCreateAcl(v6, v5, 2u) >= 0
        && RtlAddAccessAllowedAce(v0, 2u, 0x120001u, v15) >= 0
        && RtlAddAccessAllowedAce(v0, 2u, 0x1F0001u, Sid) >= 0
        && RtlAddAccessAllowedAce(v0, 2u, 0x1F0001u, v14) >= 0
        && RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v0, 0) >= 0 )
      {
        v7 = RtlLengthSid(v16) + 16;
        v8 = (ACL *)GlobalAlloc(0, v7);
        v1 = v8;
        if ( v8 )
        {
          if ( RtlCreateAcl(v8, v7, 2u) >= 0 )
          {
            LODWORD(SubAuthority3) = 1;
            if ( RtlAddMandatoryAce(v1, 2u, 0, (ULONG)v16, 0x11u, SubAuthority3) >= 0
              && RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, v1, 0) >= 0 )
            {
              MutantHandle = 0;
              memset(&ObjectAttributes, 0, 44);
              DestinationString = 0;
              RtlInitUnicodeString(&DestinationString, L"DBWinMutex");
              v17 = 0;
              NamedObjectDirectory = BaseGetNamedObjectDirectory(&v17);
              if ( NamedObjectDirectory < 0 )
                goto LABEL_37;
              ObjectAttributes.RootDirectory = v17;
              ObjectAttributes.ObjectName = &DestinationString;
              ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
              ObjectAttributes.Length = 48;
              ObjectAttributes.Attributes = 128;
              ObjectAttributes.SecurityQualityOfService = 0;
              if ( pfnAdjustObjectAttributesForPrivateNamespace )
                pfnAdjustObjectAttributesForPrivateNamespace(&ObjectAttributes);
              NamedObjectDirectory = NtCreateMutant(&MutantHandle, 0x2120001u, &ObjectAttributes, 0);
              if ( NamedObjectDirectory < 0 )
              {
LABEL_37:
                BaseSetLastNTError((unsigned int)NamedObjectDirectory);
              }
              else
              {
                if ( NamedObjectDirectory == 0x40000000 )
                  v10 = 183;
                else
                  v10 = 0;
                RtlSetLastWin32Error(v10);
                v2 = MutantHandle;
              }
            }
          }
        }
      }
    }
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v14 )
    RtlFreeSid(v14);
  if ( v15 )
    RtlFreeSid(v15);
  if ( v16 )
    RtlFreeSid(v16);
  if ( v0 )
    GlobalFree(v0);
  if ( v1 )
    GlobalFree(v1);
  return v2;
}

```

## disassembly

```asm
0x180071c10  mov     r11, rsp
0x180071c13  push    rbp
0x180071c14  push    rbx
0x180071c15  push    r14
0x180071c17  lea     rbp, [r11-38h]
0x180071c1b  sub     rsp, 120h
0x180071c22  mov     rax, cs:__security_cookie
0x180071c29  xor     rax, rsp
0x180071c2c  mov     [rbp+30h+var_20], rax
0x180071c30  xor     eax, eax
0x180071c32  mov     [r11+10h], rdi
0x180071c36  xorps   xmm0, xmm0
0x180071c39  mov     [rbp+30h+var_40], rax
0x180071c3d  mov     dword ptr [rbp+30h+IdentifierAuthority.Value], eax
0x180071c40  lea     rcx, [rbp+30h+IdentifierAuthority]; IdentifierAuthority
0x180071c44  mov     dword ptr [rbp+30h+var_30.Value], eax
0x180071c47  xor     r9d, r9d; SubAuthority1
0x180071c4a  mov     dword ptr [rbp+30h+var_28.Value], eax
0x180071c4d  mov     r8d, 12h; SubAuthority0
0x180071c53  lea     rax, [rsp+130h+Sid]
0x180071c58  mov     [r11+18h], r15
0x180071c5c  xor     r15d, r15d
0x180071c5f  mov     [rsp+50h], rax; Sid
0x180071c64  mov     [rsp+130h+SubAuthority7], r15d; SubAuthority7
0x180071c69  mov     dl, 1; SubAuthorityCount
0x180071c6b  mov     [rsp+130h+SubAuthority6], r15d; SubAuthority6
0x180071c70  mov     edi, r15d
0x180071c73  mov     [rsp+130h+SubAuthority5], r15d; SubAuthority5
0x180071c78  mov     ebx, r15d
0x180071c7b  mov     [rsp+130h+SubAuthority4], r15d; SubAuthority4
0x180071c80  mov     r14d, r15d
0x180071c83  mov     dword ptr [rsp+130h+SubAuthority3], r15d; SubAuthority3
0x180071c88  mov     [rsp+130h+SubAuthority2], r15d; SubAuthority2
0x180071c8d  movups  [rbp+30h+SecurityDescriptor], xmm0
0x180071c91  mov     word ptr [rbp+30h+IdentifierAuthority.Value+4], 500h
0x180071c97  movups  [rbp+30h+var_50], xmm0
0x180071c9b  mov     word ptr [rbp+30h+var_30.Value+4], 100h
0x180071ca1  mov     word ptr [rbp+30h+var_28.Value+4], 1000h
0x180071ca7  mov     [rsp+130h+Sid], r15
0x180071cac  mov     [rsp+130h+var_C8], r15
0x180071cb1  mov     [rsp+130h+var_C0], r15
0x180071cb6  mov     [rsp+130h+var_B8], r15
0x180071cbb  call    cs:__imp_RtlAllocateAndInitializeSid
0x180071cc2  nop     dword ptr [rax+rax+00h]
0x180071cc7  test    eax, eax
0x180071cc9  js      loc_180072040
0x180071ccf  lea     rax, [rsp+130h+var_C8]
0x180071cd4  mov     r9d, 220h; SubAuthority1
0x180071cda  mov     [rsp+50h], rax; Sid
0x180071cdf  lea     rcx, [rbp+30h+IdentifierAuthority]; IdentifierAuthority
0x180071ce3  mov     [rsp+130h+SubAuthority7], r15d; SubAuthority7
0x180071ce8  mov     r8d, 20h ; ' '; SubAuthority0
0x180071cee  mov     [rsp+130h+SubAuthority6], r15d; SubAuthority6
0x180071cf3  mov     dl, 2; SubAuthorityCount
0x180071cf5  mov     [rsp+130h+SubAuthority5], r15d; SubAuthority5
0x180071cfa  mov     [rsp+130h+SubAuthority4], r15d; SubAuthority4
0x180071cff  mov     dword ptr [rsp+130h+SubAuthority3], r15d; SubAuthority3
0x180071d04  mov     [rsp+130h+SubAuthority2], r15d; SubAuthority2
0x180071d09  call    cs:__imp_RtlAllocateAndInitializeSid
0x180071d10  nop     dword ptr [rax+rax+00h]
0x180071d15  test    eax, eax
0x180071d17  js      loc_180072040
0x180071d1d  lea     rax, [rsp+130h+var_C0]
0x180071d22  xor     r9d, r9d; SubAuthority1
0x180071d25  mov     [rsp+50h], rax; Sid
0x180071d2a  lea     rcx, [rbp+30h+var_30]; IdentifierAuthority
0x180071d2e  mov     [rsp+130h+SubAuthority7], r15d; SubAuthority7
0x180071d33  xor     r8d, r8d; SubAuthority0
0x180071d36  mov     [rsp+130h+SubAuthority6], r15d; SubAuthority6
0x180071d3b  mov     dl, 1; SubAuthorityCount
0x180071d3d  mov     [rsp+130h+SubAuthority5], r15d; SubAuthority5
0x180071d42  mov     [rsp+130h+SubAuthority4], r15d; SubAuthority4
0x180071d47  mov     dword ptr [rsp+130h+SubAuthority3], r15d; SubAuthority3
0x180071d4c  mov     [rsp+130h+SubAuthority2], r15d; SubAuthority2
0x180071d51  call    cs:__imp_RtlAllocateAndInitializeSid
0x180071d58  nop     dword ptr [rax+rax+00h]
0x180071d5d  test    eax, eax
0x180071d5f  js      loc_180072040
0x180071d65  lea     rax, [rsp+130h+var_B8]
0x180071d6a  xor     r9d, r9d; SubAuthority1
0x180071d6d  mov     [rsp+50h], rax; Sid
0x180071d72  lea     rcx, [rbp+30h+var_28]; IdentifierAuthority
0x180071d76  mov     [rsp+130h+SubAuthority7], r15d; SubAuthority7
0x180071d7b  mov     r8d, 1000h; SubAuthority0
0x180071d81  mov     [rsp+130h+SubAuthority6], r15d; SubAuthority6
0x180071d86  mov     dl, 1; SubAuthorityCount
0x180071d88  mov     [rsp+130h+SubAuthority5], r15d; SubAuthority5
0x180071d8d  mov     [rsp+130h+SubAuthority4], r15d; SubAuthority4
0x180071d92  mov     dword ptr [rsp+130h+SubAuthority3], r15d; SubAuthority3
0x180071d97  mov     [rsp+130h+SubAuthority2], r15d; SubAuthority2
0x180071d9c  call    cs:__imp_RtlAllocateAndInitializeSid
0x180071da3  nop     dword ptr [rax+rax+00h]
0x180071da8  test    eax, eax
0x180071daa  js      loc_180072040
0x180071db0  mov     edx, 1; Revision
0x180071db5  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x180071db9  call    cs:__imp_RtlCreateSecurityDescriptor
0x180071dc0  nop     dword ptr [rax+rax+00h]
0x180071dc5  test    eax, eax
0x180071dc7  js      loc_180072040
0x180071dcd  mov     rcx, [rsp+130h+var_C0]; Sid
0x180071dd2  mov     [rsp+130h+arg_0], rsi
0x180071dda  call    cs:__imp_RtlLengthSid
0x180071de1  nop     dword ptr [rax+rax+00h]
0x180071de6  mov     rcx, [rsp+130h+var_C8]; Sid
0x180071deb  mov     esi, eax
0x180071ded  call    cs:__imp_RtlLengthSid
0x180071df4  nop     dword ptr [rax+rax+00h]
0x180071df9  mov     rcx, [rsp+130h+Sid]; Sid
0x180071dfe  add     esi, eax
0x180071e00  call    cs:__imp_RtlLengthSid
0x180071e07  nop     dword ptr [rax+rax+00h]
0x180071e0c  add     eax, 20h ; ' '
0x180071e0f  xor     ecx, ecx; uFlags
0x180071e11  add     esi, eax
0x180071e13  mov     edx, esi; dwBytes
0x180071e15  call    GlobalAlloc
0x180071e1a  mov     rdi, rax
0x180071e1d  test    rax, rax
0x180071e20  jz      loc_180072038
0x180071e26  mov     r8d, 2; AclRevision
0x180071e2c  mov     edx, esi; AclSize
0x180071e2e  mov     rcx, rax; Acl
0x180071e31  call    cs:__imp_RtlCreateAcl
0x180071e38  nop     dword ptr [rax+rax+00h]
0x180071e3d  test    eax, eax
0x180071e3f  js      loc_180072038
0x180071e45  mov     r9, [rsp+130h+var_C0]; Sid
0x180071e4a  mov     edx, 2; Revision
0x180071e4f  mov     r8d, 120001h; AccessMask
0x180071e55  mov     rcx, rdi; Acl
0x180071e58  call    cs:__imp_RtlAddAccessAllowedAce
0x180071e5f  nop     dword ptr [rax+rax+00h]
0x180071e64  test    eax, eax
0x180071e66  js      loc_180072038
0x180071e6c  mov     r9, [rsp+130h+Sid]; Sid
0x180071e71  mov     edx, 2; Revision
0x180071e76  mov     r8d, 1F0001h; AccessMask
0x180071e7c  mov     rcx, rdi; Acl
0x180071e7f  call    cs:__imp_RtlAddAccessAllowedAce
0x180071e86  nop     dword ptr [rax+rax+00h]
0x180071e8b  test    eax, eax
0x180071e8d  js      loc_180072038
0x180071e93  mov     r9, [rsp+130h+var_C8]; Sid
0x180071e98  mov     edx, 2; Revision
0x180071e9d  mov     r8d, 1F0001h; AccessMask
0x180071ea3  mov     rcx, rdi; Acl
0x180071ea6  call    cs:__imp_RtlAddAccessAllowedAce
0x180071ead  nop     dword ptr [rax+rax+00h]
0x180071eb2  test    eax, eax
0x180071eb4  js      loc_180072038
0x180071eba  xor     r9d, r9d; DaclDefaulted
0x180071ebd  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x180071ec1  mov     r8, rdi; Dacl
0x180071ec4  mov     dl, 1; DaclPresent
0x180071ec6  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180071ecd  nop     dword ptr [rax+rax+00h]
0x180071ed2  test    eax, eax
0x180071ed4  js      loc_180072038
0x180071eda  mov     rcx, [rsp+130h+var_B8]; Sid
0x180071edf  call    cs:__imp_RtlLengthSid
0x180071ee6  nop     dword ptr [rax+rax+00h]
0x180071eeb  xor     ecx, ecx; uFlags
0x180071eed  lea     esi, [rax+10h]
0x180071ef0  mov     edx, esi; dwBytes
0x180071ef2  call    GlobalAlloc
0x180071ef7  mov     rbx, rax
0x180071efa  test    rax, rax
0x180071efd  jz      loc_180072038
0x180071f03  mov     r8d, 2; AclRevision
0x180071f09  mov     edx, esi; AclSize
0x180071f0b  mov     rcx, rax; Acl
0x180071f0e  call    cs:__imp_RtlCreateAcl
0x180071f15  nop     dword ptr [rax+rax+00h]
0x180071f1a  test    eax, eax
0x180071f1c  js      loc_180072038
0x180071f22  mov     r9, [rsp+130h+var_B8]; MandatoryFlags
0x180071f27  xor     r8d, r8d; Flags
0x180071f2a  mov     dword ptr [rsp+130h+SubAuthority3], 1; LabelSid
0x180071f32  mov     edx, 2; Revision
0x180071f37  mov     rcx, rbx; Acl
0x180071f3a  mov     byte ptr [rsp+130h+SubAuthority2], 11h; AceType
0x180071f3f  call    cs:__imp_RtlAddMandatoryAce
0x180071f46  nop     dword ptr [rax+rax+00h]
0x180071f4b  test    eax, eax
0x180071f4d  js      loc_180072038
0x180071f53  xor     r9d, r9d; SaclDefaulted
0x180071f56  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x180071f5a  mov     r8, rbx; Sacl
0x180071f5d  mov     dl, 1; SaclPresent
0x180071f5f  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x180071f66  nop     dword ptr [rax+rax+00h]
0x180071f6b  test    eax, eax
0x180071f6d  js      loc_180072038
0x180071f73  xorps   xmm0, xmm0
0x180071f76  mov     [rbp+30h+MutantHandle], r15
0x180071f7a  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x180071f7e  xor     eax, eax
0x180071f80  lea     rdx, aDbwinmutex; "DBWinMutex"
0x180071f87  lea     rcx, [rbp+30h+DestinationString]; DestinationString
0x180071f8b  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x180071f8f  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x180071f93  movups  xmmword ptr [rbp+30h+DestinationString.Length], xmm0
0x180071f97  call    cs:__imp_RtlInitUnicodeString
0x180071f9e  nop     dword ptr [rax+rax+00h]
0x180071fa3  lea     rcx, [rbp+30h+var_B0]
0x180071fa7  mov     [rbp+30h+var_B0], r15
0x180071fab  call    BaseGetNamedObjectDirectory
0x180071fb0  test    eax, eax
0x180071fb2  js      loc_1800720E8
0x180071fb8  mov     rax, [rbp+30h+var_B0]
0x180071fbc  mov     [rbp+30h+ObjectAttributes.RootDirectory], rax
0x180071fc0  lea     rax, [rbp+30h+DestinationString]
0x180071fc4  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x180071fc8  lea     rax, [rbp+30h+SecurityDescriptor]
0x180071fcc  mov     [rbp+30h+ObjectAttributes.SecurityDescriptor], rax
0x180071fd0  mov     rax, cs:pfnAdjustObjectAttributesForPrivateNamespace
0x180071fd7  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x180071fde  mov     [rbp+30h+ObjectAttributes.Attributes], 80h
0x180071fe5  mov     [rbp+30h+ObjectAttributes.SecurityQualityOfService], r15
0x180071fe9  test    rax, rax
0x180071fec  jz      short loc_180071FF7
0x180071fee  lea     rcx, [rbp+30h+ObjectAttributes]
0x180071ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ff7  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x180071ffb  xor     r9d, r9d; InitialOwner
0x180071ffe  mov     edx, 2120001h; DesiredAccess
0x180072003  lea     rcx, [rbp+30h+MutantHandle]; MutantHandle
0x180072007  call    cs:__imp_NtCreateMutant
0x18007200e  nop     dword ptr [rax+rax+00h]
0x180072013  test    eax, eax
0x180072015  js      loc_1800720E8
0x18007201b  cmp     eax, 40000000h
0x180072020  jz      loc_1800720DE
0x180072026  xor     ecx, ecx; LastError
0x180072028  call    cs:__imp_RtlSetLastWin32Error
0x18007202f  nop     dword ptr [rax+rax+00h]
0x180072034  mov     r14, [rbp+30h+MutantHandle]
0x180072038  mov     rsi, [rsp+130h+arg_0]
0x180072040  mov     rcx, [rsp+130h+Sid]; Sid
0x180072045  mov     r15, [rsp+130h+arg_10]
0x18007204d  test    rcx, rcx
0x180072050  jz      short loc_18007205E
0x180072052  call    cs:__imp_RtlFreeSid
0x180072059  nop     dword ptr [rax+rax+00h]
0x18007205e  mov     rcx, [rsp+130h+var_C8]; Sid
0x180072063  test    rcx, rcx
0x180072066  jz      short loc_180072074
0x180072068  call    cs:__imp_RtlFreeSid
0x18007206f  nop     dword ptr [rax+rax+00h]
0x180072074  mov     rcx, [rsp+130h+var_C0]; Sid
0x180072079  test    rcx, rcx
0x18007207c  jz      short loc_18007208A
0x18007207e  call    cs:__imp_RtlFreeSid
0x180072085  nop     dword ptr [rax+rax+00h]
0x18007208a  mov     rcx, [rsp+130h+var_B8]; Sid
0x18007208f  test    rcx, rcx
0x180072092  jz      short loc_1800720A0
0x180072094  call    cs:__imp_RtlFreeSid
0x18007209b  nop     dword ptr [rax+rax+00h]
0x1800720a0  test    rdi, rdi
0x1800720a3  jz      short loc_1800720AD
0x1800720a5  mov     rcx, rdi; hMem
0x1800720a8  call    GlobalFree
0x1800720ad  mov     rdi, [rsp+130h+arg_8]
0x1800720b5  test    rbx, rbx
0x1800720b8  jz      short loc_1800720C2
0x1800720ba  mov     rcx, rbx; hMem
0x1800720bd  call    GlobalFree
0x1800720c2  mov     rax, r14
0x1800720c5  mov     rcx, [rbp+30h+var_20]
0x1800720c9  xor     rcx, rsp; StackCookie
0x1800720cc  call    __security_check_cookie
0x1800720d1  add     rsp, 120h
0x1800720d8  pop     r14
0x1800720da  pop     rbx
0x1800720db  pop     rbp
0x1800720dc  retn
0x1800720de  mov     ecx, 0B7h
0x1800720e3  jmp     loc_180072028
0x1800720e8  mov     ecx, eax
0x1800720ea  call    BaseSetLastNTError
0x1800720ef  jmp     loc_180072038
```
