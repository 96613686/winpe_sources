# Dacl::GetAces(AceList<AccessAce> &)

- ea: `0x1401c6c30`
- end: `0x1401c6fa4`
- name: `?GetAces@Dacl@@QEAAPEAVFrsStatus@@AEAV?$AceList@VAccessAce@@@@@Z`
- size: `884`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004ef40`
- `0x1401c636c`
- `0x1401ee4d4`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x14001afd0`
- `0x14001c030`
- `0x14004ab40`
- `0x1401b9494`
- `0x1401c5c2c`
- `0x1401c5c60`
- `0x1401c5e2c`
- `0x1401c6c30`
- `0x1401c8070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c6cc8`
- `KERNEL32!GetLastError` at `0x1401c6d46`
- `KERNEL32!GetLastError` at `0x1401c6f49`
- `KERNEL32!GetLastError` at `0x1401c6cc8`
- `KERNEL32!GetLastError` at `0x1401c6d46`
- `KERNEL32!GetLastError` at `0x1401c6f49`
- `KERNEL32!GetCurrentThreadId` at `0x1401c6cba`
- `KERNEL32!GetCurrentThreadId` at `0x1401c6d38`
- `KERNEL32!GetCurrentThreadId` at `0x1401c6ddc`
- `KERNEL32!GetCurrentThreadId` at `0x1401c6f3b`
- `KERNEL32!GetCurrentThreadId` at `0x1401c6cba`
- `KERNEL32!GetCurrentThreadId` at `0x1401c6d38`
- `KERNEL32!GetCurrentThreadId` at `0x1401c6ddc`
- `KERNEL32!GetCurrentThreadId` at `0x1401c6f3b`
- `ADVAPI32!GetAclInformation` at `0x1401c6caa`
- `ADVAPI32!GetAclInformation` at `0x1401c6d28`
- `ADVAPI32!GetAclInformation` at `0x1401c6caa`
- `ADVAPI32!GetAclInformation` at `0x1401c6d28`
- `ADVAPI32!GetAce` at `0x1401c6d9e`
- `ADVAPI32!GetAce` at `0x1401c6d9e`

## string_xrefs

