# LsaDbpDsFixupTrustByInfo(_DSNAME *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *,ulong,_SECURITY_DB_DELTA_TYPE,void *,_LUID,uchar,uchar)

- ea: `0x180013cbc`
- end: `0x180014350`
- name: `?LsaDbpDsFixupTrustByInfo@@YAJPEAU_DSNAME@@PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2@@KW4_SECURITY_DB_DELTA_TYPE@@PEAXU_LUID@@EE@Z`
- size: `1684`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800136d4`

## callees

- `0x180002234`
- `0x1800099b4`
- `0x18000af18`
- `0x18000b7c8`
- `0x18000bae8`
- `0x18000bf70`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fee8`
- `0x18001287c`
- `0x180012fa4`
- `0x180013cbc`
- `0x1800153e0`
- `0x1800345c0`
- `0x18003ad24`

## import_xrefs

- `LSASRV!LsapDbReleaseLockEx` at `0x180014308`
- `LSASRV!LsapDbReleaseLockEx` at `0x180014308`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180013d73`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180013d73`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180014074`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180014074`
- `LSASRV!LsapDbAcquireLockEx` at `0x180013df9`
- `LSASRV!LsapDbAcquireLockEx` at `0x180013df9`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180013e5f`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180014147`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18001423c`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180013e5f`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180014147`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18001423c`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800140cc`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800141af`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800142db`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800142ee`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800140cc`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800141af`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800142db`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800142ee`
- `LSASRV!LsapDbExpIsCacheValid` at `0x180014271`
- `LSASRV!LsapDbExpIsCacheValid` at `0x180014271`
- `SAMSRV!SamIQueryServerRole` at `0x180013d80`
- `SAMSRV!SamIQueryServerRole` at `0x180013d80`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x1800141d9`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x1800141d9`

## pseudocode

