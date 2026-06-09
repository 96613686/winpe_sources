# FTCache::AuditChanges(FTCache::TDO_ENTRY const *,FTCache::TDO_ENTRY const *)

- ea: `0x180020bc8`
- end: `0x18002159e`
- name: `?AuditChanges@FTCache@@AEAAXPEBUTDO_ENTRY@1@0@Z`
- size: `2518`
- prototype: `void(FTCache *__hidden this, const struct FTCache::TDO_ENTRY *, const struct FTCache::TDO_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028510`

## callees

- `0x180002234`
- `0x18000fd18`
- `0x18000fd40`
- `0x180020bc8`
- `0x1800221cc`
- `0x18002b63c`
- `0x18002b68c`
- `0x180034770`
- `0x180034a5c`
- `0x180034e80`
- `0x18003b010`

## import_xrefs

- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180020db7`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180020ea1`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x1800213dc`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180020db7`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180020ea1`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x1800213dc`
- `ntdll!RtlEqualUnicodeString` at `0x180021100`
- `ntdll!RtlEqualUnicodeString` at `0x18002113e`
- `ntdll!RtlEqualUnicodeString` at `0x180021100`
- `ntdll!RtlEqualUnicodeString` at `0x18002113e`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180020c6c`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180020c6c`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x180020c36`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x180020c36`

## pseudocode

