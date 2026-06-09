# FindDnsPolicyConfigInfoPrivate

- ea: `0x180019310`
- end: `0x180019bdc`
- name: `FindDnsPolicyConfigInfoPrivate`
- size: `2252`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `5`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018554`
- `0x180032ac0`
- `0x180065d48`
- `0x180074bd0`
- `0x18007b344`

## callees

- `0x180019198`
- `0x180019310`
- `0x180019fe0`
- `0x18001a060`
- `0x18001a0c0`
- `0x18001a0e8`
- `0x18001a198`
- `0x18001a208`
- `0x18001a254`
- `0x18001a764`
- `0x180029d80`
- `0x18002a160`
- `0x18002b050`
- `0x1800cafec`
- `0x1800dbfe0`
- `0x1800dc038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800193a4`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800193a4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180019524`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180019524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019375`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019375`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800195c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019609`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001965c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800195c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019609`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001965c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019420`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019765`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800197f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019420`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019765`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800197f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800198b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800198b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800194ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800194ed`

## pseudocode

```c
__int64 __fastcall FindDnsPolicyConfigInfoPrivate(WCHAR *Src, char a2, LPVOID *a3)
{
  LPVOID *v3; // r13
  _QWORD *v4; // r14
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  char v8; // r15
  WCHAR *v9; // rbx
  unsigned int i; // edi
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // r14
  _QWORD *j; // rdi
  const WCHAR *v15; // r8
  __int64 *v16; // rbp
  int v17; // edi
  __int64 v18; // rcx
  __int64 v19; // r14
  __int64 v20; // rax
  unsigned __int64 v21; // rax
  __int64 v22; // rax
  WCHAR *v23; // r15
  __int64 *v24; // rbp
  const WCHAR *v25; // r12
  bool v26; // zf
  HANDLE ProcessHeap; // rax
  wchar_t *v28; // rax
  LPVOID v29; // rdi
  DWORD LastError; // ebx
  WCHAR v32; // dx
  int v33; // r9d
  const WCHAR *v34; // rcx
  int v35; // eax
  unsigned int SuffixHashIndex; // eax
  __int64 v37; // rcx
  __int64 v38; // r13
  _QWORD *k; // r14
  const WCHAR *v40; // r8
  const WCHAR *NextLevelSuffix; // r13
  unsigned int v42; // r14d
  unsigned int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // r12
  _QWORD *m; // r14
  const WCHAR *v47; // r8
  __int64 StringCopy_W; // rax
  void *v49; // rbx
  __int64 EntryFromDnsPrefixPolicyTable; // rax
  void *v51; // r14
  _QWORD *v52; // rcx
  __int64 v53; // rax
  const wchar_t *v54; // r9
  _QWORD *v55; // rcx
  _QWORD *v56; // rdi
  __int64 v57; // rax
  int v58; // [rsp+30h] [rbp-58h]
  unsigned int v59; // [rsp+30h] [rbp-58h]
  _QWORD *v60; // [rsp+40h] [rbp-48h] BYREF
  char v63; // [rsp+A8h] [rbp+20h]

  v3 = a3;
  v4 = 0;
  v60 = 0;
  _m_prefetchw(&dword_180112518);
  v6 = dword_180112518;
  do
  {
    v7 = v6;
    v6 = _InterlockedCompareExchange(&dword_180112518, v6, v6);
  }
  while ( v7 != v6 );
  v8 = v6;
  v63 = v6;
  AcquireSRWLockShared(&g_DnsPolicyTableLock);
  if ( dword_18011251C )
  {
    LastError = 4312;
    goto LABEL_32;
  }
  *v3 = 0;
  v9 = Src;
  for ( i = 0; *v9; i = (unsigned __int16)_o_towlower() + 33 * i )
    ++v9;
  v11 = xmmword_180112B70;
  v12 = -1;
  if ( (_QWORD)xmmword_180112B70 )
  {
    v13 = 2LL * (i % 0x1F3);
    for ( j = *(_QWORD **)(xmmword_180112B70 + 16LL * (i % 0x1F3)); j != (_QWORD *)(v11 + 8 * v13); j = (_QWORD *)*j )
    {
      v15 = (const WCHAR *)j[8];
      v16 = j - 1;
      if ( v15 )
      {
        if ( CompareStringW(0x409u, 1u, v15, -1, Src, -1) == 2 )
        {
          ReferenceDnsPolicyConfigNode(j - 1);
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_SS(1035, 25, (unsigned int)WPP_85172e4714023e67c3665ec5069963d4_Traceguids, (_DWORD)Src, v16[9]);
          *v3 = v16;
          LastError = 0;
          goto LABEL_92;
        }
        v11 = xmmword_180112B70;
      }
    }
  }
  v17 = 4312;
  v18 = -1;
  do
    ++v18;
  while ( Src[v18] );
  if ( (_DWORD)v18 )
  {
    v19 = (unsigned int)(v18 - 1);
    if ( Src[v19] != 46 )
      LODWORD(v19) = v18;
    v20 = (unsigned int)(v19 + 2);
    if ( (unsigned int)v20 >= (unsigned int)v19 )
    {
      v21 = 2 * v20;
      if ( v21 <= 0xFFFFFFFF )
      {
        v22 = Dns_Allocate((unsigned int)v21);
        v23 = (WCHAR *)v22;
        if ( !v22 )
          goto LABEL_25;
        v24 = 0;
        v25 = (const WCHAR *)(v22 + 2);
        memcpy_0((void *)(v22 + 2), Src, 2LL * (unsigned int)v19);
        *v23 = 46;
        v26 = dword_180111FF8 == 0;
        v23[(unsigned int)(v19 + 1)] = 0;
        if ( v26 )
          goto LABEL_22;
        v32 = *v25;
        v33 = 1;
        v58 = 1;
        v34 = v25;
        if ( *v25 )
        {
          do
          {
            v26 = v32 == 46;
            v35 = v33 + 1;
            v32 = v34[1];
            ++v34;
            if ( !v26 )
              v35 = v33;
            v33 = v35;
          }
          while ( v32 );
          v58 = v35;
        }
        SuffixHashIndex = GetSuffixHashIndex(v25);
        v37 = xmmword_180112B70;
        if ( (_QWORD)xmmword_180112B70 )
        {
          v38 = 2LL * SuffixHashIndex;
          for ( k = *(_QWORD **)(xmmword_180112B70 + 16LL * SuffixHashIndex); ; k = (_QWORD *)*k )
          {
            if ( k == (_QWORD *)(v37 + 8 * v38) )
            {
              v24 = 0;
              break;
            }
            v40 = (const WCHAR *)k[8];
            v24 = k - 1;
            if ( v40 )
            {
              if ( v25 )
              {
                if ( CompareStringW(0x409u, 1u, v40, -1, v25, -1) == 2 )
                  goto LABEL_94;
                v37 = xmmword_180112B70;
              }
            }
            else if ( !v25 )
            {
LABEL_94:
              ReferenceDnsPolicyConfigNode(k - 1);
              if ( k != (_QWORD *)8 )
              {
LABEL_95:
                v3 = a3;
                v17 = 0;
                goto LABEL_22;
              }
              break;
            }
          }
        }
        NextLevelSuffix = v23;
        v42 = v58 + 1;
LABEL_78:
        v59 = v42;
        if ( v42 < dword_180111FF4 )
        {
LABEL_101:
          v3 = a3;
LABEL_22:
          ProcessHeap = g_hProcessHeap;
          if ( !g_hProcessHeap )
          {
            ProcessHeap = GetProcessHeap();
            g_hProcessHeap = ProcessHeap;
          }
          HeapFree(ProcessHeap, 0, v23);
          if ( v17 )
          {
LABEL_25:
            v8 = v63;
            goto LABEL_26;
          }
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_SS(1035, 23, (unsigned int)WPP_85172e4714023e67c3665ec5069963d4_Traceguids, (_DWORD)Src, v24[9]);
LABEL_104:
          *v3 = 0;
          GetPrefixHash(Src);
          StringCopy_W = Dns_CreateStringCopy_W(Src);
          v49 = (void *)StringCopy_W;
          if ( !StringCopy_W
            || (Dns_SplitHostFromDomainNameW(StringCopy_W),
                EntryFromDnsPrefixPolicyTable = FindEntryFromDnsPrefixPolicyTable((PCNZWCH)v49),
                (v51 = (void *)EntryFromDnsPrefixPolicyTable) == 0) )
          {
            DnsApiFree(v49);
            v8 = v63;
            goto LABEL_29;
          }
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_SS(
              1035,
              26,
              (unsigned int)WPP_85172e4714023e67c3665ec5069963d4_Traceguids,
              (_DWORD)Src,
              *(_QWORD *)(EntryFromDnsPrefixPolicyTable + 72));
          *v3 = v51;
          DnsApiFree(v49);
          v52 = *v3;
          v53 = *((_QWORD *)*v3 + 6);
          if ( v53 )
          {
            if ( !v52[5] )
              goto LABEL_122;
          }
          else
          {
            if ( !g_DAConfigured )
              goto LABEL_112;
            if ( v52[5] )
              goto LABEL_117;
LABEL_122:
            if ( byte_180111F78 )
            {
              if ( v53 )
              {
                v8 = v63;
                goto LABEL_118;
              }
LABEL_117:
              v8 = v63;
              if ( (v63 & 0x60) != 0x60 || (v63 & 8) != 0 )
              {
LABEL_118:
                v4 = *v3;
                v60 = *v3;
                goto LABEL_30;
              }
LABEL_113:
              LastError = 0;
              if ( v24 )
                DereferenceDnsPolicyConfigNode(v24);
LABEL_92:
              v4 = 0;
              goto LABEL_32;
            }
          }
LABEL_112:
          v8 = v63;
          goto LABEL_113;
        }
        v43 = GetSuffixHashIndex(NextLevelSuffix);
        v44 = xmmword_180112B70;
        if ( !(_QWORD)xmmword_180112B70 )
        {
LABEL_88:
          v24 = 0;
          goto LABEL_99;
        }
        v45 = 2LL * v43;
        for ( m = *(_QWORD **)(xmmword_180112B70 + 16LL * v43); ; m = (_QWORD *)*m )
        {
          if ( m == (_QWORD *)(v44 + 8 * v45) )
          {
            v42 = v59;
            goto LABEL_88;
          }
          v47 = (const WCHAR *)m[8];
          v24 = m - 1;
          if ( v47 )
          {
            if ( NextLevelSuffix )
            {
              if ( CompareStringW(0x409u, 1u, v47, -1, NextLevelSuffix, -1) == 2 )
                goto LABEL_97;
              v44 = xmmword_180112B70;
            }
          }
          else if ( !NextLevelSuffix )
          {
LABEL_97:
            ReferenceDnsPolicyConfigNode(m - 1);
            if ( m != (_QWORD *)8 )
              goto LABEL_95;
            v42 = v59;
LABEL_99:
            NextLevelSuffix = (const WCHAR *)GetNextLevelSuffix(NextLevelSuffix + 1);
            if ( !NextLevelSuffix )
              goto LABEL_101;
            --v42;
            goto LABEL_78;
          }
        }
      }
    }
  }
LABEL_26:
  v24 = 0;
  if ( (a2 & 1) != 0 )
    goto LABEL_104;
  v28 = wcschr(Src, 0x2Eu);
  if ( !v28 || !v28[1] )
  {
    do
      ++v12;
    while ( Src[v12] );
    if ( (int)v12 <= 63 || (_DWORD)v12 == 64 && Src[63] == 46 )
      goto LABEL_104;
  }
LABEL_29:
  v4 = 0;
LABEL_30:
  *v3 = v24;
  if ( v17 )
  {
    v29 = qword_180112520;
    LastError = 4312;
    *v3 = 0;
    if ( !v29 )
      goto LABEL_32;
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_S(1035, 24, WPP_85172e4714023e67c3665ec5069963d4_Traceguids, Src);
    ReferenceDnsPolicyConfigNode(v29);
    *v3 = v29;
  }
  LastError = 0;
LABEL_32:
  if ( *v3 && *((_QWORD *)*v3 + 6) || v4 && v4[6] )
  {
    if ( (v8 & 0x60) == 0x60 && (v8 & 8) == 0 )
    {
      if ( v4 )
        DereferenceDnsPolicyConfigNode(v4);
      v4 = qword_180112528;
      if ( !qword_180112528 )
      {
        ReleaseSRWLockShared(&g_DnsPolicyTableLock);
        return 4312;
      }
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        v54 = Src;
        if ( !Src )
          v54 = L"NULL";
        WPP_SF_S(1035, 24, WPP_85172e4714023e67c3665ec5069963d4_Traceguids, v54);
      }
      ReferenceDnsPolicyConfigNode(v4);
      LastError = 0;
    }
LABEL_53:
    ReleaseSRWLockShared(&g_DnsPolicyTableLock);
    if ( !v4 )
      goto LABEL_54;
    v55 = *v3;
    if ( *v3 )
    {
      if ( !v4[5] && v55[5] || !v4[6] && v55[6] )
      {
        v56 = (_QWORD *)Dns_Allocate(96);
        if ( v56 )
        {
          v57 = Dns_CreateStringCopy_W(Src);
          v56[9] = v57;
          if ( v57 )
          {
            InheritDnsPolicyObject(v56, v4);
            InheritDnsPolicyObject(v56, *v3);
            DereferenceDnsPolicyConfigNode(v4);
            DereferenceDnsPolicyConfigNode(*v3);
            ReferenceDnsPolicyConfigNode(v56);
            *v3 = v56;
            LastError = 0;
LABEL_54:
            if ( LastError )
            {
              *v3 = 0;
              if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                WPP_SF_S(1035, 27, WPP_85172e4714023e67c3665ec5069963d4_Traceguids, Src);
            }
            return LastError;
          }
          LastError = GetLastError();
          DnsApiFree(v56);
        }
        else
        {
          LastError = GetLastError();
        }
        DereferenceDnsPolicyConfigNode(v4);
        DereferenceDnsPolicyConfigNode(*v3);
        goto LABEL_54;
      }
      DereferenceDnsPolicyConfigNode(v55);
    }
    LastError = 0;
    *v3 = v4;
    return LastError;
  }
  if ( (v8 & 4) == 0 && (v8 & 0x60) != 0x60 )
    goto LABEL_53;
  if ( v4 )
    *v3 = v4;
  LastError = MatchDnsAnyPolicy(Src, 2, &v60);
  if ( !LastError )
  {
    v4 = v60;
    goto LABEL_53;
  }
  ReleaseSRWLockShared(&g_DnsPolicyTableLock);
  return LastError;
}

