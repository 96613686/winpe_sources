# NlSetClientAttributes(ushort *,int,ushort *,_OSVERSIONINFOEXW * const,ushort *,ushort * *,ulong,ulong *)

- ea: `0x1800585a0`
- end: `0x180058e04`
- name: `?NlSetClientAttributes@@YAJPEAGH0QEAU_OSVERSIONINFOEXW@@0PEAPEAGKPEAK@Z`
- size: `2148`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, unsigned __int16 *, struct _OSVERSIONINFOEXW *const, unsigned __int16 *, unsigned __int16 **, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18005c560`
- `0x18005d780`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000da94`
- `0x18000e270`
- `0x18000ed34`
- `0x1800109fc`
- `0x180025708`
- `0x18002601c`
- `0x18002707c`
- `0x180035368`
- `0x18003e71c`
- `0x18003e7dc`
- `0x18003f034`
- `0x1800585a0`
- `0x18005f358`
- `0x18005f79c`
- `0x180060734`
- `0x18006515c`
- `0x1800675c0`
- `0x180068458`
- `0x1800688e0`
- `0x1800694d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800586d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800586d4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800588c2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180058d65`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800588c2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180058d65`
- `logoncli!I_NetChainSetClientAttributes` at `0x180058c19`
- `logoncli!I_NetChainSetClientAttributes` at `0x180058c19`
- `logoncli!I_NetChainSetClientAttributes2` at `0x180058b70`
- `logoncli!I_NetChainSetClientAttributes2` at `0x180058b70`
- `LSASRV!LsaISetClientDnsHostName` at `0x18005867e`
- `LSASRV!LsaISetClientDnsHostName` at `0x18005867e`
- `LSASRV!LsaIReplicateClientObject` at `0x180058d3c`
- `LSASRV!LsaIReplicateClientObject` at `0x180058d3c`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DNSHostNameValueCheckForNetlogon` at `0x1800587d4`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DNSHostNameValueCheckForNetlogon` at `0x1800587d4`

## string_xrefs

- `0x18005879b`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x180058ad6`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x1800587ae`: `NlSetClientAttributes: DNSHostNameValueCheck extension not present\n`
- `0x1800588f3`: `NlSetClientAttributes: can't become writer of client session\n`
- `0x180058cbe`: `NlSetClientAttributes: denying access after status: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlSetClientAttributes(
        unsigned __int16 *a1,
        int a2,
        unsigned __int16 *a3,
        struct _OSVERSIONINFOEXW *const a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6,
        unsigned int a7,
        unsigned int *a8)
{
  unsigned __int16 **v8; // r13
  unsigned __int16 *v9; // r12
  unsigned __int16 *v13; // rdx
  bool v14; // zf
  bool v15; // bl
  __int64 v16; // rdi
  __int64 v17; // rcx
  BOOL v18; // r14d
  unsigned __int8 v19; // r15
  struct _DOMAIN_INFO *DomainByServerName; // rax
  struct _CLIENT_SESSION *v21; // rdi
  int started; // ebx
  __int64 v23; // rcx
  char *v24; // r9
  struct _CLIENT_SESSION *v26; // rax
  int v27; // edx
  const wchar_t *v28; // rcx
  unsigned int *v29; // r15
  struct _NETLOGON_SESSION_KEY *v30; // rax
  struct _CYPHER_BLOCK *v31; // rcx
  int v32; // eax
  struct _OSVERSIONINFOEXW *v33; // rbx
  _OWORD *v34; // rcx
  __int64 v35; // rdx
  WCHAR *szCSDVersion; // rax
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int64 v44; // rcx
  unsigned __int16 *v45; // r12
  DWORD v46; // r15d
  char *v47; // r9
  __int64 v48; // rdx
  int v49; // eax
  __int64 v50; // rdx
  int v51; // eax
  unsigned __int64 v52; // rax
  __int64 v53; // rcx
  unsigned __int8 v54; // al
  __int64 v55; // r8
  char *v56; // r9
  unsigned __int16 *v57; // r14
  int v58; // eax
  struct _CLIENT_API *v59; // [rsp+20h] [rbp-E0h]
  char v60; // [rsp+50h] [rbp-B0h]
  char v61; // [rsp+51h] [rbp-AFh]
  int v62; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int *v63; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v64; // [rsp+60h] [rbp-A0h]
  void *Block[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v66[24]; // [rsp+78h] [rbp-88h] BYREF
  struct _OSVERSIONINFOEXW *v67; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v68; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v69; // [rsp+A0h] [rbp-60h]
  unsigned __int16 **v70; // [rsp+A8h] [rbp-58h]
  struct _DOMAIN_INFO *v71; // [rsp+B0h] [rbp-50h]
  __int128 v72; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v73; // [rsp+C8h] [rbp-38h]
  __int128 v74; // [rsp+D8h] [rbp-28h]
  _BYTE v75[9]; // [rsp+E8h] [rbp-18h] BYREF
  __int16 v76; // [rsp+F1h] [rbp-Fh]
  char v77; // [rsp+F3h] [rbp-Dh]
  __int64 v78; // [rsp+F8h] [rbp-8h] BYREF
  int v79; // [rsp+100h] [rbp+0h]
  _DWORD v80[5]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v81[254]; // [rsp+124h] [rbp+24h] BYREF
  __int16 v82; // [rsp+222h] [rbp+122h]
  WORD wServicePackMajor; // [rsp+224h] [rbp+124h]
  WORD wServicePackMinor; // [rsp+226h] [rbp+126h]
  WORD wSuiteMask; // [rsp+228h] [rbp+128h]
  BYTE wProductType; // [rsp+22Ah] [rbp+12Ah]
  BYTE wReserved; // [rsp+22Bh] [rbp+12Bh]

  v8 = a6;
  v9 = a3;
  v69 = a3;
  v64 = a1;
  v68 = a5;
  v70 = a6;
  v63 = a8;
  v78 = 0;
  v79 = 0;
  memset(v75, 0, sizeof(v75));
  v76 = 0;
  v77 = 0;
  v72 = 0;
  v73 = 0;
  v67 = a4;
  v74 = 0;
  *(_OWORD *)Block = 0;
  memset(v66, 0, sizeof(v66));
  memset_0(v80, 0, 0x11Cu);
  v13 = 0;
  v14 = a2 == 0;
  v15 = 1;
  v62 = 0;
  if ( v14 )
    v13 = v9;
  v16 = (unsigned int)LsaISetClientDnsHostName(a1, v13, a4, a5, 1, a6, a8);
  NlPrintRoutine(0x4000u, L"NlSetClientAttributes: LsaISetClientDnsHostName(), status 0x%lx\n", v16);
  if ( !NlGlobalCDC || !dword_1800F1288 )
    return (unsigned int)v16;
  if ( (int)v16 >= 0 )
  {
    v15 = 0;
    if ( v9 )
    {
      if ( !a6 || !*a6 )
      {
        v17 = 1;
        v18 = 1;
        goto LABEL_13;
      }
      v18 = _o__wcsicmp(v9) != 0;
    }
    else
    {
      v18 = 0;
    }
    v17 = 1;
LABEL_13:
    if ( a7 && a8 )
      v15 = *a8 != a7;
    if ( !v18 )
    {
      if ( v15 )
      {
        v19 = 0;
        goto LABEL_19;
      }
      return (unsigned int)v16;
    }
    v19 = 0;
    goto LABEL_23;
  }
  v19 = 1;
  v18 = v9 != 0;
  if ( !v9 )
    goto LABEL_19;
LABEL_23:
  if ( !v9 )
    goto LABEL_19;
  if ( (unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent(v17) )
  {
    if ( (unsigned int)DNSHostNameValueCheckForNetlogon(v9, v64) )
    {
      NlPrintRoutine(0x100u, L"NlSetClientAttributes: invalid DnsHostName (%ws) from client (%ws)\n", v9, v64);
      return 3221225762LL;
    }
LABEL_19:
    v61 = 0;
    Block[0] = 0;
    v62 = 1;
    DomainByServerName = NlFindDomainByServerName(0);
    v71 = DomainByServerName;
    if ( !DomainByServerName )
    {
      v21 = 0;
      NlPrintRoutine(0x100u, L"NlSetClientAttributes: no primary domain located\n");
      started = -1073741601;
      goto LABEL_87;
    }
    v26 = NlRefDomClientSession(DomainByServerName);
    v21 = v26;
    if ( v26 )
    {
      if ( v15 && !v18 && !v19 && (*((_DWORD *)v26 + 102) & 0x400) != 0 )
      {
        started = 0;
        NlPrintRoutine(0x4000u, L"NlSetClientAttributes: Skipping remote call for enctypes only\n");
LABEL_87:
        if ( (unsigned int)(v62 - 1) <= 1 && Block[0] )
        {
          v57 = v64;
          v58 = LsaIReplicateClientObject(Block[0], v64);
          if ( v58 < 0 )
          {
            LODWORD(v59) = v58;
            NlPrintRoutine(
              0x100u,
              L"NlSetClientAttributes: LsaIReplicateClientObject(%ws, %ws), status 0x%lx\n",
              Block[0],
              v57,
              v59);
          }
          free(Block[0]);
        }
        if ( v21 )
        {
          if ( v61 )
            NlResetWriterClientSession(v21);
          NlUnrefClientSession((char *)v21);
        }
        if ( v71 )
          NlDereferenceDomain(v71);
        if ( started < 0 )
          NlPrintRoutine(0x100u, L"NlSetClientAttributes: failed %lX\n", (unsigned int)started);
        NlPrintRoutine(0x4000u, L"NlSetClientAttributes: Return 0x%lx\n", (unsigned int)started);
        return (unsigned int)started;
      }
      if ( v63 )
        v27 = *v63;
      else
        v27 = -268435457;
      v28 = L"<unavail>";
      if ( a6 )
        v28 = *a6;
      LODWORD(v59) = v15;
      NlPrintRoutine(
        0x4000u,
        L"NlSetClientAttributes: Going remote: (%lu, %lu, %lu) (%ws->%ws, 0x%lx->0x%lx)\n",
        v19,
        v18,
        v59,
        v28,
        v9,
        v27,
        a7);
      if ( a6 )
      {
        if ( *a6 )
          free(*a6);
        *a6 = 0;
      }
      v29 = v63;
      if ( v63 )
        *v63 = 0;
      if ( (unsigned int)NlTimeoutSetWriterClientSession(v21, dwMilliseconds) )
      {
        v60 = 1;
        v61 = 1;
        started = NlEnsureSessionAuthenticated(v21, 0);
        if ( started < 0 )
        {
LABEL_86:
          NlPrintRoutine(0x100u, L"NlSetClientAttributes: can't authenticate client session\n");
        }
        else
        {
          v30 = (struct _CLIENT_SESSION *)((char *)v21 + 440);
          v31 = (struct _CYPHER_BLOCK *)((char *)v21 + 432);
          while ( 1 )
          {
            v32 = NlBuildAuthenticator(v31, v30, (struct _NETLOGON_AUTHENTICATOR *)&v78, *((_DWORD *)v21 + 79));
            started = v32;
            if ( v32 < 0 )
              break;
            v33 = v67;
            *((_QWORD *)&v72 + 1) = 0;
            Block[0] = 0;
            v74 = 0;
            *(_OWORD *)&v66[8] = 0;
            if ( v67 )
            {
              memset_0(v81, 0, sizeof(v81));
              v34 = v81;
              v80[0] = v33->dwOSVersionInfoSize;
              v35 = 2;
              v80[1] = v33->dwMajorVersion;
              v80[2] = v33->dwMinorVersion;
              v80[3] = v33->dwBuildNumber;
              v80[4] = v33->dwPlatformId;
              wServicePackMajor = v33->wServicePackMajor;
              wServicePackMinor = v33->wServicePackMinor;
              wSuiteMask = v33->wSuiteMask;
              wProductType = v33->wProductType;
              wReserved = v33->wReserved;
              szCSDVersion = v33->szCSDVersion;
              do
              {
                v37 = *((_OWORD *)szCSDVersion + 1);
                *v34 = *(_OWORD *)szCSDVersion;
                v38 = *((_OWORD *)szCSDVersion + 2);
                v34[1] = v37;
                v39 = *((_OWORD *)szCSDVersion + 3);
                v34[2] = v38;
                v40 = *((_OWORD *)szCSDVersion + 4);
                v34[3] = v39;
                v41 = *((_OWORD *)szCSDVersion + 5);
                v34[4] = v40;
                v42 = *((_OWORD *)szCSDVersion + 6);
                v34[5] = v41;
                v43 = *((_OWORD *)szCSDVersion + 7);
                szCSDVersion += 64;
                v34[6] = v42;
                v34[7] = v43;
                v34 += 8;
                --v35;
              }
              while ( v35 );
              v82 = 0;
              *((_QWORD *)&v72 + 1) = v80;
            }
            *(_QWORD *)v66 = v29;
            Block[1] = v8;
            *((_QWORD *)&v73 + 1) = a7;
            v44 = (unsigned __int64)v9 & -(__int64)v18;
            v45 = v64;
            v46 = 0;
            *(_QWORD *)&v72 = v44;
            started = -1073610748;
            *(_QWORD *)&v73 = v68;
            v62 = 2;
            do
            {
              started = NlStartApiClientSession(v21, 1, v46, started, (struct _CLIENT_SESSION *)((char *)v21 + 680));
              if ( started >= 0 )
              {
                if ( !*((_QWORD *)v21 + 63) )
                  NlAssertFailed(
                    "ClientSession->CsUncServerName != NULL",
                    "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
                    1216,
                    v47);
                NlPrintRoutine(0x4000u, L"NlSetClientAttributes: Chaining to %ws\n", *((_QWORD *)v21 + 63));
                if ( (*((_DWORD *)v21 + 102) & 0x400) != 0 )
                  goto LABEL_71;
                v48 = (*((_DWORD *)v21 + 73) & 0x40000) != 0
                    ? *((_QWORD *)v21 + 27)
                    : *(_QWORD *)(*((_QWORD *)v21 + 34) + 264LL);
                v49 = I_NetChainSetClientAttributes2(*((_QWORD *)v21 + 63), v48, v45, &v78, v75, 2, &v72, &v62, Block);
                started = v49;
                if ( v49 == -1073610706 )
                {
                  NlPrintRoutine(0x800u, L"Fall back to NetrChainSetClientAttributes\n");
                  *((_DWORD *)v21 + 102) |= 0x400u;
                }
                else if ( v49 < 0 )
                {
                  NlPrintRpcDebug("NetrChainSetClientAttributes2", v49);
                }
                if ( (*((_DWORD *)v21 + 102) & 0x400) != 0 )
                {
LABEL_71:
                  v62 = 1;
                  if ( (*((_DWORD *)v21 + 73) & 0x40000) != 0 )
                    v50 = *((_QWORD *)v21 + 27);
                  else
                    v50 = *(_QWORD *)(*((_QWORD *)v21 + 34) + 264LL);
                  v51 = I_NetChainSetClientAttributes(*((_QWORD *)v21 + 63), v50, v45, &v78, v75, 1, &v72, &v62, Block);
                  started = v51;
                  if ( v51 < 0 )
                    NlPrintRpcDebug("NetrChainSetClientAttributes", v51);
                }
              }
              v52 = (unsigned int)(started + 1073610748);
              if ( (unsigned int)v52 > 0x32 )
                break;
              v53 = 0x4000000080001LL;
              if ( !_bittest64(&v53, v52) )
                break;
              ++v46;
            }
            while ( v46 < 2 );
            NlFinishApiClientSession(v21, 1, 1, (struct _CLIENT_SESSION *)((char *)v21 + 680));
            v54 = NlpDidDcFail(started);
            v9 = v69;
            v8 = v70;
            v29 = v63;
            if ( !v54
              && (!(unsigned int)NlCheckRpcAuthIsNetlogon(v21)
               || (unsigned int)NlUpdateSeed(
                                  (PUCHAR)v21 + 432,
                                  (struct _CYPHER_BLOCK *)v75,
                                  (PUCHAR)v21 + 440,
                                  *((_DWORD *)v21 + 79))) )
            {
              goto LABEL_87;
            }
            NlPrintCsRoutine(
              0x100u,
              v21,
              L"NlSetClientAttributes: denying access after status: 0x%lx\n",
              (unsigned int)started);
            if ( started >= 0 )
              started = -1073741790;
            NlSetStatusClientSession(v21, started, v55, v56);
            if ( !v60 )
              goto LABEL_87;
            v60 = 0;
            started = NlEnsureSessionAuthenticated(v21, 0);
            v31 = (struct _CYPHER_BLOCK *)((char *)v21 + 432);
            v30 = (struct _CLIENT_SESSION *)((char *)v21 + 440);
            if ( started < 0 )
              goto LABEL_86;
          }
          NlPrintRoutine(
            0x100u,
            L"NlSetClientAttributes: NlBuildAuthenticator failed with status: 0x%lx\n",
            (unsigned int)v32);
        }
        goto LABEL_87;
      }
      NlPrintRoutine(0x100u, L"NlSetClientAttributes: can't become writer of client session\n");
    }
    else
    {
      NlPrintRoutine(0x100u, L"NlSetClientAttributes: no client session to HubDC\n");
    }
    started = -1073741730;
    goto LABEL_87;
  }
  if ( !(unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent(v23) )
    NlAssertFailed(
      "IsDNSHostNameValueCheckForNetlogonPresent()",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
      1047,
      v24);
  NlPrintRoutine(0x100u, L"NlSetClientAttributes: DNSHostNameValueCheck extension not present\n");
  return 3221225659LL;
}

```

