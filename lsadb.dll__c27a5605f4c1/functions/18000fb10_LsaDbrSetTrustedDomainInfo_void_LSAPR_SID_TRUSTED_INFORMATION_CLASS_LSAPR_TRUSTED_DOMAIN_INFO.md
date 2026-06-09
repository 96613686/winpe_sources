# LsaDbrSetTrustedDomainInfo(void *,_LSAPR_SID *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO *)

- ea: `0x18000fb10`
- end: `0x18000fd10`
- name: `?LsaDbrSetTrustedDomainInfo@@YAJPEAXPEAU_LSAPR_SID@@W4_TRUSTED_INFORMATION_CLASS@@PEAT_LSAPR_TRUSTED_DOMAIN_INFO@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(void *, PSID Sid, enum _TRUSTED_INFORMATION_CLASS, union _LSAPR_TRUSTED_DOMAIN_INFO *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002234`
- `0x18000cf30`
- `0x18000d5e0`
- `0x18000d680`
- `0x18000e9f0`
- `0x18000fb10`
- `0x180033f80`
- `0x18003580c`
- `0x180036d24`
- `0x180036e00`

## import_xrefs

- `LSASRV!LsapCloseHandle` at `0x18000fcf0`
- `LSASRV!LsapCloseHandle` at `0x18000fcf0`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000fcdd`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000fcdd`
- `LSASRV!LsapDbVerifyHandle` at `0x18000fb78`
- `LSASRV!LsapDbVerifyHandle` at `0x18000fb78`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x18000fc36`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x18000fc90`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x18000fc36`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x18000fc90`

## pseudocode