```c
void __fastcall FTCache::AuditChanges(
        FTCache *this,
        const struct FTCache::TDO_ENTRY *a2,
        const struct FTCache::TDO_ENTRY *a3)
{
  const struct FTCache::TDO_ENTRY *v3; // rbx
  char v5; // si
  NTSTATUS v6; // eax
  char *v7; // rdi
  char *v8; // rax
  char v9; // r13
  __int64 v10; // r10
  _QWORD *mm; // rax
  _QWORD *v12; // rsi
  char v13; // r8
  FTCache::TLN_ENTRY **v14; // rdx
  FTCache::TLN_ENTRY *v15; // rcx
  int v16; // eax
  unsigned int v17; // r12d
  FTCache::TLN_ENTRY **v18; // r14
  unsigned int v19; // eax
  int v20; // eax
  const UNICODE_STRING *String2; // r12
  unsigned int v22; // eax
  int v23; // eax
  __int64 v24; // r8
  char v25; // si
  struct _UNICODE_STRING *v26; // r12
  FTCache::TLN_ENTRY *v27; // rcx
  unsigned int v28; // eax
  int v29; // eax
  __int64 *k; // rdi
  char v31; // r14
  struct _UNICODE_STRING *v32; // r12
  FTCache::TLN_ENTRY *v33; // rcx
  unsigned int v34; // eax
  int v35; // eax
  __int64 *m; // rdi
  _QWORD **v37; // rcx
  _QWORD *n; // rax
  _QWORD *v39; // rsi
  int v40; // eax
  __int64 *ii; // rdi
  const UNICODE_STRING *v42; // rdx
  const UNICODE_STRING *v43; // rcx
  int v44; // eax
  __int64 v45; // r8
  int v46; // eax
  _DWORD *jj; // rdi
  int v48; // eax
  _DWORD *kk; // rdi
  _QWORD *v50; // rcx
  __int64 v51; // rdx
  char v52; // r14
  __int64 (__usercall *v53)@<rax>(struct _UNICODE_STRING *@<rcx>, void *@<rdx>, struct _LUID *@<r8>, enum LSA_FOREST_TRUST_RECORD_TYPE@<r9d>, unsigned int, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *); // r12
  __int64 **v54; // r15
  __int64 *i; // rdi
  char v56; // al
  FTCache::TLN_ENTRY **v57; // rsi
  int v58; // eax
  char v59; // r13
  unsigned int v60; // eax
  __int64 *v61; // rdi
  unsigned int *j; // rdi
  unsigned int v63; // [rsp+20h] [rbp-50h]
  char v64; // [rsp+B0h] [rbp+40h]
  LUID LocallyUniqueId; // [rsp+B8h] [rbp+48h] BYREF
  FTCache::TLN_ENTRY **v66; // [rsp+C8h] [rbp+58h]

  LocallyUniqueId = 0;
  v3 = a3;
  if ( a2 )
  {
    if ( *((_BYTE *)a2 + 92) )
      return;
    if ( !a3 )
      goto LABEL_7;
  }
  else if ( !a3 )
  {
    return;
  }
  if ( *((_BYTE *)a3 + 92) )
    return;
LABEL_7:
  v5 = 0;
  v64 = 0;
  if ( !(unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(this, a2, a3)
    || (v64 = LsapAdtAuditingEnabledHint(141, 8), (v5 = v64) == 0) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  }
  v6 = NtAllocateLocallyUniqueId(&LocallyUniqueId);
  if ( v6 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        237,
        &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
        (unsigned int)v6);
    return;
  }
  if ( !a2 )
  {
    if ( v3 )
    {
      v52 = 1;
      goto LABEL_129;
    }
LABEL_128:
    v52 = 0;
    v3 = a2;
LABEL_129:
    v53 = LsaDbpAdtTrustedForestInfoEntryAdd;
    v54 = (__int64 **)((char *)v3 + 24);
    if ( !v52 )
      v53 = LsaDbpAdtTrustedForestInfoEntryRem;
    for ( i = *v54; i != (__int64 *)v54; i = (__int64 *)*i )
    {
      v56 = *((_BYTE *)i + 40);
      v57 = (FTCache::TLN_ENTRY **)(i + 7);
      if ( v56 || !*v57 )
      {
        if ( v52 && !v56 )
        {
          if ( *v57 )
            LOBYTE(v58) = FTCache::TLN_ENTRY::Flags(*v57);
          else
            v58 = *((_DWORD *)i + 18);
          if ( (v58 & 1) != 0
            && (SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)LSA_FOREST_CLAIMED_NEW_TLN, L"uu", i[8], v3)
              & 0x80000000) != 0 )
          {
            return;
          }
        }
        if ( v64 )
        {
          v59 = *((_BYTE *)i + 40);
          if ( v59 || !*v57 )
            v60 = *((_DWORD *)i + 18);
          else
            v60 = FTCache::TLN_ENTRY::Flags(*v57);
          v48 = ((__int64 (__fastcall *)(const struct FTCache::TDO_ENTRY *, _QWORD, LUID *, bool, unsigned int, __int64, _QWORD, _QWORD, _QWORD))v53)(
                  v3,
                  *((_QWORD *)v3 + 2),
                  &LocallyUniqueId,
                  v59 != 0,
                  v60,
                  i[8],
                  0,
                  0,
                  0);
          if ( v48 < 0 )
          {
            v50 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              return;
            v51 = 238;
            goto LABEL_164;
          }
        }
      }
    }
    if ( !v64 )
      return;
    v61 = (__int64 *)*((_QWORD *)v3 + 5);
    if ( v61 == (__int64 *)((char *)v3 + 40) )
    {
LABEL_153:
      for ( j = (unsigned int *)*((_QWORD *)v3 + 9); ; j = *(unsigned int **)j )
      {
        if ( j == (unsigned int *)((char *)v3 + 72) )
          return;
        v48 = ((__int64 (__fastcall *)(const struct FTCache::TDO_ENTRY *, _QWORD, LUID *, _QWORD, unsigned int, _QWORD, _QWORD, _QWORD, _QWORD))v53)(
                v3,
                *((_QWORD *)v3 + 2),
                &LocallyUniqueId,
                j[6],
                j[12],
                0,
                0,
                0,
                0);
        if ( v48 < 0 )
          break;
      }
      v50 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return;
      v51 = 240;
    }
    else
    {
      while ( 1 )
      {
        v48 = ((__int64 (__fastcall *)(const struct FTCache::TDO_ENTRY *, _QWORD, LUID *, __int64, _DWORD, _QWORD, __int64, __int64, _QWORD))v53)(
                v3,
                *((_QWORD *)v3 + 2),
                &LocallyUniqueId,
                2,
                *((_DWORD *)v61 + 32),
                0,
                v61[14],
                v61[15],
                *(_QWORD *)v61[13]);
        if ( v48 < 0 )
          break;
        v61 = (__int64 *)*v61;
        if ( v61 == (__int64 *)((char *)v3 + 40) )
          goto LABEL_153;
      }
      v50 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return;
      v51 = 239;
    }
LABEL_164:
    WPP_SF_Dq(v50[2], v51, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (unsigned int)v48);
    return;
  }
  if ( !v3 )
    goto LABEL_128;
  v7 = (char *)*((_QWORD *)v3 + 3);
  if ( v7 == (char *)v3 + 24 )
  {
LABEL_70:
    if ( !v5 )
      return;
    for ( k = (__int64 *)*((_QWORD *)a2 + 3); k != (__int64 *)((char *)a2 + 24); k = (__int64 *)*k )
    {
      v31 = *((_BYTE *)k + 40);
      if ( v31 || !k[7] )
      {
        if ( *((_DWORD *)k + 11) == -1 )
        {
          *((_DWORD *)k + 11) = 0;
        }
        else
        {
          v32 = (struct _UNICODE_STRING *)k[8];
          if ( v31 || (v33 = (FTCache::TLN_ENTRY *)k[7]) == 0 )
            v34 = *((_DWORD *)k + 18);
          else
            v34 = FTCache::TLN_ENTRY::Flags(v33);
          v35 = LsaDbpAdtTrustedForestInfoEntryRem(
                  (struct _UNICODE_STRING *)v3,
                  *((void **)v3 + 2),
                  &LocallyUniqueId,
                  (enum LSA_FOREST_TRUST_RECORD_TYPE)(v31 != 0),
                  v34,
                  v32,
                  0,
                  0,
                  0);
          if ( v35 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v63 = (unsigned int)k;
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              243,
              &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
              (unsigned int)v35);
          }
        }
      }
    }
    for ( m = (__int64 *)*((_QWORD *)v3 + 5); m != (__int64 *)((char *)v3 + 40); m = (__int64 *)*m )
    {
      v37 = (_QWORD **)(m[13] + 16);
      for ( n = *v37; ; n = (_QWORD *)*n )
      {
        if ( n == v37 )
        {
          v40 = LsaDbpAdtTrustedForestInfoEntryAdd(
                  (struct _UNICODE_STRING *)v3,
                  *((void **)v3 + 2),
                  &LocallyUniqueId,
                  ForestTrustDomainInfo,
                  *((_DWORD *)m + 32),
                  0,
                  (struct _UNICODE_STRING *)m[14],
                  (struct _UNICODE_STRING *)m[15],
                  (void *)m[10]);
          if ( v40 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v63 = (unsigned int)m;
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              245,
              &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
              (unsigned int)v40);
          }
          goto LABEL_93;
        }
        v39 = n - 2;
        if ( (const struct FTCache::TDO_ENTRY *)n[9] == a2 )
          break;
      }
      if ( *((_DWORD *)v39 + 32) != *((_DWORD *)m + 32)
        || !RtlEqualUnicodeString((PCUNICODE_STRING)v39[14], (PCUNICODE_STRING)m[14], 1u)
        || (v42 = (const UNICODE_STRING *)m[15], v43 = (const UNICODE_STRING *)v39[15], (v43 == 0) != (v42 == 0))
        || v43 && v42 && !RtlEqualUnicodeString(v43, v42, 1u) )
      {
        v44 = LsaDbpAdtTrustedForestInfoEntryMod(
                (struct _UNICODE_STRING *)v3,
                *((void **)v3 + 2),
                &LocallyUniqueId,
                ForestTrustDomainInfo,
                v63,
                0,
                (PCUNICODE_STRING)v39[14],
                (PCUNICODE_STRING)v39[15],
                (void *)v39[10],
                *((_DWORD *)m + 32),
                0,
                (PCUNICODE_STRING)m[14],
                (PCUNICODE_STRING)m[15],
                (PSID)m[10]);
        if ( v44 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v63 = (unsigned int)v39;
          WPP_SF_Dqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 244, v45, (unsigned int)v44);
        }
      }
      *((_DWORD *)v39 + 18) = -1;
LABEL_93:
      ;
    }
    for ( ii = (__int64 *)*((_QWORD *)a2 + 5); ii != (__int64 *)((char *)a2 + 40); ii = (__int64 *)*ii )
    {
      if ( *((_DWORD *)ii + 18) == -1 )
      {
        *((_DWORD *)ii + 18) = 0;
      }
      else
      {
        v46 = LsaDbpAdtTrustedForestInfoEntryRem(
                (struct _UNICODE_STRING *)v3,
                *((void **)v3 + 2),
                &LocallyUniqueId,
                ForestTrustDomainInfo,
                *((_DWORD *)ii + 32),
                0,
                (struct _UNICODE_STRING *)ii[14],
                (struct _UNICODE_STRING *)ii[15],
                (void *)ii[10]);
        if ( v46 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_Dq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            246,
            &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
            (unsigned int)v46);
      }
    }
    for ( jj = (_DWORD *)*((_QWORD *)a2 + 9); ; jj = *(_DWORD **)jj )
    {
      if ( jj == (_DWORD *)((char *)a2 + 72) )
      {
        for ( kk = (_DWORD *)*((_QWORD *)v3 + 9); kk != (_DWORD *)((char *)v3 + 72); kk = *(_DWORD **)kk )
        {
          v48 = LsaDbpAdtTrustedForestInfoEntryAdd(
                  (struct _UNICODE_STRING *)v3,
                  *((void **)v3 + 2),
                  &LocallyUniqueId,
                  (enum LSA_FOREST_TRUST_RECORD_TYPE)kk[6],
                  kk[12],
                  0,
                  0,
                  0,
                  0);
          if ( v48 < 0 )
          {
            v50 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              return;
            v51 = 248;
            goto LABEL_164;
          }
        }
        return;
      }
      v48 = LsaDbpAdtTrustedForestInfoEntryRem(
              (struct _UNICODE_STRING *)a2,
              *((void **)a2 + 2),
              &LocallyUniqueId,
              (enum LSA_FOREST_TRUST_RECORD_TYPE)jj[6],
              jj[12],
              0,
              0,
              0,
              0);
      if ( v48 < 0 )
        break;
    }
    v50 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return;
    v51 = 247;
    goto LABEL_164;
  }
  v8 = (char *)v3 + 24;
  while ( 1 )
  {
    v9 = v7[40];
    if ( v9 || !*((_QWORD *)v7 + 7) )
      break;
LABEL_69:
    v7 = *(char **)v7;
    if ( v7 == v8 )
      goto LABEL_70;
  }
  v10 = *((_QWORD *)v7 + 8);
  for ( mm = *(_QWORD **)(v10 + 24); ; mm = (_QWORD *)*mm )
  {
    if ( mm == (_QWORD *)(v10 + 24) )
    {
      if ( v9
        || ((v15 = (FTCache::TLN_ENTRY *)*((_QWORD *)v7 + 7)) == 0
          ? (v16 = *((_DWORD *)v7 + 18))
          : (LOBYTE(v16) = FTCache::TLN_ENTRY::Flags(v15), v10 = *((_QWORD *)v7 + 8)),
            (v16 & 1) == 0
         || (SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)LSA_FOREST_CLAIMED_NEW_TLN, L"uu", v10, v3) & 0x80000000) == 0) )
      {
        v5 = v64;
        if ( v64 )
        {
          v25 = v7[40];
          v26 = (struct _UNICODE_STRING *)*((_QWORD *)v7 + 8);
          if ( v25 || (v27 = (FTCache::TLN_ENTRY *)*((_QWORD *)v7 + 7)) == 0 )
            v28 = *((_DWORD *)v7 + 18);
          else
            v28 = FTCache::TLN_ENTRY::Flags(v27);
          v29 = LsaDbpAdtTrustedForestInfoEntryAdd(
                  (struct _UNICODE_STRING *)v3,
                  *((void **)v3 + 2),
                  &LocallyUniqueId,
                  (enum LSA_FOREST_TRUST_RECORD_TYPE)(v25 != 0),
                  v28,
                  v26,
                  0,
                  0,
                  0);
          if ( v29 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v63 = (unsigned int)v7;
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              242,
              &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
              (unsigned int)v29);
          }
          goto LABEL_67;
        }
        goto LABEL_68;
      }
      return;
    }
    v12 = mm - 2;
    if ( (const struct FTCache::TDO_ENTRY *)mm[4] == a2 )
    {
      v13 = *((_BYTE *)v12 + 40);
      v14 = (FTCache::TLN_ENTRY **)(v12 + 7);
      v66 = (FTCache::TLN_ENTRY **)(v12 + 7);
      if ( v13 )
      {
        v66 = (FTCache::TLN_ENTRY **)(v12 + 7);
      }
      else if ( *v14 )
      {
        continue;
      }
      if ( v9 == v13 )
        break;
    }
  }
  if ( v13 || !*v14 )
    v17 = *((_DWORD *)v12 + 18);
  else
    v17 = FTCache::TLN_ENTRY::Flags(*v14);
  v18 = (FTCache::TLN_ENTRY **)(v7 + 56);
  if ( v9 || !*v18 )
    v19 = *((_DWORD *)v7 + 18);
  else
    v19 = FTCache::TLN_ENTRY::Flags(*v18);
  if ( v17 == v19 )
    goto LABEL_55;
  if ( *((_BYTE *)v12 + 40)
    || (!*v66 ? (v20 = *((_DWORD *)v12 + 18)) : (LOBYTE(v20) = FTCache::TLN_ENTRY::Flags(*v66)),
        (v20 & 1) == 0
     || (SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)LSA_FOREST_CLAIMED_NEW_TLN, L"uu", *((_QWORD *)v7 + 8), v3)
       & 0x80000000) == 0) )
  {
    if ( v64 )
    {
      String2 = (const UNICODE_STRING *)*((_QWORD *)v7 + 8);
      if ( v7[40] || !*v18 )
        v22 = *((_DWORD *)v7 + 18);
      else
        v22 = FTCache::TLN_ENTRY::Flags(*v18);
      v23 = LsaDbpAdtTrustedForestInfoEntryMod(
              (struct _UNICODE_STRING *)v3,
              *((void **)v3 + 2),
              &LocallyUniqueId,
              (enum LSA_FOREST_TRUST_RECORD_TYPE)(*((_BYTE *)v12 + 40) != 0),
              v63,
              (struct _UNICODE_STRING *)v12[8],
              0,
              0,
              0,
              v22,
              String2,
              0,
              0,
              0);
      if ( v23 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v63 = (unsigned int)v12;
        WPP_SF_Dqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 241, v24, (unsigned int)v23);
      }
    }
LABEL_55:
    *((_DWORD *)v12 + 11) = -1;
LABEL_67:
    v5 = v64;
LABEL_68:
    v8 = (char *)v3 + 24;
    goto LABEL_69;
  }
}

```

