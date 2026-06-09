# ndisBuildDeviceAcl(_ACL * *,ulong)

- ea: `0x14006c220`
- end: `0x14006c77c`
- name: `?ndisBuildDeviceAcl@@YAJPEAPEAU_ACL@@K@Z`
- size: `1372`
- prototype: `__int64 __fastcall(struct _ACL **, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x14006c030`
- `0x140143090`

## callees

- `0x14006c220`
- `0x1400e6160`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14006c263`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14006c263`
- `ntoskrnl!RtlMapGenericMask` at `0x14006c277`
- `ntoskrnl!RtlMapGenericMask` at `0x14006c277`
- `ntoskrnl!RtlInitializeSid` at `0x14006c3be`
- `ntoskrnl!RtlInitializeSid` at `0x14006c49b`
- `ntoskrnl!RtlInitializeSid` at `0x14006c3be`
- `ntoskrnl!RtlInitializeSid` at `0x14006c49b`
- `ntoskrnl!RtlLengthSid` at `0x14006c294`
- `ntoskrnl!RtlLengthSid` at `0x14006c2c5`
- `ntoskrnl!RtlLengthSid` at `0x14006c2f5`
- `ntoskrnl!RtlLengthSid` at `0x14006c322`
- `ntoskrnl!RtlLengthSid` at `0x14006c337`
- `ntoskrnl!RtlLengthSid` at `0x14006c34c`
- `ntoskrnl!RtlLengthSid` at `0x14006c3eb`
- `ntoskrnl!RtlLengthSid` at `0x14006c42b`
- `ntoskrnl!RtlLengthSid` at `0x14006c4cb`
- `ntoskrnl!RtlLengthSid` at `0x14006c4f9`
- `ntoskrnl!RtlLengthSid` at `0x14006c294`
- `ntoskrnl!RtlLengthSid` at `0x14006c2c5`
- `ntoskrnl!RtlLengthSid` at `0x14006c2f5`
- `ntoskrnl!RtlLengthSid` at `0x14006c322`
- `ntoskrnl!RtlLengthSid` at `0x14006c337`
- `ntoskrnl!RtlLengthSid` at `0x14006c34c`
- `ntoskrnl!RtlLengthSid` at `0x14006c3eb`
- `ntoskrnl!RtlLengthSid` at `0x14006c42b`
- `ntoskrnl!RtlLengthSid` at `0x14006c4cb`
- `ntoskrnl!RtlLengthSid` at `0x14006c4f9`
- `ntoskrnl!SeExports` at `0x14006c283`
- `ntoskrnl!SeExports` at `0x14006c2b4`
- `ntoskrnl!SeExports` at `0x14006c2e4`
- `ntoskrnl!SeExports` at `0x14006c41a`
- `ntoskrnl!SeExports` at `0x14006c586`
- `ntoskrnl!SeExports` at `0x14006c5b4`
- `ntoskrnl!SeExports` at `0x14006c5e2`
- `ntoskrnl!SeExports` at `0x14006c698`
- `ntoskrnl!RtlCreateAcl` at `0x14006c559`
- `ntoskrnl!RtlCreateAcl` at `0x14006c559`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c5a1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c5d2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c600`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c624`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c644`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c664`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c687`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c6b6`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c6dc`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c700`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c5a1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c5d2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c600`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c624`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c644`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c664`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c687`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c6b6`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c6dc`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c700`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c570`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c725`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c743`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c570`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c725`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c743`
- `ntoskrnl!ExAllocatePool2` at `0x14006c390`
- `ntoskrnl!ExAllocatePool2` at `0x14006c46d`
- `ntoskrnl!ExAllocatePool2` at `0x14006c51c`
- `ntoskrnl!ExAllocatePool2` at `0x14006c390`
- `ntoskrnl!ExAllocatePool2` at `0x14006c46d`
- `ntoskrnl!ExAllocatePool2` at `0x14006c51c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14006c377`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14006c454`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14006c377`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14006c454`

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
    v8 = RtlLengthSid(qword_1400FB518);
    v9 = RtlLengthSid(qword_1400FB538) + v8;
    v5 += v9 + RtlLengthSid(qword_1400FB558) + 32;
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
    v22 = RtlLengthSid(qword_1400FB4F8) + 8 + (unsigned int)v22;
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
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, qword_1400FB558);
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, qword_1400FB538);
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, qword_1400FB518);
      }
      if ( v10 )
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, Sid);
      if ( v15 )
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, SeExports->SeLocalServiceSid);
      v20 = P;
      if ( v16 )
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, P);
      if ( v23 )
        RtlAddAccessAllowedAce(v25, 2u, AccessMask, qword_1400FB4F8);
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
0x14006c220  mov     [rsp+arg_18], rbx
0x14006c225  push    rbp
0x14006c226  push    rsi
0x14006c227  push    r13
0x14006c229  push    r14
0x14006c22b  push    r15
0x14006c22d  sub     rsp, 60h
0x14006c231  mov     rax, cs:__security_cookie
0x14006c238  xor     rax, rsp
0x14006c23b  mov     [rsp+88h+var_38], rax
0x14006c240  xor     r14d, r14d
0x14006c243  mov     [rsp+88h+var_48], rcx
0x14006c248  mov     [rsp+88h+Sid], r14
0x14006c24d  mov     ebx, edx
0x14006c24f  mov     dword ptr [rsp+88h+IdentifierAuthority.Value], r14d
0x14006c254  mov     [rsp+88h+AccessMask], 10000000h
0x14006c25c  mov     word ptr [rsp+88h+IdentifierAuthority.Value+4], 500h
0x14006c263  call    cs:__imp_IoGetFileObjectGenericMapping
0x14006c26a  nop     dword ptr [rax+rax+00h]
0x14006c26f  mov     rdx, rax; GenericMapping
0x14006c272  lea     rcx, [rsp+88h+AccessMask]; AccessMask
0x14006c277  call    cs:__imp_RtlMapGenericMask
0x14006c27e  nop     dword ptr [rax+rax+00h]
0x14006c283  mov     rax, cs:__imp_SeExports
0x14006c28a  mov     rcx, [rax]
0x14006c28d  mov     rcx, [rcx+110h]; Sid
0x14006c294  call    cs:__imp_RtlLengthSid
0x14006c29b  nop     dword ptr [rax+rax+00h]
0x14006c2a0  lea     r13d, [rax+10h]
0x14006c2a4  mov     eax, ebx
0x14006c2a6  and     eax, 2
0x14006c2a9  mov     [rsp+88h+AclLength], r13d
0x14006c2ae  mov     [rsp+88h+var_50], eax
0x14006c2b2  jz      short loc_14006C2DD
0x14006c2b4  mov     rax, cs:__imp_SeExports
0x14006c2bb  mov     rcx, [rax]
0x14006c2be  mov     rcx, [rcx+108h]; Sid
0x14006c2c5  call    cs:__imp_RtlLengthSid
0x14006c2cc  nop     dword ptr [rax+rax+00h]
0x14006c2d1  add     r13d, 8
0x14006c2d5  add     r13d, eax
0x14006c2d8  mov     [rsp+88h+AclLength], r13d
0x14006c2dd  mov     esi, ebx
0x14006c2df  and     esi, 8
0x14006c2e2  jz      short loc_14006C30C
0x14006c2e4  mov     rax, cs:__imp_SeExports
0x14006c2eb  mov     rcx, [rax]
0x14006c2ee  mov     rcx, [rcx+188h]; Sid
0x14006c2f5  call    cs:__imp_RtlLengthSid
0x14006c2fc  nop     dword ptr [rax+rax+00h]
0x14006c301  add     eax, 8
0x14006c304  add     r13d, eax
0x14006c307  mov     [rsp+88h+AclLength], r13d
0x14006c30c  mov     ebp, ebx
0x14006c30e  mov     [rsp+88h+arg_8], rdi
0x14006c316  and     ebp, 10h
0x14006c319  jz      short loc_14006C365
0x14006c31b  lea     rcx, qword_1400FB518; Sid
0x14006c322  call    cs:__imp_RtlLengthSid
0x14006c329  nop     dword ptr [rax+rax+00h]
0x14006c32e  lea     rcx, qword_1400FB538; Sid
0x14006c335  mov     edi, eax
0x14006c337  call    cs:__imp_RtlLengthSid
0x14006c33e  nop     dword ptr [rax+rax+00h]
0x14006c343  lea     rcx, qword_1400FB558; Sid
0x14006c34a  add     edi, eax
0x14006c34c  call    cs:__imp_RtlLengthSid
0x14006c353  nop     dword ptr [rax+rax+00h]
0x14006c358  add     eax, 20h ; ' '
0x14006c35b  add     eax, edi
0x14006c35d  add     r13d, eax
0x14006c360  mov     [rsp+88h+AclLength], r13d
0x14006c365  mov     r15d, ebx
0x14006c368  and     r15d, 4
0x14006c36c  jz      loc_14006C402
0x14006c372  mov     ecx, 2; SubAuthorityCount
0x14006c377  call    cs:__imp_RtlLengthRequiredSid
0x14006c37e  nop     dword ptr [rax+rax+00h]
0x14006c383  mov     edx, eax
0x14006c385  mov     ecx, 40h ; '@'
0x14006c38a  mov     r8d, 7363444Eh
0x14006c390  call    cs:__imp_ExAllocatePool2
0x14006c397  nop     dword ptr [rax+rax+00h]
0x14006c39c  mov     [rsp+88h+Sid], rax
0x14006c3a1  mov     r14, rax
0x14006c3a4  test    rax, rax
0x14006c3a7  jnz     short loc_14006C3B3
0x14006c3a9  mov     eax, 0C000009Ah
0x14006c3ae  jmp     loc_14006C751
0x14006c3b3  mov     r8b, 2; SubAuthorityCount
0x14006c3b6  lea     rdx, [rsp+88h+IdentifierAuthority]; IdentifierAuthority
0x14006c3bb  mov     rcx, r14; Sid
0x14006c3be  call    cs:__imp_RtlInitializeSid
0x14006c3c5  nop     dword ptr [rax+rax+00h]
0x14006c3ca  test    eax, eax
0x14006c3cc  jz      short loc_14006C3D8
0x14006c3ce  mov     edi, 0C000009Ah
0x14006c3d3  jmp     loc_14006C73E
0x14006c3d8  mov     rcx, r14; Sid
0x14006c3db  mov     dword ptr [r14+8], 20h ; ' '
0x14006c3e3  mov     dword ptr [r14+0Ch], 22Ch
0x14006c3eb  call    cs:__imp_RtlLengthSid
0x14006c3f2  nop     dword ptr [rax+rax+00h]
0x14006c3f7  add     eax, 8
0x14006c3fa  add     r13d, eax
0x14006c3fd  mov     [rsp+88h+AclLength], r13d
0x14006c402  mov     [rsp+88h+arg_10], r12
0x14006c40a  xor     edi, edi
0x14006c40c  mov     r12d, ebx
0x14006c40f  mov     [rsp+88h+P], rdi
0x14006c414  and     r12d, 20h
0x14006c418  jz      short loc_14006C442
0x14006c41a  mov     rax, cs:__imp_SeExports
0x14006c421  mov     rcx, [rax]
0x14006c424  mov     rcx, [rcx+180h]; Sid
0x14006c42b  call    cs:__imp_RtlLengthSid
0x14006c432  nop     dword ptr [rax+rax+00h]
0x14006c437  add     eax, 8
0x14006c43a  add     r13d, eax
0x14006c43d  mov     [rsp+88h+AclLength], r13d
0x14006c442  mov     r13d, ebx
0x14006c445  and     r13d, 40h
0x14006c449  jz      loc_14006C4E6
0x14006c44f  mov     ecx, 2; SubAuthorityCount
0x14006c454  call    cs:__imp_RtlLengthRequiredSid
0x14006c45b  nop     dword ptr [rax+rax+00h]
0x14006c460  mov     edx, eax
0x14006c462  mov     ecx, 40h ; '@'
0x14006c467  mov     r8d, 6C70444Eh
0x14006c46d  call    cs:__imp_ExAllocatePool2
0x14006c474  nop     dword ptr [rax+rax+00h]
0x14006c479  mov     [rsp+88h+P], rax
0x14006c47e  mov     rdi, rax
0x14006c481  test    rax, rax
0x14006c484  jnz     short loc_14006C490
0x14006c486  mov     edi, 0C000009Ah
0x14006c48b  jmp     loc_14006C731
0x14006c490  mov     r8b, 2; SubAuthorityCount
0x14006c493  lea     rdx, [rsp+88h+IdentifierAuthority]; IdentifierAuthority
0x14006c498  mov     rcx, rdi; Sid
0x14006c49b  call    cs:__imp_RtlInitializeSid
0x14006c4a2  nop     dword ptr [rax+rax+00h]
0x14006c4a7  test    eax, eax
0x14006c4a9  jz      short loc_14006C4BA
0x14006c4ab  mov     rsi, [rsp+88h+P]
0x14006c4b0  mov     edi, 0C000009Ah
0x14006c4b5  jmp     loc_14006C720
0x14006c4ba  mov     rcx, rdi; Sid
0x14006c4bd  mov     dword ptr [rdi+8], 20h ; ' '
0x14006c4c4  mov     dword ptr [rdi+0Ch], 22Fh
0x14006c4cb  call    cs:__imp_RtlLengthSid
0x14006c4d2  nop     dword ptr [rax+rax+00h]
0x14006c4d7  mov     edi, [rsp+88h+AclLength]
0x14006c4db  add     edi, 8
0x14006c4de  add     edi, eax
0x14006c4e0  mov     [rsp+88h+AclLength], edi
0x14006c4e4  jmp     short loc_14006C4EA
0x14006c4e6  mov     edi, [rsp+88h+AclLength]
0x14006c4ea  and     ebx, 80h
0x14006c4f0  jz      short loc_14006C50E
0x14006c4f2  lea     rcx, qword_1400FB4F8; Sid
0x14006c4f9  call    cs:__imp_RtlLengthSid
0x14006c500  nop     dword ptr [rax+rax+00h]
0x14006c505  add     eax, 8
0x14006c508  add     edi, eax
0x14006c50a  mov     [rsp+88h+AclLength], edi
0x14006c50e  mov     r8d, 6573444Eh
0x14006c514  mov     rdx, rdi
0x14006c517  mov     ecx, 40h ; '@'
0x14006c51c  call    cs:__imp_ExAllocatePool2
0x14006c523  nop     dword ptr [rax+rax+00h]
0x14006c528  mov     r14, rax
0x14006c52b  test    rax, rax
0x14006c52e  jnz     short loc_14006C53F
0x14006c530  mov     rsi, [rsp+88h+P]
0x14006c535  mov     edi, 0C000009Ah
0x14006c53a  jmp     loc_14006C716
0x14006c53f  mov     r8, rdi; Size
0x14006c542  xor     edx, edx; Val
0x14006c544  mov     rcx, r14; void *
0x14006c547  call    memset
0x14006c54c  mov     edx, [rsp+88h+AclLength]; AclLength
0x14006c550  mov     r8d, 2; AclRevision
0x14006c556  mov     rcx, r14; Acl
0x14006c559  call    cs:__imp_RtlCreateAcl
0x14006c560  nop     dword ptr [rax+rax+00h]
0x14006c565  mov     edi, eax
0x14006c567  mov     rcx, r14; Acl
0x14006c56a  test    eax, eax
0x14006c56c  jns     short loc_14006C586
0x14006c56e  xor     edx, edx; Tag
0x14006c570  call    cs:__imp_ExFreePoolWithTag
0x14006c577  nop     dword ptr [rax+rax+00h]
0x14006c57c  mov     rsi, [rsp+88h+P]
0x14006c581  jmp     loc_14006C716
0x14006c586  mov     rax, cs:__imp_SeExports
0x14006c58d  mov     edx, 2; AceRevision
0x14006c592  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x14006c597  mov     r9, [rax]
0x14006c59a  mov     r9, [r9+110h]; Sid
0x14006c5a1  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c5a8  nop     dword ptr [rax+rax+00h]
0x14006c5ad  cmp     [rsp+88h+var_50], 0
0x14006c5b2  jz      short loc_14006C5DE
0x14006c5b4  mov     rax, cs:__imp_SeExports
0x14006c5bb  mov     edx, 2; AceRevision
0x14006c5c0  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x14006c5c5  mov     rcx, r14; Acl
0x14006c5c8  mov     r9, [rax]
0x14006c5cb  mov     r9, [r9+108h]; Sid
0x14006c5d2  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c5d9  nop     dword ptr [rax+rax+00h]
0x14006c5de  test    esi, esi
0x14006c5e0  jz      short loc_14006C60C
0x14006c5e2  mov     rax, cs:__imp_SeExports
0x14006c5e9  mov     edx, 2; AceRevision
0x14006c5ee  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x14006c5f3  mov     rcx, r14; Acl
0x14006c5f6  mov     r9, [rax]
0x14006c5f9  mov     r9, [r9+188h]; Sid
0x14006c600  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c607  nop     dword ptr [rax+rax+00h]
0x14006c60c  test    ebp, ebp
0x14006c60e  jz      short loc_14006C670
0x14006c610  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x14006c615  lea     r9, qword_1400FB558; Sid
0x14006c61c  mov     edx, 2; AceRevision
0x14006c621  mov     rcx, r14; Acl
0x14006c624  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c62b  nop     dword ptr [rax+rax+00h]
0x14006c630  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x14006c635  lea     r9, qword_1400FB538; Sid
0x14006c63c  mov     edx, 2; AceRevision
0x14006c641  mov     rcx, r14; Acl
0x14006c644  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c64b  nop     dword ptr [rax+rax+00h]
0x14006c650  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x14006c655  lea     r9, qword_1400FB518; Sid
0x14006c65c  mov     edx, 2; AceRevision
0x14006c661  mov     rcx, r14; Acl
0x14006c664  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c66b  nop     dword ptr [rax+rax+00h]
0x14006c670  test    r15d, r15d
0x14006c673  jz      short loc_14006C693
0x14006c675  mov     r9, [rsp+88h+Sid]; Sid
0x14006c67a  mov     edx, 2; AceRevision
0x14006c67f  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x14006c684  mov     rcx, r14; Acl
0x14006c687  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c68e  nop     dword ptr [rax+rax+00h]
0x14006c693  test    r12d, r12d
0x14006c696  jz      short loc_14006C6C2
0x14006c698  mov     rax, cs:__imp_SeExports
0x14006c69f  mov     edx, 2; AceRevision
0x14006c6a4  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x14006c6a9  mov     rcx, r14; Acl
0x14006c6ac  mov     r9, [rax]
0x14006c6af  mov     r9, [r9+180h]; Sid
0x14006c6b6  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c6bd  nop     dword ptr [rax+rax+00h]
0x14006c6c2  mov     rsi, [rsp+88h+P]
0x14006c6c7  test    r13d, r13d
0x14006c6ca  jz      short loc_14006C6E8
0x14006c6cc  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x14006c6d1  mov     r9, rsi; Sid
0x14006c6d4  mov     edx, 2; AceRevision
0x14006c6d9  mov     rcx, r14; Acl
0x14006c6dc  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c6e3  nop     dword ptr [rax+rax+00h]
0x14006c6e8  test    ebx, ebx
0x14006c6ea  jz      short loc_14006C70C
0x14006c6ec  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x14006c6f1  lea     r9, qword_1400FB4F8; Sid
0x14006c6f8  mov     edx, 2; AceRevision
0x14006c6fd  mov     rcx, r14; Acl
0x14006c700  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c707  nop     dword ptr [rax+rax+00h]
0x14006c70c  mov     rax, [rsp+88h+var_48]
0x14006c711  xor     edi, edi
0x14006c713  mov     [rax], r14
0x14006c716  mov     r14, [rsp+88h+Sid]
0x14006c71b  test    rsi, rsi
0x14006c71e  jz      short loc_14006C731
0x14006c720  xor     edx, edx; Tag
0x14006c722  mov     rcx, rsi; P
0x14006c725  call    cs:__imp_ExFreePoolWithTag
0x14006c72c  nop     dword ptr [rax+rax+00h]
0x14006c731  mov     r12, [rsp+88h+arg_10]
0x14006c739  test    r14, r14
0x14006c73c  jz      short loc_14006C74F
0x14006c73e  xor     edx, edx; Tag
0x14006c740  mov     rcx, r14; P
0x14006c743  call    cs:__imp_ExFreePoolWithTag
0x14006c74a  nop     dword ptr [rax+rax+00h]
0x14006c74f  mov     eax, edi
0x14006c751  mov     rdi, [rsp+88h+arg_8]
0x14006c759  mov     rcx, [rsp+88h+var_38]
0x14006c75e  xor     rcx, rsp; StackCookie
0x14006c761  call    __security_check_cookie
0x14006c766  mov     rbx, [rsp+88h+arg_18]
  ... truncated ...
```
