# NetrServerAuthenticate3

- ea: `0x18005d780`
- end: `0x18005e18a`
- name: `NetrServerAuthenticate3`
- size: `2570`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *, void *, UCHAR *, int *, _DWORD *)`
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005d6e0`
- `0x18005d730`

## callees

- `0x180007278`
- `0x18000bd98`
- `0x18000e270`
- `0x18000ed34`
- `0x180025708`
- `0x18002601c`
- `0x1800354d8`
- `0x180038e60`
- `0x180038f60`
- `0x18003f054`
- `0x18003f684`
- `0x18004d6e0`
- `0x1800541ac`
- `0x180055a6c`
- `0x18005726c`
- `0x180057a74`
- `0x18005826c`
- `0x180058434`
- `0x1800585a0`
- `0x18005a3a4`
- `0x18005a4a8`
- `0x18005d780`
- `0x18005f810`
- `0x18005fff4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005e11a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005e12c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005e13e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005e11a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005e12c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005e13e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005e108`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005e108`
- `ntdll!RtlLeaveCriticalSection` at `0x18005dd2c`
- `ntdll!RtlLeaveCriticalSection` at `0x18005dd91`
- `ntdll!RtlLeaveCriticalSection` at `0x18005dd2c`
- `ntdll!RtlLeaveCriticalSection` at `0x18005dd91`
- `ntdll!RtlEnterCriticalSection` at `0x18005db0e`
- `ntdll!RtlEnterCriticalSection` at `0x18005db0e`
- `netutils!NetpwNameCompare` at `0x18005db39`
- `netutils!NetpwNameCompare` at `0x18005db39`

## string_xrefs

- `0x18005da60`: `NetrServerAuthenticate: Can't NlGetIncomingPassword for %ws 0x%lx.\n`
- `0x18005daa1`: `NlGetMachineOs completely failed: %#x\n`
- `0x18005dd69`: `NetrServerAuthenticate3: Possible failure in NlComputeCredentials for %ws 0x%lx.\n`
- `0x18005de9b`: `NetrServerAuthenticate: NlComputeCredentials failed for %ws on account %ws\n`

## pseudocode

