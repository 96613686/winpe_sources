# LsaDbpFilterInboundNamespace(_FILTER_INBOUNDNAMESPACE_REQUEST *,_FILTER_INBOUNDNAMESPACE_RESULT * *)

- ea: `0x180025474`
- end: `0x180025a73`
- name: `?LsaDbpFilterInboundNamespace@@YAJPEAU_FILTER_INBOUNDNAMESPACE_REQUEST@@PEAPEAU_FILTER_INBOUNDNAMESPACE_RESULT@@@Z`
- size: `1535`
- prototype: `__int64 __fastcall(struct _FILTER_INBOUNDNAMESPACE_REQUEST *, struct _FILTER_INBOUNDNAMESPACE_RESULT **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800167c0`

## callees

- `0x18000bf70`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fee8`
- `0x180021728`
- `0x180021b94`
- `0x180025474`
- `0x180026674`
- `0x18002b494`
- `0x18002b6f0`
- `0x18002b77c`
- `0x18002b8a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025522`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025522`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a0a`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18002558f`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18002558f`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800259fc`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800259fc`
- `ntdll!RtlInitUnicodeString` at `0x180025576`
- `ntdll!RtlInitUnicodeString` at `0x180025589`
- `ntdll!RtlInitUnicodeString` at `0x180025576`
- `ntdll!RtlInitUnicodeString` at `0x180025589`

## pseudocode

```c
__int64 __fastcall LsaDbpFilterInboundNamespace(
        struct _FILTER_INBOUNDNAMESPACE_REQUEST *a1,
        struct _FILTER_INBOUNDNAMESPACE_RESULT **a2)
{
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v3; // r13
  bool v4; // zf
  _WORD *v5; // rax
  _WORD *v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  struct _FILTER_INBOUNDNAMESPACE_RESULT *v9; // rbx
  unsigned int v10; // edi
  __int64 v11; // rcx
  const WCHAR *v12; // rdx
  FTCache *v13; // rcx
  int Match; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  int v17; // r15d
  int v18; // r12d
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  const wchar_t *v22; // rdx
  const wchar_t *v23; // r8
  int v24; // eax
  const wchar_t *v25; // r9
  enum FTCache::OwnershipState *v27; // [rsp+28h] [rbp-41h]
  int v28; // [rsp+50h] [rbp-19h] BYREF
  int v29[3]; // [rsp+54h] [rbp-15h] BYREF
  __int64 v30; // [rsp+60h] [rbp-9h]
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v31; // [rsp+68h] [rbp-1h] BYREF
  struct _UNICODE_STRING v32; // [rsp+70h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+17h] BYREF
  int v34; // [rsp+D0h] [rbp+67h] BYREF
  struct _FILTER_INBOUNDNAMESPACE_RESULT **v35; // [rsp+D8h] [rbp+6Fh]
  unsigned int v36; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v37; // [rsp+E8h] [rbp+7Fh] BYREF