```c
__int64 __fastcall LsaDbpDsFixupTrustByInfo(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        void *a5,
        struct _LUID a6,
        int a7,
        char a8)
{
  int LockTrustedDomainList; // ebx
  char v9; // r12
  _QWORD *v13; // rcx
  const wchar_t *v14; // r9
  char v15; // r15
  __int64 v16; // r8
  __int64 AccountDomainHandle; // rax
  unsigned int v18; // eax
  bool v19; // di
  unsigned int v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // eax
  char v23; // r14
  unsigned int v24; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  __int128 v27; // xmm0
  unsigned int v28; // eax
  _QWORD *v29; // rcx
  void *v30; // rdi
  unsigned __int16 v31; // cx
  unsigned int inserted; // eax
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v34[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-40h] BYREF
  __int128 v36; // [rsp+50h] [rbp-30h] BYREF
  __int64 v37; // [rsp+60h] [rbp-20h]
  _DWORD v38[4]; // [rsp+68h] [rbp-18h] BYREF
  __int128 *p_Buf1; // [rsp+78h] [rbp-8h]
  unsigned int v40; // [rsp+D0h] [rbp+50h] BYREF
  char v41; // [rsp+D8h] [rbp+58h]

  v40 = a3;
  LockTrustedDomainList = 0;
  v37 = 0;
  v36 = 0;
  v41 = 0;
  v9 = 0;
  v13 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LODWORD(v14) = a1 + 56;
    if ( !a1 )
      v14 = L"<null>";
    WPP_SF_SqD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (_DWORD)v14, a2, a4);
    v13 = WPP_GLOBAL_Control;
  }
  v15 = a7;
  v16 = 1;
  if ( (_BYTE)a7 && (a4 == 1 || a4 == 7) )
  {
    a7 = 0;
    if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
      WPP_SF_(v13[2], 50, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    AccountDomainHandle = LsapGetAccountDomainHandle(v13);
    v18 = SamIQueryServerRole(AccountDomainHandle, &a7);
    LockTrustedDomainList = v18;
    v13 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v18);
      v13 = WPP_GLOBAL_Control;
    }
    if ( LockTrustedDomainList >= 0 && a7 == 3 )
    {
      if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
      {
        WPP_SF_(v13[2], 52, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
        v13 = WPP_GLOBAL_Control;
      }
      if ( DcInRootDomain )
      {
        LsapDbAcquireLockEx(2);
        v13 = WPP_GLOBAL_Control;
        v16 = 1;
        v9 = 1;
      }
      else
      {
        v16 = 1;
      }
      if ( (*(_BYTE *)(a2 + 40) & 2) == 0 || (unsigned int)(*(_DWORD *)(a2 + 44) - 1) > 1 )
      {
        if ( !v40 )
          goto LABEL_34;
        if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
        {
          WPP_SF_(v13[2], 55, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
          v13 = WPP_GLOBAL_Control;
          v16 = 1;
        }
        v40 = 0;
        v19 = 1;
        goto LABEL_29;
      }
      if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
      {
        WPP_SF_(v13[2], 53, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
        v13 = WPP_GLOBAL_Control;
      }
      if ( !v40 )
      {
        v19 = 0;
        LockTrustedDomainList = LsapDbExpAcquireWriteLockTrustedDomainList(v13);
        if ( LockTrustedDomainList >= 0 )
        {
          v41 = 1;
          LockTrustedDomainList = LsaDbpAllocatePosixOffsetTrustedDomainList(&v40);
          v19 = LockTrustedDomainList >= 0;
        }
        v13 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
            (unsigned int)LockTrustedDomainList,
            v40);
          v13 = WPP_GLOBAL_Control;
        }
        v16 = 1;
LABEL_29:
        if ( v19 )
        {
          v38[2] = 1;
          *((_QWORD *)&Buf1 + 1) = &v40;
          LODWORD(Buf1) = 4;
          p_Buf1 = &Buf1;
          v38[0] = 589958;
          v34[1] = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)v38;
          v34[0] = (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)1;
          v20 = LsaDbpDsWriteByDsName((struct _DSNAME *)a1, 0x43u, (struct _ATTRBLOCKSIMPLE *)v34);
          LockTrustedDomainList = v20;
          v13 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v20);
            v13 = WPP_GLOBAL_Control;
          }
          if ( LockTrustedDomainList < 0 )
            LockTrustedDomainList = 0;
        }
      }
    }
  }
LABEL_34:
  if ( a4 == 1 )
  {
    if ( !v15 )
      goto LABEL_89;
    if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
      WPP_SF_(v13[2], 57, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    if ( (int)LsapDbExpAcquireWriteLockTrustedDomainList(v13) < 0 )
      goto LABEL_88;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    if ( (unsigned __int8)LsapDbExpIsCacheValid(2) )
    {
      inserted = LsaDbpInsertTrustedDomainList((struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *)a2, v40);
      LockTrustedDomainList = inserted;
      v25 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, inserted);
        v25 = WPP_GLOBAL_Control;
      }
      if ( LockTrustedDomainList < 0 && (*((_BYTE *)v25 + 28) & 4) != 0 )
        WPP_SF_ZD(
          v25[2],
          60,
          (unsigned int)&WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
          a2 + 16,
          LockTrustedDomainList);
    }
    goto LABEL_87;
  }
  v21 = a4 - 3;
  if ( a4 == 3 )
  {
    v23 = a8;
    if ( !v15 && a8 )
      goto LABEL_69;
    v34[0] = 0;
    if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
      WPP_SF_(v13[2], 63, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(v13);
    if ( LockTrustedDomainList < 0 )
      goto LABEL_88;
    v24 = LsaDbpLookupNameTrustedDomainListEx((struct _LSAPR_UNICODE_STRING *)a2, v34);
    LockTrustedDomainList = v24;
    v25 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v24);
    if ( LockTrustedDomainList >= 0 )
    {
      Buf1 = *(_OWORD *)((char *)v34[0] + 104);
      LsapDbExpReleaseLockTrustedDomainList(v25);
      if ( memcmp_0(&Buf1, &LsapNullUuidValue, 0x10u) && memcmp_0(&Buf1, (const void *)(a1 + 8), 0x10u) )
      {
        v13 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
          v13 = WPP_GLOBAL_Control;
        }
        LockTrustedDomainList = -1073741771;
        goto LABEL_89;
      }
      v27 = *(_OWORD *)(a2 + 16);
      v37 = *(_QWORD *)(a2 + 32);
      v36 = v27;
      if ( (int)LsapDbExpAcquireWriteLockTrustedDomainList(v26) >= 0 )
      {
        v28 = LsaDbpDeleteTrustedDomainList((struct _LSAPR_TRUST_INFORMATION *)&v36);
        LockTrustedDomainList = v28;
        v29 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v28);
          v29 = WPP_GLOBAL_Control;
        }
        if ( LockTrustedDomainList < 0 && (*((_BYTE *)v29 + 28) & 4) != 0 )
          WPP_SF_ZD(
            v29[2],
            67,
            (unsigned int)&WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
            a2 + 16,
            LockTrustedDomainList);
        LsapDbExpReleaseLockTrustedDomainList(v29);
      }
LABEL_69:
      if ( (unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(v13, v21, v16) )
      {
        v30 = a5;
        if ( a5 )
        {
          if ( (unsigned __int8)LsapAdtAuditingEnabledHint(141, 8) && !v15 && !v23 )
            LockTrustedDomainList = LsaDbpAdtTrustedDomainRem(
                                      v31,
                                      (struct _UNICODE_STRING *)a2,
                                      *(void **)(a2 + 32),
                                      v30,
                                      &a6);
        }
      }
      goto LABEL_88;
    }
LABEL_87:
    LsapDbExpReleaseLockTrustedDomainList(v25);
    goto LABEL_88;
  }
  if ( a4 != 7 )
  {
    if ( (*((_BYTE *)v13 + 28) & 4) == 0 )
      goto LABEL_89;
    WPP_SF_d(v13[2], 68, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, a4);
    goto LABEL_88;
  }
  if ( v15 )
  {
    v22 = LsaDbpFixupTrustedDomainListEntry(
            *(void **)(a2 + 32),
            (struct _LSAPR_UNICODE_STRING *)a2,
            (struct _LSAPR_UNICODE_STRING *)(a2 + 16),
            (struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *)a2,
            &v40);
    LockTrustedDomainList = v22;
    v13 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v22);
      v13 = WPP_GLOBAL_Control;
    }
    if ( LockTrustedDomainList < 0 && (*((_BYTE *)v13 + 28) & 4) != 0 )
    {
      WPP_SF_ZD(
        v13[2],
        62,
        (unsigned int)&WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
        a2 + 16,
        LockTrustedDomainList);
LABEL_88:
      v13 = WPP_GLOBAL_Control;
    }
  }
LABEL_89:
  if ( v41 )
  {
    LsapDbExpReleaseLockTrustedDomainList(v13);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    LsapDbReleaseLockEx(2);
    v13 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
    WPP_SF_d(v13[2], 69, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, (unsigned int)LockTrustedDomainList);
  return (unsigned int)LockTrustedDomainList;
}

```