```c
__int64 __fastcall NetrServerAuthenticate3(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        void *a5,
        UCHAR *a6,
        int *a7,
        _DWORD *a8)
{
  PUCHAR v8; // rsi
  unsigned int *v9; // r13
  struct _DOMAIN_INFO *DomainByServerName; // rdi
  unsigned int v16; // ecx
  unsigned __int16 *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  int v20; // edx
  int v21; // esi
  int v22; // r13d
  int *v23; // rcx
  int IncomingPassword; // eax
  int MachineOs; // eax
  HLOCAL *i; // r12
  _CYPHER_BLOCK v27; // rax
  unsigned int j; // r14d
  struct _LM_OWF_PASSWORD v29; // xmm0
  int SessionKey; // eax
  unsigned __int16 *v31; // rdx
  unsigned __int16 *v32; // r8
  int v33; // r14d
  struct _NL_TRANSPORT *v34; // rax
  PUCHAR v35; // r14
  DWORD dwMinorVersion; // ecx
  DWORD v37; // eax
  int v38; // eax
  bool v39; // zf
  __int64 v40; // rdx
  UCHAR *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rcx
  struct _LM_OWF_PASSWORD *v44; // rax
  __int64 v45; // rcx
  struct _LM_OWF_PASSWORD *v46; // rax
  struct _LM_OWF_PASSWORD *v47; // rax
  unsigned __int16 **v48; // [rsp+20h] [rbp-100h]
  unsigned __int16 **v49; // [rsp+20h] [rbp-100h]
  unsigned __int16 **v50; // [rsp+20h] [rbp-100h]
  unsigned __int16 **v51; // [rsp+28h] [rbp-F8h]
  int v52; // [rsp+88h] [rbp-98h]
  unsigned __int8 v53[4]; // [rsp+A0h] [rbp-80h] BYREF
  unsigned int v54; // [rsp+A4h] [rbp-7Ch]
  unsigned int *v55; // [rsp+A8h] [rbp-78h]
  int v56; // [rsp+B0h] [rbp-70h]
  unsigned int v57; // [rsp+B4h] [rbp-6Ch]
  int v58; // [rsp+B8h] [rbp-68h]
  int v59; // [rsp+BCh] [rbp-64h] BYREF
  int v60; // [rsp+C0h] [rbp-60h] BYREF
  int v61; // [rsp+C4h] [rbp-5Ch] BYREF
  PUCHAR v62; // [rsp+C8h] [rbp-58h]
  int v63; // [rsp+D0h] [rbp-50h]
  _DWORD *v64; // [rsp+D8h] [rbp-48h]
  PSID pSid; // [rsp+E0h] [rbp-40h] BYREF
  void *Block; // [rsp+E8h] [rbp-38h] BYREF
  unsigned __int16 *v67; // [rsp+F0h] [rbp-30h] BYREF
  unsigned __int16 *v68; // [rsp+F8h] [rbp-28h] BYREF
  void *v69; // [rsp+100h] [rbp-20h]
  _CYPHER_BLOCK v70; // [rsp+108h] [rbp-18h] BYREF
  UCHAR pbOutput[8]; // [rsp+110h] [rbp-10h] BYREF
  UCHAR pbInput[8]; // [rsp+118h] [rbp-8h] BYREF
  UCHAR pbSecret[16]; // [rsp+120h] [rbp+0h] BYREF
  struct _LM_OWF_PASSWORD v74; // [rsp+130h] [rbp+10h] BYREF
  struct _LM_OWF_PASSWORD v75; // [rsp+140h] [rbp+20h] BYREF
  struct _LM_OWF_PASSWORD v76; // [rsp+150h] [rbp+30h] BYREF
  _OSVERSIONINFOEXW v77; // [rsp+160h] [rbp+40h] BYREF
  unsigned __int16 *v78[2]; // [rsp+280h] [rbp+160h] BYREF
  __int64 v79; // [rsp+290h] [rbp+170h]
  unsigned __int16 v80[72]; // [rsp+2A0h] [rbp+180h] BYREF

  v8 = a6;
  v9 = (unsigned int *)a7;
  v69 = a5;
  v57 = a3;
  v64 = a8;
  v62 = a6;
  v55 = (unsigned int *)a7;
  *(_DWORD *)v53 = 0;
  *(_QWORD *)pbOutput = 0;
  *(_OWORD *)pbSecret = 0;
  *(_QWORD *)pbInput = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v70 = 0;
  v61 = 0;
  v60 = 0;
  pSid = 0;
  Block = 0;
  v67 = 0;
  v68 = 0;
  v59 = 0;
  memset_0(v80, 0, 0x82u);
  if ( NlGlobalMemberWorkstation )
    return 3221225659LL;
  v54 = 0;
  NlpTraceServerAuthEvent(1, a4, a2, a3, a7, 0);
  DomainByServerName = NlFindDomainByServerName(a1);
  *(_DWORD *)v53 = NlpGetClientAddress(v16, v80);
  v17 = v80;
  if ( *(int *)v53 < 0 )
    v17 = L"<unavailable>";
  NlPrintDomRoutine(
    0x200u,
    DomainByServerName,
    L"NetrServerAuthenticate entered: %ws (%ws) on account %ws (Negot: %lx)\n",
    a4,
    v17,
    a2,
    *a7);
  v18 = 8;
  if ( !DomainByServerName )
  {
    *(_DWORD *)v53 = -1073741534;
LABEL_75:
    *(_OWORD *)v78 = 0;
    v79 = 0;
    do
    {
      *v8++ = 0;
      --v18;
    }
    while ( v18 );
    v39 = *(_DWORD *)v53 == -1073741429;
    v78[0] = a4;
    v78[1] = a2;
    *v64 = 0;
    if ( v39 )
    {
      NlpWriteEventlogEx(0x165Bu, 1u, 0, 0xFFFFFFFF, v78, 2u, v53, 4u);
    }
    else if ( *(_DWORD *)v53 != -1073741790 || !v54 )
    {
      v79 = *(int *)v53;
      NlpWriteEventlogEx(0x165Au, 1u, 0x80000000, 0xFFFFFFFF, v78, 3u, v53, 4u);
    }
    if ( !DomainByServerName )
      goto LABEL_84;
    goto LABEL_83;
  }
  if ( a3 == 5 )
  {
    NlPrintRoutine(0x100u, L"NetrServerAuthenticate from LM 2.x (disallowed).\n");
    *(_DWORD *)v53 = -1073741790;
LABEL_74:
    v18 = 8;
    goto LABEL_75;
  }
  v19 = *a7;
  v20 = dword_1800F1310 & *a7;
  *a7 = v20;
  v63 = v19;
  if ( !dword_1800F1248 && (v20 & 0x1004000) == 0 )
  {
    NlPrintRoutine(
      0x200u,
      L"NetrServerAuthenticate3: the client %ws is asking for NT4 crypto and this server disallows it.\n",
      a2);
    *(_DWORD *)v53 = -1073740920;
    goto LABEL_74;
  }
  if ( a3 - 3 <= 1 )
  {
    v21 = 1;
    v56 = 1;
    v22 = 1;
  }
  else
  {
    v21 = 0;
    v56 = 0;
    v22 = a3 - 6 > 1 ? 2 : 0;
  }
  if ( (v20 & 0x1000000) == 0 )
  {
    if ( dword_1800F1294 )
    {
      NlpLogRc4Usage(1, a2, DomainByServerName, v80, v22, v20);
      NlPrintRoutine(
        0x200u,
        L"NetrServerAuthenticate3: the client %ws is asking for MD5 and this server disallows it.\n",
        a2);
      *(_DWORD *)v53 = -1073740920;
LABEL_18:
      v9 = v55;
      v18 = 8;
      v8 = v62;
      goto LABEL_75;
    }
    NlpLogRc4Usage(0, a2, DomainByServerName, v80, v22, v20);
  }
  v23 = &v59;
  if ( a3 != 7 )
    v23 = 0;
  IncomingPassword = NlGetIncomingPassword(
                       DomainByServerName,
                       a2,
                       a3,
                       0,
                       1,
                       &v74,
                       (unsigned __int64)&v75 & -(__int64)(v21 != 0),
                       v64,
                       &v61,
                       &v60,
                       &pSid,
                       0,
                       v23);
  *(_DWORD *)v53 = IncomingPassword;
  if ( IncomingPassword < 0 )
  {
    LODWORD(v48) = IncomingPassword;
    NlPrintDomRoutine(
      0x100u,
      DomainByServerName,
      L"NetrServerAuthenticate: Can't NlGetIncomingPassword for %ws 0x%lx.\n",
      a2,
      v48);
LABEL_24:
    v9 = v55;
    goto LABEL_70;
  }
  if ( v22 != 1 )
  {
    MachineOs = NlGetMachineOs(a2, (unsigned __int16 **)&Block, &v67, &v68);
    *(_DWORD *)v53 = MachineOs;
    if ( MachineOs < 0 )
    {
      NlPrintRoutine(0x200u, L"NlGetMachineOs completely failed: %#x\n", (unsigned int)MachineOs);
      goto LABEL_24;
    }
  }
  v58 = 0;
  NlPrintRoutine(0x4000000u, L"NetrServerAuthenticate: Password for account %ws = ", a2);
  NlpDumpBuffer(0x4000000u, &v74, 0x10u);
  if ( v21 )
  {
    NlPrintRoutine(0x4000000u, L"NetrServerAuthenticate: Previous Password for account %ws = ", a2);
    NlpDumpBuffer(0x4000000u, &v75, 0x10u);
  }
  RtlEnterCriticalSection(&NlGlobalChallengeCritSect);
  NlScavengeOldChallenges();
  for ( i = (HLOCAL *)NlGlobalChallengeList; i != &NlGlobalChallengeList; i = (HLOCAL *)*i )
  {
    if ( (unsigned int)NetpwNameCompare(a4, i + 6, 4) )
      continue;
    *(_QWORD *)pbInput = i[3];
    v27 = (_CYPHER_BLOCK)i[2];
    ++v54;
    v70 = v27;
    NlPrintRoutine(0x4000000u, L"NetrServerAuthenticate: ClientChallenge %lu = ", v54);
    NlpDumpBuffer(0x4000000u, &v70, 8u);
    NlPrintRoutine(0x4000000u, L"NetrServerAuthenticate: ServerChallenge %lu = ", v54);
    NlpDumpBuffer(0x4000000u, pbInput, 8u);
    if ( NlIsChallengeVulnerable(&v70) )
      continue;
    for ( j = 0; j < 2; ++j )
    {
      if ( j )
      {
        if ( !v56 )
          break;
        v29 = v75;
      }
      else
      {
        v29 = v74;
      }
      v76 = v29;
      SessionKey = NlMakeSessionKey(
                     *v55,
                     &v76,
                     &v70,
                     (struct _CYPHER_BLOCK *)pbInput,
                     (struct _NETLOGON_SESSION_KEY *)pbSecret);
      *(_DWORD *)v53 = SessionKey;
      if ( SessionKey < 0 )
      {
        v32 = L"NetrServerAuthenticate: Can't NlMakeSessionKey for %ws 0x%lx.\n";
        goto LABEL_51;
      }
      NlPrintRoutine(0x4000000u, L"NetrServerAuthenticate: SessionKey %lu = ", j);
      NlpDumpBuffer(0x4000000u, pbSecret, 0x10u);
      SessionKey = NlComputeCredentials((PUCHAR)&v70, pbOutput, pbSecret, *v55);
      *(_DWORD *)v53 = SessionKey;
      if ( SessionKey < 0 )
      {
        v32 = L"NetrServerAuthenticate3: Possible failure in NlComputeCredentials for %ws 0x%lx.\n";
LABEL_51:
        LODWORD(v49) = SessionKey;
        NlPrintDomRoutine(0x100u, DomainByServerName, v32, a2, v49);
        RtlLeaveCriticalSection(&NlGlobalChallengeCritSect);
        goto LABEL_24;
      }
      NlPrintRoutine(0x4000000u, L"NetrServerAuthenticate: ClientCredential %lu GOT  = ", j);
      NlpDumpBuffer(0x4000000u, v69, 8u);
      NlPrintRoutine(0x4000000u, L"NetrServerAuthenticate: ClientCredential %lu MADE = ", j);
      NlpDumpBuffer(0x4000000u, pbOutput, 8u);
      if ( *(_QWORD *)v69 == *(_QWORD *)pbOutput )
      {
        v58 = 1;
        goto LABEL_46;
      }
      NlPrintDomRoutine(
        0x100u,
        DomainByServerName,
        L"NetrServerAuthenticate: Bad password %lu for %ws on account %ws\n",
        j,
        a4,
        a2);
    }
    if ( !(unsigned int)NlStrArrayContains((unsigned __int16 *)i[5], a2) )
      NlStrArrayAppendStr((unsigned __int16 **)i + 5, v31);
  }
LABEL_46:
  RtlLeaveCriticalSection(&NlGlobalChallengeCritSect);
  if ( !v58 )
  {
    NlPrintDomRoutine(
      0x100u,
      DomainByServerName,
      L"NetrServerAuthenticate: Failed to authenticate %ws on account %ws\n",
      a4,
      a2);
    *(_DWORD *)v53 = -1073741790;
    goto LABEL_18;
  }
  NlRemoveChallengeForClient(a4, a2, v56);
  v33 = v59;
  if ( v57 == 6 )
    v34 = NlTransportLookup(a4);
  else
    v34 = 0;
  v52 = v22;
  v9 = v55;
  *(_DWORD *)v53 = NlInsertServerSession(
                     DomainByServerName,
                     a4,
                     a2,
                     v57,
                     2,
                     v61,
                     v60,
                     pSid,
                     *v64,
                     *v55,
                     v63,
                     v34,
                     pbSecret,
                     pbOutput,
                     Block,
                     v67,
                     v68,
                     v52,
                     v33);
  if ( *(int *)v53 < 0 )
  {
    NlPrintDomRoutine(
      0x100u,
      DomainByServerName,
      L"NetrServerAuthenticate: NlInsertServerSession failed for %ws on account %ws\n",
      a4,
      a2);
    goto LABEL_70;
  }
  v35 = v62;
  *(_DWORD *)v53 = NlComputeCredentials(pbInput, v62, pbSecret, *v55);
  if ( *(int *)v53 < 0 )
  {
    NlPrintDomRoutine(
      0x100u,
      DomainByServerName,
      L"NetrServerAuthenticate: NlComputeCredentials failed for %ws on account %ws\n",
      a4,
      a2);
    goto LABEL_70;
  }
  NlPrintRoutine(0x4000000u, L"NetrServerAuthenticate: ServerCredential SEND = ");
  NlpDumpBuffer(0x4000000u, v35, 8u);
  if ( !v56 && (*v55 & 0xBFFFFE00) == 0 )
  {
    memset_0(&v77.dwMajorVersion, 0, 0x118u);
    v77.dwOSVersionInfoSize = 284;
    if ( *v55 )
    {
      if ( (*v55 & 0xFFFFFF00) != 0 )
      {
        dwMinorVersion = v77.dwMinorVersion;
        v37 = 4;
LABEL_67:
        LODWORD(v51) = dwMinorVersion;
        v77.dwMajorVersion = v37;
        LODWORD(v50) = v37;
        NlPrintDomRoutine(
          0x200u,
          DomainByServerName,
          L"NetrServerAuthenticate: %ws is running NT %ld.%ld\n",
          a4,
          v50,
          v51);
        v38 = NlSetClientAttributes(a4, 1, 0, &v77, L"Windows NT", 0, 0, 0);
        *(_DWORD *)v53 = v38;
        if ( v38 < 0 )
          NlPrintDomRoutine(
            0x100u,
            DomainByServerName,
            L"NetrServerAuthenticate: Cannot set client DNS host name %lx (ignoring)\n",
            (unsigned int)v38);
        goto LABEL_69;
      }
      dwMinorVersion = 5;
    }
    else
    {
      dwMinorVersion = 1;
    }
    v37 = 3;
    v77.dwMinorVersion = dwMinorVersion;
    goto LABEL_67;
  }
LABEL_69:
  LODWORD(v51) = *v55;
  *(_DWORD *)v53 = 0;
  NlPrintDomRoutine(
    0x200u,
    DomainByServerName,
    L"NetrServerAuthenticate returns Success: %ws on account %ws (Negot: %lx)\n",
    a4,
    a2,
    v51);
LABEL_70:
  if ( *(_DWORD *)v53 == -1073741724 )
    *(_DWORD *)v53 = -1073741429;
  if ( *(int *)v53 < 0 )
  {
    v8 = v62;
    goto LABEL_74;
  }
LABEL_83:
  NlDereferenceDomain(DomainByServerName);
LABEL_84:
  v40 = 16;
  v41 = pbSecret;
  v42 = 16;
  do
  {
    *v41++ = 0;
    --v42;
  }
  while ( v42 );
  v43 = 16;
  v44 = &v74;
  do
  {
    v44->data[0].data[0] = 0;
    v44 = (struct _LM_OWF_PASSWORD *)((char *)v44 + 1);
    --v43;
  }
  while ( v43 );
  v45 = 16;
  v46 = &v75;
  do
  {
    v46->data[0].data[0] = 0;
    v46 = (struct _LM_OWF_PASSWORD *)((char *)v46 + 1);
    --v45;
  }
  while ( v45 );
  v47 = &v76;
  do
  {
    v47->data[0].data[0] = 0;
    v47 = (struct _LM_OWF_PASSWORD *)((char *)v47 + 1);
    --v40;
  }
  while ( v40 );
  if ( pSid )
    FreeSid(pSid);
  if ( Block )
    free(Block);
  if ( v67 )
    free(v67);
  if ( v68 )
    free(v68);
  NlpTraceServerAuthEvent(2, a4, a2, v57, v9, *(_DWORD *)v53);
  return *(unsigned int *)v53;
}

```