  v35 = a2;
  v28 = 0;
  v29[0] = 0;
  v34 = 0;
  v3 = 0;
  v31 = 0;
  v36 = 3;
  v37 = 3;
  v4 = *((_QWORD *)a1 + 1) == 0;
  v30 = *((_QWORD *)a1 + 1);
  *a2 = 0;
  v5 = (_WORD *)*((_QWORD *)a1 + 3);
  v29[1] = v4;
  DestinationString = 0;
  v32 = 0;
  if ( !v5 || !*v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v8 = 358;
      goto LABEL_112;
    }
LABEL_113:
    v10 = -1073741811;
    goto LABEL_114;
  }
  v6 = (_WORD *)*((_QWORD *)a1 + 4);
  if ( v6 && !*v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v8 = 359;
LABEL_112:
      WPP_SF_(v7[2], v8, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
      goto LABEL_113;
    }
    goto LABEL_113;
  }
  v9 = (struct _FILTER_INBOUNDNAMESPACE_RESULT *)LocalAlloc(0x40u, 8u);
  if ( !v9 )
  {
    v10 = -1073741670;
    goto LABEL_114;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_ZDSS(*((_QWORD *)WPP_GLOBAL_Control + 2), *((_DWORD *)a1 + 4), *((_QWORD *)a1 + 3), *((_QWORD *)a1 + 4));
  RtlInitUnicodeString(&DestinationString, *((PCWSTR *)a1 + 3));
  v12 = (const WCHAR *)*((_QWORD *)a1 + 4);
  if ( v12 )
    RtlInitUnicodeString(&v32, v12);
  LsapDbExpAcquireReadLockTrustedDomainList(v11);
  Match = FTCache::CheckIfNamesAreOwnedByLocalForest(
            v13,
            &DestinationString,
            (struct _UNICODE_STRING *)((unsigned __int64)&v32 & -(__int64)(*((_QWORD *)a1 + 4) != 0)),
            &v28,
            v29);
  v10 = Match;
  if ( Match < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_108;
    v16 = 361;
    goto LABEL_16;
  }
  v15 = WPP_GLOBAL_Control;
  v17 = v28;
  v18 = v29[0];
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      362,
      &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
      (unsigned int)v28,
      v29[0]);
    v15 = WPP_GLOBAL_Control;
  }
  if ( !v17 || !v18 && *((_QWORD *)a1 + 4) )
  {
    if ( !v30 )
    {
LABEL_46:
      Match = FTCache::FilterInboundNamespace(
                g_FTCache,
                v3,
                a1,
                v17,
                v18,
                (enum FTCache::OwnershipState *)&v36,
                (enum FTCache::OwnershipState *)&v37,
                &v34);
      v10 = Match;
      if ( Match < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_108;
        v16 = 370;
LABEL_16:
        WPP_SF_d(v15[2], v16, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (unsigned int)Match);
        goto LABEL_108;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v22 = (const wchar_t *)L"<unknown>";
        if ( v37 )
        {
          switch ( v37 )
          {
            case 1u:
              v23 = L"Contested";
              break;
            case 2u:
              v23 = L"OtherOwner";
              break;
            case 3u:
              v23 = L"Unowned";
              break;
            default:
              v23 = (const wchar_t *)L"<unknown>";
              break;
          }
        }
        else
        {
          v23 = L"UniquelyOwned";
        }
        if ( v36 )
        {
          switch ( v36 )
          {
            case 1u:
              v22 = L"Contested";
              break;
            case 2u:
              v22 = L"OtherOwner";
              break;
            case 3u:
              v22 = L"Unowned";
              break;
          }
        }
        else
        {
          v22 = L"UniquelyOwned";
        }
        WPP_SF_DSDSDD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v22, v36, (__int64)v23, v37, v34);
      }
      v15 = (_QWORD *)v36;
      if ( v36 )
      {
        v15 = (_QWORD *)(v36 - 1);
        if ( v36 != 1 )
        {
          v15 = (_QWORD *)(v36 - 2);
          if ( v36 != 2 )
          {
            if ( v36 != 3 )
            {
LABEL_43:
              v10 = -1073741595;
              goto LABEL_108;
            }
            if ( v30 )
            {
              *(_DWORD *)v9 = 6;
LABEL_74:
              *((_DWORD *)v9 + 1) = v34;
              goto LABEL_86;
            }
            goto LABEL_85;
          }
LABEL_75:
          *(_DWORD *)v9 = 8;
          goto LABEL_74;
        }
        if ( !*((_QWORD *)a1 + 4) )
          goto LABEL_82;
        v15 = (_QWORD *)v37;
        if ( v37 )
        {
          v15 = (_QWORD *)(v37 - 1);
          if ( v37 == 1 )
          {
            v24 = v17 != 0 ? 1 : 4;
            goto LABEL_83;
          }
          v15 = (_QWORD *)(v37 - 2);
          if ( v37 == 2 )
            goto LABEL_75;
          if ( v37 != 3 )
            goto LABEL_86;
          if ( v30 )
          {
LABEL_82:
            v24 = v17 != 0 ? 1 : 3;
LABEL_83:
            *(_DWORD *)v9 = v24;
            goto LABEL_74;
          }
        }
      }
LABEL_85:
      *(_QWORD *)v9 = 0;
LABEL_86:
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        if ( *(_DWORD *)v9 )
        {
          switch ( *(_DWORD *)v9 )
          {
            case 1:
              v25 = L"ResourceDomainNameCollidesWithLocalForest";
              break;
            case 2:
              v25 = L"ResourceDomainNameUnknownInLocalForest";
              break;
            case 3:
              v25 = L"ResourceDomainNetbiosName_Ambiguous";
              break;
            case 4:
              v25 = L"ResourceDomainDnsName_Ambiguous";
              break;
            case 5:
              v25 = L"ResourceDomainDoesNotMatchExternalTrustDomainName";
              break;
            case 6:
              v25 = L"ResourceDomainUnknown";
              break;
            case 7:
              v25 = L"ResourceServerUnauthorizedOnRODC";
              break;
            case 8:
              v25 = L"ResourceDomainHasOtherOwnerPossibleAttack";
              break;
            default:
              v25 = L"<unknown reason>";
              break;
          }
        }
        else
        {
          v25 = L"FilterInboundNamespaceSucceeded";
        }
        LODWORD(v27) = *((_DWORD *)v9 + 1);
        WPP_SF_SDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          372,
          (unsigned int)&WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
          (_DWORD)v25,
          *(_DWORD *)v9,
          v27);
      }
      goto LABEL_107;
    }