## disassembly

```asm
0x1800585a0  mov     [rsp-8+arg_8], rbx
0x1800585a5  push    rbp
0x1800585a6  push    rsi
0x1800585a7  push    rdi
0x1800585a8  push    r12
0x1800585aa  push    r13
0x1800585ac  push    r14
0x1800585ae  push    r15
0x1800585b0  lea     rbp, [rsp-140h]
0x1800585b8  sub     rsp, 240h
0x1800585bf  mov     rax, cs:__security_cookie
0x1800585c6  xor     rax, rsp
0x1800585c9  mov     [rbp+170h+var_40], rax
0x1800585d0  mov     r15, [rbp+170h+arg_20]
0x1800585d7  xor     eax, eax
0x1800585d9  mov     r13, [rbp+170h+arg_28]
0x1800585e0  xorps   xmm0, xmm0
0x1800585e3  mov     rsi, [rbp+170h+arg_38]
0x1800585ea  xorps   xmm1, xmm1
0x1800585ed  mov     r12, r8
0x1800585f0  mov     [rbp+170h+var_1D0], r8
0x1800585f4  mov     ebx, edx
0x1800585f6  mov     [rsp+270h+var_210], rcx
0x1800585fb  mov     rdi, rcx
0x1800585fe  mov     [rbp+170h+var_1D8], r15
0x180058602  xor     edx, edx; Val
0x180058604  mov     [rbp+170h+var_1C8], r13
0x180058608  mov     r8d, 11Ch; Size
0x18005860e  mov     [rsp+270h+var_218], rsi
0x180058613  lea     rcx, [rbp+170h+var_160]; void *
0x180058617  mov     [rbp+170h+var_178], rax
0x18005861b  mov     [rbp+170h+var_170], eax
0x18005861e  mov     r14, r9
0x180058621  mov     [rbp+170h+var_188], al
0x180058624  mov     qword ptr [rbp+170h+var_188+1], rax
0x180058628  mov     [rbp+170h+var_17F], ax
0x18005862c  mov     [rbp+170h+var_17D], al
0x18005862f  movups  [rbp+170h+var_1B8], xmm0
0x180058633  mov     [rbp+170h+var_1E8], rax
0x180058637  movups  [rbp+170h+var_1A8], xmm0
0x18005863b  mov     [rbp+170h+var_1E0], r9
0x18005863f  movups  [rbp+170h+var_198], xmm0
0x180058643  movups  xmmword ptr [rsp+270h+Block], xmm1
0x180058648  movups  [rsp+270h+var_1F8], xmm1
0x18005864d  call    memset_0
0x180058652  xor     edx, edx
0x180058654  mov     [rsp+270h+var_240], rsi
0x180058659  test    ebx, ebx
0x18005865b  mov     [rsp+270h+var_248], r13
0x180058660  mov     ebx, 1
0x180058665  mov     [rsp+270h+var_21C], 0
0x18005866d  cmovz   rdx, r12
0x180058671  mov     dword ptr [rsp+270h+var_250], ebx
0x180058675  mov     r9, r15
0x180058678  mov     r8, r14
0x18005867b  mov     rcx, rdi
0x18005867e  call    cs:__imp_LsaISetClientDnsHostName
0x180058684  lea     rdx, aNlsetclientatt_7; "NlSetClientAttributes: LsaISetClientDns"...
0x18005868b  mov     ecx, 4000h; unsigned int
0x180058690  mov     r8d, eax
0x180058693  mov     edi, eax
0x180058695  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005869a  cmp     cs:?NlGlobalCDC@@3HA, 0; int NlGlobalCDC
0x1800586a1  jz      loc_180058DD8
0x1800586a7  cmp     cs:dword_1800F1288, 0
0x1800586ae  jz      loc_180058DD8
0x1800586b4  test    edi, edi
0x1800586b6  js      loc_18005876C
0x1800586bc  xor     bl, bl
0x1800586be  test    r12, r12
0x1800586c1  jz      short loc_1800586EF
0x1800586c3  test    r13, r13
0x1800586c6  jz      short loc_1800586E5
0x1800586c8  mov     rdx, [r13+0]
0x1800586cc  test    rdx, rdx
0x1800586cf  jz      short loc_1800586E5
0x1800586d1  mov     rcx, r12
0x1800586d4  call    cs:__imp__o__wcsicmp
0x1800586da  xor     r14d, r14d
0x1800586dd  test    eax, eax
0x1800586df  setnz   r14b
0x1800586e3  jmp     short loc_1800586F2
0x1800586e5  mov     ecx, 1
0x1800586ea  mov     r14d, ecx
0x1800586ed  jmp     short loc_1800586F7
0x1800586ef  xor     r14d, r14d
0x1800586f2  mov     ecx, 1
0x1800586f7  mov     eax, [rbp+170h+arg_30]
0x1800586fd  test    eax, eax
0x1800586ff  jz      short loc_18005870E
0x180058701  test    rsi, rsi
0x180058704  jz      short loc_18005870E
0x180058706  cmp     [rsi], eax
0x180058708  movzx   ebx, bl
0x18005870b  cmovnz  ebx, ecx
0x18005870e  test    r14d, r14d
0x180058711  jnz     short loc_180058767
0x180058713  test    bl, bl
0x180058715  jz      loc_180058DD8
0x18005871b  xor     r15b, r15b
0x18005871e  xor     ecx, ecx; unsigned __int16 *
0x180058720  mov     [rsp+270h+var_21F], 0
0x180058725  mov     [rsp+270h+Block], 0
0x18005872e  mov     [rsp+270h+var_21C], 1
0x180058736  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18005873b  mov     [rbp+170h+var_1C0], rax
0x18005873f  mov     esi, 100h
0x180058744  test    rax, rax
0x180058747  jnz     loc_180058803
0x18005874d  xor     edi, edi
0x18005874f  lea     rdx, aNlsetclientatt_1; "NlSetClientAttributes: no primary domai"...
0x180058756  mov     ecx, esi; unsigned int
0x180058758  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005875d  mov     ebx, 0C00000DFh
0x180058762  jmp     loc_180058D1F
0x180058767  xor     r15b, r15b
0x18005876a  jmp     short loc_18005877E
0x18005876c  xor     r14d, r14d
0x18005876f  mov     r15b, bl
0x180058772  test    r12, r12
0x180058775  setnz   r14b
0x180058779  test    r14d, r14d
0x18005877c  jz      short loc_18005871E
0x18005877e  test    r12, r12
0x180058781  jz      short loc_18005871E
0x180058783  call    IsDsGetServersAndSitesForNetLogonPresent
0x180058788  test    al, al
0x18005878a  jnz     short loc_1800587C9
0x18005878c  call    IsDsGetServersAndSitesForNetLogonPresent
0x180058791  test    al, al
0x180058793  jnz     short loc_1800587AE
0x180058795  mov     r8d, 417h; unsigned int
0x18005879b  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800587a2  lea     rcx, aIsdnshostnamev; "IsDNSHostNameValueCheckForNetlogonPrese"...
0x1800587a9  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800587ae  lea     rdx, aNlsetclientatt_13; "NlSetClientAttributes: DNSHostNameValue"...
0x1800587b5  mov     ecx, 100h; unsigned int
0x1800587ba  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800587bf  mov     eax, 0C00000BBh
0x1800587c4  jmp     loc_180058DDA
0x1800587c9  mov     rdi, [rsp+270h+var_210]
0x1800587ce  mov     rcx, r12
0x1800587d1  mov     rdx, rdi
0x1800587d4  call    cs:__imp_DNSHostNameValueCheckForNetlogon
0x1800587da  test    eax, eax
0x1800587dc  jz      loc_18005871E
0x1800587e2  mov     r9, rdi
0x1800587e5  lea     rdx, aNlsetclientatt_6; "NlSetClientAttributes: invalid DnsHostN"...
0x1800587ec  mov     r8, r12
0x1800587ef  mov     ecx, 100h; unsigned int
0x1800587f4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800587f9  mov     eax, 0C0000122h
0x1800587fe  jmp     loc_180058DDA
0x180058803  mov     rcx, rax; struct _DOMAIN_INFO *
0x180058806  call    ?NlRefDomClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@@Z; NlRefDomClientSession(_DOMAIN_INFO *)
0x18005880b  mov     rdi, rax
0x18005880e  test    rax, rax
0x180058811  jnz     short loc_18005882B
0x180058813  lea     rdx, aNlsetclientatt_5; "NlSetClientAttributes: no client sessio"...
0x18005881a  mov     ecx, esi; unsigned int
0x18005881c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180058821  mov     ebx, 0C000005Eh
0x180058826  jmp     loc_180058D1F
0x18005882b  test    bl, bl
0x18005882d  jz      short loc_180058858
0x18005882f  test    r14d, r14d
0x180058832  jnz     short loc_180058858
0x180058834  test    r15b, r15b
0x180058837  jnz     short loc_180058858
0x180058839  test    dword ptr [rax+198h], 400h
0x180058843  jz      short loc_180058858
0x180058845  xor     ebx, ebx
0x180058847  lea     rdx, aNlsetclientatt_11; "NlSetClientAttributes: Skipping remote "...
0x18005884e  mov     ecx, 4000h
0x180058853  jmp     loc_180058D1A
0x180058858  mov     rdx, [rsp+270h+var_218]
0x18005885d  test    rdx, rdx
0x180058860  jnz     short loc_180058869
0x180058862  mov     edx, 0EFFFFFFFh
0x180058867  jmp     short loc_18005886B
0x180058869  mov     edx, [rdx]
0x18005886b  lea     rcx, aUnavail; "<unavail>"
0x180058872  test    r13, r13
0x180058875  jz      short loc_18005887B
0x180058877  mov     rcx, [r13+0]
0x18005887b  mov     r9d, [rbp+170h+arg_30]
0x180058882  mov     dword ptr [rsp+270h+var_230], r9d
0x180058887  mov     r9d, r14d
0x18005888a  mov     dword ptr [rsp+270h+var_238], edx
0x18005888e  lea     rdx, aNlsetclientatt; "NlSetClientAttributes: Going remote: (%"...
0x180058895  mov     [rsp+270h+var_240], r12
0x18005889a  mov     [rsp+270h+var_248], rcx
0x18005889f  mov     ecx, 4000h; unsigned int
0x1800588a4  movzx   eax, bl
0x1800588a7  movzx   r8d, r15b
0x1800588ab  mov     dword ptr [rsp+270h+var_250], eax
0x1800588af  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800588b4  test    r13, r13
0x1800588b7  jz      short loc_1800588D0
0x1800588b9  mov     rcx, [r13+0]; Block
0x1800588bd  test    rcx, rcx
0x1800588c0  jz      short loc_1800588C8
0x1800588c2  call    cs:__imp_free
0x1800588c8  mov     qword ptr [r13+0], 0
0x1800588d0  mov     r15, [rsp+270h+var_218]
0x1800588d5  test    r15, r15
0x1800588d8  jz      short loc_1800588E1
0x1800588da  mov     dword ptr [r15], 0
0x1800588e1  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x1800588e7  mov     rcx, rdi; struct _CLIENT_SESSION *
0x1800588ea  call    ?NlTimeoutSetWriterClientSession@@YAHPEAU_CLIENT_SESSION@@K@Z; NlTimeoutSetWriterClientSession(_CLIENT_SESSION *,ulong)
0x1800588ef  test    eax, eax
0x1800588f1  jnz     short loc_1800588FF
0x1800588f3  lea     rdx, aNlsetclientatt_9; "NlSetClientAttributes: can't become wri"...
0x1800588fa  jmp     loc_18005881A
0x1800588ff  mov     eax, 1
0x180058904  xor     edx, edx; unsigned int
0x180058906  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180058909  mov     [rsp+270h+var_220], al
0x18005890d  mov     [rsp+270h+var_21F], al
0x180058911  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x180058916  mov     ebx, eax
0x180058918  test    eax, eax
0x18005891a  js      loc_180058D11
0x180058920  lea     rax, [rdi+1B8h]
0x180058927  lea     rcx, [rdi+1B0h]; struct _CYPHER_BLOCK *
0x18005892e  mov     r9d, [rdi+13Ch]; unsigned int
0x180058935  lea     r8, [rbp+170h+var_178]; struct _NETLOGON_AUTHENTICATOR *
0x180058939  mov     rdx, rax; struct _NETLOGON_SESSION_KEY *
0x18005893c  call    ?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z; NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)
0x180058941  mov     ebx, eax
0x180058943  test    eax, eax
0x180058945  js      loc_180058DC2
0x18005894b  mov     rbx, [rbp+170h+var_1E0]
0x18005894f  xorps   xmm0, xmm0
0x180058952  mov     qword ptr [rbp+170h+var_1B8+8], 0
0x18005895a  xorps   xmm1, xmm1
0x18005895d  mov     [rsp+270h+Block], 0
0x180058966  movdqu  [rbp+170h+var_198], xmm0
0x18005896b  movdqu  [rbp+170h+var_1F8+8], xmm1
0x180058970  test    rbx, rbx
0x180058973  jz      loc_180058A55
0x180058979  xor     edx, edx; Val
0x18005897b  lea     rcx, [rbp+170h+var_14C]; void *
0x18005897f  mov     r8d, 0FEh; Size
0x180058985  call    memset_0
0x18005898a  mov     eax, [rbx]
0x18005898c  lea     rcx, [rbp+170h+var_14C]
0x180058990  mov     [rbp+170h+var_160], eax
0x180058993  mov     edx, 2
0x180058998  mov     eax, [rbx+4]
0x18005899b  mov     [rbp+170h+var_15C], eax
0x18005899e  mov     eax, [rbx+8]
0x1800589a1  mov     [rbp+170h+var_158], eax
0x1800589a4  lea     r8d, [rdx+7Eh]
0x1800589a8  mov     eax, [rbx+0Ch]
0x1800589ab  mov     [rbp+170h+var_154], eax
0x1800589ae  mov     eax, [rbx+10h]
0x1800589b1  mov     [rbp+170h+var_150], eax
0x1800589b4  movzx   eax, word ptr [rbx+114h]
0x1800589bb  mov     [rbp+170h+var_4C], ax
0x1800589c2  movzx   eax, word ptr [rbx+116h]
0x1800589c9  mov     [rbp+170h+var_4A], ax
0x1800589d0  movzx   eax, word ptr [rbx+118h]
0x1800589d7  mov     [rbp+170h+var_48], ax
0x1800589de  mov     al, [rbx+11Ah]
0x1800589e4  mov     [rbp+170h+var_46], al
0x1800589ea  mov     al, [rbx+11Bh]
0x1800589f0  mov     [rbp+170h+var_45], al
0x1800589f6  lea     rax, [rbx+14h]
0x1800589fa  movups  xmm0, xmmword ptr [rax]
0x1800589fd  movups  xmm1, xmmword ptr [rax+10h]
0x180058a01  movups  xmmword ptr [rcx], xmm0
0x180058a04  movups  xmm0, xmmword ptr [rax+20h]
0x180058a08  movups  xmmword ptr [rcx+10h], xmm1
0x180058a0c  movups  xmm1, xmmword ptr [rax+30h]
0x180058a10  movups  xmmword ptr [rcx+20h], xmm0
0x180058a14  movups  xmm0, xmmword ptr [rax+40h]
0x180058a18  movups  xmmword ptr [rcx+30h], xmm1
0x180058a1c  movups  xmm1, xmmword ptr [rax+50h]
0x180058a20  movups  xmmword ptr [rcx+40h], xmm0
0x180058a24  movups  xmm0, xmmword ptr [rax+60h]
0x180058a28  movups  xmmword ptr [rcx+50h], xmm1
0x180058a2c  movups  xmm1, xmmword ptr [rax+70h]
0x180058a30  add     rax, r8
0x180058a33  movups  xmmword ptr [rcx+60h], xmm0
0x180058a37  movups  xmmword ptr [rcx+70h], xmm1
0x180058a3b  add     rcx, r8
0x180058a3e  sub     rdx, 1
0x180058a42  jnz     short loc_1800589FA
0x180058a44  xor     eax, eax
0x180058a46  mov     [rbp+170h+var_4E], ax
0x180058a4d  lea     rax, [rbp+170h+var_160]
0x180058a51  mov     qword ptr [rbp+170h+var_1B8+8], rax
0x180058a55  mov     eax, r14d
0x180058a58  mov     qword ptr [rsp+270h+var_1F8], r15
0x180058a5d  neg     eax
0x180058a5f  mov     [rsp+270h+Block+8], r13
0x180058a64  mov     eax, [rbp+170h+arg_30]
0x180058a6a  lea     rsi, [rdi+2A8h]
  ... truncated ...
```
