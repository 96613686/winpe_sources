# ndisBuildDeviceAcl(_ACL * *,ulong)

- ea: `0x140071ba0`
- end: `0x1400720fc`
- name: `?ndisBuildDeviceAcl@@YAJPEAPEAU_ACL@@K@Z`
- size: `1372`
- prototype: `__int64 __fastcall(struct _ACL **, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x1400719b0`
- `0x14014a030`

## callees

- `0x140071ba0`
- `0x1400eb380`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140071be3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140071be3`
- `ntoskrnl!RtlMapGenericMask` at `0x140071bf7`
- `ntoskrnl!RtlMapGenericMask` at `0x140071bf7`
- `ntoskrnl!RtlInitializeSid` at `0x140071d3e`
- `ntoskrnl!RtlInitializeSid` at `0x140071e1b`
- `ntoskrnl!RtlInitializeSid` at `0x140071d3e`
- `ntoskrnl!RtlInitializeSid` at `0x140071e1b`
- `ntoskrnl!RtlLengthSid` at `0x140071c14`
- `ntoskrnl!RtlLengthSid` at `0x140071c45`
- `ntoskrnl!RtlLengthSid` at `0x140071c75`
- `ntoskrnl!RtlLengthSid` at `0x140071ca2`
- `ntoskrnl!RtlLengthSid` at `0x140071cb7`
- `ntoskrnl!RtlLengthSid` at `0x140071ccc`
- `ntoskrnl!RtlLengthSid` at `0x140071d6b`
- `ntoskrnl!RtlLengthSid` at `0x140071dab`
- `ntoskrnl!RtlLengthSid` at `0x140071e4b`
- `ntoskrnl!RtlLengthSid` at `0x140071e79`
- `ntoskrnl!RtlLengthSid` at `0x140071c14`
- `ntoskrnl!RtlLengthSid` at `0x140071c45`
- `ntoskrnl!RtlLengthSid` at `0x140071c75`
- `ntoskrnl!RtlLengthSid` at `0x140071ca2`
- `ntoskrnl!RtlLengthSid` at `0x140071cb7`
- `ntoskrnl!RtlLengthSid` at `0x140071ccc`
- `ntoskrnl!RtlLengthSid` at `0x140071d6b`
- `ntoskrnl!RtlLengthSid` at `0x140071dab`
- `ntoskrnl!RtlLengthSid` at `0x140071e4b`
- `ntoskrnl!RtlLengthSid` at `0x140071e79`
- `ntoskrnl!SeExports` at `0x140071c03`
- `ntoskrnl!SeExports` at `0x140071c34`
- `ntoskrnl!SeExports` at `0x140071c64`
- `ntoskrnl!SeExports` at `0x140071d9a`
- `ntoskrnl!SeExports` at `0x140071f06`
- `ntoskrnl!SeExports` at `0x140071f34`
- `ntoskrnl!SeExports` at `0x140071f62`
- `ntoskrnl!SeExports` at `0x140072018`
- `ntoskrnl!RtlCreateAcl` at `0x140071ed9`
- `ntoskrnl!RtlCreateAcl` at `0x140071ed9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071f21`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071f52`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071f80`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071fa4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071fc4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071fe4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140072007`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140072036`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14007205c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140072080`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071f21`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071f52`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071f80`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071fa4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071fc4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140071fe4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140072007`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140072036`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14007205c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140072080`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071ef0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400720a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400720c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071ef0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400720a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400720c3`
- `ntoskrnl!ExAllocatePool2` at `0x140071d10`
- `ntoskrnl!ExAllocatePool2` at `0x140071ded`
- `ntoskrnl!ExAllocatePool2` at `0x140071e9c`
- `ntoskrnl!ExAllocatePool2` at `0x140071d10`
- `ntoskrnl!ExAllocatePool2` at `0x140071ded`
- `ntoskrnl!ExAllocatePool2` at `0x140071e9c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140071cf7`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140071dd4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140071cf7`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140071dd4`

## pseudocode

```c
__int64 __fastcall ndisBuildDeviceAcl(struct _ACL **a1, char a2)
{
  _DWORD *v2; // r14
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  ULONG v5; // r13d
  int v6; // esi
  int v7; // ebp
  ULONG v8; // edi
  ULONG v9; // edi
  int v10; // r15d
  ULONG v11; // eax
  void *Pool2; // rax
  NTSTATUS Acl; // edi
  int v15; // r12d
  int v16; // r13d
  ULONG v17; // eax
  void *v18; // rax
  _DWORD *v19; // rdi
  PSID v20; // rsi
  ULONG v21; // eax
  size_t v22; // rdi
  int v23; // ebx
  struct _ACL *v24; // rax
  struct _ACL *v25; // r14
  DWORD AccessMask; // [rsp+20h] [rbp-68h] BYREF
  ULONG AclLength; // [rsp+24h] [rbp-64h]
  PSID P; // [rsp+28h] [rbp-60h]
  PSID Sid; // [rsp+30h] [rbp-58h]
  int v30; // [rsp+38h] [rbp-50h]
  struct _ACL **v31; // [rsp+40h] [rbp-48h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+48h] [rbp-40h] BYREF

  v2 = 0;
  v31 = a1;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  AccessMask = 0x10000000;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  v5 = RtlLengthSid(SeExports->SeAliasAdminsSid) + 16;
  AclLength = v5;
  v30 = a2 & 2;
  if ( (a2 & 2) != 0 )
  {
    v5 += RtlLengthSid(SeExports->SeLocalSystemSid) + 8;
    AclLength = v5;
  }
  v6 = a2 & 8;
  if ( (a2 & 8) != 0 )
  {
    v5 += RtlLengthSid(SeExports->SeNetworkServiceSid) + 8;
    AclLength = v5;
  }
  v7 = a2 & 0x10;
  if ( (a2 & 0x10) != 0 )
  {
    v8 = RtlLengthSid(qword_140100558);
    v9 = RtlLengthSid(qword_140100578) + v8;
    v5 += v9 + RtlLengthSid(qword_140100598) + 32;
    AclLength = v5;
  }
  v10 = a2 & 4;
  if ( (a2 & 4) != 0 )
  {
    v11 = RtlLengthRequiredSid(2u);
    Pool2 = (void *)ExAllocatePool2(64, v11, 1935885390);
    Sid = Pool2;
    v2 = Pool2;
    if ( !Pool2 )
      return 3221225626LL;
    if ( RtlInitializeSid(Pool2, &IdentifierAuthority, 2u) )
    {
      Acl = -1073741670;
LABEL_46:
      ExFreePoolWithTag(v2, 0);
      return (unsigned int)Acl;
    }
    v2[2] = 32;
    v2[3] = 556;
    v5 += RtlLengthSid(v2) + 8;
    AclLength = v5;
  }
  P = 0;
  v15 = a2 & 0x20;
  if ( (a2 & 0x20) != 0 )
    AclLength = RtlLengthSid(SeExports->SeLocalServiceSid) + 8 + v5;
  v16 = a2 & 0x40;
  if ( (a2 & 0x40) != 0 )
  {
    v17 = RtlLengthRequiredSid(2u);
    v18 = (void *)ExAllocatePool2(64, v17, 1819296846);
    P = v18;
    v19 = v18;
    if ( !v18 )
    {
      Acl = -1073741670;
      goto LABEL_45;
    }
    if ( RtlInitializeSid(v18, &IdentifierAuthority, 2u) )
    {
      v20 = P;
      Acl = -1073741670;
LABEL_44:
      ExFreePoolWithTag(v20, 0);
      goto LABEL_45;
    }
    v19[2] = 32;
    v19[3] = 559;
    v21 = RtlLengthSid(v19);
    v22 = v21 + AclLength + 8;
    AclLength += v21 + 8;
  }
  else
  {
    v22 = AclLength;
  }
  v23 = a2 & 0x80;
  if ( v23 )
  {
    v22 = RtlLengthSid(qword_140100538) + 8 + (unsigned int)v22;
    AclLength = v22;
  }
  v24 = (struct _ACL *)ExAllocatePool2(64, v22, 1702052942);
  v25 = v24;
  if ( v24 )
  {
    memset(v24, 0, v22);
    Acl = RtlCreateAcl(v25, AclLength, 2u);
    if ( Acl >= 0 )
    {
      RtlAddAccessAllowedAce(v25, 2u, AccessMask, SeExports->SeAliasAdminsSid);
      if ( v30 )
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, SeExports->SeLocalSystemSid);
      if ( v6 )
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, SeExports->SeNetworkServiceSid);
      if ( v7 )
      {
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, qword_140100598);
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, qword_140100578);
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, qword_140100558);
      }
      if ( v10 )
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, Sid);
      if ( v15 )
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, SeExports->SeLocalServiceSid);
      v20 = P;
      if ( v16 )
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, P);
      if ( v23 )
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, qword_140100538);
      Acl = 0;
      *v31 = v25;
    }
    else
    {
      ExFreePoolWithTag(v25, 0);
      v20 = P;
    }
  }
  else
  {
    v20 = P;
    Acl = -1073741670;
  }
  v2 = Sid;
  if ( v20 )
    goto LABEL_44;