```c
__int64 __fastcall LsaDbrSetTrustedDomainInfo(
        unsigned __int64 a1,
        PSID Sid,
        __int64 a3,
        union _LSAPR_TRUSTED_DOMAIN_INFO *a4)
{
  enum _TRUSTED_INFORMATION_CLASS v5; // esi
  _BYTE *v7; // rbx
  int v8; // edi
  LSA_UNICODE_STRING v9; // xmm0
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  char v13; // bl
  __int64 v14; // rcx
  __int64 v15; // r9
  unsigned int v17; // [rsp+20h] [rbp-60h]
  union _LSAPR_TRUSTED_DOMAIN_INFO *v18; // [rsp+50h] [rbp-30h] BYREF
  void *v19; // [rsp+58h] [rbp-28h] BYREF
  _LSA_TRUST_INFORMATION v20; // [rsp+60h] [rbp-20h] BYREF
  void *v21; // [rsp+A0h] [rbp+20h] BYREF

  v21 = 0;
  v18 = 0;
  v19 = (void *)a1;
  v5 = (int)a3;
  v7 = (_BYTE *)a1;
  if ( (_DWORD)a3 != 1 && (_DWORD)a3 != 3
    || !LsapValidateLsaprHandle(&v19)
    || !(unsigned int)LsapDbVerifyHandle(v7, 0, 1, 0)
    || !LsapValidateDomainSid(Sid)
    || !LsaDbpValidateLsaprTrustedDomainInfo(a4, v5) )
  {
    goto LABEL_15;
  }
  a1 = (unsigned int)(v5 - 1);
  if ( v5 != TrustedDomainNameInformation )
  {
    if ( v5 == TrustedPosixOffsetInformation )
    {
      v8 = LsaDbrOpenTrustedDomain(v7, Sid, 0x10u, &v21);
      if ( v8 >= 0 )
        v8 = LsaDbrSetInformationTrustedDomain(
               (char *)v21,
               TrustedPosixOffsetInformation,
               (struct _TRUSTED_DOMAIN_AUTH_INFORMATION *)a4);
      goto LABEL_16;
    }
LABEL_15:
    v8 = -1073741811;
    goto LABEL_16;
  }
  v9 = *(LSA_UNICODE_STRING *)a4;
  v20.Sid = Sid;
  v20.Name = v9;
  v8 = LsaDbrCreateTrustedDomain(v7, &v20, 0, &v21);
  if ( (unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(v11, v10, v12)
    && v8 >= 0
    && (unsigned __int8)LsapAdtAuditingEnabledHint(141, 8) )
  {
    v13 = *((_BYTE *)v21 + 133);
    *((_BYTE *)v21 + 133) = 1;
    v8 = LsaDbrQueryInfoTrustedDomain(v21, TrustedDomainFullInformation, &v18);
    *((_BYTE *)v21 + 133) = v13;
  }
LABEL_16:
  if ( (unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(a1, Sid, a3)
    && v8 >= 0
    && v5 == TrustedDomainNameInformation
    && (unsigned __int8)LsapAdtAuditingEnabledHint(141, 8) )
  {
    LsaDbpAdtTrustedDomainMod(v14, *((void **)v18 + 4), 0, v15, v17, 0, (struct _UNICODE_STRING *)a4, 0, 0, 0);
  }
  if ( v18 )
    LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(8, v18);
  if ( v21 )
    LsapCloseHandle(&v21, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000fb10  mov     [rsp-18h+arg_8], rbx
0x18000fb15  mov     [rsp-18h+arg_10], rsi
0x18000fb1a  push    rbp
0x18000fb1b  push    rdi
0x18000fb1c  push    r14
0x18000fb1e  mov     rbp, rsp
0x18000fb21  sub     rsp, 80h
0x18000fb28  mov     r10d, r8d
0x18000fb2b  mov     [rbp+arg_0], 0
0x18000fb33  mov     [rbp+var_30], 0
0x18000fb3b  mov     r14, r9
0x18000fb3e  mov     [rbp+var_28], rcx
0x18000fb42  mov     esi, r8d
0x18000fb45  mov     rdi, rdx
0x18000fb48  mov     rbx, rcx
0x18000fb4b  sub     r10d, 1
0x18000fb4f  jz      short loc_18000FB5B
0x18000fb51  cmp     r10d, 2
0x18000fb55  jnz     loc_18000FC71
0x18000fb5b  lea     rcx, [rbp+var_28]; void **
0x18000fb5f  call    ?LsapValidateLsaprHandle@@YAEPEAPEAX@Z; LsapValidateLsaprHandle(void * *)
0x18000fb64  test    al, al
0x18000fb66  jz      loc_18000FC71
0x18000fb6c  xor     r9d, r9d
0x18000fb6f  xor     edx, edx
0x18000fb71  mov     rcx, rbx
0x18000fb74  lea     r8d, [r9+1]
0x18000fb78  call    cs:__imp_LsapDbVerifyHandle
0x18000fb7e  test    eax, eax
0x18000fb80  jz      loc_18000FC71
0x18000fb86  mov     rcx, rdi; Sid1
0x18000fb89  call    ?LsapValidateDomainSid@@YAEPEAX@Z; LsapValidateDomainSid(void *)
0x18000fb8e  test    al, al
0x18000fb90  jz      loc_18000FC71
0x18000fb96  mov     edx, esi; enum _TRUSTED_INFORMATION_CLASS
0x18000fb98  mov     rcx, r14; union _LSAPR_TRUSTED_DOMAIN_INFO *
0x18000fb9b  call    ?LsaDbpValidateLsaprTrustedDomainInfo@@YAEPEAT_LSAPR_TRUSTED_DOMAIN_INFO@@W4_TRUSTED_INFORMATION_CLASS@@@Z; LsaDbpValidateLsaprTrustedDomainInfo(_LSAPR_TRUSTED_DOMAIN_INFO *,_TRUSTED_INFORMATION_CLASS)
0x18000fba0  test    al, al
0x18000fba2  jz      loc_18000FC71
0x18000fba8  mov     ecx, esi
0x18000fbaa  sub     ecx, 1
0x18000fbad  jz      short loc_18000FBED
0x18000fbaf  cmp     ecx, 2
0x18000fbb2  jnz     loc_18000FC71
0x18000fbb8  lea     r8d, [rcx+0Eh]; unsigned int
0x18000fbbc  mov     rdx, rdi; Sid
0x18000fbbf  mov     rcx, rbx; void *
0x18000fbc2  lea     r9, [rbp+arg_0]; void **
0x18000fbc6  call    ?LsaDbrOpenTrustedDomain@@YAJPEAXPEAU_LSAPR_SID@@KPEAPEAX@Z; LsaDbrOpenTrustedDomain(void *,_LSAPR_SID *,ulong,void * *)
0x18000fbcb  mov     edi, eax
0x18000fbcd  test    eax, eax
0x18000fbcf  js      loc_18000FC76
0x18000fbd5  mov     rcx, [rbp+arg_0]; void *
0x18000fbd9  mov     r8, r14; union _LSAPR_TRUSTED_DOMAIN_INFO *
0x18000fbdc  mov     edx, 3; enum _TRUSTED_INFORMATION_CLASS
0x18000fbe1  call    ?LsaDbrSetInformationTrustedDomain@@YAJPEAXW4_TRUSTED_INFORMATION_CLASS@@PEAT_LSAPR_TRUSTED_DOMAIN_INFO@@@Z; LsaDbrSetInformationTrustedDomain(void *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO *)
0x18000fbe6  mov     edi, eax
0x18000fbe8  jmp     loc_18000FC76
0x18000fbed  movups  xmm0, xmmword ptr [r14]
0x18000fbf1  mov     qword ptr [rbp+var_20.Name.Length], 0
0x18000fbf9  lea     r9, [rbp+arg_0]; void **
0x18000fbfd  mov     [rbp+var_20.Name.Buffer], 0
0x18000fc05  lea     rdx, [rbp+var_20]; struct _LSA_TRUST_INFORMATION *
0x18000fc09  xor     r8d, r8d; unsigned int
0x18000fc0c  mov     [rbp+var_20.Sid], rdi
0x18000fc10  mov     rcx, rbx; void *
0x18000fc13  movdqu  xmmword ptr [rbp+var_20.Name.Length], xmm0
0x18000fc18  call    ?LsaDbrCreateTrustedDomain@@YAJPEAXPEAU_LSAPR_TRUST_INFORMATION@@KPEAPEAX@Z; LsaDbrCreateTrustedDomain(void *,_LSAPR_TRUST_INFORMATION *,ulong,void * *)
0x18000fc1d  mov     edi, eax
0x18000fc1f  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x18000fc24  test    al, al
0x18000fc26  jz      short loc_18000FC76
0x18000fc28  test    edi, edi
0x18000fc2a  js      short loc_18000FC76
0x18000fc2c  mov     edx, 8
0x18000fc31  mov     ecx, 8Dh
0x18000fc36  call    cs:__imp_LsapAdtAuditingEnabledHint
0x18000fc3c  test    al, al
0x18000fc3e  jz      short loc_18000FC76
0x18000fc40  mov     rax, [rbp+arg_0]
0x18000fc44  lea     r8, [rbp+var_30]; union _LSAPR_TRUSTED_DOMAIN_INFO **
0x18000fc48  mov     edx, 8; enum _TRUSTED_INFORMATION_CLASS
0x18000fc4d  mov     bl, [rax+85h]
0x18000fc53  mov     byte ptr [rax+85h], 1
0x18000fc5a  mov     rcx, [rbp+arg_0]; void *
0x18000fc5e  call    ?LsaDbrQueryInfoTrustedDomain@@YAJPEAXW4_TRUSTED_INFORMATION_CLASS@@PEAPEAT_LSAPR_TRUSTED_DOMAIN_INFO@@@Z; LsaDbrQueryInfoTrustedDomain(void *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO * *)
0x18000fc63  mov     edi, eax
0x18000fc65  mov     rax, [rbp+arg_0]
0x18000fc69  mov     [rax+85h], bl
0x18000fc6f  jmp     short loc_18000FC76
0x18000fc71  mov     edi, 0C000000Dh
0x18000fc76  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x18000fc7b  test    al, al
0x18000fc7d  jz      short loc_18000FCCF
0x18000fc7f  test    edi, edi
0x18000fc81  js      short loc_18000FCCF
0x18000fc83  cmp     esi, 1
0x18000fc86  jnz     short loc_18000FCCF
0x18000fc88  lea     edx, [rsi+7]
0x18000fc8b  mov     ecx, 8Dh
0x18000fc90  call    cs:__imp_LsapAdtAuditingEnabledHint
0x18000fc96  test    al, al
0x18000fc98  jz      short loc_18000FCCF
0x18000fc9a  mov     rdx, [rbp+var_30]
0x18000fc9e  xor     r8d, r8d; struct _UNICODE_STRING *
0x18000fca1  mov     [rsp+80h+var_38], 0; unsigned int
0x18000fca9  mov     [rsp+80h+var_40], 0; unsigned int
0x18000fcb1  mov     [rsp+80h+var_48], 0; unsigned int
0x18000fcb9  mov     rdx, [rdx+20h]; void *
0x18000fcbd  mov     [rsp+80h+var_50], r14; struct _UNICODE_STRING *
0x18000fcc2  mov     [rsp+80h+var_58], 0; unsigned int
0x18000fcca  call    ?LsaDbpAdtTrustedDomainMod@@YAJGPEAXPEAU_UNICODE_STRING@@KKK1KKK@Z; LsaDbpAdtTrustedDomainMod(ushort,void *,_UNICODE_STRING *,ulong,ulong,ulong,_UNICODE_STRING *,ulong,ulong,ulong)
0x18000fccf  mov     rdx, [rbp+var_30]
0x18000fcd3  test    rdx, rdx
0x18000fcd6  jz      short loc_18000FCE3
0x18000fcd8  mov     ecx, 8
0x18000fcdd  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO
0x18000fce3  cmp     [rbp+arg_0], 0
0x18000fce8  jz      short loc_18000FCF6
0x18000fcea  mov     edx, edi
0x18000fcec  lea     rcx, [rbp+arg_0]
0x18000fcf0  call    cs:__imp_LsapCloseHandle
0x18000fcf6  lea     r11, [rsp+80h+var_s0]
0x18000fcfe  mov     eax, edi
0x18000fd00  mov     rbx, [r11+28h]
0x18000fd04  mov     rsi, [r11+30h]
0x18000fd08  mov     rsp, r11
0x18000fd0b  pop     r14
0x18000fd0d  pop     rdi
0x18000fd0e  pop     rbp
0x18000fd0f  retn
```