## disassembly

```asm
0x180020bc8  mov     [rsp-38h+arg_10], rbx
0x180020bcd  mov     [rsp-38h+arg_0], rcx
0x180020bd2  push    rbp
0x180020bd3  push    rsi
0x180020bd4  push    rdi
0x180020bd5  push    r12
0x180020bd7  push    r13
0x180020bd9  push    r14
0x180020bdb  push    r15
0x180020bdd  mov     rbp, rsp
0x180020be0  sub     rsp, 70h
0x180020be4  mov     qword ptr [rbp+LocallyUniqueId.LowPart], 0
0x180020bec  mov     rbx, r8
0x180020bef  mov     r15, rdx
0x180020bf2  test    rdx, rdx
0x180020bf5  jnz     short loc_180020C02
0x180020bf7  test    rbx, rbx
0x180020bfa  jz      loc_180021586
0x180020c00  jmp     short loc_180020C11
0x180020c02  cmp     byte ptr [rdx+5Ch], 0
0x180020c06  jnz     loc_180021586
0x180020c0c  test    rbx, rbx
0x180020c0f  jz      short loc_180020C1C
0x180020c11  cmp     byte ptr [r8+5Ch], 0
0x180020c16  jnz     loc_180021586
0x180020c1c  xor     sil, sil
0x180020c1f  mov     byte ptr [rbp+arg_0], sil
0x180020c23  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x180020c28  test    al, al
0x180020c2a  jz      short loc_180020C46
0x180020c2c  mov     edx, 8
0x180020c31  mov     ecx, 8Dh
0x180020c36  call    cs:__imp_LsapAdtAuditingEnabledHint
0x180020c3c  mov     byte ptr [rbp+arg_0], al
0x180020c3f  mov     sil, al
0x180020c42  test    al, al
0x180020c44  jnz     short loc_180020C68
0x180020c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c4d  test    byte ptr [rcx+1Ch], 8
0x180020c51  jz      short loc_180020C68
0x180020c53  mov     rcx, [rcx+10h]
0x180020c57  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180020c5e  mov     edx, 0ECh
0x180020c63  call    WPP_SF_
0x180020c68  lea     rcx, [rbp+LocallyUniqueId]; LocallyUniqueId
0x180020c6c  call    cs:__imp_NtAllocateLocallyUniqueId
0x180020c72  test    eax, eax
0x180020c74  jns     short loc_180020CA4
0x180020c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c7d  test    byte ptr [rcx+1Ch], 8
0x180020c81  jz      loc_180021586
0x180020c87  mov     rcx, [rcx+10h]
0x180020c8b  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180020c92  mov     edx, 0EDh
0x180020c97  mov     r9d, eax
0x180020c9a  call    WPP_SF_d
0x180020c9f  jmp     loc_180021586
0x180020ca4  test    r15, r15
0x180020ca7  jz      loc_180021362
0x180020cad  test    rbx, rbx
0x180020cb0  jz      loc_18002136C
0x180020cb6  lea     r14, [rbx+18h]
0x180020cba  mov     rdi, [r14]
0x180020cbd  cmp     rdi, r14
0x180020cc0  jz      loc_180020F5C
0x180020cc6  lea     rax, [rbx+18h]
0x180020cca  mov     r13b, [rdi+28h]
0x180020cce  test    r13b, r13b
0x180020cd1  jnz     short loc_180020CDE
0x180020cd3  cmp     qword ptr [rdi+38h], 0
0x180020cd8  jnz     loc_180020F50
0x180020cde  mov     r10, [rdi+40h]
0x180020ce2  lea     rcx, [r10+18h]
0x180020ce6  mov     rax, [rcx]
0x180020ce9  jmp     short loc_180020D1A
0x180020ceb  lea     rsi, [rax-10h]
0x180020cef  cmp     [rsi+30h], r15
0x180020cf3  jnz     short loc_180020D17
0x180020cf5  mov     r8b, [rsi+28h]
0x180020cf9  lea     rdx, [rsi+38h]
0x180020cfd  mov     [rbp+arg_18], rdx
0x180020d01  test    r8b, r8b
0x180020d04  jnz     short loc_180020D0E
0x180020d06  cmp     qword ptr [rdx], 0
0x180020d0a  jnz     short loc_180020D17
0x180020d0c  jmp     short loc_180020D12
0x180020d0e  mov     [rbp+arg_18], rdx
0x180020d12  cmp     r13b, r8b
0x180020d15  jz      short loc_180020D43
0x180020d17  mov     rax, [rax]
0x180020d1a  cmp     rax, rcx
0x180020d1d  jnz     short loc_180020CEB
0x180020d1f  test    r13b, r13b
0x180020d22  jnz     loc_180020EAF
0x180020d28  mov     rcx, [rdi+38h]; this
0x180020d2c  test    rcx, rcx
0x180020d2f  jz      loc_180020E86
0x180020d35  call    ?Flags@TLN_ENTRY@FTCache@@QEAAKXZ; FTCache::TLN_ENTRY::Flags(void)
0x180020d3a  mov     r10, [rdi+40h]
0x180020d3e  jmp     loc_180020E89
0x180020d43  test    r8b, r8b
0x180020d46  jnz     short loc_180020D5A
0x180020d48  mov     rcx, [rdx]; this
0x180020d4b  test    rcx, rcx
0x180020d4e  jz      short loc_180020D5A
0x180020d50  call    ?Flags@TLN_ENTRY@FTCache@@QEAAKXZ; FTCache::TLN_ENTRY::Flags(void)
0x180020d55  mov     r12d, eax
0x180020d58  jmp     short loc_180020D5E
0x180020d5a  mov     r12d, [rsi+48h]
0x180020d5e  lea     r14, [rdi+38h]
0x180020d62  test    r13b, r13b
0x180020d65  jnz     short loc_180020D76
0x180020d67  mov     rcx, [r14]; this
0x180020d6a  test    rcx, rcx
0x180020d6d  jz      short loc_180020D76
0x180020d6f  call    ?Flags@TLN_ENTRY@FTCache@@QEAAKXZ; FTCache::TLN_ENTRY::Flags(void)
0x180020d74  jmp     short loc_180020D79
0x180020d76  mov     eax, [rdi+48h]
0x180020d79  cmp     r12d, eax
0x180020d7c  jz      loc_180020E7A
0x180020d82  cmp     byte ptr [rsi+28h], 0
0x180020d86  jnz     short loc_180020DC5
0x180020d88  mov     rcx, [rbp+arg_18]
0x180020d8c  mov     rcx, [rcx]; this
0x180020d8f  test    rcx, rcx
0x180020d92  jz      short loc_180020D9B
0x180020d94  call    ?Flags@TLN_ENTRY@FTCache@@QEAAKXZ; FTCache::TLN_ENTRY::Flags(void)
0x180020d99  jmp     short loc_180020D9E
0x180020d9b  mov     eax, [rsi+48h]
0x180020d9e  test    al, 1
0x180020da0  jz      short loc_180020DC5
0x180020da2  mov     r8, [rdi+40h]
0x180020da6  lea     rdx, aUu; "uu"
0x180020dad  mov     r9, rbx
0x180020db0  lea     rcx, LSA_FOREST_CLAIMED_NEW_TLN
0x180020db7  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180020dbd  test    eax, eax
0x180020dbf  js      loc_180021586
0x180020dc5  cmp     byte ptr [rbp+arg_0], 0
0x180020dc9  jz      loc_180020E7A
0x180020dcf  cmp     byte ptr [rdi+28h], 0
0x180020dd3  mov     r12, [rdi+40h]
0x180020dd7  jnz     short loc_180020DE8
0x180020dd9  mov     rcx, [r14]; this
0x180020ddc  test    rcx, rcx
0x180020ddf  jz      short loc_180020DE8
0x180020de1  call    ?Flags@TLN_ENTRY@FTCache@@QEAAKXZ; FTCache::TLN_ENTRY::Flags(void)
0x180020de6  jmp     short loc_180020DEB
0x180020de8  mov     eax, [rdi+48h]
0x180020deb  mov     rdx, [rbx+10h]; void *
0x180020def  lea     r8, [rbp+LocallyUniqueId]; struct _LUID *
0x180020df3  mov     [rsp+70h+Sid2], 0; Sid2
0x180020dfc  xor     r9d, r9d
0x180020dff  cmp     [rsi+28h], r9b
0x180020e03  mov     rcx, rbx; struct _UNICODE_STRING *
0x180020e06  mov     [rsp+70h+var_10], 0; PCUNICODE_STRING
0x180020e0f  mov     [rsp+70h+var_18], 0; PCUNICODE_STRING
0x180020e18  setnz   r9b; enum LSA_FOREST_TRUST_RECORD_TYPE
0x180020e1c  mov     [rsp+70h+String2], r12; String2
0x180020e21  mov     [rsp+70h+var_28], eax; unsigned int
0x180020e25  mov     rax, [rsi+40h]
0x180020e29  mov     [rsp+70h+var_30], 0; void *
0x180020e32  mov     [rsp+70h+var_38], 0; PCUNICODE_STRING
0x180020e3b  mov     [rsp+70h+var_40], 0; PCUNICODE_STRING
0x180020e44  mov     [rsp+70h+var_48], rax; struct _UNICODE_STRING *
0x180020e49  call    ?LsaDbpAdtTrustedForestInfoEntryMod@@YAJPEAU_UNICODE_STRING@@PEAXPEAU_LUID@@W4LSA_FOREST_TRUST_RECORD_TYPE@@K0001K0001@Z; LsaDbpAdtTrustedForestInfoEntryMod(_UNICODE_STRING *,void *,_LUID *,LSA_FOREST_TRUST_RECORD_TYPE,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *)
0x180020e4e  test    eax, eax
0x180020e50  jns     short loc_180020E7A
0x180020e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e59  test    byte ptr [rcx+1Ch], 8
0x180020e5d  jz      short loc_180020E7A
0x180020e5f  mov     rcx, [rcx+10h]
0x180020e63  mov     edx, 0F1h
0x180020e68  mov     [rsp+70h+var_48], rdi
0x180020e6d  mov     r9d, eax
0x180020e70  mov     qword ptr [rsp+70h+var_50], rsi
0x180020e75  call    WPP_SF_Dqq
0x180020e7a  mov     dword ptr [rsi+2Ch], 0FFFFFFFFh
0x180020e81  jmp     loc_180020F48
0x180020e86  mov     eax, [rdi+48h]
0x180020e89  test    al, 1
0x180020e8b  jz      short loc_180020EAF
0x180020e8d  mov     r9, rbx
0x180020e90  lea     rdx, aUu; "uu"
0x180020e97  mov     r8, r10
0x180020e9a  lea     rcx, LSA_FOREST_CLAIMED_NEW_TLN
0x180020ea1  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180020ea7  test    eax, eax
0x180020ea9  js      loc_180021586
0x180020eaf  mov     sil, byte ptr [rbp+arg_0]
0x180020eb3  test    sil, sil
0x180020eb6  jz      loc_180020F4C
0x180020ebc  mov     sil, [rdi+28h]
0x180020ec0  mov     r12, [rdi+40h]
0x180020ec4  test    sil, sil
0x180020ec7  jnz     short loc_180020ED9
0x180020ec9  mov     rcx, [rdi+38h]; this
0x180020ecd  test    rcx, rcx
0x180020ed0  jz      short loc_180020ED9
0x180020ed2  call    ?Flags@TLN_ENTRY@FTCache@@QEAAKXZ; FTCache::TLN_ENTRY::Flags(void)
0x180020ed7  jmp     short loc_180020EDC
0x180020ed9  mov     eax, [rdi+48h]
0x180020edc  mov     rdx, [rbx+10h]; void *
0x180020ee0  lea     r8, [rbp+LocallyUniqueId]; struct _LUID *
0x180020ee4  mov     [rsp+70h+var_30], 0; void *
0x180020eed  xor     r9d, r9d
0x180020ef0  mov     [rsp+70h+var_38], 0; struct _UNICODE_STRING *
0x180020ef9  test    sil, sil
0x180020efc  mov     [rsp+70h+var_40], 0; struct _UNICODE_STRING *
0x180020f05  mov     rcx, rbx; struct _UNICODE_STRING *
0x180020f08  setnz   r9b; enum LSA_FOREST_TRUST_RECORD_TYPE
0x180020f0c  mov     [rsp+70h+var_48], r12; struct _UNICODE_STRING *
0x180020f11  mov     [rsp+70h+var_50], eax; unsigned int
0x180020f15  call    ?LsaDbpAdtTrustedForestInfoEntryAdd@@YAJPEAU_UNICODE_STRING@@PEAXPEAU_LUID@@W4LSA_FOREST_TRUST_RECORD_TYPE@@K0001@Z; LsaDbpAdtTrustedForestInfoEntryAdd(_UNICODE_STRING *,void *,_LUID *,LSA_FOREST_TRUST_RECORD_TYPE,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *)
0x180020f1a  test    eax, eax
0x180020f1c  jns     short loc_180020F48
0x180020f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f25  test    byte ptr [rcx+1Ch], 8
0x180020f29  jz      short loc_180020F48
0x180020f2b  mov     rcx, [rcx+10h]
0x180020f2f  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180020f36  mov     edx, 0F2h
0x180020f3b  mov     qword ptr [rsp+70h+var_50], rdi
0x180020f40  mov     r9d, eax
0x180020f43  call    WPP_SF_Dq
0x180020f48  mov     sil, byte ptr [rbp+arg_0]
0x180020f4c  lea     rax, [rbx+18h]
0x180020f50  mov     rdi, [rdi]
0x180020f53  cmp     rdi, rax
0x180020f56  jnz     loc_180020CCA
0x180020f5c  test    sil, sil
0x180020f5f  jz      loc_180021586
0x180020f65  lea     rsi, [r15+18h]
0x180020f69  mov     rdi, [rsi]
0x180020f6c  jmp     loc_180021022
0x180020f71  mov     r14b, [rdi+28h]
0x180020f75  test    r14b, r14b
0x180020f78  jnz     short loc_180020F85
0x180020f7a  cmp     qword ptr [rdi+38h], 0
0x180020f7f  jnz     loc_18002101F
0x180020f85  cmp     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x180020f89  jnz     short loc_180020F97
0x180020f8b  mov     dword ptr [rdi+2Ch], 0
0x180020f92  jmp     loc_18002101F
0x180020f97  mov     r12, [rdi+40h]
0x180020f9b  test    r14b, r14b
0x180020f9e  jnz     short loc_180020FB0
0x180020fa0  mov     rcx, [rdi+38h]; this
0x180020fa4  test    rcx, rcx
0x180020fa7  jz      short loc_180020FB0
0x180020fa9  call    ?Flags@TLN_ENTRY@FTCache@@QEAAKXZ; FTCache::TLN_ENTRY::Flags(void)
0x180020fae  jmp     short loc_180020FB3
0x180020fb0  mov     eax, [rdi+48h]
0x180020fb3  mov     rdx, [rbx+10h]; void *
0x180020fb7  lea     r8, [rbp+LocallyUniqueId]; struct _LUID *
0x180020fbb  mov     [rsp+70h+var_30], 0; void *
0x180020fc4  xor     r9d, r9d
0x180020fc7  mov     [rsp+70h+var_38], 0; struct _UNICODE_STRING *
0x180020fd0  test    r14b, r14b
0x180020fd3  mov     [rsp+70h+var_40], 0; struct _UNICODE_STRING *
0x180020fdc  mov     rcx, rbx; struct _UNICODE_STRING *
0x180020fdf  setnz   r9b; enum LSA_FOREST_TRUST_RECORD_TYPE
0x180020fe3  mov     [rsp+70h+var_48], r12; struct _UNICODE_STRING *
0x180020fe8  mov     [rsp+70h+var_50], eax; unsigned int
0x180020fec  call    ?LsaDbpAdtTrustedForestInfoEntryRem@@YAJPEAU_UNICODE_STRING@@PEAXPEAU_LUID@@W4LSA_FOREST_TRUST_RECORD_TYPE@@K0001@Z; LsaDbpAdtTrustedForestInfoEntryRem(_UNICODE_STRING *,void *,_LUID *,LSA_FOREST_TRUST_RECORD_TYPE,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *)
0x180020ff1  test    eax, eax
0x180020ff3  jns     short loc_18002101F
0x180020ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ffc  test    byte ptr [rcx+1Ch], 8
0x180021000  jz      short loc_18002101F
0x180021002  mov     rcx, [rcx+10h]
0x180021006  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002100d  mov     edx, 0F3h
0x180021012  mov     qword ptr [rsp+70h+var_50], rdi
0x180021017  mov     r9d, eax
0x18002101a  call    WPP_SF_Dq
0x18002101f  mov     rdi, [rdi]
0x180021022  cmp     rdi, rsi
0x180021025  jnz     loc_180020F71
0x18002102b  lea     r14, [rbx+28h]
0x18002102f  mov     r13d, 2
0x180021035  mov     rdi, [r14]
0x180021038  jmp     loc_1800210D2
0x18002103d  mov     rcx, [rdi+68h]
0x180021041  add     rcx, 10h
0x180021045  mov     rax, [rcx]
0x180021048  jmp     short loc_18002105B
0x18002104a  lea     rsi, [rax-10h]
0x18002104e  cmp     [rsi+58h], r15
0x180021052  jz      loc_1800210E7
0x180021058  mov     rax, [rax]
0x18002105b  cmp     rax, rcx
0x18002105e  jnz     short loc_18002104A
0x180021060  mov     rax, [rdi+50h]
0x180021064  lea     r8, [rbp+LocallyUniqueId]; struct _LUID *
0x180021068  mov     rcx, [rdi+78h]
0x18002106c  mov     r9d, r13d; enum LSA_FOREST_TRUST_RECORD_TYPE
0x18002106f  mov     rdx, [rbx+10h]; void *
0x180021073  mov     [rsp+70h+var_30], rax; void *
0x180021078  mov     rax, [rdi+70h]
  ... truncated ...
```
