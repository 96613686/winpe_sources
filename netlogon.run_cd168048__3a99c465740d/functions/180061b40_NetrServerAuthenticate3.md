# NetrServerAuthenticate3

- ea: `0x180061b40`
- end: `0x18006257b`
- name: `NetrServerAuthenticate3`
- size: `2619`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180061aa0`
- `0x180061af0`

## callees

- `0x180007518`
- `0x18000c440`
- `0x18000e910`
- `0x18000f3e4`
- `0x1800267ec`
- `0x1800271d4`
- `0x1800374dc`
- `0x18003b0f0`
- `0x18003b1fc`
- `0x180041944`
- `0x180041fbc`
- `0x180050cb0`
- `0x180057c4c`
- `0x180059750`
- `0x18005b0bc`
- `0x18005b950`
- `0x18005c1ac`
- `0x18005c38c`
- `0x18005c514`
- `0x18005e540`
- `0x18005e660`
- `0x180061b40`
- `0x180063cac`
- `0x1800644f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800624f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062510`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062528`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800624f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062510`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180062528`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800624e0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800624e0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800620f8`
- `ntdll!RtlLeaveCriticalSection` at `0x180062163`
- `ntdll!RtlLeaveCriticalSection` at `0x1800620f8`
- `ntdll!RtlLeaveCriticalSection` at `0x180062163`
- `ntdll!RtlEnterCriticalSection` at `0x180061ece`
- `ntdll!RtlEnterCriticalSection` at `0x180061ece`
- `netutils!NetpwNameCompare` at `0x180061eff`
- `netutils!NetpwNameCompare` at `0x180061eff`

## string_xrefs

- `0x180061e20`: `NetrServerAuthenticate: Can't NlGetIncomingPassword for %ws 0x%lx.\n`
- `0x180061e61`: `NlGetMachineOs completely failed: %#x\n`
- `0x18006213b`: `NetrServerAuthenticate3: Possible failure in NlComputeCredentials for %ws 0x%lx.\n`
- `0x180062273`: `NetrServerAuthenticate: NlComputeCredentials failed for %ws on account %ws\n`

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
        unsigned int *a8)
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
  unsigned int *v23; // rcx
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
  unsigned int *v64; // [rsp+D8h] [rbp-48h]
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
  v20 = dword_1800F8310 & *a7;
  *a7 = v20;
  v63 = v19;
  if ( !dword_1800F8248 && (v20 & 0x1004000) == 0 )
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
    if ( dword_1800F8294 )
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
  v23 = (unsigned int *)&v59;
  if ( a3 != 7 )
    v23 = 0;
  IncomingPassword = NlGetIncomingPassword(
                       (__int64)DomainByServerName,
                       a2,
                       a3,
                       0,
                       1,
                       &v74,
                       (char *)((unsigned __int64)&v75 & -(__int64)(v21 != 0)),
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
0x180061b40  push    rbp
0x180061b42  push    rbx
0x180061b43  push    rsi
0x180061b44  push    rdi
0x180061b45  push    r12
0x180061b47  push    r13
0x180061b49  push    r14
0x180061b4b  push    r15
0x180061b4d  lea     rbp, [rsp-228h]
0x180061b55  sub     rsp, 348h
0x180061b5c  mov     rax, cs:__security_cookie
0x180061b63  xor     rax, rsp
0x180061b66  mov     [rbp+260h+var_50], rax
0x180061b6d  mov     rax, [rbp+260h+arg_20]
0x180061b74  xor     r14d, r14d
0x180061b77  mov     rsi, [rbp+260h+arg_28]
0x180061b7e  xorps   xmm0, xmm0
0x180061b81  mov     r13, [rbp+260h+arg_30]
0x180061b88  xorps   xmm1, xmm1
0x180061b8b  mov     [rbp+260h+var_280], rax
0x180061b8f  mov     r12d, r8d
0x180061b92  mov     rax, [rbp+260h+arg_38]
0x180061b99  mov     rbx, rdx
0x180061b9c  mov     [rbp+260h+var_2CC], r8d
0x180061ba0  mov     rdi, rcx
0x180061ba3  xor     edx, edx; Val
0x180061ba5  mov     [rbp+260h+var_2A8], rax
0x180061ba9  mov     r8d, 82h; Size
0x180061baf  mov     [rbp+260h+var_2B8], rsi
0x180061bb3  lea     rcx, [rbp+260h+var_E0]; void *
0x180061bba  mov     [rbp+260h+var_2D8], r13
0x180061bbe  mov     r15, r9
0x180061bc1  mov     dword ptr [rbp+260h+var_2E0], r14d
0x180061bc5  mov     qword ptr [rbp+260h+pbOutput], r14
0x180061bc9  movups  xmmword ptr [rbp+260h+pbSecret], xmm0
0x180061bcd  mov     qword ptr [rbp+260h+pbInput], r14
0x180061bd1  movdqa  [rbp+260h+var_250], xmm1
0x180061bd6  movdqa  [rbp+260h+var_240], xmm0
0x180061bdb  movdqa  xmmword ptr [rbp+260h+var_230.data.data], xmm1
0x180061be0  mov     qword ptr [rbp+260h+var_278.data], r14
0x180061be4  mov     [rbp+260h+var_2BC], r14d
0x180061be8  mov     [rbp+260h+var_2C0], r14d
0x180061bec  mov     [rbp+260h+pSid], r14
0x180061bf0  mov     [rbp+260h+Block], r14
0x180061bf4  mov     [rbp+260h+var_290], r14
0x180061bf8  mov     [rbp+260h+var_288], r14
0x180061bfc  mov     [rbp+260h+var_2C4], r14d
0x180061c00  call    memset_0
0x180061c05  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r14d; int NlGlobalMemberWorkstation
0x180061c0c  jz      short loc_180061C18
0x180061c0e  mov     eax, 0C00000BBh
0x180061c13  jmp     loc_180062557
0x180061c18  mov     dword ptr [rsp+380h+var_358], r14d
0x180061c1d  mov     r9d, r12d
0x180061c20  mov     r8, rbx
0x180061c23  mov     [rsp+380h+var_360], r13
0x180061c28  mov     rdx, r15
0x180061c2b  mov     [rbp+260h+var_2DC], r14d
0x180061c2f  mov     ecx, 1
0x180061c34  call    ?NlpTraceServerAuthEvent@@YAXKPEAG0W4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAKJ@Z; NlpTraceServerAuthEvent(ulong,ushort *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong *,long)
0x180061c39  mov     rcx, rdi; unsigned __int16 *
0x180061c3c  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x180061c41  lea     rdx, [rbp+260h+var_E0]; unsigned __int16 *
0x180061c48  mov     rdi, rax
0x180061c4b  call    ?NlpGetClientAddress@@YAJKPEAG@Z; NlpGetClientAddress(ulong,ushort *)
0x180061c50  lea     rcx, aUnavailable_0; "<unavailable>"
0x180061c57  mov     dword ptr [rbp+260h+var_2E0], eax
0x180061c5a  test    eax, eax
0x180061c5c  lea     rdx, [rbp+260h+var_E0]
0x180061c63  mov     r9, r15
0x180061c66  lea     r8, aNetrserverauth_22; "NetrServerAuthenticate entered: %ws (%w"...
0x180061c6d  cmovs   rdx, rcx
0x180061c71  mov     ecx, [r13+0]
0x180061c75  mov     dword ptr [rsp+380h+var_350], ecx
0x180061c79  mov     ecx, 200h; unsigned int
0x180061c7e  mov     [rsp+380h+var_358], rbx
0x180061c83  mov     [rsp+380h+var_360], rdx
0x180061c88  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180061c8b  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180061c90  mov     eax, 8
0x180061c95  lea     r14d, [rax+8]
0x180061c99  test    rdi, rdi
0x180061c9c  jnz     short loc_180061CAA
0x180061c9e  mov     dword ptr [rbp+260h+var_2E0], 0C0000122h
0x180061ca5  jmp     loc_1800623C1
0x180061caa  cmp     r12d, 5
0x180061cae  jnz     short loc_180061CCD
0x180061cb0  lea     rdx, aNetrserverauth_18; "NetrServerAuthenticate from LM 2.x (dis"...
0x180061cb7  mov     ecx, 100h; unsigned int
0x180061cbc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061cc1  mov     dword ptr [rbp+260h+var_2E0], 0C0000022h
0x180061cc8  jmp     loc_1800623BC
0x180061ccd  mov     eax, [r13+0]
0x180061cd1  mov     edx, eax
0x180061cd3  and     edx, cs:dword_1800F8310
0x180061cd9  mov     [r13+0], edx
0x180061cdd  cmp     cs:dword_1800F8248, 0
0x180061ce4  mov     [rbp+260h+var_2B0], eax
0x180061ce7  jnz     short loc_180061D11
0x180061ce9  test    edx, 1004000h
0x180061cef  jnz     short loc_180061D11
0x180061cf1  mov     r8, rbx
0x180061cf4  lea     rdx, aNetrserverauth_15; "NetrServerAuthenticate3: the client %ws"...
0x180061cfb  mov     ecx, 200h; unsigned int
0x180061d00  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061d05  mov     dword ptr [rbp+260h+var_2E0], 0C0000388h
0x180061d0c  jmp     loc_1800623BC
0x180061d11  lea     eax, [r12-3]
0x180061d16  mov     ecx, 1
0x180061d1b  cmp     eax, ecx
0x180061d1d  jbe     short loc_180061D34
0x180061d1f  xor     esi, esi
0x180061d21  lea     eax, [r12-6]
0x180061d26  cmp     ecx, eax
0x180061d28  mov     [rbp+260h+var_2D0], esi
0x180061d2b  sbb     r13d, r13d
0x180061d2e  and     r13d, 2
0x180061d32  jmp     short loc_180061D3C
0x180061d34  mov     esi, ecx
0x180061d36  mov     [rbp+260h+var_2D0], ecx
0x180061d39  mov     r13d, ecx
0x180061d3c  bt      edx, 18h
0x180061d40  jb      short loc_180061D9D
0x180061d42  cmp     cs:dword_1800F8294, 0
0x180061d49  lea     r9, [rbp+260h+var_E0]
0x180061d50  mov     dword ptr [rsp+380h+var_358], edx
0x180061d54  mov     r8, rdi
0x180061d57  mov     dword ptr [rsp+380h+var_360], r13d
0x180061d5c  mov     rdx, rbx
0x180061d5f  jz      short loc_180061D96
0x180061d61  mov     r14, rcx
0x180061d64  call    ?NlpLogRc4Usage@@YAXHPEAGPEAU_DOMAIN_INFO@@0W4ACCOUNT_TYPE@@K@Z; NlpLogRc4Usage(int,ushort *,_DOMAIN_INFO *,ushort *,ACCOUNT_TYPE,ulong)
0x180061d69  mov     r8, rbx
0x180061d6c  lea     rdx, aNetrserverauth_19; "NetrServerAuthenticate3: the client %ws"...
0x180061d73  mov     ecx, 200h; unsigned int
0x180061d78  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061d7d  mov     dword ptr [rbp+260h+var_2E0], 0C0000388h
0x180061d84  mov     r13, [rbp+260h+var_2D8]
0x180061d88  mov     eax, 8
0x180061d8d  mov     rsi, [rbp+260h+var_2B8]
0x180061d91  jmp     loc_1800623C7
0x180061d96  xor     ecx, ecx
0x180061d98  call    ?NlpLogRc4Usage@@YAXHPEAGPEAU_DOMAIN_INFO@@0W4ACCOUNT_TYPE@@K@Z; NlpLogRc4Usage(int,ushort *,_DOMAIN_INFO *,ushort *,ACCOUNT_TYPE,ulong)
0x180061d9d  xor     eax, eax
0x180061d9f  lea     rcx, [rbp+260h+var_2C4]
0x180061da3  cmp     r12d, 7
0x180061da7  mov     r8d, r12d
0x180061daa  cmovnz  rcx, rax
0x180061dae  mov     eax, esi
0x180061db0  mov     [rsp+380h+var_320], rcx
0x180061db5  neg     eax
0x180061db7  mov     [rsp+380h+var_328], 0
0x180061dc0  lea     rax, [rbp+260h+var_240]
0x180061dc4  sbb     rdx, rdx
0x180061dc7  mov     rcx, rdi
0x180061dca  and     rdx, rax
0x180061dcd  xor     r9d, r9d
0x180061dd0  lea     rax, [rbp+260h+pSid]
0x180061dd4  mov     [rsp+380h+var_330], rax
0x180061dd9  lea     rax, [rbp+260h+var_2C0]
0x180061ddd  mov     [rsp+380h+var_338], rax
0x180061de2  lea     rax, [rbp+260h+var_2BC]
0x180061de6  mov     [rsp+380h+var_340], rax
0x180061deb  mov     rax, [rbp+260h+var_2A8]
0x180061def  mov     [rsp+380h+var_348], rax
0x180061df4  lea     rax, [rbp+260h+var_250]
0x180061df8  mov     [rsp+380h+var_350], rdx
0x180061dfd  mov     rdx, rbx
0x180061e00  mov     [rsp+380h+var_358], rax
0x180061e05  mov     dword ptr [rsp+380h+var_360], 1
0x180061e0d  call    ?NlGetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEBGW4_NETLOGON_SECURE_CHANNEL_TYPE@@KHPEAU_LM_OWF_PASSWORD@@3PEAK44PEAPEAXPEAH4@Z; NlGetIncomingPassword(_DOMAIN_INFO *,ushort const *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,int,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,ulong *,ulong *,ulong *,void * *,int *,ulong *)
0x180061e12  mov     dword ptr [rbp+260h+var_2E0], eax
0x180061e15  test    eax, eax
0x180061e17  jns     short loc_180061E3D
0x180061e19  mov     r9, rbx
0x180061e1c  mov     dword ptr [rsp+380h+var_360], eax
0x180061e20  lea     r8, aNetrserverauth_3; "NetrServerAuthenticate: Can't NlGetInco"...
0x180061e27  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180061e2a  mov     ecx, 100h; unsigned int
0x180061e2f  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180061e34  mov     r13, [rbp+260h+var_2D8]
0x180061e38  jmp     loc_18006239E
0x180061e3d  cmp     r13d, 1
0x180061e41  jz      short loc_180061E74
0x180061e43  lea     r9, [rbp+260h+var_288]; unsigned __int16 **
0x180061e47  mov     rcx, rbx; unsigned __int16 *
0x180061e4a  lea     r8, [rbp+260h+var_290]; unsigned __int16 **
0x180061e4e  lea     rdx, [rbp+260h+Block]; unsigned __int16 **
0x180061e52  call    ?NlGetMachineOs@@YAJPEBGPEAPEAG11@Z; NlGetMachineOs(ushort const *,ushort * *,ushort * *,ushort * *)
0x180061e57  mov     dword ptr [rbp+260h+var_2E0], eax
0x180061e5a  test    eax, eax
0x180061e5c  jns     short loc_180061E74
0x180061e5e  mov     r8d, eax
0x180061e61  lea     rdx, aNlgetmachineos; "NlGetMachineOs completely failed: %#x\n"
0x180061e68  mov     ecx, 200h; unsigned int
0x180061e6d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061e72  jmp     short loc_180061E34
0x180061e74  mov     r12d, 4000000h
0x180061e7a  mov     [rbp+260h+var_2C8], 0
0x180061e81  mov     ecx, r12d; unsigned int
0x180061e84  lea     rdx, aNetrserverauth_16; "NetrServerAuthenticate: Password for ac"...
0x180061e8b  mov     r8, rbx
0x180061e8e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061e93  mov     r8d, r14d; unsigned int
0x180061e96  lea     rdx, [rbp+260h+var_250]; void *
0x180061e9a  mov     ecx, r12d; unsigned int
0x180061e9d  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x180061ea2  test    esi, esi
0x180061ea4  jz      short loc_180061EC7
0x180061ea6  mov     r8, rbx
0x180061ea9  lea     rdx, aNetrserverauth_20; "NetrServerAuthenticate: Previous Passwo"...
0x180061eb0  mov     ecx, r12d; unsigned int
0x180061eb3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061eb8  mov     r8d, r14d; unsigned int
0x180061ebb  lea     rdx, [rbp+260h+var_240]; void *
0x180061ebf  mov     ecx, r12d; unsigned int
0x180061ec2  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x180061ec7  lea     rcx, ?NlGlobalChallengeCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180061ece  call    cs:__imp_RtlEnterCriticalSection
0x180061ed5  nop     dword ptr [rax+rax+00h]
0x180061eda  call    ?NlScavengeOldChallenges@@YAXXZ; NlScavengeOldChallenges(void)
0x180061edf  mov     r12, cs:?NlGlobalChallengeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChallengeList
0x180061ee6  mov     esi, 100h
0x180061eeb  jmp     loc_1800620DB
0x180061ef0  xor     r9d, r9d
0x180061ef3  lea     rdx, [r12+30h]
0x180061ef8  mov     rcx, r15
0x180061efb  lea     r8d, [r9+4]
0x180061eff  call    cs:__imp_NetpwNameCompare
0x180061f06  nop     dword ptr [rax+rax+00h]
0x180061f0b  test    eax, eax
0x180061f0d  jnz     loc_1800620D7
0x180061f13  mov     rax, [r12+18h]
0x180061f18  lea     rdx, aNetrserverauth_10; "NetrServerAuthenticate: ClientChallenge"...
0x180061f1f  mov     ecx, [rbp+260h+var_2DC]
0x180061f22  inc     ecx
0x180061f24  mov     qword ptr [rbp+260h+pbInput], rax
0x180061f28  mov     rax, [r12+10h]
0x180061f2d  mov     r8d, ecx
0x180061f30  mov     [rbp+260h+var_2DC], ecx
0x180061f33  mov     ecx, 4000000h; unsigned int
0x180061f38  mov     qword ptr [rbp+260h+var_278.data], rax
0x180061f3c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061f41  mov     r14d, 8
0x180061f47  lea     rdx, [rbp+260h+var_278]; void *
0x180061f4b  mov     r8d, r14d; unsigned int
0x180061f4e  mov     ecx, 4000000h; unsigned int
0x180061f53  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x180061f58  mov     r8d, [rbp+260h+var_2DC]
0x180061f5c  lea     rdx, aNetrserverauth_32; "NetrServerAuthenticate: ServerChallenge"...
0x180061f63  mov     ecx, 4000000h; unsigned int
0x180061f68  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061f6d  mov     r8d, r14d; unsigned int
0x180061f70  lea     rdx, [rbp+260h+pbInput]; void *
0x180061f74  mov     ecx, 4000000h; unsigned int
0x180061f79  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x180061f7e  lea     rcx, [rbp+260h+var_278]; struct _CYPHER_BLOCK *
0x180061f82  call    ?NlIsChallengeVulnerable@@YAEQEAU_CYPHER_BLOCK@@@Z; NlIsChallengeVulnerable(_CYPHER_BLOCK * const)
0x180061f87  test    al, al
0x180061f89  jnz     loc_1800620D7
0x180061f8f  xor     r14d, r14d
0x180061f92  test    r14d, r14d
0x180061f95  jnz     short loc_180061F9D
0x180061f97  movaps  xmm0, [rbp+260h+var_250]
0x180061f9b  jmp     short loc_180061FB5
0x180061f9d  cmp     r14d, 1
0x180061fa1  jnz     loc_1800620BC
0x180061fa7  cmp     [rbp+260h+var_2D0], 0
0x180061fab  jz      loc_1800620BC
0x180061fb1  movaps  xmm0, [rbp+260h+var_240]
0x180061fb5  mov     rcx, [rbp+260h+var_2D8]
0x180061fb9  lea     rax, [rbp+260h+pbSecret]
0x180061fbd  lea     r9, [rbp+260h+pbInput]; struct _CYPHER_BLOCK *
0x180061fc1  movdqa  xmmword ptr [rbp+260h+var_230.data.data], xmm0
0x180061fc6  lea     r8, [rbp+260h+var_278]; struct _CYPHER_BLOCK *
0x180061fca  mov     [rsp+380h+var_360], rax; struct _NETLOGON_SESSION_KEY *
0x180061fcf  lea     rdx, [rbp+260h+var_230]; struct _LM_OWF_PASSWORD *
0x180061fd3  mov     ecx, [rcx]; unsigned int
0x180061fd5  call    ?NlMakeSessionKey@@YAJKPEAU_LM_OWF_PASSWORD@@PEAU_CYPHER_BLOCK@@1PEAU_NETLOGON_SESSION_KEY@@@Z; NlMakeSessionKey(ulong,_LM_OWF_PASSWORD *,_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *)
0x180061fda  mov     dword ptr [rbp+260h+var_2E0], eax
0x180061fdd  test    eax, eax
0x180061fdf  js      loc_180062144
0x180061fe5  mov     r8d, r14d
0x180061fe8  lea     rdx, aNetrserverauth_25; "NetrServerAuthenticate: SessionKey %lu "...
0x180061fef  mov     ecx, 4000000h; unsigned int
0x180061ff4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061ff9  mov     r8d, 10h; unsigned int
0x180061fff  lea     rdx, [rbp+260h+pbSecret]; void *
0x180062003  mov     ecx, 4000000h; unsigned int
0x180062008  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18006200d  mov     rax, [rbp+260h+var_2D8]
0x180062011  lea     r8, [rbp+260h+pbSecret]; pbSecret
0x180062015  lea     rdx, [rbp+260h+pbOutput]; pbOutput
0x180062019  lea     rcx, [rbp+260h+var_278]; pbInput
0x18006201d  mov     r9d, [rax]; unsigned int
0x180062020  call    ?NlComputeCredentials@@YAJPEAU_CYPHER_BLOCK@@0PEAU_NETLOGON_SESSION_KEY@@K@Z; NlComputeCredentials(_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,ulong)
0x180062025  mov     dword ptr [rbp+260h+var_2E0], eax
0x180062028  test    eax, eax
0x18006202a  js      loc_18006213B
0x180062030  mov     r8d, r14d
  ... truncated ...
```