LABEL_28:
    Match = LsaDbpLookupNameTrustedDomainListEx(*((struct _LSAPR_UNICODE_STRING **)a1 + 1), &v31);
    v10 = Match;
    if ( Match < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_108;
      v16 = 364;
      goto LABEL_16;
    }
    v15 = WPP_GLOBAL_Control;
    v3 = v31;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_ZZDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v31 + 32,
        v20,
        (_DWORD)v31 + 16,
        (__int64)v31 + 32,
        *((_DWORD *)v31 + 14),
        *((_DWORD *)v31 + 15),
        *((_DWORD *)v31 + 16));
      v15 = WPP_GLOBAL_Control;
    }
    if ( (*((_BYTE *)v3 + 64) & 0x20) != 0 )
    {
      if ( (*((_BYTE *)v15 + 28) & 8) == 0 )
        goto LABEL_26;
      v19 = 366;
      goto LABEL_25;
    }
    LOBYTE(v20) = 1;
    Match = LsaDbpForestTrustFindMatch(1, (char *)v3 + 16, v20, 0, 0);
    v10 = Match;
    if ( Match >= 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_26;
      v19 = 367;
      goto LABEL_25;
    }
    if ( Match != -1073741198 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_108;
      v16 = 368;
      goto LABEL_16;
    }
    v21 = *((unsigned int *)v3 + 14);
    if ( (v21 & 1) == 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 369, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, v21);
      goto LABEL_43;
    }
    goto LABEL_46;
  }
  if ( v30 )
    goto LABEL_28;
  if ( (*((_BYTE *)v15 + 28) & 8) != 0 )
  {
    v19 = 363;
LABEL_25:
    WPP_SF_(v15[2], v19, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  }
LABEL_26:
  *(_QWORD *)v9 = 0;
LABEL_107:
  *v35 = v9;
  v9 = 0;
LABEL_108:
  LsapDbExpReleaseLockTrustedDomainList(v15);
  if ( v9 )
    LocalFree(v9);
LABEL_114:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 373, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180025474  mov     [rsp-8+arg_8], rdx
0x180025479  push    rbp
0x18002547a  push    rbx
0x18002547b  push    rdi
0x18002547c  push    r12
0x18002547e  push    r13
0x180025480  push    r14
0x180025482  push    r15
0x180025484  lea     rbp, [rsp-27h]
0x180025489  sub     rsp, 90h
0x180025490  xor     r12d, r12d
0x180025493  mov     r14, rcx
0x180025496  xorps   xmm0, xmm0
0x180025499  mov     [rbp+57h+var_70], r12d
0x18002549d  xorps   xmm1, xmm1
0x1800254a0  mov     [rbp+57h+var_6C], r12d
0x1800254a4  mov     [rbp+57h+arg_0], r12d
0x1800254a8  mov     r13d, r12d
0x1800254ab  lea     eax, [r12+3]
0x1800254b0  mov     [rbp+57h+var_58], r12
0x1800254b4  mov     [rbp+57h+arg_10], eax
0x1800254b7  mov     [rbp+57h+arg_18], eax
0x1800254ba  mov     rax, [rcx+8]
0x1800254be  mov     ecx, r12d
0x1800254c1  test    rax, rax
0x1800254c4  mov     [rbp+57h+var_60], rax
0x1800254c8  mov     [rdx], r12
0x1800254cb  mov     rax, [r14+18h]
0x1800254cf  setz    cl
0x1800254d2  mov     [rbp+57h+var_68], ecx
0x1800254d5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800254d9  movups  xmmword ptr [rbp+57h+var_50.Length], xmm1
0x1800254dd  test    rax, rax
0x1800254e0  jz      loc_180025A12
0x1800254e6  cmp     [rax], r12w
0x1800254ea  jz      loc_180025A12
0x1800254f0  mov     rax, [r14+20h]
0x1800254f4  test    rax, rax
0x1800254f7  jz      short loc_18002551A
0x1800254f9  cmp     [rax], r12w
0x1800254fd  jnz     short loc_18002551A
0x1800254ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180025506  test    byte ptr [rcx+1Ch], 8
0x18002550a  jz      loc_180025A34
0x180025510  mov     edx, 167h
0x180025515  jmp     loc_180025A24
0x18002551a  mov     edx, 8; uBytes
0x18002551f  lea     ecx, [rdx+38h]; uFlags
0x180025522  call    cs:__imp_LocalAlloc
0x180025528  mov     rbx, rax
0x18002552b  test    rax, rax
0x18002552e  jnz     short loc_18002553A
0x180025530  mov     edi, 0C000009Ah
0x180025535  jmp     loc_180025A39
0x18002553a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025541  test    byte ptr [rcx+1Ch], 8
0x180025545  jz      short loc_18002556E
0x180025547  mov     rax, [r14+20h]
0x18002554b  mov     r9, [r14+8]
0x18002554f  mov     rcx, [rcx+10h]; LoggerHandle
0x180025553  mov     [rsp+0C0h+var_90], rax; __int64
0x180025558  mov     rax, [r14+18h]
0x18002555c  mov     [rsp+0C0h+var_98], rax; __int64
0x180025561  mov     eax, [r14+10h]
0x180025565  mov     dword ptr [rsp+0C0h+var_A0], eax; char
0x180025569  call    WPP_SF_ZDSS
0x18002556e  mov     rdx, [r14+18h]; SourceString
0x180025572  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180025576  call    cs:__imp_RtlInitUnicodeString
0x18002557c  mov     rdx, [r14+20h]; SourceString
0x180025580  test    rdx, rdx
0x180025583  jz      short loc_18002558F
0x180025585  lea     rcx, [rbp+57h+var_50]; DestinationString
0x180025589  call    cs:__imp_RtlInitUnicodeString
0x18002558f  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x180025595  mov     rax, [r14+20h]
0x180025599  lea     r9, [rbp+57h+var_70]; int *
0x18002559d  neg     rax
0x1800255a0  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x1800255a4  lea     rax, [rbp+57h+var_50]
0x1800255a8  sbb     r8, r8
0x1800255ab  and     r8, rax; struct _UNICODE_STRING *
0x1800255ae  lea     rax, [rbp+57h+var_6C]
0x1800255b2  mov     [rsp+0C0h+var_A0], rax; int *
0x1800255b7  call    ?CheckIfNamesAreOwnedByLocalForest@FTCache@@AEAAJPEAU_UNICODE_STRING@@0PEAH1@Z; FTCache::CheckIfNamesAreOwnedByLocalForest(_UNICODE_STRING *,_UNICODE_STRING *,int *,int *)
0x1800255bc  mov     edi, eax
0x1800255be  test    eax, eax
0x1800255c0  jns     short loc_1800255F0
0x1800255c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255c9  test    byte ptr [rcx+1Ch], 8
0x1800255cd  jz      loc_1800259FC
0x1800255d3  mov     edx, 169h
0x1800255d8  mov     rcx, [rcx+10h]
0x1800255dc  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800255e3  mov     r9d, eax
0x1800255e6  call    WPP_SF_d
0x1800255eb  jmp     loc_1800259FC
0x1800255f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255f7  mov     r15d, [rbp+57h+var_70]
0x1800255fb  mov     r12d, [rbp+57h+var_6C]
0x1800255ff  test    byte ptr [rcx+1Ch], 8
0x180025603  jz      short loc_180025629
0x180025605  mov     rcx, [rcx+10h]
0x180025609  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180025610  mov     edx, 16Ah
0x180025615  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x18002561a  mov     r9d, r15d
0x18002561d  call    WPP_SF_dd
0x180025622  mov     rcx, cs:WPP_GLOBAL_Control
0x180025629  xor     eax, eax
0x18002562b  test    r15d, r15d
0x18002562e  jz      short loc_180025667
0x180025630  test    r12d, r12d
0x180025633  jnz     short loc_18002563B
0x180025635  cmp     [r14+20h], rax
0x180025639  jnz     short loc_180025667
0x18002563b  cmp     [rbp+57h+var_60], rax
0x18002563f  jnz     short loc_180025671
0x180025641  test    byte ptr [rcx+1Ch], 8
0x180025645  jz      short loc_18002565C
0x180025647  mov     edx, 16Bh
0x18002564c  mov     rcx, [rcx+10h]
0x180025650  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180025657  call    WPP_SF_
0x18002565c  xor     r12d, r12d
0x18002565f  mov     [rbx], r12
0x180025662  jmp     loc_1800259F2
0x180025667  cmp     [rbp+57h+var_60], rax
0x18002566b  jz      loc_180025794
0x180025671  mov     rcx, [r14+8]; struct _LSAPR_UNICODE_STRING *
0x180025675  lea     rdx, [rbp+57h+var_58]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x180025679  call    ?LsaDbpLookupNameTrustedDomainListEx@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupNameTrustedDomainListEx(_LSAPR_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18002567e  mov     edi, eax
0x180025680  test    eax, eax
0x180025682  jns     short loc_18002569F
0x180025684  mov     rcx, cs:WPP_GLOBAL_Control
0x18002568b  test    byte ptr [rcx+1Ch], 8
0x18002568f  jz      loc_1800259FC
0x180025695  mov     edx, 16Ch
0x18002569a  jmp     loc_1800255D8
0x18002569f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256a6  mov     r13, [rbp+57h+var_58]
0x1800256aa  test    byte ptr [rcx+1Ch], 8
0x1800256ae  jz      short loc_1800256E5
0x1800256b0  mov     rcx, [rcx+10h]
0x1800256b4  lea     r9, [r13+10h]
0x1800256b8  mov     eax, [r9+30h]
0x1800256bc  lea     rdx, [r9+10h]
0x1800256c0  mov     dword ptr [rsp+0C0h+var_88], eax
0x1800256c4  mov     eax, [r13+3Ch]
0x1800256c8  mov     dword ptr [rsp+0C0h+var_90], eax
0x1800256cc  mov     eax, [r13+38h]
0x1800256d0  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800256d4  mov     [rsp+0C0h+var_A0], rdx
0x1800256d9  call    WPP_SF_ZZDDD
0x1800256de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256e5  lea     rdx, [r13+10h]
0x1800256e9  test    byte ptr [rdx+30h], 20h
0x1800256ed  jz      short loc_180025703
0x1800256ef  test    byte ptr [rcx+1Ch], 8
0x1800256f3  jz      loc_18002565C
0x1800256f9  mov     edx, 16Eh
0x1800256fe  jmp     loc_18002564C
0x180025703  xor     r9d, r9d
0x180025706  mov     [rsp+0C0h+var_A0], 0
0x18002570f  mov     r8b, 1
0x180025712  lea     ecx, [r9+1]
0x180025716  call    ?LsaDbpForestTrustFindMatch@@YAJW4LSA_ROUTING_MATCH_TYPE@@PEAXEPEAU_UNICODE_STRING@@PEAPEAX@Z; LsaDbpForestTrustFindMatch(LSA_ROUTING_MATCH_TYPE,void *,uchar,_UNICODE_STRING *,void * *)
0x18002571b  mov     edi, eax
0x18002571d  test    eax, eax
0x18002571f  js      short loc_18002573C
0x180025721  mov     rcx, cs:WPP_GLOBAL_Control
0x180025728  test    byte ptr [rcx+1Ch], 8
0x18002572c  jz      loc_18002565C
0x180025732  mov     edx, 16Fh
0x180025737  jmp     loc_18002564C
0x18002573c  cmp     eax, 0C0000272h
0x180025741  jnz     short loc_180025779
0x180025743  mov     r9d, [r13+38h]
0x180025747  test    r9b, 1
0x18002574b  jnz     short loc_180025794
0x18002574d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025754  test    byte ptr [rcx+1Ch], 8
0x180025758  jz      short loc_18002576F
0x18002575a  mov     rcx, [rcx+10h]
0x18002575e  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180025765  mov     edx, 171h
0x18002576a  call    WPP_SF_d
0x18002576f  mov     edi, 0C00000E5h
0x180025774  jmp     loc_1800259FC
0x180025779  mov     rcx, cs:WPP_GLOBAL_Control
0x180025780  test    byte ptr [rcx+1Ch], 8
0x180025784  jz      loc_1800259FC
0x18002578a  mov     edx, 170h
0x18002578f  jmp     loc_1800255D8
0x180025794  mov     rcx, cs:?g_FTCache@@3PEAVFTCache@@EA; this
0x18002579b  lea     rax, [rbp+57h+arg_0]
0x18002579f  mov     [rsp+0C0h+var_88], rax; int *
0x1800257a4  mov     r9d, r15d; int
0x1800257a7  lea     rax, [rbp+57h+arg_18]
0x1800257ab  mov     r8, r14; struct _FILTER_INBOUNDNAMESPACE_REQUEST *
0x1800257ae  mov     [rsp+0C0h+var_90], rax; enum FTCache::OwnershipState *
0x1800257b3  mov     rdx, r13; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *
0x1800257b6  lea     rax, [rbp+57h+arg_10]
0x1800257ba  mov     [rsp+0C0h+var_98], rax; enum FTCache::OwnershipState *
0x1800257bf  mov     dword ptr [rsp+0C0h+var_A0], r12d; int
0x1800257c4  call    ?FilterInboundNamespace@FTCache@@AEAAJPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@PEAU_FILTER_INBOUNDNAMESPACE_REQUEST@@HHPEAW4OwnershipState@1@2PEAH@Z; FTCache::FilterInboundNamespace(_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *,_FILTER_INBOUNDNAMESPACE_REQUEST *,int,int,FTCache::OwnershipState *,FTCache::OwnershipState *,int *)
0x1800257c9  xor     r12d, r12d
0x1800257cc  mov     edi, eax
0x1800257ce  test    eax, eax
0x1800257d0  jns     short loc_1800257ED
0x1800257d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257d9  test    byte ptr [rcx+1Ch], 8
0x1800257dd  jz      loc_1800259FC
0x1800257e3  mov     edx, 172h
0x1800257e8  jmp     loc_1800255D8
0x1800257ed  mov     rax, cs:WPP_GLOBAL_Control
0x1800257f4  test    byte ptr [rax+1Ch], 8
0x1800257f8  jz      loc_1800258B5
0x1800257fe  mov     r10d, [rbp+57h+arg_18]
0x180025802  lea     rdx, aUnknown; "<unknown>"
0x180025809  mov     r11d, [rbp+57h+arg_0]
0x18002580d  mov     ecx, r10d
0x180025810  test    r10d, r10d
0x180025813  jz      short loc_180025844
0x180025815  sub     ecx, 1
0x180025818  jz      short loc_18002583B
0x18002581a  sub     ecx, 1
0x18002581d  jz      short loc_180025832
0x18002581f  cmp     ecx, 1
0x180025822  jz      short loc_180025829
0x180025824  mov     r8, rdx
0x180025827  jmp     short loc_18002584B
0x180025829  lea     r8, aUnowned; "Unowned"
0x180025830  jmp     short loc_18002584B
0x180025832  lea     r8, aOtherowner; "OtherOwner"
0x180025839  jmp     short loc_18002584B
0x18002583b  lea     r8, aContested; "Contested"
0x180025842  jmp     short loc_18002584B
0x180025844  lea     r8, aUniquelyowned; "UniquelyOwned"
0x18002584b  mov     r9d, [rbp+57h+arg_10]
0x18002584f  mov     ecx, r9d
0x180025852  test    r9d, r9d
0x180025855  jz      short loc_180025881
0x180025857  sub     ecx, 1
0x18002585a  jz      short loc_180025878
0x18002585c  sub     ecx, 1
0x18002585f  jz      short loc_18002586F
0x180025861  cmp     ecx, 1
0x180025864  jnz     short loc_180025888
0x180025866  lea     rdx, aUnowned; "Unowned"
0x18002586d  jmp     short loc_180025888
0x18002586f  lea     rdx, aOtherowner; "OtherOwner"
0x180025876  jmp     short loc_180025888
0x180025878  lea     rdx, aContested; "Contested"
0x18002587f  jmp     short loc_180025888
0x180025881  lea     rdx, aUniquelyowned; "UniquelyOwned"
0x180025888  mov     rcx, cs:WPP_GLOBAL_Control
0x18002588f  mov     dword ptr [rsp+0C0h+var_80], r11d; char
0x180025894  mov     dword ptr [rsp+0C0h+var_88], r10d; char
0x180025899  mov     [rsp+0C0h+var_90], r8; __int64
0x18002589e  mov     rcx, [rcx+10h]; LoggerHandle
0x1800258a2  mov     dword ptr [rsp+0C0h+var_98], r9d; char
0x1800258a7  mov     r9d, [rbp+57h+var_68]
0x1800258ab  mov     [rsp+0C0h+var_A0], rdx; __int64
0x1800258b0  call    WPP_SF_DSDSDD
0x1800258b5  mov     ecx, [rbp+57h+arg_10]
0x1800258b8  test    ecx, ecx
0x1800258ba  jz      short loc_180025929
0x1800258bc  sub     ecx, 1
0x1800258bf  jz      short loc_1800258EB
0x1800258c1  sub     ecx, 1
0x1800258c4  jz      short loc_1800258E3
0x1800258c6  cmp     ecx, 1
0x1800258c9  jnz     loc_18002576F
0x1800258cf  cmp     [rbp+57h+var_60], r12
0x1800258d3  jz      short loc_180025929
0x1800258d5  mov     dword ptr [rbx], 6
0x1800258db  mov     eax, [rbp+57h+arg_0]
0x1800258de  mov     [rbx+4], eax
0x1800258e1  jmp     short loc_18002592C
0x1800258e3  mov     dword ptr [rbx], 8
0x1800258e9  jmp     short loc_1800258DB
0x1800258eb  cmp     [r14+20h], r12
0x1800258ef  jz      short loc_18002590D
0x1800258f1  mov     ecx, [rbp+57h+arg_18]
0x1800258f4  test    ecx, ecx
0x1800258f6  jz      short loc_180025929
0x1800258f8  sub     ecx, 1
0x1800258fb  jz      short loc_18002591C
0x1800258fd  sub     ecx, 1
0x180025900  jz      short loc_1800258E3
0x180025902  cmp     ecx, 1
0x180025905  jnz     short loc_18002592C
0x180025907  cmp     [rbp+57h+var_60], r12
0x18002590b  jz      short loc_180025929
0x18002590d  neg     r15d
0x180025910  sbb     eax, eax
0x180025912  and     eax, 0FFFFFFFEh
0x180025915  add     eax, 3
  ... truncated ...
```
