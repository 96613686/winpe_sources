# LsaDbpUpdateTDOAttributesForCreation(_UNICODE_STRING *,_LSAP_DB_ATTRIBUTE *,ulong *,ulong)

- ea: `0x180036a7c`
- end: `0x180036d1c`
- name: `?LsaDbpUpdateTDOAttributesForCreation@@YAJPEAU_UNICODE_STRING@@PEAU_LSAP_DB_ATTRIBUTE@@PEAKK@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _LSAP_DB_ATTRIBUTE *, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015830`

## callees

- `0x180001670`
- `0x1800107e0`
- `0x180011580`
- `0x180012120`
- `0x180012a24`
- `0x180012a74`
- `0x1800361ec`
- `0x180036940`
- `0x180036a7c`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180036b0c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180036b0c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036b50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036c49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036b50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036c49`
- `LSASRV!LsapDbInitializeAttribute` at `0x180036bab`
- `LSASRV!LsapDbInitializeAttribute` at `0x180036c84`
- `LSASRV!LsapDbInitializeAttribute` at `0x180036bab`
- `LSASRV!LsapDbInitializeAttribute` at `0x180036c84`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180036cc4`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180036cc4`
- `LSASRV!LsapFreeLsaHeap` at `0x180036cb0`
- `LSASRV!LsapFreeLsaHeap` at `0x180036cdf`
- `LSASRV!LsapFreeLsaHeap` at `0x180036ced`
- `LSASRV!LsapFreeLsaHeap` at `0x180036cb0`
- `LSASRV!LsapFreeLsaHeap` at `0x180036cdf`
- `LSASRV!LsapFreeLsaHeap` at `0x180036ced`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x180036ae2`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x180036ae2`
- `ntdll!RtlCopySid` at `0x180036b89`
- `ntdll!RtlCopySid` at `0x180036b89`
- `ntdll!RtlLengthSid` at `0x180036b40`
- `ntdll!RtlLengthSid` at `0x180036b92`
- `ntdll!RtlLengthSid` at `0x180036b40`
- `ntdll!RtlLengthSid` at `0x180036b92`

## pseudocode

```c
__int64 __fastcall LsaDbpUpdateTDOAttributesForCreation(
        struct _UNICODE_STRING *a1,
        struct _LSAP_DB_ATTRIBUTE *a2,
        unsigned int *a3)
{
  __int64 v3; // rsi
  struct _DSNAME *v5; // r14
  void *v6; // r15
  int NewSelfRelativeSecurityDescriptor; // edi
  __int64 v8; // r8
  __int64 v9; // r13
  int CurrentOwnerAndPrimaryGroup; // eax
  __int64 v11; // rdx
  struct _TOKEN_OWNER *v12; // r12
  HLOCAL v13; // rdi
  PSID Owner; // r8
  struct _LSAP_DB_ATTRIBUTE *v15; // r14
  struct _LSAP_DB_HANDLE *v16; // rdx
  struct _UNICODE_STRING *v17; // rcx
  int v18; // eax
  int v19; // eax
  struct _ACL *Sacl; // rbx
  struct _ACL *Dacl; // rax
  HLOCAL v22; // rax
  HLOCAL v23; // r13
  struct _LSAP_DB_ATTRIBUTE *v24; // rbx
  struct _LSAP_DB_HANDLE *v25; // rcx
  __int64 v26; // rdx
  DWORD cbSid; // [rsp+30h] [rbp-79h] BYREF
  DWORD uBytes[3]; // [rsp+34h] [rbp-75h] BYREF
  void *v30; // [rsp+40h] [rbp-69h] BYREF
  struct _DSNAME *v31; // [rsp+48h] [rbp-61h] BYREF
  __int64 v32; // [rsp+50h] [rbp-59h] BYREF
  struct _LSAP_DB_ATTRIBUTE *v33; // [rsp+58h] [rbp-51h]
  struct _TOKEN_OWNER *v34; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING *v35; // [rsp+68h] [rbp-41h]
  unsigned int *v36; // [rsp+70h] [rbp-39h]
  _BYTE pSid[72]; // [rsp+78h] [rbp-31h] BYREF

  v3 = 0;
  v33 = a2;
  v35 = a1;
  v5 = 0;
  v36 = a3;
  v6 = 0;
  v34 = 0;
  v31 = 0;
  v30 = 0;
  memset(uBytes, 0, sizeof(uBytes));
  cbSid = 0;
  v32 = 0;
  NewSelfRelativeSecurityDescriptor = LsaIQueryInformationPolicyTrusted(12, &v32);
  if ( NewSelfRelativeSecurityDescriptor < 0 )
    goto LABEL_15;
  cbSid = 68;
  if ( !CreateWellKnownSid(WinAccountDomainAdminsSid, *(PSID *)(v32 + 64), pSid, &cbSid) )
  {
    NewSelfRelativeSecurityDescriptor = -1073741801;
    goto LABEL_15;
  }
  v9 = *a3;
  CurrentOwnerAndPrimaryGroup = LsaDbpGetCurrentOwnerAndPrimaryGroup(&v34, 0);
  v12 = v34;
  NewSelfRelativeSecurityDescriptor = CurrentOwnerAndPrimaryGroup;
  if ( CurrentOwnerAndPrimaryGroup >= 0 )
  {
    cbSid = RtlLengthSid(v34->Owner);
    v13 = LocalAlloc(0x40u, cbSid);
    if ( !v13 )
    {
LABEL_6:
      NewSelfRelativeSecurityDescriptor = -1073741801;
      goto LABEL_13;
    }
    Owner = v12->Owner;
    v33 = (struct _LSAP_DB_ATTRIBUTE *)((char *)v33 + 40 * v9);
    v15 = v33;
    RtlCopySid(cbSid, v13, Owner);
    RtlLengthSid(v13);
    LsapDbInitializeAttribute(v15, 46, v13);
    v16 = LsaDbpDsAttInfo;
    v17 = v35;
    *((_DWORD *)v15 + 8) = *((_DWORD *)LsaDbpDsAttInfo + 138);
    *((_DWORD *)v15 + 9) = *((_DWORD *)v16 + 139);
    ++*a3;
    v18 = LsaDbpAllocAndInitializeDsNameFromUnicode(v17, &v31);
    v5 = v31;
    NewSelfRelativeSecurityDescriptor = v18;
    if ( v18 >= 0 )
    {
      v19 = LsaDbpDsReadObjectSDByDsName(v31, &v30);
      v6 = v30;
      NewSelfRelativeSecurityDescriptor = v19;
      if ( v19 >= 0 )
      {
        Sacl = LsaDbpGetSacl(v30);
        Dacl = LsaDbpGetDacl(v6);
        NewSelfRelativeSecurityDescriptor = LsaDbpMakeNewSelfRelativeSecurityDescriptor(
                                              pSid,
                                              pSid,
                                              Dacl,
                                              Sacl,
                                              uBytes,
                                              (void **)&uBytes[1]);
        if ( NewSelfRelativeSecurityDescriptor < 0 )
        {
          v3 = *(_QWORD *)&uBytes[1];
        }
        else
        {
          v22 = LocalAlloc(0x40u, uBytes[0]);
          v3 = *(_QWORD *)&uBytes[1];
          v23 = v22;
          if ( !v22 )
            goto LABEL_6;
          v24 = v33;
          memcpy_0(v22, *(const void **)&uBytes[1], uBytes[0]);
          LsapDbInitializeAttribute((char *)v24 + 40, 0, v23);
          v25 = LsaDbpDsAttInfo;
          *((_DWORD *)v24 + 18) = *(_DWORD *)LsaDbpDsAttInfo;
          *((_DWORD *)v24 + 19) = *((_DWORD *)v25 + 1);
          ++*v36;
        }
      }
    }
  }
LABEL_13:
  if ( v12 )
    LsapFreeLsaHeap(v12, v11, v8);
LABEL_15:
  v26 = v32;
  if ( v32 )
    LsaIFree_LSAPR_POLICY_INFORMATION(12);
  if ( v5 )
    LsaDbpDsFree(v5);
  if ( v6 )
    LsapFreeLsaHeap(v6, v26, v8);
  if ( v3 )
    LsapFreeLsaHeap(v3, v26, v8);
  return (unsigned int)NewSelfRelativeSecurityDescriptor;
}

