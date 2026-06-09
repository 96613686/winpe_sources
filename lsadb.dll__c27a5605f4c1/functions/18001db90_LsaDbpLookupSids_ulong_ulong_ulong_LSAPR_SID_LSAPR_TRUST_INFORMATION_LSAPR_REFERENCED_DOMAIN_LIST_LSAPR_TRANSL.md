# LsaDbpLookupSids(ulong,ulong,ulong,_LSAPR_SID * *,_LSAPR_TRUST_INFORMATION,_LSAPR_REFERENCED_DOMAIN_LIST * *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *,ulong *)

- ea: `0x18001db90`
- end: `0x18001de1a`
- name: `?LsaDbpLookupSids@@YAJKKKPEAPEAU_LSAPR_SID@@U_LSAPR_TRUST_INFORMATION@@PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK4@Z`
- size: `650`
- prototype: `int __high(unsigned int, unsigned int, unsigned int, struct _LSAPR_SID **, struct _LSAPR_TRUST_INFORMATION, struct _LSAPR_REFERENCED_DOMAIN_LIST **, struct _LSAPR_TRANSLATED_NAMES_EX *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x18001db90`
- `0x18001de20`
- `0x18001e138`
- `0x18001e860`
- `0x18001e968`

## import_xrefs

- `LSASRV!LsapDbLookupSidsInPrimaryDomain` at `0x18001dc51`
- `LSASRV!LsapDbLookupSidsInPrimaryDomain` at `0x18001dd68`
- `LSASRV!LsapDbLookupSidsInPrimaryDomain` at `0x18001dc51`
- `LSASRV!LsapDbLookupSidsInPrimaryDomain` at `0x18001dd68`
- `LSASRV!LsaIIsDsPaused` at `0x18001dbf3`
- `LSASRV!LsaIIsDsPaused` at `0x18001dbf3`
- `LSASRV!LsapDbLookupGetDomainInfo` at `0x18001dbd7`
- `LSASRV!LsapDbLookupGetDomainInfo` at `0x18001dd15`
- `LSASRV!LsapDbLookupGetDomainInfo` at `0x18001dbd7`
- `LSASRV!LsapDbLookupGetDomainInfo` at `0x18001dd15`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupSids(
        unsigned int a1,
        int a2,
        int a3,
        struct _LSAPR_SID **a4,
        __int64 a5,
        struct _LSAPR_REFERENCED_DOMAIN_LIST **a6,
        struct _LSAPR_TRANSLATED_NAMES_EX *a7,
        unsigned int *a8,
        unsigned int *a9)
{
  int v9; // ebx
  struct _LSAPR_SID **v10; // r14
  unsigned int v12; // eax
  __int64 v13; // rax
  __int64 v14; // r8
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v15; // r9
  int DomainInfo; // eax
  unsigned int *v17; // r15
  unsigned int *v18; // rsi
  struct _LSAPR_TRANSLATED_NAMES_EX *v19; // r12
  struct _LSAPR_REFERENCED_DOMAIN_LIST **v20; // r13
  unsigned int v21; // r14d
  __int64 v22; // r14
  __int64 v23; // rax
  __int64 v24; // r8
  struct _LSAPR_TRANSLATED_NAMES_EX *v26; // [rsp+20h] [rbp-40h]
  ULONG v27; // [rsp+30h] [rbp-30h]
  _QWORD v28[2]; // [rsp+50h] [rbp-10h] BYREF
  int v30; // [rsp+A8h] [rbp+48h] BYREF
  struct _LSAPR_SID **v31; // [rsp+B8h] [rbp+58h]

  v31 = a4;
  v9 = 0;
  v30 = 0;
  v28[0] = 0;
  v10 = a4;
  v12 = a1;
  if ( a2 != 1 )
  {
LABEL_10:
    v17 = a9;
    v18 = a8;
    v19 = a7;
    v20 = a6;
    if ( (a3 & 0xB) != 0 )
    {
      v21 = *a8;
      DomainInfo = LsaDbpLookupSidsAsDomainSids(a3, v12, v31, *a6, a7, a8);
      if ( DomainInfo < 0 )
        return (unsigned int)DomainInfo;
      *v17 += v21 - *v18;
      v10 = v31;
    }
    if ( (a3 & 2) != 0 )
    {
      LOBYTE(v27) = 1;
      DomainInfo = LsaDbpLookupSidsInGlobalCatalog(a1, v10, *v20, v19, v18, v17, v27, &v30);
      if ( DomainInfo < 0 )
        return (unsigned int)DomainInfo;
      if ( v30 < 0 )
        v9 = v30;
    }
    if ( (a3 & 0x20) != 0 )
    {
      v22 = a5;
      if ( !*(_QWORD *)(a5 + 16) )
      {
        DomainInfo = LsapDbLookupGetDomainInfo(0, v28, 0);
        if ( DomainInfo < 0 )
          return (unsigned int)DomainInfo;
        v23 = v28[0];
        *(_OWORD *)v22 = *(_OWORD *)v28[0];
        *(_QWORD *)(v22 + 16) = *(_QWORD *)(v23 + 64);
      }
      v24 = v22;
      v10 = v31;
      v26 = v19;
      DomainInfo = LsapDbLookupSidsInPrimaryDomain(a1, v31, v24, *v20);
      if ( DomainInfo < 0 )
        return (unsigned int)DomainInfo;
      if ( v30 < 0 && v9 >= 0 )
        v9 = v30;
    }
    if ( (a3 & 4) == 0 )
    {
LABEL_30:
      if ( (a3 & 1) == 0 )
        return (unsigned int)v9;
      DomainInfo = LsaDbpLookupSidsInTrustedDomains(
                     a1,
                     (__int64)v10,
                     (__int64)*v20,
                     (__int64)v19,
                     (__int64)v26,
                     (__int64)v18,
                     (__int64)v17,
                     &v30);
      if ( DomainInfo < 0 )
        return (unsigned int)DomainInfo;
      if ( v30 < 0 && v9 >= 0 )
        return (unsigned int)v30;
      return (unsigned int)v9;
    }
    DomainInfo = LsaDbpLookupSidsInTrustedForests(a1, v10, *v20, v19, v18, v17, &v30);
    if ( DomainInfo >= 0 )
    {
      if ( v30 < 0 && v9 >= 0 )
        v9 = v30;
      goto LABEL_30;
    }
    return (unsigned int)DomainInfo;
  }
  if ( (int)LsapDbLookupGetDomainInfo(0, v28, 0) < 0 || !*(_QWORD *)(v28[0] + 64LL) )
    return (unsigned int)v9;
  if ( !(unsigned __int8)LsaIIsDsPaused() )
  {
    v12 = a1;
    goto LABEL_10;
  }
  v13 = v28[0];
  v14 = a5;
  v15 = *a6;
  *(_OWORD *)a5 = *(_OWORD *)v28[0];
  *(_QWORD *)(v14 + 16) = *(_QWORD *)(v13 + 64);
  DomainInfo = LsapDbLookupSidsInPrimaryDomain(a1, v10, v14, v15);
  if ( DomainInfo < 0 )
    return (unsigned int)DomainInfo;
  DomainInfo = v30;
  if ( v30 < 0 )
    return (unsigned int)DomainInfo;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001db90  mov     [rsp-38h+arg_10], rbx
0x18001db95  mov     [rsp-38h+arg_18], r9
0x18001db9a  mov     dword ptr [rsp-38h+Size], ecx
0x18001db9e  push    rbp
0x18001db9f  push    rsi
0x18001dba0  push    rdi
0x18001dba1  push    r12
0x18001dba3  push    r13
0x18001dba5  push    r14
0x18001dba7  push    r15
0x18001dba9  mov     rbp, rsp
0x18001dbac  sub     rsp, 60h
0x18001dbb0  xor     ebx, ebx
0x18001dbb2  mov     [rbp+arg_8], 0
0x18001dbb9  mov     [rbp+var_10], rbx
0x18001dbbd  mov     r14, r9
0x18001dbc0  mov     edi, r8d
0x18001dbc3  mov     eax, ecx
0x18001dbc5  cmp     edx, 1
0x18001dbc8  jnz     loc_18001DC72
0x18001dbce  xor     r8d, r8d
0x18001dbd1  lea     rdx, [rbp+var_10]
0x18001dbd5  xor     ecx, ecx
0x18001dbd7  call    cs:__imp_LsapDbLookupGetDomainInfo
0x18001dbdd  test    eax, eax
0x18001dbdf  js      loc_18001DE00
0x18001dbe5  mov     rax, [rbp+var_10]
0x18001dbe9  cmp     [rax+40h], rbx
0x18001dbed  jz      loc_18001DE00
0x18001dbf3  call    cs:__imp_LsaIIsDsPaused
0x18001dbf9  test    al, al
0x18001dbfb  jz      short loc_18001DC6F
0x18001dbfd  mov     rax, [rbp+var_10]
0x18001dc01  mov     rdx, r14
0x18001dc04  mov     r8, [rbp+arg_20]
0x18001dc08  mov     r9, [rbp+arg_28]
0x18001dc0c  mov     ecx, dword ptr [rbp+Size]
0x18001dc0f  movups  xmm0, xmmword ptr [rax]
0x18001dc12  mov     r9, [r9]
0x18001dc15  movdqu  xmmword ptr [r8], xmm0
0x18001dc1a  mov     rax, [rax+40h]
0x18001dc1e  mov     [r8+10h], rax
0x18001dc22  lea     rax, [rbp+arg_8]
0x18001dc26  mov     [rsp+60h+var_20], rax
0x18001dc2b  mov     rax, [rbp+arg_40]
0x18001dc32  mov     [rsp+60h+var_28], rax
0x18001dc37  mov     rax, [rbp+arg_38]
0x18001dc3b  mov     [rsp+60h+var_30], rax
0x18001dc40  mov     rax, [rbp+arg_30]
0x18001dc44  mov     dword ptr [rsp+60h+var_38], 2
0x18001dc4c  mov     [rsp+60h+var_40], rax
0x18001dc51  call    cs:__imp_LsapDbLookupSidsInPrimaryDomain
0x18001dc57  test    eax, eax
0x18001dc59  jns     short loc_18001DC62
0x18001dc5b  mov     ebx, eax
0x18001dc5d  jmp     loc_18001DE00
0x18001dc62  mov     eax, [rbp+arg_8]
0x18001dc65  test    eax, eax
0x18001dc67  jns     loc_18001DE00
0x18001dc6d  jmp     short loc_18001DC5B
0x18001dc6f  mov     eax, dword ptr [rbp+Size]
0x18001dc72  mov     r15, [rbp+arg_40]
0x18001dc79  mov     rsi, [rbp+arg_38]
0x18001dc7d  mov     r12, [rbp+arg_30]
0x18001dc81  mov     r13, [rbp+arg_28]
0x18001dc85  test    dil, 0Bh
0x18001dc89  jz      short loc_18001DCB7
0x18001dc8b  mov     r9, [r13+0]; struct _LSAPR_REFERENCED_DOMAIN_LIST *
0x18001dc8f  mov     edx, eax; unsigned int
0x18001dc91  mov     r8, [rbp+arg_18]; struct _LSAPR_SID **
0x18001dc95  mov     ecx, edi; unsigned int
0x18001dc97  mov     r14d, [rsi]
0x18001dc9a  mov     [rsp+60h+var_38], rsi; unsigned int *
0x18001dc9f  mov     [rsp+60h+var_40], r12; struct _LSAPR_TRANSLATED_NAMES_EX *
0x18001dca4  call    ?LsaDbpLookupSidsAsDomainSids@@YAJKKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK@Z; LsaDbpLookupSidsAsDomainSids(ulong,ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *)
0x18001dca9  test    eax, eax
0x18001dcab  js      short loc_18001DC5B
0x18001dcad  sub     r14d, [rsi]
0x18001dcb0  add     [r15], r14d
0x18001dcb3  mov     r14, [rbp+arg_18]
0x18001dcb7  test    dil, 2
0x18001dcbb  jz      short loc_18001DCF7
0x18001dcbd  mov     r8, [r13+0]; struct _LSAPR_REFERENCED_DOMAIN_LIST *
0x18001dcc1  lea     rax, [rbp+arg_8]
0x18001dcc5  mov     ecx, dword ptr [rbp+Size]; Size
0x18001dcc8  mov     r9, r12; struct _LSAPR_TRANSLATED_NAMES_EX *
0x18001dccb  mov     [rsp+60h+var_28], rax; int *
0x18001dcd0  mov     rdx, r14; struct _LSAPR_SID **
0x18001dcd3  mov     byte ptr [rsp+60h+var_30], 1; unsigned __int8
0x18001dcd8  mov     [rsp+60h+var_38], r15; unsigned int *
0x18001dcdd  mov     [rsp+60h+var_40], rsi; unsigned int *
0x18001dce2  call    ?LsaDbpLookupSidsInGlobalCatalog@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK3EPEAJ@Z; LsaDbpLookupSidsInGlobalCatalog(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *,ulong *,uchar,long *)
0x18001dce7  test    eax, eax
0x18001dce9  js      loc_18001DC5B
0x18001dcef  mov     eax, [rbp+arg_8]
0x18001dcf2  test    eax, eax
0x18001dcf4  cmovs   ebx, eax
0x18001dcf7  test    dil, 20h
0x18001dcfb  jz      loc_18001DD82
0x18001dd01  mov     r14, [rbp+arg_20]
0x18001dd05  cmp     qword ptr [r14+10h], 0
0x18001dd0a  jnz     short loc_18001DD37
0x18001dd0c  xor     r8d, r8d
0x18001dd0f  lea     rdx, [rbp+var_10]
0x18001dd13  xor     ecx, ecx
0x18001dd15  call    cs:__imp_LsapDbLookupGetDomainInfo
0x18001dd1b  test    eax, eax
0x18001dd1d  js      loc_18001DC5B
0x18001dd23  mov     rax, [rbp+var_10]
0x18001dd27  movups  xmm0, xmmword ptr [rax]
0x18001dd2a  movdqu  xmmword ptr [r14], xmm0
0x18001dd2f  mov     rax, [rax+40h]
0x18001dd33  mov     [r14+10h], rax
0x18001dd37  mov     r9, [r13+0]
0x18001dd3b  lea     rax, [rbp+arg_8]
0x18001dd3f  mov     ecx, dword ptr [rbp+Size]
0x18001dd42  mov     r8, r14
0x18001dd45  mov     r14, [rbp+arg_18]
0x18001dd49  mov     [rsp+60h+var_20], rax
0x18001dd4e  mov     rdx, r14
0x18001dd51  mov     [rsp+60h+var_28], r15
0x18001dd56  mov     [rsp+60h+var_30], rsi
0x18001dd5b  mov     dword ptr [rsp+60h+var_38], 7
0x18001dd63  mov     [rsp+60h+var_40], r12
0x18001dd68  call    cs:__imp_LsapDbLookupSidsInPrimaryDomain
0x18001dd6e  test    eax, eax
0x18001dd70  js      loc_18001DC5B
0x18001dd76  mov     eax, [rbp+arg_8]
0x18001dd79  test    eax, eax
0x18001dd7b  jns     short loc_18001DD82
0x18001dd7d  test    ebx, ebx
0x18001dd7f  cmovns  ebx, eax
0x18001dd82  test    dil, 4
0x18001dd86  jz      short loc_18001DDC1
0x18001dd88  mov     r8, [r13+0]; struct _LSAPR_REFERENCED_DOMAIN_LIST *
0x18001dd8c  lea     rax, [rbp+arg_8]
0x18001dd90  mov     ecx, dword ptr [rbp+Size]; Size
0x18001dd93  mov     r9, r12; struct _LSAPR_TRANSLATED_NAMES_EX *
0x18001dd96  mov     [rsp+60h+var_30], rax; int *
0x18001dd9b  mov     rdx, r14; struct _LSAPR_SID **
0x18001dd9e  mov     [rsp+60h+var_38], r15; unsigned int *
0x18001dda3  mov     [rsp+60h+var_40], rsi; unsigned int *
0x18001dda8  call    ?LsaDbpLookupSidsInTrustedForests@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK3PEAJ@Z; LsaDbpLookupSidsInTrustedForests(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *,ulong *,long *)
0x18001ddad  test    eax, eax
0x18001ddaf  js      loc_18001DC5B
0x18001ddb5  mov     eax, [rbp+arg_8]
0x18001ddb8  test    eax, eax
0x18001ddba  jns     short loc_18001DDC1
0x18001ddbc  test    ebx, ebx
0x18001ddbe  cmovns  ebx, eax
0x18001ddc1  test    dil, 1
0x18001ddc5  jz      short loc_18001DE00
0x18001ddc7  mov     r8, [r13+0]
0x18001ddcb  lea     rax, [rbp+arg_8]
0x18001ddcf  mov     ecx, dword ptr [rbp+Size]
0x18001ddd2  mov     r9, r12
0x18001ddd5  mov     [rsp+60h+var_28], rax
0x18001ddda  mov     rdx, r14
0x18001dddd  mov     [rsp+60h+var_30], r15
0x18001dde2  mov     [rsp+60h+var_38], rsi
0x18001dde7  call    ?LsaDbpLookupSidsInTrustedDomains@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAJ@Z; LsaDbpLookupSidsInTrustedDomains(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,long *)
0x18001ddec  test    eax, eax
0x18001ddee  js      loc_18001DC5B
0x18001ddf4  mov     eax, [rbp+arg_8]
0x18001ddf7  test    eax, eax
0x18001ddf9  jns     short loc_18001DE00
0x18001ddfb  test    ebx, ebx
0x18001ddfd  cmovns  ebx, eax
0x18001de00  mov     eax, ebx
0x18001de02  mov     rbx, [rsp+60h+arg_10]
0x18001de0a  add     rsp, 60h
0x18001de0e  pop     r15
0x18001de10  pop     r14
0x18001de12  pop     r13
0x18001de14  pop     r12
0x18001de16  pop     rdi
0x18001de17  pop     rsi
0x18001de18  pop     rbp
0x18001de19  retn
```
