# NlSetClientAttributes(ushort *,int,ushort *,_OSVERSIONINFOEXW * const,ushort *,ushort * *,ulong,ulong *)

- ea: `0x18005c514`
- end: `0x18005cdad`
- name: `?NlSetClientAttributes@@YAJPEAGH0QEAU_OSVERSIONINFOEXW@@0PEAPEAGKPEAK@Z`
- size: `2201`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, unsigned __int16 *, struct _OSVERSIONINFOEXW *const, unsigned __int16 *, unsigned __int16 **, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180060840`
- `0x180061b40`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000e0e0`
- `0x18000e910`
- `0x18000f3e4`
- `0x1800110ac`
- `0x1800267ec`
- `0x1800271d4`
- `0x1800283ec`
- `0x180037344`
- `0x180040f18`
- `0x180040fe4`
- `0x180041924`
- `0x18005c514`
- `0x1800637d0`
- `0x180063c38`
- `0x180064c90`
- `0x180069c60`
- `0x18006c2e8`
- `0x18006d2b0`
- `0x18006d794`
- `0x18006e444`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c64e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c64e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c848`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005cd07`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c848`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005cd07`
- `logoncli!I_NetChainSetClientAttributes` at `0x18005cbaf`
- `logoncli!I_NetChainSetClientAttributes` at `0x18005cbaf`
- `logoncli!I_NetChainSetClientAttributes2` at `0x18005cafc`
- `logoncli!I_NetChainSetClientAttributes2` at `0x18005cafc`
- `LSASRV!LsaISetClientDnsHostName` at `0x18005c5f2`
- `LSASRV!LsaISetClientDnsHostName` at `0x18005c5f2`
- `LSASRV!LsaIReplicateClientObject` at `0x18005ccd8`
- `LSASRV!LsaIReplicateClientObject` at `0x18005ccd8`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DNSHostNameValueCheckForNetlogon` at `0x18005c754`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DNSHostNameValueCheckForNetlogon` at `0x18005c754`

## string_xrefs

- `0x18005c71b`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005ca62`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005c72e`: `NlSetClientAttributes: DNSHostNameValueCheck extension not present\n`
- `0x18005c87f`: `NlSetClientAttributes: can't become writer of client session\n`
- `0x18005cc5a`: `NlSetClientAttributes: denying access after status: 0x%lx\n`

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
  if ( !NlGlobalCDC || !dword_1800F8288 )
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
      v18 = _o__wcsicmp(v9, *a6) != 0;
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
                    0x4C0u,
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
      0x417u,
      v24);
  NlPrintRoutine(0x100u, L"NlSetClientAttributes: DNSHostNameValueCheck extension not present\n");
  return 3221225659LL;
}