- `0x1401c6cec`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c6d76`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c6ce5`: `Dacl::GetAces`
- `0x1401c6d6f`: `Dacl::GetAces`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dacl::GetAces(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  __int64 v4; // rdi
  struct FrsStatus *v5; // rbx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  DWORD v10; // ebx
  DWORD v11; // eax
  __int64 v12; // rcx
  DWORD i; // eax
  DWORD v14; // eax
  __int64 v15; // rcx
  char *v16; // r9
  const struct _GUID *v17; // r14
  const struct _SID *v18; // rcx
  AccessAce *v20; // rax
  DWORD v21; // ebx
  DWORD v22; // eax
  __int64 v23; // rcx
  struct _GUID *v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v27; // [rsp+5Ch] [rbp-A4h]
  DWORD v28; // [rsp+60h] [rbp-A0h]
  LPVOID pAce; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h]
  AccessObjectAce *v31; // [rsp+78h] [rbp-88h]
  __int64 pAclInformation; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+88h] [rbp-78h]
  _BYTE v34[128]; // [rsp+90h] [rbp-70h] BYREF

  v2 = a2;
  v30 = a2;
  pAclInformation = 0;
  v33 = 0;
  v4 = 0;
  v26 = 0;
  pAce = 0;
  Sid::Sid((Sid *)v34);
  v5 = 0;
  PtrList<Config::VolumeConfig>::DeleteAll(v2);
  if ( !*(_DWORD *)(a1 + 16) )
  {
    if ( !GetAclInformation(*(PACL *)(a1 + 24), &pAclInformation, 0xCu, AclSizeInformation) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LastError = GetLastError();
      v9 = FrsStatusList::PushNewError(
             v8,
             LastError,
             0,
             1,
             "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
             "Dacl::GetAces",
             1728,
             CurrentThreadId,
             0);
LABEL_4:
      v4 = v9;
      goto LABEL_30;
    }
    if ( !GetAclInformation(*(PACL *)(a1 + 24), &v26, 4u, AclRevisionInformation) )
    {
      v10 = GetCurrentThreadId();
      v11 = GetLastError();
      v9 = FrsStatusList::PushNewError(
             v12,
             v11,
             0,
             1,
             "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
             "Dacl::GetAces",
             1732,
             v10,
             0);
      goto LABEL_4;
    }
    *(_DWORD *)(a1 + 8) = v26;
    for ( i = 0; ; i = v28 + 1 )
    {
      v28 = i;
      if ( i >= (unsigned int)pAclInformation || v5 )
      {
        v4 = (__int64)v5;
        break;
      }
      if ( !GetAce(*(PACL *)(a1 + 24), i, &pAce) )
      {
        v21 = GetCurrentThreadId();
        v22 = GetLastError();
        v9 = FrsStatusList::PushNewError(
               v23,
               v22,
               0,
               1,
               "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
               "Dacl::GetAces",
               1740,
               v21,
               0);
        goto LABEL_4;
      }
      v27 = *((_DWORD *)pAce + 1);
      if ( !*(_BYTE *)pAce || *(_BYTE *)pAce == 1 )
      {
        v5 = Sid::Set((Sid *)v34, (const struct _SID *)((char *)pAce + 8));
        if ( !v5 )
        {
          v25 = (struct _GUID *)operator new(0x98u);
          v20 = AccessAce::AccessAce(
                  (AccessAce *)v25,
                  (const struct Sid *)v34,
                  v27,
                  *((_BYTE *)pAce + 1),
                  *(_BYTE *)pAce == 0);
          goto LABEL_23;
        }
      }
      else
      {
        if ( (unsigned int)*(unsigned __int8 *)pAce - 5 >= 2 )
        {
          v14 = GetCurrentThreadId();
          v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v15,
                                     13,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                     "Dacl::GetAces",
                                     1799,
                                     v14,
                                     0);
          continue;
        }
        v16 = 0;
        v25 = 0;
        v17 = 0;
        v18 = (const struct _SID *)((char *)pAce + 44);
        if ( *((_DWORD *)pAce + 2) & 1 )
        {
          v16 = (char *)pAce + 12;
          v25 = (struct _GUID *)((char *)pAce + 12);
        }
        else
        {
          v18 = (const struct _SID *)((char *)pAce + 28);
        }
        if ( (*((_BYTE *)pAce + 8) & 2) != 0 )
          v17 = (const struct _GUID *)((char *)pAce + (v16 != 0 ? 28LL : 12LL));
        else
          v18 = (const struct _SID *)((char *)v18 - 16);
        v5 = Sid::Set((Sid *)v34, v18);
        if ( !v5 )
        {
          v31 = (AccessObjectAce *)operator new(0xA8u);
          v20 = AccessObjectAce::AccessObjectAce(
                  v31,
                  (const struct Sid *)v34,
                  v27,
                  *((_BYTE *)pAce + 1),
                  *(_BYTE *)pAce == 5,
                  v25,
                  v17);
          v2 = v30;
LABEL_23:
          v25 = (struct _GUID *)v20;
          std::vector<ReplicaSetManager *>::push_back(v2 + 8, &v25);
          continue;
        }
        v2 = v30;
      }
    }
  }
LABEL_30:
  Sid::~Sid((Sid *)v34);
  return v4;
}