## disassembly

```asm
0x180013cbc  mov     [rsp-38h+arg_0], rbx
0x180013cc1  mov     [rsp-38h+arg_10], r8d
0x180013cc6  push    rbp
0x180013cc7  push    rsi
0x180013cc8  push    rdi
0x180013cc9  push    r12
0x180013ccb  push    r13
0x180013ccd  push    r14
0x180013ccf  push    r15
0x180013cd1  mov     rbp, rsp
0x180013cd4  sub     rsp, 80h
0x180013cdb  xor     eax, eax
0x180013cdd  xor     ebx, ebx
0x180013cdf  xorps   xmm0, xmm0
0x180013ce2  mov     [rbp+var_20], rax
0x180013ce6  movups  [rbp+var_30], xmm0
0x180013cea  mov     [rbp+arg_18], al
0x180013ced  xor     r12b, r12b
0x180013cf0  mov     r14d, r9d
0x180013cf3  mov     rsi, rdx
0x180013cf6  mov     r13, rcx
0x180013cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d00  lea     edi, [rbx+4]
0x180013d03  test    [rcx+1Ch], dil
0x180013d07  jz      short loc_180013D33
0x180013d09  lea     r9, [r13+38h]
0x180013d0d  test    r13, r13
0x180013d10  jnz     short loc_180013D19
0x180013d12  lea     r9, aNull; "<null>"
0x180013d19  mov     rcx, [rcx+10h]
0x180013d1d  mov     [rsp+80h+var_58], r14d
0x180013d22  mov     [rsp+80h+var_60], rsi
0x180013d27  call    WPP_SF_SqD
0x180013d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d33  mov     r15b, byte ptr [rbp+arg_30]
0x180013d37  mov     r8d, 1
0x180013d3d  test    r15b, r15b
0x180013d40  jz      loc_180013F3B
0x180013d46  cmp     r14d, r8d
0x180013d49  jz      short loc_180013D55
0x180013d4b  cmp     r14d, 7
0x180013d4f  jnz     loc_180013F3B
0x180013d55  mov     [rbp+arg_30], ebx
0x180013d58  test    [rcx+1Ch], dil
0x180013d5c  jz      short loc_180013D73
0x180013d5e  mov     rcx, [rcx+10h]
0x180013d62  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013d69  mov     edx, 32h ; '2'
0x180013d6e  call    WPP_SF_
0x180013d73  call    cs:__imp_LsapGetAccountDomainHandle
0x180013d79  mov     rcx, rax
0x180013d7c  lea     rdx, [rbp+arg_30]
0x180013d80  call    cs:__imp_SamIQueryServerRole
0x180013d86  mov     ebx, eax
0x180013d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d8f  test    [rcx+1Ch], dil
0x180013d93  jz      short loc_180013DB4
0x180013d95  mov     rcx, [rcx+10h]
0x180013d99  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013da0  mov     edx, 33h ; '3'
0x180013da5  mov     r9d, eax
0x180013da8  call    WPP_SF_d
0x180013dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180013db4  test    ebx, ebx
0x180013db6  js      loc_180013F3B
0x180013dbc  cmp     [rbp+arg_30], 3
0x180013dc0  jnz     loc_180013F3B
0x180013dc6  test    [rcx+1Ch], dil
0x180013dca  jz      short loc_180013DE8
0x180013dcc  mov     rcx, [rcx+10h]
0x180013dd0  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013dd7  mov     edx, 34h ; '4'
0x180013ddc  call    WPP_SF_
0x180013de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013de8  cmp     cs:?DcInRootDomain@@3EA, r12b; uchar DcInRootDomain
0x180013def  jz      short loc_180013E11
0x180013df1  mov     edx, 1
0x180013df6  lea     ecx, [rdx+1]
0x180013df9  call    cs:__imp_LsapDbAcquireLockEx
0x180013dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e06  mov     r8d, 1
0x180013e0c  mov     r12b, r8b
0x180013e0f  jmp     short loc_180013E17
0x180013e11  mov     r8d, 1
0x180013e17  test    byte ptr [rsi+28h], 2
0x180013e1b  jz      loc_180013F7B
0x180013e21  mov     eax, [rsi+2Ch]
0x180013e24  sub     eax, r8d
0x180013e27  cmp     eax, r8d
0x180013e2a  ja      loc_180013F7B
0x180013e30  test    [rcx+1Ch], dil
0x180013e34  jz      short loc_180013E52
0x180013e36  mov     rcx, [rcx+10h]
0x180013e3a  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013e41  mov     edx, 35h ; '5'
0x180013e46  call    WPP_SF_
0x180013e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e52  cmp     [rbp+arg_10], 0
0x180013e56  jnz     loc_180013F3B
0x180013e5c  xor     dil, dil
0x180013e5f  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x180013e65  mov     ebx, eax
0x180013e67  test    eax, eax
0x180013e69  js      short loc_180013E88
0x180013e6b  lea     rcx, [rbp+arg_10]; unsigned int *
0x180013e6f  mov     [rbp+arg_18], 1
0x180013e73  call    ?LsaDbpAllocatePosixOffsetTrustedDomainList@@YAJPEAK@Z; LsaDbpAllocatePosixOffsetTrustedDomainList(ulong *)
0x180013e78  test    eax, eax
0x180013e7a  movzx   edi, dil
0x180013e7e  mov     ebx, eax
0x180013e80  mov     eax, 1
0x180013e85  cmovns  edi, eax
0x180013e88  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e8f  test    byte ptr [rcx+1Ch], 4
0x180013e93  jz      short loc_180013EBB
0x180013e95  mov     eax, [rbp+arg_10]
0x180013e98  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013e9f  mov     rcx, [rcx+10h]
0x180013ea3  mov     edx, 36h ; '6'
0x180013ea8  mov     r9d, ebx
0x180013eab  mov     dword ptr [rsp+80h+var_60], eax
0x180013eaf  call    WPP_SF_dd
0x180013eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ebb  mov     r8d, 1
0x180013ec1  test    dil, dil
0x180013ec4  mov     edi, 4
0x180013ec9  jz      short loc_180013F3B
0x180013ecb  lea     rax, [rbp+arg_10]
0x180013ecf  mov     [rbp+var_10], r8d
0x180013ed3  mov     qword ptr [rbp+Buf1+8], rax
0x180013ed7  lea     r8, [rbp+var_50]; struct _ATTRBLOCKSIMPLE *
0x180013edb  lea     rax, [rbp+Buf1]
0x180013edf  mov     dword ptr [rbp+Buf1], edi
0x180013ee2  mov     [rbp+var_8], rax
0x180013ee6  lea     edx, [rdi+3Fh]; unsigned int
0x180013ee9  lea     rax, [rbp+var_18]
0x180013eed  mov     [rbp+var_18], 90086h
0x180013ef4  mov     rcx, r13; struct _DSNAME *
0x180013ef7  mov     [rbp+var_48], rax
0x180013efb  mov     [rbp+var_50], 1
0x180013f03  call    ?LsaDbpDsWriteByDsName@@YAJPEAU_DSNAME@@KPEAU_ATTRBLOCKSIMPLE@@@Z; LsaDbpDsWriteByDsName(_DSNAME *,ulong,_ATTRBLOCKSIMPLE *)
0x180013f08  mov     ebx, eax
0x180013f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f11  test    [rcx+1Ch], dil
0x180013f15  jz      short loc_180013F34
0x180013f17  mov     rcx, [rcx+10h]
0x180013f1b  lea     edx, [rdi+34h]
0x180013f1e  mov     r9d, eax
0x180013f21  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013f28  call    WPP_SF_d
0x180013f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f34  xor     eax, eax
0x180013f36  test    ebx, ebx
0x180013f38  cmovs   ebx, eax
0x180013f3b  mov     edx, r14d
0x180013f3e  sub     edx, 1
0x180013f41  jz      loc_180014218
0x180013f47  sub     edx, 2
0x180013f4a  jz      loc_18001403F
0x180013f50  cmp     edx, edi
0x180013f52  jz      short loc_180013FB8
0x180013f54  test    [rcx+1Ch], dil
0x180013f58  jz      loc_1800142E8
0x180013f5e  mov     rcx, [rcx+10h]
0x180013f62  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013f69  mov     edx, 44h ; 'D'
0x180013f6e  mov     r9d, r14d
0x180013f71  call    WPP_SF_d
0x180013f76  jmp     loc_1800142E1
0x180013f7b  cmp     [rbp+arg_10], 0
0x180013f7f  jz      short loc_180013F3B
0x180013f81  test    [rcx+1Ch], dil
0x180013f85  jz      short loc_180013FA9
0x180013f87  mov     rcx, [rcx+10h]
0x180013f8b  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013f92  mov     edx, 37h ; '7'
0x180013f97  call    WPP_SF_
0x180013f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fa3  mov     r8d, 1
0x180013fa9  mov     [rbp+arg_10], 0
0x180013fb0  mov     dil, r8b
0x180013fb3  jmp     loc_180013EC1
0x180013fb8  test    r15b, r15b
0x180013fbb  jz      loc_1800142E8
0x180013fc1  mov     rcx, [rsi+20h]; void *
0x180013fc5  lea     rax, [rbp+arg_10]
0x180013fc9  mov     r9, rsi; struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *
0x180013fcc  mov     [rsp+80h+var_60], rax; unsigned int *
0x180013fd1  lea     r8, [rsi+10h]; struct _LSAPR_UNICODE_STRING *
0x180013fd5  mov     rdx, rsi; struct _LSAPR_UNICODE_STRING *
0x180013fd8  call    ?LsaDbpFixupTrustedDomainListEntry@@YAJPEAXPEAU_LSAPR_UNICODE_STRING@@1PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2@@PEAK@Z; LsaDbpFixupTrustedDomainListEntry(void *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *,ulong *)
0x180013fdd  mov     ebx, eax
0x180013fdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fe6  test    byte ptr [rcx+1Ch], 4
0x180013fea  jz      short loc_18001400B
0x180013fec  mov     rcx, [rcx+10h]
0x180013ff0  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013ff7  mov     edx, 3Dh ; '='
0x180013ffc  mov     r9d, eax
0x180013fff  call    WPP_SF_d
0x180014004  mov     rcx, cs:WPP_GLOBAL_Control
0x18001400b  test    ebx, ebx
0x18001400d  jns     loc_1800142E8
0x180014013  test    byte ptr [rcx+1Ch], 4
0x180014017  jz      loc_1800142E8
0x18001401d  mov     rcx, [rcx+10h]
0x180014021  lea     r9, [rsi+10h]
0x180014025  mov     edx, 3Eh ; '>'
0x18001402a  mov     dword ptr [rsp+80h+var_60], ebx
0x18001402e  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180014035  call    WPP_SF_ZD
0x18001403a  jmp     loc_1800142E1
0x18001403f  mov     r14b, [rbp+arg_38]
0x180014043  test    r15b, r15b
0x180014046  jnz     short loc_180014051
0x180014048  test    r14b, r14b
0x18001404b  jnz     loc_1800141B5
0x180014051  mov     [rbp+var_50], 0
0x180014059  test    [rcx+1Ch], dil
0x18001405d  jz      short loc_180014074
0x18001405f  mov     rcx, [rcx+10h]
0x180014063  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x18001406a  mov     edx, 3Fh ; '?'
0x18001406f  call    WPP_SF_
0x180014074  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x18001407a  mov     ebx, eax
0x18001407c  test    eax, eax
0x18001407e  js      loc_1800142E1
0x180014084  lea     rdx, [rbp+var_50]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x180014088  mov     rcx, rsi; struct _LSAPR_UNICODE_STRING *
0x18001408b  call    ?LsaDbpLookupNameTrustedDomainListEx@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupNameTrustedDomainListEx(_LSAPR_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x180014090  mov     ebx, eax
0x180014092  mov     rcx, cs:WPP_GLOBAL_Control
0x180014099  test    [rcx+1Ch], dil
0x18001409d  jz      short loc_1800140B7
0x18001409f  mov     rcx, [rcx+10h]
0x1800140a3  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x1800140aa  mov     edx, 40h ; '@'
0x1800140af  mov     r9d, eax
0x1800140b2  call    WPP_SF_d
0x1800140b7  test    ebx, ebx
0x1800140b9  js      loc_1800142DB
0x1800140bf  mov     rax, [rbp+var_50]
0x1800140c3  movups  xmm0, xmmword ptr [rax+68h]
0x1800140c7  movdqu  [rbp+Buf1], xmm0
0x1800140cc  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x1800140d2  mov     r8d, 10h; Size
0x1800140d8  lea     rdx, ?LsapNullUuidValue@@3U_GUID@@A; Buf2
0x1800140df  lea     rcx, [rbp+Buf1]; Buf1
0x1800140e3  call    memcmp_0
0x1800140e8  test    eax, eax
0x1800140ea  jz      short loc_180014136
0x1800140ec  lea     rdx, [r13+8]; Buf2
0x1800140f0  mov     r8d, 10h; Size
0x1800140f6  lea     rcx, [rbp+Buf1]; Buf1
0x1800140fa  call    memcmp_0
0x1800140ff  test    eax, eax
0x180014101  jz      short loc_180014136
0x180014103  mov     rcx, cs:WPP_GLOBAL_Control
0x18001410a  test    [rcx+1Ch], dil
0x18001410e  jz      short loc_18001412C
0x180014110  mov     rcx, [rcx+10h]
0x180014114  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x18001411b  mov     edx, 41h ; 'A'
0x180014120  call    WPP_SF_
0x180014125  mov     rcx, cs:WPP_GLOBAL_Control
0x18001412c  mov     ebx, 0C0000035h
0x180014131  jmp     loc_1800142E8
0x180014136  movups  xmm0, xmmword ptr [rsi+10h]
0x18001413a  mov     rax, [rsi+20h]
0x18001413e  mov     [rbp+var_20], rax
0x180014142  movdqu  [rbp+var_30], xmm0
0x180014147  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x18001414d  test    eax, eax
0x18001414f  js      short loc_1800141B5
0x180014151  lea     rcx, [rbp+var_30]; struct _LSAPR_TRUST_INFORMATION *
0x180014155  call    ?LsaDbpDeleteTrustedDomainList@@YAJPEAU_LSAPR_TRUST_INFORMATION@@@Z; LsaDbpDeleteTrustedDomainList(_LSAPR_TRUST_INFORMATION *)
0x18001415a  mov     ebx, eax
0x18001415c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014163  test    byte ptr [rcx+1Ch], 4
0x180014167  jz      short loc_180014188
0x180014169  mov     rcx, [rcx+10h]
0x18001416d  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180014174  mov     edx, 42h ; 'B'
0x180014179  mov     r9d, eax
0x18001417c  call    WPP_SF_d
0x180014181  mov     rcx, cs:WPP_GLOBAL_Control
0x180014188  test    ebx, ebx
0x18001418a  jns     short loc_1800141AF
0x18001418c  test    byte ptr [rcx+1Ch], 4
0x180014190  jz      short loc_1800141AF
0x180014192  mov     rcx, [rcx+10h]
0x180014196  lea     r9, [rsi+10h]
0x18001419a  mov     edx, 43h ; 'C'
0x18001419f  mov     dword ptr [rsp+80h+var_60], ebx
0x1800141a3  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x1800141aa  call    WPP_SF_ZD
0x1800141af  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x1800141b5  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x1800141ba  test    al, al
  ... truncated ...
```