## disassembly

```asm
0x18005d780  push    rbp
0x18005d782  push    rbx
0x18005d783  push    rsi
0x18005d784  push    rdi
0x18005d785  push    r12
0x18005d787  push    r13
0x18005d789  push    r14
0x18005d78b  push    r15
0x18005d78d  lea     rbp, [rsp-228h]
0x18005d795  sub     rsp, 348h
0x18005d79c  mov     rax, cs:__security_cookie
0x18005d7a3  xor     rax, rsp
0x18005d7a6  mov     [rbp+260h+var_50], rax
0x18005d7ad  mov     rax, [rbp+260h+arg_20]
0x18005d7b4  xor     r14d, r14d
0x18005d7b7  mov     rsi, [rbp+260h+arg_28]
0x18005d7be  xorps   xmm0, xmm0
0x18005d7c1  mov     r13, [rbp+260h+arg_30]
0x18005d7c8  xorps   xmm1, xmm1
0x18005d7cb  mov     [rbp+260h+var_280], rax
0x18005d7cf  mov     r12d, r8d
0x18005d7d2  mov     rax, [rbp+260h+arg_38]
0x18005d7d9  mov     rbx, rdx
0x18005d7dc  mov     [rbp+260h+var_2CC], r8d
0x18005d7e0  mov     rdi, rcx
0x18005d7e3  xor     edx, edx; Val
0x18005d7e5  mov     [rbp+260h+var_2A8], rax
0x18005d7e9  mov     r8d, 82h; Size
0x18005d7ef  mov     [rbp+260h+var_2B8], rsi
0x18005d7f3  lea     rcx, [rbp+260h+var_E0]; void *
0x18005d7fa  mov     [rbp+260h+var_2D8], r13
0x18005d7fe  mov     r15, r9
0x18005d801  mov     dword ptr [rbp+260h+var_2E0], r14d
0x18005d805  mov     qword ptr [rbp+260h+pbOutput], r14
0x18005d809  movups  xmmword ptr [rbp+260h+pbSecret], xmm0
0x18005d80d  mov     qword ptr [rbp+260h+pbInput], r14
0x18005d811  movdqa  [rbp+260h+var_250], xmm1
0x18005d816  movdqa  [rbp+260h+var_240], xmm0
0x18005d81b  movdqa  xmmword ptr [rbp+260h+var_230.data.data], xmm1
0x18005d820  mov     qword ptr [rbp+260h+var_278.data], r14
0x18005d824  mov     [rbp+260h+var_2BC], r14d
0x18005d828  mov     [rbp+260h+var_2C0], r14d
0x18005d82c  mov     [rbp+260h+pSid], r14
0x18005d830  mov     [rbp+260h+Block], r14
0x18005d834  mov     [rbp+260h+var_290], r14
0x18005d838  mov     [rbp+260h+var_288], r14
0x18005d83c  mov     [rbp+260h+var_2C4], r14d
0x18005d840  call    memset_0
0x18005d845  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r14d; int NlGlobalMemberWorkstation
0x18005d84c  jz      short loc_18005D858
0x18005d84e  mov     eax, 0C00000BBh
0x18005d853  jmp     loc_18005E167
0x18005d858  mov     dword ptr [rsp+380h+var_358], r14d
0x18005d85d  mov     r9d, r12d
0x18005d860  mov     r8, rbx
0x18005d863  mov     [rsp+380h+var_360], r13
0x18005d868  mov     rdx, r15
0x18005d86b  mov     [rbp+260h+var_2DC], r14d
0x18005d86f  mov     ecx, 1
0x18005d874  call    ?NlpTraceServerAuthEvent@@YAXKPEAG0W4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAKJ@Z; NlpTraceServerAuthEvent(ulong,ushort *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong *,long)
0x18005d879  mov     rcx, rdi; unsigned __int16 *
0x18005d87c  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18005d881  lea     rdx, [rbp+260h+var_E0]; unsigned __int16 *
0x18005d888  mov     rdi, rax
0x18005d88b  call    ?NlpGetClientAddress@@YAJKPEAG@Z; NlpGetClientAddress(ulong,ushort *)
0x18005d890  lea     rcx, aUnavailable_0; "<unavailable>"
0x18005d897  mov     dword ptr [rbp+260h+var_2E0], eax
0x18005d89a  test    eax, eax
0x18005d89c  lea     rdx, [rbp+260h+var_E0]
0x18005d8a3  mov     r9, r15
0x18005d8a6  lea     r8, aNetrserverauth_22; "NetrServerAuthenticate entered: %ws (%w"...
0x18005d8ad  cmovs   rdx, rcx
0x18005d8b1  mov     ecx, [r13+0]
0x18005d8b5  mov     dword ptr [rsp+380h+var_350], ecx
0x18005d8b9  mov     ecx, 200h; unsigned int
0x18005d8be  mov     [rsp+380h+var_358], rbx
0x18005d8c3  mov     [rsp+380h+var_360], rdx
0x18005d8c8  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005d8cb  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005d8d0  mov     eax, 8
0x18005d8d5  lea     r14d, [rax+8]
0x18005d8d9  test    rdi, rdi
0x18005d8dc  jnz     short loc_18005D8EA
0x18005d8de  mov     dword ptr [rbp+260h+var_2E0], 0C0000122h
0x18005d8e5  jmp     loc_18005DFE9
0x18005d8ea  cmp     r12d, 5
0x18005d8ee  jnz     short loc_18005D90D
0x18005d8f0  lea     rdx, aNetrserverauth_18; "NetrServerAuthenticate from LM 2.x (dis"...
0x18005d8f7  mov     ecx, 100h; unsigned int
0x18005d8fc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005d901  mov     dword ptr [rbp+260h+var_2E0], 0C0000022h
0x18005d908  jmp     loc_18005DFE4
0x18005d90d  mov     eax, [r13+0]
0x18005d911  mov     edx, eax
0x18005d913  and     edx, cs:dword_1800F1310
0x18005d919  mov     [r13+0], edx
0x18005d91d  cmp     cs:dword_1800F1248, 0
0x18005d924  mov     [rbp+260h+var_2B0], eax
0x18005d927  jnz     short loc_18005D951
0x18005d929  test    edx, 1004000h
0x18005d92f  jnz     short loc_18005D951
0x18005d931  mov     r8, rbx
0x18005d934  lea     rdx, aNetrserverauth_15; "NetrServerAuthenticate3: the client %ws"...
0x18005d93b  mov     ecx, 200h; unsigned int
0x18005d940  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005d945  mov     dword ptr [rbp+260h+var_2E0], 0C0000388h
0x18005d94c  jmp     loc_18005DFE4
0x18005d951  lea     eax, [r12-3]
0x18005d956  mov     ecx, 1
0x18005d95b  cmp     eax, ecx
0x18005d95d  jbe     short loc_18005D974
0x18005d95f  xor     esi, esi
0x18005d961  lea     eax, [r12-6]
0x18005d966  cmp     ecx, eax
0x18005d968  mov     [rbp+260h+var_2D0], esi
0x18005d96b  sbb     r13d, r13d
0x18005d96e  and     r13d, 2
0x18005d972  jmp     short loc_18005D97C
0x18005d974  mov     esi, ecx
0x18005d976  mov     [rbp+260h+var_2D0], ecx
0x18005d979  mov     r13d, ecx
0x18005d97c  bt      edx, 18h
0x18005d980  jb      short loc_18005D9DD
0x18005d982  cmp     cs:dword_1800F1294, 0
0x18005d989  lea     r9, [rbp+260h+var_E0]
0x18005d990  mov     dword ptr [rsp+380h+var_358], edx
0x18005d994  mov     r8, rdi
0x18005d997  mov     dword ptr [rsp+380h+var_360], r13d
0x18005d99c  mov     rdx, rbx
0x18005d99f  jz      short loc_18005D9D6
0x18005d9a1  mov     r14, rcx
0x18005d9a4  call    ?NlpLogRc4Usage@@YAXHPEAGPEAU_DOMAIN_INFO@@0W4ACCOUNT_TYPE@@K@Z; NlpLogRc4Usage(int,ushort *,_DOMAIN_INFO *,ushort *,ACCOUNT_TYPE,ulong)
0x18005d9a9  mov     r8, rbx
0x18005d9ac  lea     rdx, aNetrserverauth_19; "NetrServerAuthenticate3: the client %ws"...
0x18005d9b3  mov     ecx, 200h; unsigned int
0x18005d9b8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005d9bd  mov     dword ptr [rbp+260h+var_2E0], 0C0000388h
0x18005d9c4  mov     r13, [rbp+260h+var_2D8]
0x18005d9c8  mov     eax, 8
0x18005d9cd  mov     rsi, [rbp+260h+var_2B8]
0x18005d9d1  jmp     loc_18005DFEF
0x18005d9d6  xor     ecx, ecx
0x18005d9d8  call    ?NlpLogRc4Usage@@YAXHPEAGPEAU_DOMAIN_INFO@@0W4ACCOUNT_TYPE@@K@Z; NlpLogRc4Usage(int,ushort *,_DOMAIN_INFO *,ushort *,ACCOUNT_TYPE,ulong)
0x18005d9dd  xor     eax, eax
0x18005d9df  lea     rcx, [rbp+260h+var_2C4]
0x18005d9e3  cmp     r12d, 7
0x18005d9e7  mov     r8d, r12d
0x18005d9ea  cmovnz  rcx, rax
0x18005d9ee  mov     eax, esi
0x18005d9f0  mov     [rsp+380h+var_320], rcx
0x18005d9f5  neg     eax
0x18005d9f7  mov     [rsp+380h+var_328], 0
0x18005da00  lea     rax, [rbp+260h+var_240]
0x18005da04  sbb     rdx, rdx
0x18005da07  mov     rcx, rdi
0x18005da0a  and     rdx, rax
0x18005da0d  xor     r9d, r9d
0x18005da10  lea     rax, [rbp+260h+pSid]
0x18005da14  mov     [rsp+380h+var_330], rax
0x18005da19  lea     rax, [rbp+260h+var_2C0]
0x18005da1d  mov     [rsp+380h+var_338], rax
0x18005da22  lea     rax, [rbp+260h+var_2BC]
0x18005da26  mov     [rsp+380h+var_340], rax
0x18005da2b  mov     rax, [rbp+260h+var_2A8]
0x18005da2f  mov     [rsp+380h+var_348], rax
0x18005da34  lea     rax, [rbp+260h+var_250]
0x18005da38  mov     [rsp+380h+var_350], rdx
0x18005da3d  mov     rdx, rbx
0x18005da40  mov     [rsp+380h+var_358], rax
0x18005da45  mov     dword ptr [rsp+380h+var_360], 1
0x18005da4d  call    ?NlGetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEBGW4_NETLOGON_SECURE_CHANNEL_TYPE@@KHPEAU_LM_OWF_PASSWORD@@3PEAK44PEAPEAXPEAH4@Z; NlGetIncomingPassword(_DOMAIN_INFO *,ushort const *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,int,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,ulong *,ulong *,ulong *,void * *,int *,ulong *)
0x18005da52  mov     dword ptr [rbp+260h+var_2E0], eax
0x18005da55  test    eax, eax
0x18005da57  jns     short loc_18005DA7D
0x18005da59  mov     r9, rbx
0x18005da5c  mov     dword ptr [rsp+380h+var_360], eax
0x18005da60  lea     r8, aNetrserverauth_3; "NetrServerAuthenticate: Can't NlGetInco"...
0x18005da67  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005da6a  mov     ecx, 100h; unsigned int
0x18005da6f  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005da74  mov     r13, [rbp+260h+var_2D8]
0x18005da78  jmp     loc_18005DFC6
0x18005da7d  cmp     r13d, 1
0x18005da81  jz      short loc_18005DAB4
0x18005da83  lea     r9, [rbp+260h+var_288]; unsigned __int16 **
0x18005da87  mov     rcx, rbx; unsigned __int16 *
0x18005da8a  lea     r8, [rbp+260h+var_290]; unsigned __int16 **
0x18005da8e  lea     rdx, [rbp+260h+Block]; unsigned __int16 **
0x18005da92  call    ?NlGetMachineOs@@YAJPEBGPEAPEAG11@Z; NlGetMachineOs(ushort const *,ushort * *,ushort * *,ushort * *)
0x18005da97  mov     dword ptr [rbp+260h+var_2E0], eax
0x18005da9a  test    eax, eax
0x18005da9c  jns     short loc_18005DAB4
0x18005da9e  mov     r8d, eax
0x18005daa1  lea     rdx, aNlgetmachineos; "NlGetMachineOs completely failed: %#x\n"
0x18005daa8  mov     ecx, 200h; unsigned int
0x18005daad  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005dab2  jmp     short loc_18005DA74
0x18005dab4  mov     r12d, 4000000h
0x18005daba  mov     [rbp+260h+var_2C8], 0
0x18005dac1  mov     ecx, r12d; unsigned int
0x18005dac4  lea     rdx, aNetrserverauth_16; "NetrServerAuthenticate: Password for ac"...
0x18005dacb  mov     r8, rbx
0x18005dace  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005dad3  mov     r8d, r14d; unsigned int
0x18005dad6  lea     rdx, [rbp+260h+var_250]; void *
0x18005dada  mov     ecx, r12d; unsigned int
0x18005dadd  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005dae2  test    esi, esi
0x18005dae4  jz      short loc_18005DB07
0x18005dae6  mov     r8, rbx
0x18005dae9  lea     rdx, aNetrserverauth_20; "NetrServerAuthenticate: Previous Passwo"...
0x18005daf0  mov     ecx, r12d; unsigned int
0x18005daf3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005daf8  mov     r8d, r14d; unsigned int
0x18005dafb  lea     rdx, [rbp+260h+var_240]; void *
0x18005daff  mov     ecx, r12d; unsigned int
0x18005db02  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005db07  lea     rcx, ?NlGlobalChallengeCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005db0e  call    cs:__imp_RtlEnterCriticalSection
0x18005db14  call    ?NlScavengeOldChallenges@@YAXXZ; NlScavengeOldChallenges(void)
0x18005db19  mov     r12, cs:?NlGlobalChallengeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChallengeList
0x18005db20  mov     esi, 100h
0x18005db25  jmp     loc_18005DD0F
0x18005db2a  xor     r9d, r9d
0x18005db2d  lea     rdx, [r12+30h]
0x18005db32  mov     rcx, r15
0x18005db35  lea     r8d, [r9+4]
0x18005db39  call    cs:__imp_NetpwNameCompare
0x18005db3f  test    eax, eax
0x18005db41  jnz     loc_18005DD0B
0x18005db47  mov     rax, [r12+18h]
0x18005db4c  lea     rdx, aNetrserverauth_10; "NetrServerAuthenticate: ClientChallenge"...
0x18005db53  mov     ecx, [rbp+260h+var_2DC]
0x18005db56  inc     ecx
0x18005db58  mov     qword ptr [rbp+260h+pbInput], rax
0x18005db5c  mov     rax, [r12+10h]
0x18005db61  mov     r8d, ecx
0x18005db64  mov     [rbp+260h+var_2DC], ecx
0x18005db67  mov     ecx, 4000000h; unsigned int
0x18005db6c  mov     qword ptr [rbp+260h+var_278.data], rax
0x18005db70  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005db75  mov     r14d, 8
0x18005db7b  lea     rdx, [rbp+260h+var_278]; void *
0x18005db7f  mov     r8d, r14d; unsigned int
0x18005db82  mov     ecx, 4000000h; unsigned int
0x18005db87  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005db8c  mov     r8d, [rbp+260h+var_2DC]
0x18005db90  lea     rdx, aNetrserverauth_32; "NetrServerAuthenticate: ServerChallenge"...
0x18005db97  mov     ecx, 4000000h; unsigned int
0x18005db9c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005dba1  mov     r8d, r14d; unsigned int
0x18005dba4  lea     rdx, [rbp+260h+pbInput]; void *
0x18005dba8  mov     ecx, 4000000h; unsigned int
0x18005dbad  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005dbb2  lea     rcx, [rbp+260h+var_278]; struct _CYPHER_BLOCK *
0x18005dbb6  call    ?NlIsChallengeVulnerable@@YAEQEAU_CYPHER_BLOCK@@@Z; NlIsChallengeVulnerable(_CYPHER_BLOCK * const)
0x18005dbbb  test    al, al
0x18005dbbd  jnz     loc_18005DD0B
0x18005dbc3  xor     r14d, r14d
0x18005dbc6  test    r14d, r14d
0x18005dbc9  jnz     short loc_18005DBD1
0x18005dbcb  movaps  xmm0, [rbp+260h+var_250]
0x18005dbcf  jmp     short loc_18005DBE9
0x18005dbd1  cmp     r14d, 1
0x18005dbd5  jnz     loc_18005DCF0
0x18005dbdb  cmp     [rbp+260h+var_2D0], 0
0x18005dbdf  jz      loc_18005DCF0
0x18005dbe5  movaps  xmm0, [rbp+260h+var_240]
0x18005dbe9  mov     rcx, [rbp+260h+var_2D8]
0x18005dbed  lea     rax, [rbp+260h+pbSecret]
0x18005dbf1  lea     r9, [rbp+260h+pbInput]; struct _CYPHER_BLOCK *
0x18005dbf5  movdqa  xmmword ptr [rbp+260h+var_230.data.data], xmm0
0x18005dbfa  lea     r8, [rbp+260h+var_278]; struct _CYPHER_BLOCK *
0x18005dbfe  mov     [rsp+380h+var_360], rax; struct _NETLOGON_SESSION_KEY *
0x18005dc03  lea     rdx, [rbp+260h+var_230]; struct _LM_OWF_PASSWORD *
0x18005dc07  mov     ecx, [rcx]; unsigned int
0x18005dc09  call    ?NlMakeSessionKey@@YAJKPEAU_LM_OWF_PASSWORD@@PEAU_CYPHER_BLOCK@@1PEAU_NETLOGON_SESSION_KEY@@@Z; NlMakeSessionKey(ulong,_LM_OWF_PASSWORD *,_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *)
0x18005dc0e  mov     dword ptr [rbp+260h+var_2E0], eax
0x18005dc11  test    eax, eax
0x18005dc13  js      loc_18005DD72
0x18005dc19  mov     r8d, r14d
0x18005dc1c  lea     rdx, aNetrserverauth_25; "NetrServerAuthenticate: SessionKey %lu "...
0x18005dc23  mov     ecx, 4000000h; unsigned int
0x18005dc28  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005dc2d  mov     r8d, 10h; unsigned int
0x18005dc33  lea     rdx, [rbp+260h+pbSecret]; void *
0x18005dc37  mov     ecx, 4000000h; unsigned int
0x18005dc3c  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005dc41  mov     rax, [rbp+260h+var_2D8]
0x18005dc45  lea     r8, [rbp+260h+pbSecret]; pbSecret
0x18005dc49  lea     rdx, [rbp+260h+pbOutput]; pbOutput
0x18005dc4d  lea     rcx, [rbp+260h+var_278]; pbInput
0x18005dc51  mov     r9d, [rax]; unsigned int
0x18005dc54  call    ?NlComputeCredentials@@YAJPEAU_CYPHER_BLOCK@@0PEAU_NETLOGON_SESSION_KEY@@K@Z; NlComputeCredentials(_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,ulong)
0x18005dc59  mov     dword ptr [rbp+260h+var_2E0], eax
0x18005dc5c  test    eax, eax
0x18005dc5e  js      loc_18005DD69
0x18005dc64  mov     r8d, r14d
0x18005dc67  lea     rdx, aNetrserverauth_28; "NetrServerAuthenticate: ClientCredentia"...
0x18005dc6e  mov     ecx, 4000000h; unsigned int
  ... truncated ...
```