```

## disassembly

```asm
0x180019310  mov     [rsp+arg_10], r8
0x180019315  mov     [rsp+arg_8], edx
0x180019319  push    rsi
0x18001931a  push    r12
0x18001931c  push    r13
0x18001931e  push    r14
0x180019320  push    r15
0x180019322  sub     rsp, 60h
0x180019326  xor     r12d, r12d
0x180019329  mov     r13, r8
0x18001932c  mov     r14d, r12d
0x18001932f  mov     [rsp+88h+lpMem], r12
0x180019334  mov     [rsp+88h+var_48], r12
0x180019339  mov     rsi, rcx
0x18001933c  prefetchw byte ptr cs:dword_180112518
0x180019343  mov     eax, cs:dword_180112518
0x180019349  mov     r9d, eax
0x18001934c  lock cmpxchg cs:dword_180112518, r9d
0x180019355  jnz     short loc_180019349
0x180019357  mov     [rsp+88h+arg_0], rbx
0x18001935f  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x180019366  mov     [rsp+88h+var_38], rdi
0x18001936b  mov     r15d, eax
0x18001936e  mov     [rsp+88h+arg_18], eax
0x180019375  call    cs:__imp_AcquireSRWLockShared
0x18001937c  nop     dword ptr [rax+rax+00h]
0x180019381  cmp     cs:dword_18011251C, r12d
0x180019388  jnz     loc_180019932
0x18001938e  mov     [r13+0], r12
0x180019392  mov     rbx, rsi
0x180019395  movzx   ecx, word ptr [rsi]
0x180019398  mov     edi, r12d
0x18001939b  test    cx, cx
0x18001939e  jz      short loc_1800193C0
0x1800193a0  lea     rbx, [rbx+2]
0x1800193a4  call    cs:__imp__o_towlower
0x1800193ab  nop     dword ptr [rax+rax+00h]
0x1800193b0  imul    edi, 21h ; '!'
0x1800193b3  movzx   ecx, ax
0x1800193b6  add     edi, ecx
0x1800193b8  movzx   ecx, word ptr [rbx]
0x1800193bb  test    cx, cx
0x1800193be  jnz     short loc_1800193A0
0x1800193c0  mov     rcx, qword ptr cs:xmmword_180112B70
0x1800193c7  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800193ce  mov     [rsp+88h+var_30], rbp
0x1800193d3  test    rcx, rcx
0x1800193d6  jz      short loc_180019441
0x1800193d8  mov     eax, 20D56B39h
0x1800193dd  mul     edi
0x1800193df  shr     edx, 6
0x1800193e2  imul    eax, edx, 1F3h
0x1800193e8  sub     edi, eax
0x1800193ea  mov     r14d, edi
0x1800193ed  add     r14, r14
0x1800193f0  mov     rdi, [rcx+r14*8]
0x1800193f4  lea     rax, [rcx+r14*8]
0x1800193f8  cmp     rdi, rax
0x1800193fb  jz      short loc_180019441
0x1800193fd  mov     r8, [rdi+40h]; lpString1
0x180019401  lea     rbp, [rdi-8]
0x180019405  test    r8, r8
0x180019408  jz      short loc_18001943C
0x18001940a  mov     [rsp+88h+cchCount2], ebx; cchCount2
0x18001940e  mov     r9d, ebx; cchCount1
0x180019411  mov     edx, 1; dwCmpFlags
0x180019416  mov     [rsp+88h+lpString2], rsi; lpString2
0x18001941b  mov     ecx, 409h; Locale
0x180019420  call    cs:__imp_CompareStringW
0x180019427  nop     dword ptr [rax+rax+00h]
0x18001942c  cmp     eax, 2
0x18001942f  jz      loc_18001981E
0x180019435  mov     rcx, qword ptr cs:xmmword_180112B70
0x18001943c  mov     rdi, [rdi]
0x18001943f  jmp     short loc_1800193F4
0x180019441  mov     edi, 10D8h
0x180019446  mov     rcx, rbx
0x180019449  nop     dword ptr [rax+00000000h]
0x180019450  inc     rcx
0x180019453  cmp     [rsi+rcx*2], r12w
0x180019458  jnz     short loc_180019450
0x18001945a  mov     eax, 2Eh ; '.'
0x18001945f  test    ecx, ecx
0x180019461  jz      loc_18001950E
0x180019467  lea     r14d, [rcx-1]
0x18001946b  cmp     [rsi+r14*2], ax
0x180019470  cmovnz  r14d, ecx
0x180019474  lea     eax, [r14+2]
0x180019478  cmp     eax, r14d
0x18001947b  jb      loc_180019509
0x180019481  add     rax, rax
0x180019484  mov     ecx, 0FFFFFFFFh
0x180019489  cmp     rax, rcx
0x18001948c  ja      short loc_180019509
0x18001948e  mov     ecx, eax
0x180019490  call    Dns_Allocate
0x180019495  mov     r15, rax
0x180019498  test    rax, rax
0x18001949b  jz      short loc_180019501
0x18001949d  mov     rbp, r12
0x1800194a0  mov     r8d, r14d
0x1800194a3  lea     r12, [rax+2]
0x1800194a7  add     r8, r8; Size
0x1800194aa  mov     rcx, r12; void *
0x1800194ad  mov     rdx, rsi; Src
0x1800194b0  call    memcpy_0
0x1800194b5  xor     eax, eax
0x1800194b7  mov     word ptr [r15], 2Eh ; '.'
0x1800194bd  cmp     cs:dword_180111FF8, eax
0x1800194c3  lea     ecx, [r14+1]
0x1800194c7  mov     [r15+rcx*2], ax
0x1800194cc  jnz     loc_1800196D0
0x1800194d2  xor     r12d, r12d
0x1800194d5  mov     rax, cs:g_hProcessHeap
0x1800194dc  test    rax, rax
0x1800194df  jz      loc_1800198B3
0x1800194e5  mov     r8, r15; lpMem
0x1800194e8  xor     edx, edx; dwFlags
0x1800194ea  mov     rcx, rax; hHeap
0x1800194ed  call    cs:__imp_HeapFree
0x1800194f4  nop     dword ptr [rax+rax+00h]
0x1800194f9  test    edi, edi
0x1800194fb  jz      loc_1800198CB
0x180019501  mov     r15d, [rsp+88h+arg_18]
0x180019509  mov     eax, 2Eh ; '.'
0x18001950e  test    byte ptr [rsp+88h+arg_8], 1
0x180019516  mov     rbp, r12
0x180019519  jnz     loc_1800198D8
0x18001951f  mov     edx, eax; Ch
0x180019521  mov     rcx, rsi; Str
0x180019524  call    cs:__imp_wcschr
0x18001952b  nop     dword ptr [rax+rax+00h]
0x180019530  test    rax, rax
0x180019533  jz      loc_1800196A4
0x180019539  cmp     word ptr [rax+2], 0
0x18001953e  jz      loc_1800196A4
0x180019544  mov     r14, [rsp+88h+lpMem]
0x180019549  mov     [r13+0], rbp
0x18001954d  test    edi, edi
0x18001954f  jz      loc_180019635
0x180019555  mov     rdi, cs:qword_180112520
0x18001955c  mov     ebx, 10D8h
0x180019561  mov     [r13+0], r12
0x180019565  test    rdi, rdi
0x180019568  jnz     loc_18001961C
0x18001956e  mov     rbp, [rsp+88h+var_30]
0x180019573  mov     rax, [r13+0]
0x180019577  test    rax, rax
0x18001957a  jnz     short loc_1800195D6
0x18001957c  test    r14, r14
0x18001957f  jnz     loc_18001993C
0x180019585  test    r15b, 4
0x180019589  jnz     short loc_180019599
0x18001958b  and     r15d, 60h
0x18001958f  cmp     r15b, 60h ; '`'
0x180019593  jnz     loc_180019655
0x180019599  test    r14, r14
0x18001959c  jz      short loc_1800195A2
0x18001959e  mov     [r13+0], r14
0x1800195a2  lea     r8, [rsp+88h+var_48]
0x1800195a7  mov     edx, 2
0x1800195ac  mov     rcx, rsi
0x1800195af  call    MatchDnsAnyPolicy
0x1800195b4  mov     ebx, eax
0x1800195b6  test    eax, eax
0x1800195b8  jz      loc_180019AF5
0x1800195be  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x1800195c5  call    cs:__imp_ReleaseSRWLockShared
0x1800195cc  nop     dword ptr [rax+rax+00h]
0x1800195d1  jmp     loc_180019686
0x1800195d6  cmp     qword ptr [rax+30h], 0
0x1800195db  jz      short loc_18001957C
0x1800195dd  mov     eax, r15d
0x1800195e0  and     eax, 60h
0x1800195e3  cmp     al, 60h ; '`'
0x1800195e5  jnz     short loc_180019655
0x1800195e7  test    r15b, 8
0x1800195eb  jnz     short loc_180019655
0x1800195ed  test    r14, r14
0x1800195f0  jnz     loc_180019ABC
0x1800195f6  mov     r14, cs:qword_180112528
0x1800195fd  test    r14, r14
0x180019600  jnz     short loc_18001963D
0x180019602  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x180019609  call    cs:__imp_ReleaseSRWLockShared
0x180019610  nop     dword ptr [rax+rax+00h]
0x180019615  mov     eax, 10D8h
0x18001961a  jmp     short loc_180019688
0x18001961c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180019623  jnz     loc_180019A9E
0x180019629  mov     rcx, rdi
0x18001962c  call    ReferenceDnsPolicyConfigNode
0x180019631  mov     [r13+0], rdi
0x180019635  mov     ebx, r12d
0x180019638  jmp     loc_18001956E
0x18001963d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180019644  jnz     loc_180019AC9
0x18001964a  mov     rcx, r14
0x18001964d  call    ReferenceDnsPolicyConfigNode
0x180019652  mov     ebx, r12d
0x180019655  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x18001965c  call    cs:__imp_ReleaseSRWLockShared
0x180019663  nop     dword ptr [rax+rax+00h]
0x180019668  test    r14, r14
0x18001966b  jnz     loc_180019AFF
0x180019671  test    ebx, ebx
0x180019673  jz      short loc_180019686
0x180019675  mov     [r13+0], r12
0x180019679  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180019680  jnz     loc_18001994C
0x180019686  mov     eax, ebx
0x180019688  mov     rdi, [rsp+88h+var_38]
0x18001968d  mov     rbx, [rsp+88h+arg_0]
0x180019695  add     rsp, 60h
0x180019699  pop     r15
0x18001969b  pop     r14
0x18001969d  pop     r13
0x18001969f  pop     r12
0x1800196a1  pop     rsi
0x1800196a2  retn
0x1800196a4  inc     rbx
0x1800196a7  cmp     word ptr [rsi+rbx*2], 0
0x1800196ac  jnz     short loc_1800196A4
0x1800196ae  cmp     ebx, 3Fh ; '?'
0x1800196b1  jle     loc_1800198D8
0x1800196b7  cmp     ebx, 40h ; '@'
0x1800196ba  jnz     loc_180019544
0x1800196c0  cmp     word ptr [rsi+7Eh], 2Eh ; '.'
0x1800196c5  jnz     loc_180019544
0x1800196cb  jmp     loc_1800198D8
0x1800196d0  movzx   edx, word ptr [r12]
0x1800196d5  mov     r9d, 1
0x1800196db  mov     [rsp+88h+var_58], r9d
0x1800196e0  mov     rcx, r12
0x1800196e3  mov     r8, r12
0x1800196e6  test    dx, dx
0x1800196e9  jz      short loc_18001970B
0x1800196eb  cmp     dx, 2Eh ; '.'
0x1800196ef  lea     eax, [r9+1]
0x1800196f3  movzx   edx, word ptr [rcx+2]
0x1800196f7  lea     rcx, [rcx+2]
0x1800196fb  cmovnz  eax, r9d
0x1800196ff  mov     r9d, eax
0x180019702  test    dx, dx
0x180019705  jnz     short loc_1800196EB
0x180019707  mov     [rsp+88h+var_58], eax
0x18001970b  mov     rcx, r8
0x18001970e  call    GetSuffixHashIndex
0x180019713  mov     rcx, qword ptr cs:xmmword_180112B70
0x18001971a  test    rcx, rcx
0x18001971d  jz      short loc_180019788
0x18001971f  mov     r13d, eax
0x180019722  add     r13, r13
0x180019725  mov     r14, [rcx+r13*8]
0x180019729  nop     dword ptr [rax+00000000h]
0x180019730  lea     rax, [rcx+r13*8]
0x180019734  cmp     r14, rax
0x180019737  jz      short loc_180019786
0x180019739  mov     r8, [r14+40h]; lpString1
0x18001973d  lea     rbp, [r14-8]
0x180019741  test    r8, r8
0x180019744  jz      loc_180019844
0x18001974a  test    r12, r12
0x18001974d  jz      short loc_180019781
0x18001974f  mov     [rsp+88h+cchCount2], ebx; cchCount2
0x180019753  mov     r9d, ebx; cchCount1
0x180019756  mov     edx, 1; dwCmpFlags
0x18001975b  mov     [rsp+88h+lpString2], r12; lpString2
0x180019760  mov     ecx, 409h; Locale
0x180019765  call    cs:__imp_CompareStringW
0x18001976c  nop     dword ptr [rax+rax+00h]
0x180019771  cmp     eax, 2
0x180019774  jz      loc_18001984D
0x18001977a  mov     rcx, qword ptr cs:xmmword_180112B70
0x180019781  mov     r14, [r14]
0x180019784  jmp     short loc_180019730
0x180019786  xor     ebp, ebp
0x180019788  mov     r14d, [rsp+88h+var_58]
0x18001978d  mov     r13, r15
0x180019790  inc     r14d
0x180019793  cmp     r14d, cs:dword_180111FF4
0x18001979a  mov     [rsp+88h+var_58], r14d
0x18001979f  jb      loc_1800198A6
0x1800197a5  mov     rcx, r13
0x1800197a8  call    GetSuffixHashIndex
0x1800197ad  mov     rcx, qword ptr cs:xmmword_180112B70
0x1800197b4  test    rcx, rcx
0x1800197b7  jz      short loc_18001981A
0x1800197b9  mov     r12d, eax
0x1800197bc  add     r12, r12
0x1800197bf  mov     r14, [rcx+r12*8]
0x1800197c3  lea     rax, [rcx+r12*8]
0x1800197c7  cmp     r14, rax
0x1800197ca  jz      short loc_180019815
0x1800197cc  mov     r8, [r14+40h]; lpString1
0x1800197d0  lea     rbp, [r14-8]
0x1800197d4  test    r8, r8
0x1800197d7  jz      loc_180019871
0x1800197dd  test    r13, r13
0x1800197e0  jz      short loc_180019810
  ... truncated ...
```