```

## disassembly

```asm
0x1401c6c30  mov     [rsp-8+arg_10], rbx
0x1401c6c35  mov     [rsp-8+arg_18], rdi
0x1401c6c3a  push    rbp
0x1401c6c3b  push    r12
0x1401c6c3d  push    r13
0x1401c6c3f  push    r14
0x1401c6c41  push    r15
0x1401c6c43  lea     rbp, [rsp-20h]
0x1401c6c48  sub     rsp, 120h
0x1401c6c4f  mov     rax, cs:__security_cookie
0x1401c6c56  xor     rax, rsp
0x1401c6c59  mov     [rbp+40h+var_30], rax
0x1401c6c5d  mov     r14, rdx
0x1401c6c60  mov     [rsp+140h+var_D0], rdx
0x1401c6c65  mov     r15, rcx
0x1401c6c68  xor     eax, eax
0x1401c6c6a  mov     [rbp+40h+pAclInformation], rax
0x1401c6c6e  mov     [rbp+40h+var_B8], eax
0x1401c6c71  xor     edi, edi
0x1401c6c73  mov     [rsp+140h+var_E8], edi
0x1401c6c77  mov     [rsp+140h+pAce], rdi
0x1401c6c7c  lea     rcx, [rbp+40h+var_B0]; this
0x1401c6c80  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x1401c6c85  nop
0x1401c6c86  mov     ebx, edi
0x1401c6c88  mov     rcx, r14
0x1401c6c8b  call    ?DeleteAll@?$PtrList@VVolumeConfig@Config@@@@QEAAXXZ; PtrList<Config::VolumeConfig>::DeleteAll(void)
0x1401c6c90  cmp     [r15+10h], edi
0x1401c6c94  jnz     loc_1401C6F6E
0x1401c6c9a  lea     r9d, [rdi+2]; dwAclInformationClass
0x1401c6c9e  lea     r8d, [rdi+0Ch]; nAclInformationLength
0x1401c6ca2  lea     rdx, [rbp+40h+pAclInformation]; pAclInformation
0x1401c6ca6  mov     rcx, [r15+18h]; pAcl
0x1401c6caa  call    cs:__imp_GetAclInformation
0x1401c6cb1  nop     dword ptr [rax+rax+00h]
0x1401c6cb6  test    eax, eax
0x1401c6cb8  jnz     short loc_1401C6D15
0x1401c6cba  call    cs:__imp_GetCurrentThreadId
0x1401c6cc1  nop     dword ptr [rax+rax+00h]
0x1401c6cc6  mov     ebx, eax
0x1401c6cc8  call    cs:__imp_GetLastError
0x1401c6ccf  nop     dword ptr [rax+rax+00h]
0x1401c6cd4  mov     [rsp+140h+var_100], rdi
0x1401c6cd9  mov     [rsp+140h+var_108], ebx
0x1401c6cdd  mov     dword ptr [rsp+140h+var_110], 6C0h
0x1401c6ce5  lea     r12, aDaclGetaces; "Dacl::GetAces"
0x1401c6cec  lea     r13, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c6cf3  mov     [rsp+140h+var_118], r12
0x1401c6cf8  mov     qword ptr [rsp+140h+var_120], r13
0x1401c6cfd  mov     r9d, 1
0x1401c6d03  xor     r8d, r8d
0x1401c6d06  mov     edx, eax
0x1401c6d08  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c6d0d  mov     rdi, rax
0x1401c6d10  jmp     loc_1401C6F6E
0x1401c6d15  mov     r9d, 1; dwAclInformationClass
0x1401c6d1b  lea     r8d, [r9+3]; nAclInformationLength
0x1401c6d1f  lea     rdx, [rsp+140h+var_E8]; pAclInformation
0x1401c6d24  mov     rcx, [r15+18h]; pAcl
0x1401c6d28  call    cs:__imp_GetAclInformation
0x1401c6d2f  nop     dword ptr [rax+rax+00h]
0x1401c6d34  test    eax, eax
0x1401c6d36  jnz     short loc_1401C6D65
0x1401c6d38  call    cs:__imp_GetCurrentThreadId
0x1401c6d3f  nop     dword ptr [rax+rax+00h]
0x1401c6d44  mov     ebx, eax
0x1401c6d46  call    cs:__imp_GetLastError
0x1401c6d4d  nop     dword ptr [rax+rax+00h]
0x1401c6d52  mov     [rsp+140h+var_100], rdi
0x1401c6d57  mov     [rsp+140h+var_108], ebx
0x1401c6d5b  mov     dword ptr [rsp+140h+var_110], 6C4h
0x1401c6d63  jmp     short loc_1401C6CE5
0x1401c6d65  mov     eax, [rsp+140h+var_E8]
0x1401c6d69  mov     [r15+8], eax
0x1401c6d6d  mov     eax, edi
0x1401c6d6f  lea     r12, aDaclGetaces; "Dacl::GetAces"
0x1401c6d76  lea     r13, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c6d7d  mov     [rsp+140h+var_E0], eax
0x1401c6d81  cmp     eax, dword ptr [rbp+40h+pAclInformation]
0x1401c6d84  jnb     loc_1401C6F6B
0x1401c6d8a  test    rbx, rbx
0x1401c6d8d  jnz     loc_1401C6F6B
0x1401c6d93  lea     r8, [rsp+140h+pAce]; pAce
0x1401c6d98  mov     edx, eax; dwAceIndex
0x1401c6d9a  mov     rcx, [r15+18h]; pAcl
0x1401c6d9e  call    cs:__imp_GetAce
0x1401c6da5  nop     dword ptr [rax+rax+00h]
0x1401c6daa  test    eax, eax
0x1401c6dac  jz      loc_1401C6F3B
0x1401c6db2  mov     rdx, [rsp+140h+pAce]
0x1401c6db7  mov     eax, [rdx+4]
0x1401c6dba  mov     [rsp+140h+var_E4], eax
0x1401c6dbe  movzx   ecx, byte ptr [rdx]
0x1401c6dc1  test    ecx, ecx
0x1401c6dc3  jz      loc_1401C6EDF
0x1401c6dc9  sub     ecx, 1
0x1401c6dcc  jz      loc_1401C6EDF
0x1401c6dd2  sub     ecx, 4
0x1401c6dd5  jz      short loc_1401C6E1A
0x1401c6dd7  cmp     ecx, 1
0x1401c6dda  jz      short loc_1401C6E1A
0x1401c6ddc  call    cs:__imp_GetCurrentThreadId
0x1401c6de3  nop     dword ptr [rax+rax+00h]
0x1401c6de8  mov     [rsp+140h+var_100], rdi
0x1401c6ded  mov     [rsp+140h+var_108], eax
0x1401c6df1  mov     dword ptr [rsp+140h+var_110], 707h
0x1401c6df9  mov     [rsp+140h+var_118], r12
0x1401c6dfe  mov     qword ptr [rsp+140h+var_120], r13
0x1401c6e03  lea     r9d, [rbx+1]
0x1401c6e07  xor     r8d, r8d
0x1401c6e0a  lea     edx, [rbx+0Dh]
0x1401c6e0d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c6e12  mov     rbx, rax
0x1401c6e15  jmp     loc_1401C6F30
0x1401c6e1a  mov     r9, rdi
0x1401c6e1d  mov     [rsp+140h+var_F0], rdi
0x1401c6e22  mov     r14, rdi
0x1401c6e25  lea     rcx, [rdx+2Ch]
0x1401c6e29  mov     r8d, [rdx+8]
0x1401c6e2d  and     r8d, 1
0x1401c6e31  jz      short loc_1401C6E3C
0x1401c6e33  lea     r9, [rdx+0Ch]
0x1401c6e37  mov     [rsp+140h+var_F0], r9
0x1401c6e3c  lea     rax, [rcx-10h]
0x1401c6e40  test    r8d, r8d
0x1401c6e43  cmovz   rcx, rax
0x1401c6e47  test    byte ptr [rdx+8], 2
0x1401c6e4b  jz      short loc_1401C6E63
0x1401c6e4d  mov     rax, r9
0x1401c6e50  neg     rax
0x1401c6e53  sbb     r14, r14
0x1401c6e56  and     r14d, 10h
0x1401c6e5a  add     r14, 0Ch
0x1401c6e5e  add     r14, rdx
0x1401c6e61  jmp     short loc_1401C6E67
0x1401c6e63  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1401c6e67  mov     rdx, rcx; struct _SID *
0x1401c6e6a  lea     rcx, [rbp+40h+var_B0]; this
0x1401c6e6e  call    ?Set@Sid@@QEAAPEAVFrsStatus@@PEBU_SID@@@Z; Sid::Set(_SID const *)
0x1401c6e73  mov     rbx, rax
0x1401c6e76  test    rax, rax
0x1401c6e79  jnz     loc_1401C6F2B
0x1401c6e7f  mov     ecx, 0A8h; Size
0x1401c6e84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401c6e89  mov     [rsp+140h+var_C8], rax
0x1401c6e8e  mov     ecx, edi
0x1401c6e90  mov     r9, [rsp+140h+pAce]
0x1401c6e95  cmp     byte ptr [r9], 5
0x1401c6e99  setz    cl
0x1401c6e9c  mov     [rsp+140h+var_110], r14; struct _GUID *
0x1401c6ea1  mov     rdx, [rsp+140h+var_F0]
0x1401c6ea6  mov     [rsp+140h+var_118], rdx; struct _GUID *
0x1401c6eab  mov     [rsp+140h+var_120], ecx; int
0x1401c6eaf  mov     r9b, [r9+1]; unsigned __int8
0x1401c6eb3  mov     r8d, [rsp+140h+var_E4]; unsigned int
0x1401c6eb8  lea     rdx, [rbp+40h+var_B0]; struct Sid *
0x1401c6ebc  mov     rcx, rax; this
0x1401c6ebf  call    ??0AccessObjectAce@@QEAA@AEBVSid@@KEHPEBU_GUID@@1@Z; AccessObjectAce::AccessObjectAce(Sid const &,ulong,uchar,int,_GUID const *,_GUID const *)
0x1401c6ec4  nop
0x1401c6ec5  mov     r14, [rsp+140h+var_D0]
0x1401c6eca  mov     [rsp+140h+var_F0], rax
0x1401c6ecf  lea     rcx, [r14+8]
0x1401c6ed3  lea     rdx, [rsp+140h+var_F0]
0x1401c6ed8  call    ?push_back@?$vector@PEAVReplicaSetManager@@V?$allocator@PEAVReplicaSetManager@@@std@@@std@@QEAAXAEBQEAVReplicaSetManager@@@Z; std::vector<ReplicaSetManager *>::push_back(ReplicaSetManager * const &)
0x1401c6edd  jmp     short loc_1401C6F30
0x1401c6edf  add     rdx, 8; struct _SID *
0x1401c6ee3  lea     rcx, [rbp+40h+var_B0]; this
0x1401c6ee7  call    ?Set@Sid@@QEAAPEAVFrsStatus@@PEBU_SID@@@Z; Sid::Set(_SID const *)
0x1401c6eec  mov     rbx, rax
0x1401c6eef  test    rax, rax
0x1401c6ef2  jnz     short loc_1401C6F30
0x1401c6ef4  mov     ecx, 98h; Size
0x1401c6ef9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401c6efe  mov     [rsp+140h+var_F0], rax
0x1401c6f03  mov     ecx, edi
0x1401c6f05  mov     r9, [rsp+140h+pAce]
0x1401c6f0a  cmp     [r9], dil
0x1401c6f0d  setz    cl
0x1401c6f10  mov     [rsp+140h+var_120], ecx; int
0x1401c6f14  mov     r9b, [r9+1]; unsigned __int8
0x1401c6f18  mov     r8d, [rsp+140h+var_E4]; unsigned int
0x1401c6f1d  lea     rdx, [rbp+40h+var_B0]; struct Sid *
0x1401c6f21  mov     rcx, rax; this
0x1401c6f24  call    ??0AccessAce@@QEAA@AEBVSid@@KEH@Z; AccessAce::AccessAce(Sid const &,ulong,uchar,int)
0x1401c6f29  jmp     short loc_1401C6ECA
0x1401c6f2b  mov     r14, [rsp+140h+var_D0]
0x1401c6f30  mov     eax, [rsp+140h+var_E0]
0x1401c6f34  inc     eax
0x1401c6f36  jmp     loc_1401C6D7D
0x1401c6f3b  call    cs:__imp_GetCurrentThreadId
0x1401c6f42  nop     dword ptr [rax+rax+00h]
0x1401c6f47  mov     ebx, eax
0x1401c6f49  call    cs:__imp_GetLastError
0x1401c6f50  nop     dword ptr [rax+rax+00h]
0x1401c6f55  mov     [rsp+140h+var_100], rdi
0x1401c6f5a  mov     [rsp+140h+var_108], ebx
0x1401c6f5e  mov     dword ptr [rsp+140h+var_110], 6CCh
0x1401c6f66  jmp     loc_1401C6CF3
0x1401c6f6b  mov     rdi, rbx
0x1401c6f6e  lea     rcx, [rbp+40h+var_B0]; this
0x1401c6f72  call    ??1Sid@@UEAA@XZ; Sid::~Sid(void)
0x1401c6f77  mov     rax, rdi
0x1401c6f7a  mov     rcx, [rbp+40h+var_30]
0x1401c6f7e  xor     rcx, rsp; StackCookie
0x1401c6f81  call    __security_check_cookie
0x1401c6f86  lea     r11, [rsp+140h+var_20]
0x1401c6f8e  mov     rbx, [r11+40h]
0x1401c6f92  mov     rdi, [r11+48h]
0x1401c6f96  mov     rsp, r11
0x1401c6f99  pop     r15
0x1401c6f9b  pop     r14
0x1401c6f9d  pop     r13
0x1401c6f9f  pop     r12
0x1401c6fa1  pop     rbp
0x1401c6fa2  retn
```