```

## disassembly

```asm
0x18005c514  mov     [rsp-8+arg_8], rbx
0x18005c519  push    rbp
0x18005c51a  push    rsi
0x18005c51b  push    rdi
0x18005c51c  push    r12
0x18005c51e  push    r13
0x18005c520  push    r14
0x18005c522  push    r15
0x18005c524  lea     rbp, [rsp-140h]
0x18005c52c  sub     rsp, 240h
0x18005c533  mov     rax, cs:__security_cookie
0x18005c53a  xor     rax, rsp
0x18005c53d  mov     [rbp+170h+var_40], rax
0x18005c544  mov     r15, [rbp+170h+arg_20]
0x18005c54b  xor     eax, eax
0x18005c54d  mov     r13, [rbp+170h+arg_28]
0x18005c554  xorps   xmm0, xmm0
0x18005c557  mov     rsi, [rbp+170h+arg_38]
0x18005c55e  xorps   xmm1, xmm1
0x18005c561  mov     r12, r8
0x18005c564  mov     [rbp+170h+var_1D0], r8
0x18005c568  mov     ebx, edx
0x18005c56a  mov     [rsp+270h+var_210], rcx
0x18005c56f  mov     rdi, rcx
0x18005c572  mov     [rbp+170h+var_1D8], r15
0x18005c576  xor     edx, edx; Val
0x18005c578  mov     [rbp+170h+var_1C8], r13
0x18005c57c  mov     r8d, 11Ch; Size
0x18005c582  mov     [rsp+270h+var_218], rsi
0x18005c587  lea     rcx, [rbp+170h+var_160]; void *
0x18005c58b  mov     [rbp+170h+var_178], rax
0x18005c58f  mov     [rbp+170h+var_170], eax
0x18005c592  mov     r14, r9
0x18005c595  mov     [rbp+170h+var_188], al
0x18005c598  mov     qword ptr [rbp+170h+var_188+1], rax
0x18005c59c  mov     [rbp+170h+var_17F], ax
0x18005c5a0  mov     [rbp+170h+var_17D], al
0x18005c5a3  movups  [rbp+170h+var_1B8], xmm0
0x18005c5a7  mov     [rbp+170h+var_1E8], rax
0x18005c5ab  movups  [rbp+170h+var_1A8], xmm0
0x18005c5af  mov     [rbp+170h+var_1E0], r9
0x18005c5b3  movups  [rbp+170h+var_198], xmm0
0x18005c5b7  movups  xmmword ptr [rsp+270h+Block], xmm1
0x18005c5bc  movups  [rsp+270h+var_1F8], xmm1
0x18005c5c1  call    memset_0
0x18005c5c6  xor     edx, edx
0x18005c5c8  mov     [rsp+270h+var_240], rsi
0x18005c5cd  test    ebx, ebx
0x18005c5cf  mov     [rsp+270h+var_248], r13
0x18005c5d4  mov     ebx, 1
0x18005c5d9  mov     [rsp+270h+var_21C], 0
0x18005c5e1  cmovz   rdx, r12
0x18005c5e5  mov     dword ptr [rsp+270h+var_250], ebx
0x18005c5e9  mov     r9, r15
0x18005c5ec  mov     r8, r14
0x18005c5ef  mov     rcx, rdi
0x18005c5f2  call    cs:__imp_LsaISetClientDnsHostName
0x18005c5f9  nop     dword ptr [rax+rax+00h]
0x18005c5fe  lea     rdx, aNlsetclientatt_7; "NlSetClientAttributes: LsaISetClientDns"...
0x18005c605  mov     ecx, 4000h; unsigned int
0x18005c60a  mov     r8d, eax
0x18005c60d  mov     edi, eax
0x18005c60f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005c614  cmp     cs:?NlGlobalCDC@@3HA, 0; int NlGlobalCDC
0x18005c61b  jz      loc_18005CD80
0x18005c621  cmp     cs:dword_1800F8288, 0
0x18005c628  jz      loc_18005CD80
0x18005c62e  test    edi, edi
0x18005c630  js      loc_18005C6EC
0x18005c636  xor     bl, bl
0x18005c638  test    r12, r12
0x18005c63b  jz      short loc_18005C66F
0x18005c63d  test    r13, r13
0x18005c640  jz      short loc_18005C665
0x18005c642  mov     rdx, [r13+0]
0x18005c646  test    rdx, rdx
0x18005c649  jz      short loc_18005C665
0x18005c64b  mov     rcx, r12
0x18005c64e  call    cs:__imp__o__wcsicmp
0x18005c655  nop     dword ptr [rax+rax+00h]
0x18005c65a  xor     r14d, r14d
0x18005c65d  test    eax, eax
0x18005c65f  setnz   r14b
0x18005c663  jmp     short loc_18005C672
0x18005c665  mov     ecx, 1
0x18005c66a  mov     r14d, ecx
0x18005c66d  jmp     short loc_18005C677
0x18005c66f  xor     r14d, r14d
0x18005c672  mov     ecx, 1
0x18005c677  mov     eax, [rbp+170h+arg_30]
0x18005c67d  test    eax, eax
0x18005c67f  jz      short loc_18005C68E
0x18005c681  test    rsi, rsi
0x18005c684  jz      short loc_18005C68E
0x18005c686  cmp     [rsi], eax
0x18005c688  movzx   ebx, bl
0x18005c68b  cmovnz  ebx, ecx
0x18005c68e  test    r14d, r14d
0x18005c691  jnz     short loc_18005C6E7
0x18005c693  test    bl, bl
0x18005c695  jz      loc_18005CD80
0x18005c69b  xor     r15b, r15b
0x18005c69e  xor     ecx, ecx; unsigned __int16 *
0x18005c6a0  mov     [rsp+270h+var_21F], 0
0x18005c6a5  mov     [rsp+270h+Block], 0
0x18005c6ae  mov     [rsp+270h+var_21C], 1
0x18005c6b6  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18005c6bb  mov     [rbp+170h+var_1C0], rax
0x18005c6bf  mov     esi, 100h
0x18005c6c4  test    rax, rax
0x18005c6c7  jnz     loc_18005C789
0x18005c6cd  xor     edi, edi
0x18005c6cf  lea     rdx, aNlsetclientatt_1; "NlSetClientAttributes: no primary domai"...
0x18005c6d6  mov     ecx, esi; unsigned int
0x18005c6d8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005c6dd  mov     ebx, 0C00000DFh
0x18005c6e2  jmp     loc_18005CCBB
0x18005c6e7  xor     r15b, r15b
0x18005c6ea  jmp     short loc_18005C6FE
0x18005c6ec  xor     r14d, r14d
0x18005c6ef  mov     r15b, bl
0x18005c6f2  test    r12, r12
0x18005c6f5  setnz   r14b
0x18005c6f9  test    r14d, r14d
0x18005c6fc  jz      short loc_18005C69E
0x18005c6fe  test    r12, r12
0x18005c701  jz      short loc_18005C69E
0x18005c703  call    IsDsGetServersAndSitesForNetLogonPresent
0x18005c708  test    al, al
0x18005c70a  jnz     short loc_18005C749
0x18005c70c  call    IsDsGetServersAndSitesForNetLogonPresent
0x18005c711  test    al, al
0x18005c713  jnz     short loc_18005C72E
0x18005c715  mov     r8d, 417h; unsigned int
0x18005c71b  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005c722  lea     rcx, aIsdnshostnamev; "IsDNSHostNameValueCheckForNetlogonPrese"...
0x18005c729  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005c72e  lea     rdx, aNlsetclientatt_13; "NlSetClientAttributes: DNSHostNameValue"...
0x18005c735  mov     ecx, 100h; unsigned int
0x18005c73a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005c73f  mov     eax, 0C00000BBh
0x18005c744  jmp     loc_18005CD82
0x18005c749  mov     rdi, [rsp+270h+var_210]
0x18005c74e  mov     rcx, r12
0x18005c751  mov     rdx, rdi
0x18005c754  call    cs:__imp_DNSHostNameValueCheckForNetlogon
0x18005c75b  nop     dword ptr [rax+rax+00h]
0x18005c760  test    eax, eax
0x18005c762  jz      loc_18005C69E
0x18005c768  mov     r9, rdi
0x18005c76b  lea     rdx, aNlsetclientatt_6; "NlSetClientAttributes: invalid DnsHostN"...
0x18005c772  mov     r8, r12
0x18005c775  mov     ecx, 100h; unsigned int
0x18005c77a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005c77f  mov     eax, 0C0000122h
0x18005c784  jmp     loc_18005CD82
0x18005c789  mov     rcx, rax; struct _DOMAIN_INFO *
0x18005c78c  call    ?NlRefDomClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@@Z; NlRefDomClientSession(_DOMAIN_INFO *)
0x18005c791  mov     rdi, rax
0x18005c794  test    rax, rax
0x18005c797  jnz     short loc_18005C7B1
0x18005c799  lea     rdx, aNlsetclientatt_5; "NlSetClientAttributes: no client sessio"...
0x18005c7a0  mov     ecx, esi; unsigned int
0x18005c7a2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005c7a7  mov     ebx, 0C000005Eh
0x18005c7ac  jmp     loc_18005CCBB
0x18005c7b1  test    bl, bl
0x18005c7b3  jz      short loc_18005C7DE
0x18005c7b5  test    r14d, r14d
0x18005c7b8  jnz     short loc_18005C7DE
0x18005c7ba  test    r15b, r15b
0x18005c7bd  jnz     short loc_18005C7DE
0x18005c7bf  test    dword ptr [rax+198h], 400h
0x18005c7c9  jz      short loc_18005C7DE
0x18005c7cb  xor     ebx, ebx
0x18005c7cd  lea     rdx, aNlsetclientatt_11; "NlSetClientAttributes: Skipping remote "...
0x18005c7d4  mov     ecx, 4000h
0x18005c7d9  jmp     loc_18005CCB6
0x18005c7de  mov     rdx, [rsp+270h+var_218]
0x18005c7e3  test    rdx, rdx
0x18005c7e6  jnz     short loc_18005C7EF
0x18005c7e8  mov     edx, 0EFFFFFFFh
0x18005c7ed  jmp     short loc_18005C7F1
0x18005c7ef  mov     edx, [rdx]
0x18005c7f1  lea     rcx, aUnavail; "<unavail>"
0x18005c7f8  test    r13, r13
0x18005c7fb  jz      short loc_18005C801
0x18005c7fd  mov     rcx, [r13+0]
0x18005c801  mov     r9d, [rbp+170h+arg_30]
0x18005c808  mov     dword ptr [rsp+270h+var_230], r9d
0x18005c80d  mov     r9d, r14d
0x18005c810  mov     dword ptr [rsp+270h+var_238], edx
0x18005c814  lea     rdx, aNlsetclientatt; "NlSetClientAttributes: Going remote: (%"...
0x18005c81b  mov     [rsp+270h+var_240], r12
0x18005c820  mov     [rsp+270h+var_248], rcx
0x18005c825  mov     ecx, 4000h; unsigned int
0x18005c82a  movzx   eax, bl
0x18005c82d  movzx   r8d, r15b
0x18005c831  mov     dword ptr [rsp+270h+var_250], eax
0x18005c835  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005c83a  test    r13, r13
0x18005c83d  jz      short loc_18005C85C
0x18005c83f  mov     rcx, [r13+0]; Block
0x18005c843  test    rcx, rcx
0x18005c846  jz      short loc_18005C854
0x18005c848  call    cs:__imp_free
0x18005c84f  nop     dword ptr [rax+rax+00h]
0x18005c854  mov     qword ptr [r13+0], 0
0x18005c85c  mov     r15, [rsp+270h+var_218]
0x18005c861  test    r15, r15
0x18005c864  jz      short loc_18005C86D
0x18005c866  mov     dword ptr [r15], 0
0x18005c86d  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x18005c873  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18005c876  call    ?NlTimeoutSetWriterClientSession@@YAHPEAU_CLIENT_SESSION@@K@Z; NlTimeoutSetWriterClientSession(_CLIENT_SESSION *,ulong)
0x18005c87b  test    eax, eax
0x18005c87d  jnz     short loc_18005C88B
0x18005c87f  lea     rdx, aNlsetclientatt_9; "NlSetClientAttributes: can't become wri"...
0x18005c886  jmp     loc_18005C7A0
0x18005c88b  mov     eax, 1
0x18005c890  xor     edx, edx; unsigned int
0x18005c892  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18005c895  mov     [rsp+270h+var_220], al
0x18005c899  mov     [rsp+270h+var_21F], al
0x18005c89d  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x18005c8a2  mov     ebx, eax
0x18005c8a4  test    eax, eax
0x18005c8a6  js      loc_18005CCAD
0x18005c8ac  lea     rax, [rdi+1B8h]
0x18005c8b3  lea     rcx, [rdi+1B0h]; struct _CYPHER_BLOCK *
0x18005c8ba  mov     r9d, [rdi+13Ch]; unsigned int
0x18005c8c1  lea     r8, [rbp+170h+var_178]; struct _NETLOGON_AUTHENTICATOR *
0x18005c8c5  mov     rdx, rax; struct _NETLOGON_SESSION_KEY *
0x18005c8c8  call    ?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z; NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)
0x18005c8cd  mov     ebx, eax
0x18005c8cf  test    eax, eax
0x18005c8d1  js      loc_18005CD6A
0x18005c8d7  mov     rbx, [rbp+170h+var_1E0]
0x18005c8db  xorps   xmm0, xmm0
0x18005c8de  mov     qword ptr [rbp+170h+var_1B8+8], 0
0x18005c8e6  xorps   xmm1, xmm1
0x18005c8e9  mov     [rsp+270h+Block], 0
0x18005c8f2  movdqu  [rbp+170h+var_198], xmm0
0x18005c8f7  movdqu  [rbp+170h+var_1F8+8], xmm1
0x18005c8fc  test    rbx, rbx
0x18005c8ff  jz      loc_18005C9E1
0x18005c905  xor     edx, edx; Val
0x18005c907  lea     rcx, [rbp+170h+var_14C]; void *
0x18005c90b  mov     r8d, 0FEh; Size
0x18005c911  call    memset_0
0x18005c916  mov     eax, [rbx]
0x18005c918  lea     rcx, [rbp+170h+var_14C]
0x18005c91c  mov     [rbp+170h+var_160], eax
0x18005c91f  mov     edx, 2
0x18005c924  mov     eax, [rbx+4]
0x18005c927  mov     [rbp+170h+var_15C], eax
0x18005c92a  mov     eax, [rbx+8]
0x18005c92d  mov     [rbp+170h+var_158], eax
0x18005c930  lea     r8d, [rdx+7Eh]
0x18005c934  mov     eax, [rbx+0Ch]
0x18005c937  mov     [rbp+170h+var_154], eax
0x18005c93a  mov     eax, [rbx+10h]
0x18005c93d  mov     [rbp+170h+var_150], eax
0x18005c940  movzx   eax, word ptr [rbx+114h]
0x18005c947  mov     [rbp+170h+var_4C], ax
0x18005c94e  movzx   eax, word ptr [rbx+116h]
0x18005c955  mov     [rbp+170h+var_4A], ax
0x18005c95c  movzx   eax, word ptr [rbx+118h]
0x18005c963  mov     [rbp+170h+var_48], ax
0x18005c96a  mov     al, [rbx+11Ah]
0x18005c970  mov     [rbp+170h+var_46], al
0x18005c976  mov     al, [rbx+11Bh]
0x18005c97c  mov     [rbp+170h+var_45], al
0x18005c982  lea     rax, [rbx+14h]
0x18005c986  movups  xmm0, xmmword ptr [rax]
0x18005c989  movups  xmm1, xmmword ptr [rax+10h]
0x18005c98d  movups  xmmword ptr [rcx], xmm0
0x18005c990  movups  xmm0, xmmword ptr [rax+20h]
0x18005c994  movups  xmmword ptr [rcx+10h], xmm1
0x18005c998  movups  xmm1, xmmword ptr [rax+30h]
0x18005c99c  movups  xmmword ptr [rcx+20h], xmm0
0x18005c9a0  movups  xmm0, xmmword ptr [rax+40h]
0x18005c9a4  movups  xmmword ptr [rcx+30h], xmm1
0x18005c9a8  movups  xmm1, xmmword ptr [rax+50h]
0x18005c9ac  movups  xmmword ptr [rcx+40h], xmm0
0x18005c9b0  movups  xmm0, xmmword ptr [rax+60h]
0x18005c9b4  movups  xmmword ptr [rcx+50h], xmm1
0x18005c9b8  movups  xmm1, xmmword ptr [rax+70h]
0x18005c9bc  add     rax, r8
0x18005c9bf  movups  xmmword ptr [rcx+60h], xmm0
0x18005c9c3  movups  xmmword ptr [rcx+70h], xmm1
0x18005c9c7  add     rcx, r8
0x18005c9ca  sub     rdx, 1
0x18005c9ce  jnz     short loc_18005C986
0x18005c9d0  xor     eax, eax
0x18005c9d2  mov     [rbp+170h+var_4E], ax
0x18005c9d9  lea     rax, [rbp+170h+var_160]
0x18005c9dd  mov     qword ptr [rbp+170h+var_1B8+8], rax
0x18005c9e1  mov     eax, r14d
0x18005c9e4  mov     qword ptr [rsp+270h+var_1F8], r15
  ... truncated ...
```