LABEL_45:
  if ( v2 )
    goto LABEL_46;
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x140071ba0  mov     [rsp+arg_18], rbx
0x140071ba5  push    rbp
0x140071ba6  push    rsi
0x140071ba7  push    r13
0x140071ba9  push    r14
0x140071bab  push    r15
0x140071bad  sub     rsp, 60h
0x140071bb1  mov     rax, cs:__security_cookie
0x140071bb8  xor     rax, rsp
0x140071bbb  mov     [rsp+88h+var_38], rax
0x140071bc0  xor     r14d, r14d
0x140071bc3  mov     [rsp+88h+var_48], rcx
0x140071bc8  mov     [rsp+88h+Sid], r14
0x140071bcd  mov     ebx, edx
0x140071bcf  mov     dword ptr [rsp+88h+IdentifierAuthority.Value], r14d
0x140071bd4  mov     [rsp+88h+AccessMask], 10000000h
0x140071bdc  mov     word ptr [rsp+88h+IdentifierAuthority.Value+4], 500h
0x140071be3  call    cs:__imp_IoGetFileObjectGenericMapping
0x140071bea  nop     dword ptr [rax+rax+00h]
0x140071bef  mov     rdx, rax; GenericMapping
0x140071bf2  lea     rcx, [rsp+88h+AccessMask]; AccessMask
0x140071bf7  call    cs:__imp_RtlMapGenericMask
0x140071bfe  nop     dword ptr [rax+rax+00h]
0x140071c03  mov     rax, cs:__imp_SeExports
0x140071c0a  mov     rcx, [rax]
0x140071c0d  mov     rcx, [rcx+110h]; Sid
0x140071c14  call    cs:__imp_RtlLengthSid
0x140071c1b  nop     dword ptr [rax+rax+00h]
0x140071c20  lea     r13d, [rax+10h]
0x140071c24  mov     eax, ebx
0x140071c26  and     eax, 2
0x140071c29  mov     [rsp+88h+AclLength], r13d
0x140071c2e  mov     [rsp+88h+var_50], eax
0x140071c32  jz      short loc_140071C5D
0x140071c34  mov     rax, cs:__imp_SeExports
0x140071c3b  mov     rcx, [rax]
0x140071c3e  mov     rcx, [rcx+108h]; Sid
0x140071c45  call    cs:__imp_RtlLengthSid
0x140071c4c  nop     dword ptr [rax+rax+00h]
0x140071c51  add     r13d, 8
0x140071c55  add     r13d, eax
0x140071c58  mov     [rsp+88h+AclLength], r13d
0x140071c5d  mov     esi, ebx
0x140071c5f  and     esi, 8
0x140071c62  jz      short loc_140071C8C
0x140071c64  mov     rax, cs:__imp_SeExports
0x140071c6b  mov     rcx, [rax]
0x140071c6e  mov     rcx, [rcx+188h]; Sid
0x140071c75  call    cs:__imp_RtlLengthSid
0x140071c7c  nop     dword ptr [rax+rax+00h]
0x140071c81  add     eax, 8
0x140071c84  add     r13d, eax
0x140071c87  mov     [rsp+88h+AclLength], r13d
0x140071c8c  mov     ebp, ebx
0x140071c8e  mov     [rsp+88h+arg_8], rdi
0x140071c96  and     ebp, 10h
0x140071c99  jz      short loc_140071CE5
0x140071c9b  lea     rcx, qword_140100558; Sid
0x140071ca2  call    cs:__imp_RtlLengthSid
0x140071ca9  nop     dword ptr [rax+rax+00h]
0x140071cae  lea     rcx, qword_140100578; Sid
0x140071cb5  mov     edi, eax
0x140071cb7  call    cs:__imp_RtlLengthSid
0x140071cbe  nop     dword ptr [rax+rax+00h]
0x140071cc3  lea     rcx, qword_140100598; Sid
0x140071cca  add     edi, eax
0x140071ccc  call    cs:__imp_RtlLengthSid
0x140071cd3  nop     dword ptr [rax+rax+00h]
0x140071cd8  add     eax, 20h ; ' '
0x140071cdb  add     eax, edi
0x140071cdd  add     r13d, eax
0x140071ce0  mov     [rsp+88h+AclLength], r13d
0x140071ce5  mov     r15d, ebx
0x140071ce8  and     r15d, 4
0x140071cec  jz      loc_140071D82
0x140071cf2  mov     ecx, 2; SubAuthorityCount
0x140071cf7  call    cs:__imp_RtlLengthRequiredSid
0x140071cfe  nop     dword ptr [rax+rax+00h]
0x140071d03  mov     edx, eax
0x140071d05  mov     ecx, 40h ; '@'
0x140071d0a  mov     r8d, 7363444Eh
0x140071d10  call    cs:__imp_ExAllocatePool2
0x140071d17  nop     dword ptr [rax+rax+00h]
0x140071d1c  mov     [rsp+88h+Sid], rax
0x140071d21  mov     r14, rax
0x140071d24  test    rax, rax
0x140071d27  jnz     short loc_140071D33
0x140071d29  mov     eax, 0C000009Ah
0x140071d2e  jmp     loc_1400720D1
0x140071d33  mov     r8b, 2; SubAuthorityCount
0x140071d36  lea     rdx, [rsp+88h+IdentifierAuthority]; IdentifierAuthority
0x140071d3b  mov     rcx, r14; Sid
0x140071d3e  call    cs:__imp_RtlInitializeSid
0x140071d45  nop     dword ptr [rax+rax+00h]
0x140071d4a  test    eax, eax
0x140071d4c  jz      short loc_140071D58
0x140071d4e  mov     edi, 0C000009Ah
0x140071d53  jmp     loc_1400720BE
0x140071d58  mov     rcx, r14; Sid
0x140071d5b  mov     dword ptr [r14+8], 20h ; ' '
0x140071d63  mov     dword ptr [r14+0Ch], 22Ch
0x140071d6b  call    cs:__imp_RtlLengthSid
0x140071d72  nop     dword ptr [rax+rax+00h]
0x140071d77  add     eax, 8
0x140071d7a  add     r13d, eax
0x140071d7d  mov     [rsp+88h+AclLength], r13d
0x140071d82  mov     [rsp+88h+arg_10], r12
0x140071d8a  xor     edi, edi
0x140071d8c  mov     r12d, ebx
0x140071d8f  mov     [rsp+88h+P], rdi
0x140071d94  and     r12d, 20h
0x140071d98  jz      short loc_140071DC2
0x140071d9a  mov     rax, cs:__imp_SeExports
0x140071da1  mov     rcx, [rax]
0x140071da4  mov     rcx, [rcx+180h]; Sid
0x140071dab  call    cs:__imp_RtlLengthSid
0x140071db2  nop     dword ptr [rax+rax+00h]
0x140071db7  add     eax, 8
0x140071dba  add     r13d, eax
0x140071dbd  mov     [rsp+88h+AclLength], r13d
0x140071dc2  mov     r13d, ebx
0x140071dc5  and     r13d, 40h
0x140071dc9  jz      loc_140071E66
0x140071dcf  mov     ecx, 2; SubAuthorityCount
0x140071dd4  call    cs:__imp_RtlLengthRequiredSid
0x140071ddb  nop     dword ptr [rax+rax+00h]
0x140071de0  mov     edx, eax
0x140071de2  mov     ecx, 40h ; '@'
0x140071de7  mov     r8d, 6C70444Eh
0x140071ded  call    cs:__imp_ExAllocatePool2
0x140071df4  nop     dword ptr [rax+rax+00h]
0x140071df9  mov     [rsp+88h+P], rax
0x140071dfe  mov     rdi, rax
0x140071e01  test    rax, rax
0x140071e04  jnz     short loc_140071E10
0x140071e06  mov     edi, 0C000009Ah
0x140071e0b  jmp     loc_1400720B1
0x140071e10  mov     r8b, 2; SubAuthorityCount
0x140071e13  lea     rdx, [rsp+88h+IdentifierAuthority]; IdentifierAuthority
0x140071e18  mov     rcx, rdi; Sid
0x140071e1b  call    cs:__imp_RtlInitializeSid
0x140071e22  nop     dword ptr [rax+rax+00h]
0x140071e27  test    eax, eax
0x140071e29  jz      short loc_140071E3A
0x140071e2b  mov     rsi, [rsp+88h+P]
0x140071e30  mov     edi, 0C000009Ah
0x140071e35  jmp     loc_1400720A0
0x140071e3a  mov     rcx, rdi; Sid
0x140071e3d  mov     dword ptr [rdi+8], 20h ; ' '
0x140071e44  mov     dword ptr [rdi+0Ch], 22Fh
0x140071e4b  call    cs:__imp_RtlLengthSid
0x140071e52  nop     dword ptr [rax+rax+00h]
0x140071e57  mov     edi, [rsp+88h+AclLength]
0x140071e5b  add     edi, 8
0x140071e5e  add     edi, eax
0x140071e60  mov     [rsp+88h+AclLength], edi
0x140071e64  jmp     short loc_140071E6A
0x140071e66  mov     edi, [rsp+88h+AclLength]
0x140071e6a  and     ebx, 80h
0x140071e70  jz      short loc_140071E8E
0x140071e72  lea     rcx, qword_140100538; Sid
0x140071e79  call    cs:__imp_RtlLengthSid
0x140071e80  nop     dword ptr [rax+rax+00h]
0x140071e85  add     eax, 8
0x140071e88  add     edi, eax
0x140071e8a  mov     [rsp+88h+AclLength], edi
0x140071e8e  mov     r8d, 6573444Eh
0x140071e94  mov     rdx, rdi
0x140071e97  mov     ecx, 40h ; '@'
0x140071e9c  call    cs:__imp_ExAllocatePool2
0x140071ea3  nop     dword ptr [rax+rax+00h]
0x140071ea8  mov     r14, rax
0x140071eab  test    rax, rax
0x140071eae  jnz     short loc_140071EBF
0x140071eb0  mov     rsi, [rsp+88h+P]
0x140071eb5  mov     edi, 0C000009Ah
0x140071eba  jmp     loc_140072096
0x140071ebf  mov     r8, rdi; Size
0x140071ec2  xor     edx, edx; Val
0x140071ec4  mov     rcx, r14; void *
0x140071ec7  call    memset
0x140071ecc  mov     edx, [rsp+88h+AclLength]; AclLength
0x140071ed0  mov     r8d, 2; AclRevision
0x140071ed6  mov     rcx, r14; Acl
0x140071ed9  call    cs:__imp_RtlCreateAcl
0x140071ee0  nop     dword ptr [rax+rax+00h]
0x140071ee5  mov     edi, eax
0x140071ee7  mov     rcx, r14; Acl
0x140071eea  test    eax, eax
0x140071eec  jns     short loc_140071F06
0x140071eee  xor     edx, edx; Tag
0x140071ef0  call    cs:__imp_ExFreePoolWithTag
0x140071ef7  nop     dword ptr [rax+rax+00h]
0x140071efc  mov     rsi, [rsp+88h+P]
0x140071f01  jmp     loc_140072096
0x140071f06  mov     rax, cs:__imp_SeExports
0x140071f0d  mov     edx, 2; AceRevision
0x140071f12  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x140071f17  mov     r9, [rax]
0x140071f1a  mov     r9, [r9+110h]; Sid
0x140071f21  call    cs:__imp_RtlAddAccessAllowedAce
0x140071f28  nop     dword ptr [rax+rax+00h]
0x140071f2d  cmp     [rsp+88h+var_50], 0
0x140071f32  jz      short loc_140071F5E
0x140071f34  mov     rax, cs:__imp_SeExports
0x140071f3b  mov     edx, 2; AceRevision
0x140071f40  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x140071f45  mov     rcx, r14; Acl
0x140071f48  mov     r9, [rax]
0x140071f4b  mov     r9, [r9+108h]; Sid
0x140071f52  call    cs:__imp_RtlAddAccessAllowedAce
0x140071f59  nop     dword ptr [rax+rax+00h]
0x140071f5e  test    esi, esi
0x140071f60  jz      short loc_140071F8C
0x140071f62  mov     rax, cs:__imp_SeExports
0x140071f69  mov     edx, 2; AceRevision
0x140071f6e  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x140071f73  mov     rcx, r14; Acl
0x140071f76  mov     r9, [rax]
0x140071f79  mov     r9, [r9+188h]; Sid
0x140071f80  call    cs:__imp_RtlAddAccessAllowedAce
0x140071f87  nop     dword ptr [rax+rax+00h]
0x140071f8c  test    ebp, ebp
0x140071f8e  jz      short loc_140071FF0
0x140071f90  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x140071f95  lea     r9, qword_140100598; Sid
0x140071f9c  mov     edx, 2; AceRevision
0x140071fa1  mov     rcx, r14; Acl
0x140071fa4  call    cs:__imp_RtlAddAccessAllowedAce
0x140071fab  nop     dword ptr [rax+rax+00h]
0x140071fb0  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x140071fb5  lea     r9, qword_140100578; Sid
0x140071fbc  mov     edx, 2; AceRevision
0x140071fc1  mov     rcx, r14; Acl
0x140071fc4  call    cs:__imp_RtlAddAccessAllowedAce
0x140071fcb  nop     dword ptr [rax+rax+00h]
0x140071fd0  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x140071fd5  lea     r9, qword_140100558; Sid
0x140071fdc  mov     edx, 2; AceRevision
0x140071fe1  mov     rcx, r14; Acl
0x140071fe4  call    cs:__imp_RtlAddAccessAllowedAce
0x140071feb  nop     dword ptr [rax+rax+00h]
0x140071ff0  test    r15d, r15d
0x140071ff3  jz      short loc_140072013
0x140071ff5  mov     r9, [rsp+88h+Sid]; Sid
0x140071ffa  mov     edx, 2; AceRevision
0x140071fff  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x140072004  mov     rcx, r14; Acl
0x140072007  call    cs:__imp_RtlAddAccessAllowedAce
0x14007200e  nop     dword ptr [rax+rax+00h]
0x140072013  test    r12d, r12d
0x140072016  jz      short loc_140072042
0x140072018  mov     rax, cs:__imp_SeExports
0x14007201f  mov     edx, 2; AceRevision
0x140072024  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x140072029  mov     rcx, r14; Acl
0x14007202c  mov     r9, [rax]
0x14007202f  mov     r9, [r9+180h]; Sid
0x140072036  call    cs:__imp_RtlAddAccessAllowedAce
0x14007203d  nop     dword ptr [rax+rax+00h]
0x140072042  mov     rsi, [rsp+88h+P]
0x140072047  test    r13d, r13d
0x14007204a  jz      short loc_140072068
0x14007204c  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x140072051  mov     r9, rsi; Sid
0x140072054  mov     edx, 2; AceRevision
0x140072059  mov     rcx, r14; Acl
0x14007205c  call    cs:__imp_RtlAddAccessAllowedAce
0x140072063  nop     dword ptr [rax+rax+00h]
0x140072068  test    ebx, ebx
0x14007206a  jz      short loc_14007208C
0x14007206c  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x140072071  lea     r9, qword_140100538; Sid
0x140072078  mov     edx, 2; AceRevision
0x14007207d  mov     rcx, r14; Acl
0x140072080  call    cs:__imp_RtlAddAccessAllowedAce
0x140072087  nop     dword ptr [rax+rax+00h]
0x14007208c  mov     rax, [rsp+88h+var_48]
0x140072091  xor     edi, edi
0x140072093  mov     [rax], r14
0x140072096  mov     r14, [rsp+88h+Sid]
0x14007209b  test    rsi, rsi
0x14007209e  jz      short loc_1400720B1
0x1400720a0  xor     edx, edx; Tag
0x1400720a2  mov     rcx, rsi; P
0x1400720a5  call    cs:__imp_ExFreePoolWithTag
0x1400720ac  nop     dword ptr [rax+rax+00h]
0x1400720b1  mov     r12, [rsp+88h+arg_10]
0x1400720b9  test    r14, r14
0x1400720bc  jz      short loc_1400720CF
0x1400720be  xor     edx, edx; Tag
0x1400720c0  mov     rcx, r14; P
0x1400720c3  call    cs:__imp_ExFreePoolWithTag
0x1400720ca  nop     dword ptr [rax+rax+00h]
0x1400720cf  mov     eax, edi
0x1400720d1  mov     rdi, [rsp+88h+arg_8]
0x1400720d9  mov     rcx, [rsp+88h+var_38]
0x1400720de  xor     rcx, rsp; StackCookie
0x1400720e1  call    __security_check_cookie
0x1400720e6  mov     rbx, [rsp+88h+arg_18]
  ... truncated ...
```