```

## disassembly

```asm
0x180036a7c  mov     [rsp-8+arg_18], rbx
0x180036a81  push    rbp
0x180036a82  push    rsi
0x180036a83  push    rdi
0x180036a84  push    r12
0x180036a86  push    r13
0x180036a88  push    r14
0x180036a8a  push    r15
0x180036a8c  lea     rbp, [rsp-27h]
0x180036a91  sub     rsp, 0D0h
0x180036a98  mov     rax, cs:__security_cookie
0x180036a9f  xor     rax, rsp
0x180036aa2  mov     [rbp+57h+var_40], rax
0x180036aa6  xor     esi, esi
0x180036aa8  mov     [rbp+57h+var_A8], rdx
0x180036aac  mov     rbx, r8
0x180036aaf  mov     [rbp+57h+var_98], rcx
0x180036ab3  xor     r14d, r14d
0x180036ab6  mov     [rbp+57h+var_90], rbx
0x180036aba  xor     r15d, r15d
0x180036abd  mov     [rbp+57h+var_A0], 0
0x180036ac5  lea     ecx, [rsi+0Ch]
0x180036ac8  mov     [rbp+57h+var_B8], r14
0x180036acc  lea     rdx, [rbp+57h+var_B0]
0x180036ad0  mov     [rbp+57h+var_C0], r15
0x180036ad4  mov     qword ptr [rbp+57h+uBytes+4], rsi
0x180036ad8  mov     dword ptr [rbp+57h+uBytes], esi
0x180036adb  mov     [rbp+57h+cbSid], esi
0x180036ade  mov     [rbp+57h+var_B0], rsi
0x180036ae2  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x180036ae8  mov     edi, eax
0x180036aea  test    eax, eax
0x180036aec  js      loc_180036CB6
0x180036af2  mov     rdx, [rbp+57h+var_B0]
0x180036af6  lea     r9, [rbp+57h+cbSid]; cbSid
0x180036afa  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180036b01  lea     r8, [rbp+57h+pSid]; pSid
0x180036b05  lea     ecx, [rsi+29h]; WellKnownSidType
0x180036b08  mov     rdx, [rdx+40h]; DomainSid
0x180036b0c  call    cs:__imp_CreateWellKnownSid
0x180036b12  test    eax, eax
0x180036b14  jnz     short loc_180036B20
0x180036b16  mov     edi, 0C0000017h
0x180036b1b  jmp     loc_180036CB6
0x180036b20  mov     r13d, [rbx]
0x180036b23  lea     rcx, [rbp+57h+var_A0]; struct _TOKEN_OWNER **
0x180036b27  xor     edx, edx; struct _TOKEN_PRIMARY_GROUP **
0x180036b29  call    ?LsaDbpGetCurrentOwnerAndPrimaryGroup@@YAJPEAPEAU_TOKEN_OWNER@@PEAPEAU_TOKEN_PRIMARY_GROUP@@@Z; LsaDbpGetCurrentOwnerAndPrimaryGroup(_TOKEN_OWNER * *,_TOKEN_PRIMARY_GROUP * *)
0x180036b2e  mov     r12, [rbp+57h+var_A0]
0x180036b32  mov     edi, eax
0x180036b34  test    eax, eax
0x180036b36  js      loc_180036CA8
0x180036b3c  mov     rcx, [r12]; Sid
0x180036b40  call    cs:__imp_RtlLengthSid
0x180036b46  mov     edx, eax; uBytes
0x180036b48  mov     ecx, 40h ; '@'; uFlags
0x180036b4d  mov     [rbp+57h+cbSid], edx
0x180036b50  call    cs:__imp_LocalAlloc
0x180036b56  mov     rdi, rax
0x180036b59  test    rax, rax
0x180036b5c  jnz     short loc_180036B68
0x180036b5e  mov     edi, 0C0000017h
0x180036b63  jmp     loc_180036CA8
0x180036b68  mov     rax, [rbp+57h+var_A8]
0x180036b6c  lea     rcx, ds:0[r13*4]
0x180036b74  mov     r8, [r12]; SourceSid
0x180036b78  add     rcx, r13
0x180036b7b  mov     rdx, rdi; DestinationSid
0x180036b7e  lea     r14, [rax+rcx*8]
0x180036b82  mov     ecx, [rbp+57h+cbSid]; DestinationSidLength
0x180036b85  mov     [rbp+57h+var_A8], r14
0x180036b89  call    cs:__imp_RtlCopySid
0x180036b8f  mov     rcx, rdi; Sid
0x180036b92  call    cs:__imp_RtlLengthSid
0x180036b98  mov     r8, rdi
0x180036b9b  mov     byte ptr [rsp+100h+lpdwBufferLength], 1
0x180036ba0  mov     r9d, eax
0x180036ba3  mov     edx, 2Eh ; '.'
0x180036ba8  mov     rcx, r14
0x180036bab  call    cs:__imp_LsapDbInitializeAttribute
0x180036bb1  mov     rdx, cs:?LsaDbpDsAttInfo@@3PEAU_LSAP_DB_DS_INFO@@EA; _LSAP_DB_DS_INFO * LsaDbpDsAttInfo
0x180036bb8  mov     rcx, [rbp+57h+var_98]; struct _UNICODE_STRING *
0x180036bbc  mov     eax, [rdx+228h]
0x180036bc2  mov     [r14+20h], eax
0x180036bc6  mov     eax, [rdx+22Ch]
0x180036bcc  lea     rdx, [rbp+57h+var_B8]; struct _DSNAME **
0x180036bd0  mov     [r14+24h], eax
0x180036bd4  inc     dword ptr [rbx]
0x180036bd6  call    ?LsaDbpAllocAndInitializeDsNameFromUnicode@@YAJPEAU_UNICODE_STRING@@PEAPEAU_DSNAME@@@Z; LsaDbpAllocAndInitializeDsNameFromUnicode(_UNICODE_STRING *,_DSNAME * *)
0x180036bdb  mov     r14, [rbp+57h+var_B8]
0x180036bdf  mov     edi, eax
0x180036be1  test    eax, eax
0x180036be3  js      loc_180036CA8
0x180036be9  lea     rdx, [rbp+57h+var_C0]; void **
0x180036bed  mov     rcx, r14; struct _DSNAME *
0x180036bf0  call    ?LsaDbpDsReadObjectSDByDsName@@YAJPEAU_DSNAME@@PEAPEAX@Z; LsaDbpDsReadObjectSDByDsName(_DSNAME *,void * *)
0x180036bf5  mov     r15, [rbp+57h+var_C0]
0x180036bf9  mov     edi, eax
0x180036bfb  test    eax, eax
0x180036bfd  js      loc_180036CA8
0x180036c03  mov     rcx, r15; void *
0x180036c06  call    ?LsaDbpGetSacl@@YAPEAU_ACL@@PEAX@Z; LsaDbpGetSacl(void *)
0x180036c0b  mov     rcx, r15; void *
0x180036c0e  mov     rbx, rax
0x180036c11  call    ?LsaDbpGetDacl@@YAPEAU_ACL@@PEAX@Z; LsaDbpGetDacl(void *)
0x180036c16  lea     rdx, [rbp+57h+uBytes+4]
0x180036c1a  mov     r9, rbx; pSacl
0x180036c1d  mov     [rsp+100h+var_D8], rdx; void **
0x180036c22  lea     rcx, [rbp+57h+pSid]; pOwner
0x180036c26  lea     rdx, [rbp+57h+uBytes]
0x180036c2a  mov     r8, rax; pDacl
0x180036c2d  mov     [rsp+100h+lpdwBufferLength], rdx; lpdwBufferLength
0x180036c32  lea     rdx, [rbp+57h+pSid]; pGroup
0x180036c36  call    ?LsaDbpMakeNewSelfRelativeSecurityDescriptor@@YAJPEAX0PEAU_ACL@@1PEAKPEAPEAX@Z; LsaDbpMakeNewSelfRelativeSecurityDescriptor(void *,void *,_ACL *,_ACL *,ulong *,void * *)
0x180036c3b  mov     edi, eax
0x180036c3d  test    eax, eax
0x180036c3f  js      short loc_180036CA4
0x180036c41  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x180036c44  mov     ecx, 40h ; '@'; uFlags
0x180036c49  call    cs:__imp_LocalAlloc
0x180036c4f  mov     rsi, qword ptr [rbp+57h+uBytes+4]
0x180036c53  mov     r13, rax
0x180036c56  test    rax, rax
0x180036c59  jz      loc_180036B5E
0x180036c5f  mov     r8d, dword ptr [rbp+57h+uBytes]; Size
0x180036c63  mov     rdx, rsi; Src
0x180036c66  mov     rbx, [rbp+57h+var_A8]
0x180036c6a  mov     rcx, rax; void *
0x180036c6d  call    memcpy_0
0x180036c72  mov     r9d, dword ptr [rbp+57h+uBytes]
0x180036c76  lea     rcx, [rbx+28h]
0x180036c7a  mov     r8, r13
0x180036c7d  mov     byte ptr [rsp+100h+lpdwBufferLength], 1
0x180036c82  xor     edx, edx
0x180036c84  call    cs:__imp_LsapDbInitializeAttribute
0x180036c8a  mov     rcx, cs:?LsaDbpDsAttInfo@@3PEAU_LSAP_DB_DS_INFO@@EA; _LSAP_DB_DS_INFO * LsaDbpDsAttInfo
0x180036c91  mov     eax, [rcx]
0x180036c93  mov     [rbx+48h], eax
0x180036c96  mov     eax, [rcx+4]
0x180036c99  mov     [rbx+4Ch], eax
0x180036c9c  mov     rax, [rbp+57h+var_90]
0x180036ca0  inc     dword ptr [rax]
0x180036ca2  jmp     short loc_180036CA8
0x180036ca4  mov     rsi, qword ptr [rbp+57h+uBytes+4]
0x180036ca8  test    r12, r12
0x180036cab  jz      short loc_180036CB6
0x180036cad  mov     rcx, r12
0x180036cb0  call    cs:__imp_LsapFreeLsaHeap
0x180036cb6  mov     rdx, [rbp+57h+var_B0]
0x180036cba  test    rdx, rdx
0x180036cbd  jz      short loc_180036CCA
0x180036cbf  mov     ecx, 0Ch
0x180036cc4  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x180036cca  test    r14, r14
0x180036ccd  jz      short loc_180036CD7
0x180036ccf  mov     rcx, r14; void *
0x180036cd2  call    ?LsaDbpDsFree@@YAXPEAX@Z; LsaDbpDsFree(void *)
0x180036cd7  test    r15, r15
0x180036cda  jz      short loc_180036CE5
0x180036cdc  mov     rcx, r15
0x180036cdf  call    cs:__imp_LsapFreeLsaHeap
0x180036ce5  test    rsi, rsi
0x180036ce8  jz      short loc_180036CF3
0x180036cea  mov     rcx, rsi
0x180036ced  call    cs:__imp_LsapFreeLsaHeap
0x180036cf3  mov     eax, edi
0x180036cf5  mov     rcx, [rbp+57h+var_40]
0x180036cf9  xor     rcx, rsp; StackCookie
0x180036cfc  call    __security_check_cookie
0x180036d01  mov     rbx, [rsp+100h+arg_18]
0x180036d09  add     rsp, 0D0h
0x180036d10  pop     r15
0x180036d12  pop     r14
0x180036d14  pop     r13
0x180036d16  pop     r12
0x180036d18  pop     rdi
0x180036d19  pop     rsi
0x180036d1a  pop     rbp
0x180036d1b  retn
```
