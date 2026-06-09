# NlSessionSetup(_CLIENT_SESSION *,uchar)

- ea: `0x1800378d4`
- end: `0x1800382ef`
- name: `?NlSessionSetup@@YAJPEAU_CLIENT_SESSION@@E@Z`
- size: `2587`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, unsigned __int8)`
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800378d4`
- `0x1800382f8`

## callees

- `0x180004420`
- `0x180007278`
- `0x18000d100`
- `0x18000d710`
- `0x18000e270`
- `0x1800291f4`
- `0x180034a40`
- `0x180036df8`
- `0x1800378d4`
- `0x180039194`
- `0x1800395e8`
- `0x18003e71c`
- `0x18003f684`
- `0x18004d664`
- `0x180064834`
- `0x18006515c`
- `0x180068458`
- `0x1800688e0`
- `0x180069580`
- `0x1800898c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003807a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003807a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180037be5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180037be5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180037f20`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180037f20`
- `logoncli!I_NetServerAuthenticateKerberos` at `0x180037ce7`
- `logoncli!I_NetServerAuthenticateKerberos` at `0x180037ce7`
- `ntdll!RtlLeaveCriticalSection` at `0x180037f2d`
- `ntdll!RtlLeaveCriticalSection` at `0x180037f2d`
- `ntdll!RtlEnterCriticalSection` at `0x180037f16`
- `ntdll!RtlEnterCriticalSection` at `0x180037f16`
- `netutils!NetApiBufferFree` at `0x180037b30`
- `netutils!NetApiBufferFree` at `0x180037eb8`
- `netutils!NetApiBufferFree` at `0x180037b30`
- `netutils!NetApiBufferFree` at `0x180037eb8`
- `CRYPTBASE!SystemFunction036` at `0x180037b74`
- `CRYPTBASE!SystemFunction036` at `0x180037b74`

## string_xrefs

- `0x18003796b`: `ClientSession->CsFlags & CS_WRITER`
- `0x180037942`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180037964`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180037a1e`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180037a75`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180037d03`: `NlSessionSetup: Denied access as we could not authenticate with Kerberos 0x%lX\n`
- `0x180037d27`: `NlSessionSetup: Denied access as we could not authenticate with Kerberos (translated status) 0x%lX\n`
- `0x180037dce`: `NlSessionSetup: denying access due to being unable to authenticate with Netlogon 0x%lX\n`
- `0x180037dff`: `NlSessionSetup: denying access because of unmatching capabilities 0x%lX\n`
- `0x180037e4d`: `NlSessionSetup: NlUpdateDomainInfo failed 0x%lX\n`

## pseudocode

```c
__int64 __fastcall NlSessionSetup(struct _CLIENT_SESSION *a1, __int64 a2, __int64 a3, char *a4)
{
  bool v4; // si
  unsigned __int8 v5; // di
  char v7; // r12
  char v8; // r13
  char v9; // r14
  int v10; // r15d
  unsigned int v11; // edx
  char *v12; // r9
  char *v13; // r9
  int DcNameEx2; // eax
  void *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // r8
  char *v20; // r9
  char v21; // di
  __int64 v22; // rcx
  DWORD v23; // edi
  int v24; // ecx
  __int64 v25; // r9
  unsigned int v26; // eax
  unsigned __int64 v27; // rax
  __int64 v28; // rdx
  unsigned __int8 v29; // al
  __int64 v30; // r8
  char *v31; // r9
  int v32; // eax
  int v33; // eax
  int updated; // eax
  __int64 v35; // rax
  int ForestTrustInfoHigher; // eax
  int v37; // r9d
  const char *v38; // r9
  unsigned int v39; // edx
  unsigned __int8 v40; // dl
  int v41; // eax
  const char *v43; // r9
  __int64 v44; // r8
  char *v45; // r9
  __int64 v46; // rcx
  unsigned int v47; // ecx
  int v48; // edx
  char v49; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v50[4]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int8 v51; // [rsp+48h] [rbp-B8h] BYREF
  char v52; // [rsp+49h] [rbp-B7h]
  char v53; // [rsp+4Ah] [rbp-B6h]
  unsigned __int8 v54; // [rsp+4Bh] [rbp-B5h]
  LPVOID Buffer; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v56[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v57; // [rsp+68h] [rbp-98h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  _BYTE v59[528]; // [rsp+80h] [rbp-80h] BYREF

  v4 = 0;
  v54 = a2;
  v5 = a2;
  v7 = 0;
  *(_DWORD *)v50 = 0;
  v8 = 0;
  v52 = 0;
  v9 = 0;
  v51 = 0;
  v10 = 0;
  v49 = 0;
  v53 = 0;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      4397,
      a4);
  if ( (*((_BYTE *)a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      4398,
      a4);
  if ( v5 )
  {
    if ( !dword_1800F12A4 )
    {
      *(_DWORD *)v50 = -1073741811;
      goto LABEL_68;
    }
    LOBYTE(a2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::GetImpl'::`2'::impl,
      a2);
  }
  NlPrintCsRoutine(0x200u, a1, L"NlSessionSetup: Try Session setup\n");
  NlpTraceEvent(1u, v11);
  if ( !NlGlobalCDC || *((_DWORD *)a1 + 70) == 7 )
  {
    NlPrintRoutine(0x80000u, L"NlSessionSetup: ClientSession->CsState = 0x%lx\n", *((unsigned int *)a1 + 71));
    if ( *((_DWORD *)a1 + 71) )
      goto LABEL_19;
    if ( *((_QWORD *)a1 + 63) )
      NlAssertFailed(
        "ClientSession->CsUncServerName == NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
        4436,
        v12);
    v7 = 1;
    *(_DWORD *)v50 = NlDiscoverDc((__int64)a1, 2, 0, 0);
    if ( *(int *)v50 >= 0 )
    {
      if ( !*((_DWORD *)a1 + 71) )
        NlAssertFailed(
          "ClientSession->CsState != CS_IDLE",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
          4466,
          v13);
      goto LABEL_19;
    }
    NlPrintCsRoutine(0x100u, a1, L"NlSessionSetup: Session setup: cannot pick trusted DC\n");
  }
  else
  {
    NlPrintCsRoutine(
      0x200u,
      a1,
      L"NlSessionSetup: RODC is asked to establish a non CdcSecureChannel. Failing session setup.\n");
    *(_DWORD *)v50 = -1073741430;
  }
LABEL_68:
  if ( *(int *)v50 >= 0 )
  {
    NlSetStatusClientSession(a1, *(int *)v50, a3, a4);
    v37 = *((_DWORD *)a1 + 79);
    *((_DWORD *)a1 + 80) = 0;
    *((_QWORD *)a1 + 53) = 0;
    if ( v37 != v10 )
      NlPrintCsRoutine(0x200u, a1, L"NlSessionSetup: negotiated %lx flags rather than %lx\n");
    goto LABEL_71;
  }
  while ( 1 )
  {
    if ( (*((_DWORD *)a1 + 73) & 0x80000) != 0 )
      goto LABEL_71;
    v58 = 0;
    *(_OWORD *)v56 = 0;
    v57 = 0;
    _o_wcscpy_s(v59, 258);
    if ( !v51 )
      goto LABEL_92;
    v21 = 0;
    if ( !v7 )
      v4 = NlTimeToRediscover(a1, 0) != 0;
    if ( !v8 && (*(_DWORD *)v50 == -1073741724 || *(_DWORD *)v50 == -1073741429) )
      v21 = NlTimeToRediscover(a1, 1u) != 0;
    if ( v4 )
    {
      v4 = 0;
    }
    else
    {
      v4 = 0;
      if ( !v21 )
        goto LABEL_92;
    }
    v43 = "with";
    if ( !v21 )
      v43 = "without";
    NlPrintCsRoutine(
      0x200u,
      a1,
      L"NlSessionSetup: Retry failed session setup (%hs account) since discovery wasn't recent.\n",
      v43);
    NlSetStatusClientSession(a1, -1073741730, v44, v45);
    if ( (int)NlDiscoverDc((__int64)a1, 2, 0, v21) < 0 )
      break;
    if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)a1 + 63)) )
    {
      NlPrintCsRoutine(0x200u, a1, L"NlSessionSetup: Skip retry failed session setup since same DC discovered.\n");
      goto LABEL_92;
    }
    v8 = v21;
    v52 = v21;
    v5 = v54;
    v7 = 1;
LABEL_19:
    if ( NlGlobalMemberWorkstation && (*((_BYTE *)a1 + 408) & 4) == 0 && (*((_BYTE *)a1 + 292) & 4) != 0 )
    {
      Buffer = 0;
      v49 = 1;
      NlPrintCsRoutine(0x100u, a1, L"NlSessionSetup: Only downlevel DC available\n");
      DcNameEx2 = DsrGetDcNameEx2(0, 0, 0, 0, 0, 0, 0x81u, (struct _DOMAIN_CONTROLLER_INFOW **)&Buffer);
      v15 = Buffer;
      if ( !DcNameEx2 && (*((_BYTE *)Buffer + 56) & 0x10) == 0 )
      {
        v53 = 1;
        NlPrintCsRoutine(0x100u, a1, L"NlSessionSetup: NT5 domain has been downgraded.\n");
        v15 = Buffer;
      }
      if ( v15 )
        NetApiBufferFree(v15);
      *(_DWORD *)v50 = -1073741730;
      v9 = 1;
      v51 = 1;
    }
    else
    {
      if ( !v5 )
      {
        v32 = NlSessionAuthenticationNetlogon(a1, &v51);
        *(_DWORD *)v50 = v32;
        if ( v32 < 0 )
        {
          NlPrintCsRoutine(
            0x200u,
            a1,
            L"NlSessionSetup: denying access due to being unable to authenticate with Netlogon 0x%lX\n",
            (unsigned int)v32);
          goto LABEL_67;
        }
LABEL_55:
        v33 = NlConfirmCapabilities(a1);
        *(_DWORD *)v50 = v33;
        if ( v33 >= 0 )
        {
          if ( (*((_DWORD *)a1 + 73) & 0x20000) == 0 )
          {
            if ( NlGlobalMemberWorkstation )
            {
              updated = NlUpdateDomainInfo(a1);
              *(_DWORD *)v50 = updated;
              if ( updated < 0 )
              {
                NlPrintCsRoutine(
                  0x100u,
                  a1,
                  L"NlSessionSetup: NlUpdateDomainInfo failed 0x%lX\n",
                  (unsigned int)updated);
                goto LABEL_61;
              }
            }
            else
            {
              v35 = *((_QWORD *)a1 + 34);
              Buffer = 0;
              if ( *(_DWORD *)(v35 + 588) == 1 && (*((_BYTE *)a1 + 296) & 8) != 0 )
              {
                ForestTrustInfoHigher = NlpGetForestTrustInfoHigher(
                                          a1,
                                          1u,
                                          0,
                                          1u,
                                          (struct _LSA_FOREST_TRUST_INFORMATION **)&Buffer);
                *(_DWORD *)v50 = ForestTrustInfoHigher;
                if ( ForestTrustInfoHigher >= 0 )
                {
                  NetApiBufferFree(Buffer);
                }
                else
                {
                  NlPrintCsRoutine(
                    0x100u,
                    a1,
                    L"NlSessionSetup: NlpGetForestTrustInfoHigher failed 0x%lX\n",
                    (unsigned int)ForestTrustInfoHigher);
LABEL_61:
                  v51 = 1;
                }
              }
            }
          }
LABEL_67:
          v9 = v49;
          goto LABEL_68;
        }
        NlPrintCsRoutine(
          0x200u,
          a1,
          L"NlSessionSetup: denying access because of unmatching capabilities 0x%lX\n",
          (unsigned int)v33);
        *(_DWORD *)v50 = -1073741790;
        v51 = 1;
        goto LABEL_31;
      }
      *((_DWORD *)a1 + 71) = 2;
      *((_DWORD *)a1 + 79) = -1073741824;
      if ( !SystemFunction036((char *)a1 + 440, 0x10u) )
      {
        NlPrintCsRoutine(0x100u, a1, L"RtlGenRandom failed.\n");
        v4 = 0;
        *(_DWORD *)v50 = -1073741595;
        goto LABEL_31;
      }
      v22 = dword_1800F123C != 0 ? 0x2000 : 0;
      v10 = v22 | (dword_1800F1238 != 0 ? -516956161 : -516960257);
      if ( !*((_QWORD *)a1 + 63) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v22, v16, v17, v18);
      *((_DWORD *)a1 + 79) |= v10;
      v23 = 0;
      *((_DWORD *)a1 + 78) = v10;
      v24 = -1073610748;
      *(_DWORD *)v50 = -1073610748;
      do
      {
        *(_DWORD *)v50 = NlStartApiClientSession(a1, 1, v23, v24, (struct _CLIENT_SESSION *)((char *)a1 + 680));
        v24 = *(_DWORD *)v50;
        if ( *(int *)v50 >= 0 )
        {
          if ( (*((_DWORD *)a1 + 73) & 0x40000) != 0 )
            v25 = *((_QWORD *)a1 + 27);
          else
            v25 = *(_QWORD *)(*((_QWORD *)a1 + 34) + 264LL);
          v26 = I_NetServerAuthenticateKerberos(
                  *((_QWORD *)a1 + 63),
                  *((_QWORD *)a1 + 25),
                  *((unsigned int *)a1 + 70),
                  v25,
                  (char *)a1 + 316,
                  (char *)a1 + 488);
          *(_DWORD *)v50 = v26;
          v24 = v26;
          if ( v26 )
          {
            NlPrintCsRoutine(
              0x200u,
              a1,
              L"NlSessionSetup: Denied access as we could not authenticate with Kerberos 0x%lX\n",
              v26);
            *(_DWORD *)v50 = NetpApiStatusToNtStatus(*(unsigned int *)v50);
            NlPrintCsRoutine(
              0x200u,
              a1,
              L"NlSessionSetup: Denied access as we could not authenticate with Kerberos (translated status) 0x%lX\n",
              *(unsigned int *)v50);
            v24 = *(_DWORD *)v50;
          }
          else
          {
            *((_DWORD *)a1 + 176) |= 0x14u;
          }
        }
        v27 = (unsigned int)(v24 + 1073610748);
        if ( (unsigned int)v27 > 0x32 )
          break;
        v28 = 0x4000000080001LL;
        if ( !_bittest64(&v28, v27) )
          break;
        ++v23;
      }
      while ( v23 < 2 );
      v29 = NlFinishApiClientSession(a1, 1u, 1u, (struct _CLIENT_SESSION *)((char *)a1 + 680));
      v8 = v52;
      v4 = 0;
      if ( !v29 )
        NlPrintCsRoutine(
          0x100u,
          a1,
          L"NlSessionSetup: Session setup: cannot FinishApiClientSession for I_NetServerAuthenticateKerberos 0x%lx\n",
          *(unsigned int *)v50);
      NlSetStatusClientSession(a1, *(int *)v50, v30, v31);
      if ( *(int *)v50 >= 0 )
        goto LABEL_55;
LABEL_31:
      v9 = v49;
    }
  }
  NlPrintCsRoutine(0x100u, a1, L"NlSessionSetup: Session setup: cannot re-pick trusted DC\n");
LABEL_92:
  switch ( *(_DWORD *)v50 )
  {
    case 0xC0000022:
      v56[0] = *((unsigned __int16 **)a1 + 23);
      v56[1] = (unsigned __int16 *)v59;
      *(_QWORD *)&v57 = 0;
      NlpWriteEventlogEx(0xC8Au, 1u, 0, 0xFFFFFFFF, v56, 2u, v50, 4u);
      goto LABEL_111;
    case 0xC000005E:
      goto LABEL_100;
    case 0xC000018A:
      if ( !NlGlobalCDC || *((_DWORD *)a1 + 70) == 7 )
      {
        v56[0] = (unsigned __int16 *)v59;
        v56[1] = *((unsigned __int16 **)a1 + 23);
        v57 = *(unsigned __int64 *)(*((_QWORD *)a1 + 34) + 264LL);
        NlpWriteEventlogEx(0x1658u, 1u, 0, 0xFFFFFFFF, v56, 3u, v50, 4u);
        goto LABEL_111;
      }
      break;
    case 0xC000018B:
      v56[0] = (unsigned __int16 *)v59;
      v56[1] = *((unsigned __int16 **)a1 + 23);
      v46 = *(_QWORD *)(*((_QWORD *)a1 + 34) + 264LL);
      *((_QWORD *)&v57 + 1) = *((_QWORD *)a1 + 25);
      *(_QWORD *)&v57 = v46;
      v58 = 0;
      NlpWriteEventlogEx(0x1659u, 1u, 0, 0xFFFFFFFF, v56, 4u, v50, 4u);
      goto LABEL_111;
    default:
LABEL_100:
      v56[0] = *((unsigned __int16 **)a1 + 23);
      v56[1] = (unsigned __int16 *)*(int *)v50;
      if ( v53 )
      {
        v47 = 5791;
        goto LABEL_108;
      }
      if ( v9 )
      {
        v47 = 5790;
        goto LABEL_108;
      }
      if ( NlGlobalWinsockPnpAddressSize || NlGlobalV6WinsockPnpAddressSize )
      {
        v47 = 5719;
LABEL_108:
        NlpWriteEventlogEx(v47, 1u, 0x80000000, 0xFFFFFFFF, v56, 2u, v50, 4u);
      }
      else
      {
        NlPrintRoutine(0x200u, L"No IP addresses present, skipping No DC event log\n");
      }
      v56[0] = *((unsigned __int16 **)a1 + 23);
      v56[1] = (unsigned __int16 *)v59;
      *(_QWORD *)&v57 = 0;
LABEL_111:
      *((_DWORD *)a1 + 80) = (*((_DWORD *)a1 + 80) + 1) % 0xAu;
      break;
  }
  if ( *(_DWORD *)v50 == -1073741790 || (unsigned int)(*(_DWORD *)v50 + 1073741430) <= 1 )
    v48 = *(_DWORD *)v50;
  else
    v48 = -1073741730;
  NlSetStatusClientSession(a1, v48, v19, v20);
LABEL_71:
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  GetSystemTimeAsFileTime((LPFILETIME)a1 + 2);
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  v38 = "Succeeded";
  if ( *((int *)a1 + 72) < 0 )
    v38 = "Failed";
  NlPrintCsRoutine(0x200u, a1, L"NlSessionSetup: Session setup %hs\n", v38);
  if ( *(_DWORD *)v50 == -1073741790 && (*((_DWORD *)a1 + 73) & 0xC0000) == 0x40000 )
  {
    v40 = v54;
    *((_DWORD *)a1 + 73) |= 0x80000u;
    v41 = NlSessionSetup(a1, v40);
    *((_DWORD *)a1 + 73) &= ~0x80000u;
    *(_DWORD *)v50 = v41;
  }
  NlpTraceEvent(2u, v39);
  return *(unsigned int *)v50;
}

```

## disassembly

```asm
0x1800378d4  mov     [rsp-8+arg_10], rbx
0x1800378d9  push    rbp
0x1800378da  push    rsi
0x1800378db  push    rdi
0x1800378dc  push    r12
0x1800378de  push    r13
0x1800378e0  push    r14
0x1800378e2  push    r15
0x1800378e4  lea     rbp, [rsp-1A0h]
0x1800378ec  sub     rsp, 2A0h
0x1800378f3  mov     rax, cs:__security_cookie
0x1800378fa  xor     rax, rsp
0x1800378fd  mov     [rbp+1D0h+var_40], rax
0x180037904  xor     esi, esi
0x180037906  mov     [rsp+2D0h+var_285], dl
0x18003790a  mov     dil, dl
0x18003790d  mov     rbx, rcx
0x180037910  mov     r12b, sil
0x180037913  mov     dword ptr [rsp+2D0h+var_28C], esi
0x180037917  mov     r13b, sil
0x18003791a  mov     [rsp+2D0h+var_287], sil
0x18003791f  mov     r14b, sil
0x180037922  mov     [rsp+2D0h+var_288], sil
0x180037927  mov     r15d, esi
0x18003792a  mov     [rsp+2D0h+var_290], sil
0x18003792f  mov     [rsp+2D0h+var_286], sil
0x180037934  cmp     [rcx+148h], esi
0x18003793a  ja      short loc_180037955
0x18003793c  mov     r8d, 112Dh; unsigned int
0x180037942  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180037949  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180037950  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180037955  test    byte ptr [rbx+124h], 8
0x18003795c  jnz     short loc_180037977
0x18003795e  mov     r8d, 112Eh; unsigned int
0x180037964  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18003796b  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x180037972  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180037977  test    dil, dil
0x18003797a  jz      short loc_180037992
0x18003797c  cmp     cs:dword_1800F12A4, esi
0x180037982  jz      short loc_1800379E2
0x180037984  mov     dl, 1
0x180037986  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos> `wil::Feature<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::GetImpl(void)'::`2'::impl
0x18003798d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180037992  lea     r8, aNlsessionsetup_2; "NlSessionSetup: Try Session setup\n"
0x180037999  mov     rdx, rbx; struct _CLIENT_SESSION *
0x18003799c  mov     ecx, 200h; unsigned int
0x1800379a1  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800379a6  mov     ecx, 1; unsigned int
0x1800379ab  call    ?NlpTraceEvent@@YAXKK@Z; NlpTraceEvent(ulong,ulong)
0x1800379b0  cmp     cs:?NlGlobalCDC@@3HA, esi; int NlGlobalCDC
0x1800379b6  jz      short loc_1800379EF
0x1800379b8  cmp     dword ptr [rbx+118h], 7
0x1800379bf  jz      short loc_1800379EF
0x1800379c1  lea     r8, aNlsessionsetup_15; "NlSessionSetup: RODC is asked to establ"...
0x1800379c8  mov     rdx, rbx; struct _CLIENT_SESSION *
0x1800379cb  mov     ecx, 200h; unsigned int
0x1800379d0  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800379d5  mov     dword ptr [rsp+2D0h+var_28C], 0C000018Ah
0x1800379dd  jmp     loc_180037EC3
0x1800379e2  mov     dword ptr [rsp+2D0h+var_28C], 0C000000Dh
0x1800379ea  jmp     loc_180037EC3
0x1800379ef  mov     r8d, [rbx+11Ch]
0x1800379f6  lea     rdx, aNlsessionsetup_28; "NlSessionSetup: ClientSession->CsState "...
0x1800379fd  mov     ecx, 80000h; unsigned int
0x180037a02  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180037a07  cmp     [rbx+11Ch], esi
0x180037a0d  jnz     short loc_180037A88
0x180037a0f  cmp     [rbx+1F8h], rsi
0x180037a16  jz      short loc_180037A31
0x180037a18  mov     r8d, 1154h; unsigned int
0x180037a1e  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180037a25  lea     rcx, aClientsessionC; "ClientSession->CsUncServerName == NULL"
0x180037a2c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180037a31  xor     r9d, r9d
0x180037a34  xor     r8d, r8d
0x180037a37  mov     rcx, rbx
0x180037a3a  mov     r12b, 1
0x180037a3d  lea     edx, [r9+2]
0x180037a41  call    ?NlDiscoverDc@@YAJPEAU_CLIENT_SESSION@@W4_DISCOVERY_TYPE@@EE@Z; NlDiscoverDc(_CLIENT_SESSION *,_DISCOVERY_TYPE,uchar,uchar)
0x180037a46  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180037a4a  test    eax, eax
0x180037a4c  jns     short loc_180037A67
0x180037a4e  lea     r8, aNlsessionsetup_1; "NlSessionSetup: Session setup: cannot p"...
0x180037a55  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180037a58  mov     ecx, 100h; unsigned int
0x180037a5d  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180037a62  jmp     loc_180037EC3
0x180037a67  cmp     [rbx+11Ch], esi
0x180037a6d  jnz     short loc_180037A88
0x180037a6f  mov     r8d, 1172h; unsigned int
0x180037a75  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180037a7c  lea     rcx, aClientsessionC_7; "ClientSession->CsState != CS_IDLE"
0x180037a83  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180037a88  cmp     cs:?NlGlobalMemberWorkstation@@3HA, esi; int NlGlobalMemberWorkstation
0x180037a8e  jz      loc_180037B48
0x180037a94  test    byte ptr [rbx+198h], 4
0x180037a9b  jnz     loc_180037B48
0x180037aa1  test    byte ptr [rbx+124h], 4
0x180037aa8  jz      loc_180037B48
0x180037aae  mov     r14d, 100h
0x180037ab4  mov     [rsp+2D0h+Buffer], rsi
0x180037ab9  mov     edi, 1
0x180037abe  lea     r8, aNlsessionsetup_18; "NlSessionSetup: Only downlevel DC avail"...
0x180037ac5  mov     ecx, r14d; unsigned int
0x180037ac8  mov     [rsp+2D0h+var_290], dil
0x180037acd  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180037ad0  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180037ad5  lea     rax, [rsp+2D0h+Buffer]
0x180037ada  xor     r9d, r9d
0x180037add  mov     qword ptr [rsp+2D0h+var_298], rax
0x180037ae2  xor     r8d, r8d
0x180037ae5  mov     dword ptr [rsp+2D0h+var_2A0], 81h
0x180037aed  xor     edx, edx
0x180037aef  mov     qword ptr [rsp+2D0h+var_2A8], rsi
0x180037af4  xor     ecx, ecx
0x180037af6  mov     [rsp+2D0h+var_2B0], rsi
0x180037afb  call    DsrGetDcNameEx2
0x180037b00  mov     rcx, [rsp+2D0h+Buffer]
0x180037b05  test    eax, eax
0x180037b07  jnz     short loc_180037B2B
0x180037b09  test    byte ptr [rcx+38h], 10h
0x180037b0d  jnz     short loc_180037B2B
0x180037b0f  lea     r8, aNlsessionsetup_9; "NlSessionSetup: NT5 domain has been dow"...
0x180037b16  mov     [rsp+2D0h+var_286], dil
0x180037b1b  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180037b1e  mov     ecx, r14d; unsigned int
0x180037b21  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180037b26  mov     rcx, [rsp+2D0h+Buffer]; Buffer
0x180037b2b  test    rcx, rcx
0x180037b2e  jz      short loc_180037B36
0x180037b30  call    cs:__imp_NetApiBufferFree
0x180037b36  mov     dword ptr [rsp+2D0h+var_28C], 0C000005Eh
0x180037b3e  mov     r14b, dil
0x180037b41  mov     [rsp+2D0h+var_288], dil
0x180037b46  jmp     short loc_180037BA5
0x180037b48  test    dil, dil
0x180037b4b  jz      loc_180037DB6
0x180037b51  lea     rsi, [rbx+13Ch]
0x180037b58  mov     dword ptr [rbx+11Ch], 2
0x180037b62  lea     rcx, [rbx+1B8h]; RandomBuffer
0x180037b69  mov     dword ptr [rsi], 0C0000000h
0x180037b6f  mov     edx, 10h; RandomBufferLength
0x180037b74  call    cs:__imp_SystemFunction036
0x180037b7a  test    al, al
0x180037b7c  jnz     loc_180037C1F
0x180037b82  lea     r8, aRtlgenrandomFa; "RtlGenRandom failed.\n"
0x180037b89  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180037b8c  mov     ecx, 100h; unsigned int
0x180037b91  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180037b96  xor     esi, esi
0x180037b98  mov     dword ptr [rsp+2D0h+var_28C], 0C00000E5h
0x180037ba0  mov     r14b, [rsp+2D0h+var_290]
0x180037ba5  test    dword ptr [rbx+124h], 80000h
0x180037baf  jnz     loc_180037F0F
0x180037bb5  mov     r8, [rbx+1F8h]
0x180037bbc  lea     rcx, [rbp+1D0h+var_250]
0x180037bc0  xor     eax, eax
0x180037bc2  xorps   xmm0, xmm0
0x180037bc5  mov     [rsp+2D0h+var_258], rax
0x180037bca  mov     edx, 102h
0x180037bcf  movups  xmmword ptr [rsp+2D0h+var_278], xmm0
0x180037bd4  movups  [rsp+2D0h+var_268], xmm0
0x180037bd9  test    r8, r8
0x180037bdc  jnz     short loc_180037BE5
0x180037bde  lea     r8, aUnknown_5; "<Unknown>"
0x180037be5  call    cs:__imp__o_wcscpy_s
0x180037beb  cmp     [rsp+2D0h+var_288], sil
0x180037bf0  jz      loc_1800380BB
0x180037bf6  xor     dil, dil
0x180037bf9  test    r12b, r12b
0x180037bfc  jnz     loc_180037FDB
0x180037c02  xor     edx, edx; unsigned __int8
0x180037c04  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180037c07  call    ?NlTimeToRediscover@@YAEPEAU_CLIENT_SESSION@@E@Z; NlTimeToRediscover(_CLIENT_SESSION *,uchar)
0x180037c0c  test    al, al
0x180037c0e  movzx   esi, sil
0x180037c12  mov     edx, 1
0x180037c17  cmovnz  esi, edx
0x180037c1a  jmp     loc_180037FE0
0x180037c1f  mov     eax, cs:dword_1800F1238
0x180037c25  neg     eax
0x180037c27  mov     eax, cs:dword_1800F123C
0x180037c2d  sbb     r15d, r15d
0x180037c30  and     r15d, 1000h
0x180037c37  add     r15d, 0E12FCFFFh
0x180037c3e  neg     eax
0x180037c40  sbb     ecx, ecx
0x180037c42  and     ecx, 2000h
0x180037c48  or      r15d, ecx
0x180037c4b  cmp     qword ptr [rbx+1F8h], 0
0x180037c53  jnz     short loc_180037C5A
0x180037c55  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180037c5a  or      [rsi], r15d
0x180037c5d  lea     r14, [rbx+2A8h]
0x180037c64  xor     edi, edi
0x180037c66  mov     [rbx+138h], r15d
0x180037c6d  mov     ecx, 0C0020004h
0x180037c72  mov     dword ptr [rsp+2D0h+var_28C], ecx
0x180037c76  lea     r13d, [rdi+1]
0x180037c7a  mov     r9d, ecx; int
0x180037c7d  mov     [rsp+2D0h+var_2B0], r14; struct _CLIENT_API *
0x180037c82  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180037c85  mov     r8d, edi; unsigned int
0x180037c88  mov     dl, r13b; unsigned __int8
0x180037c8b  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x180037c90  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180037c94  mov     ecx, eax
0x180037c96  test    eax, eax
0x180037c98  js      loc_180037D3F
0x180037c9e  test    dword ptr [rbx+124h], 40000h
0x180037ca8  lea     rcx, [rbx+1E8h]
0x180037caf  jz      short loc_180037CBA
0x180037cb1  mov     r9, [rbx+0D8h]
0x180037cb8  jmp     short loc_180037CC8
0x180037cba  mov     rax, [rbx+110h]
0x180037cc1  mov     r9, [rax+108h]
0x180037cc8  mov     r8d, [rbx+118h]
0x180037ccf  mov     rdx, [rbx+0C8h]
0x180037cd6  mov     qword ptr [rsp+2D0h+var_2A8], rcx
0x180037cdb  mov     rcx, [rbx+1F8h]
0x180037ce2  mov     [rsp+2D0h+var_2B0], rsi
0x180037ce7  call    cs:__imp_I_NetServerAuthenticateKerberos
0x180037ced  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180037cf1  mov     ecx, eax
0x180037cf3  test    eax, eax
0x180037cf5  jnz     short loc_180037D00
0x180037cf7  or      dword ptr [rbx+2C0h], 14h
0x180037cfe  jmp     short loc_180037D3F
0x180037d00  mov     r9d, eax
0x180037d03  lea     r8, aNlsessionsetup_27; "NlSessionSetup: Denied access as we cou"...
0x180037d0a  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180037d0d  mov     ecx, 200h; unsigned int
0x180037d12  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180037d17  mov     ecx, dword ptr [rsp+2D0h+var_28C]
0x180037d1b  call    NetpApiStatusToNtStatus
0x180037d20  mov     r9d, eax
0x180037d23  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180037d27  lea     r8, aNlsessionsetup_36; "NlSessionSetup: Denied access as we cou"...
0x180037d2e  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180037d31  mov     ecx, 200h; unsigned int
0x180037d36  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180037d3b  mov     ecx, dword ptr [rsp+2D0h+var_28C]
0x180037d3f  lea     eax, [rcx+3FFDFFFCh]
0x180037d45  cmp     eax, 32h ; '2'
0x180037d48  ja      short loc_180037D66
0x180037d4a  mov     rdx, 4000000080001h
0x180037d54  bt      rdx, rax
0x180037d58  jnb     short loc_180037D66
0x180037d5a  add     edi, r13d
0x180037d5d  cmp     edi, 2
0x180037d60  jb      loc_180037C7A
0x180037d66  mov     r9, r14; struct _CLIENT_API *
0x180037d69  mov     r8b, r13b; unsigned __int8
0x180037d6c  mov     dl, r13b; unsigned __int8
0x180037d6f  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180037d72  mov     edi, r13d
0x180037d75  call    ?NlFinishApiClientSession@@YAEPEAU_CLIENT_SESSION@@EEPEAU_CLIENT_API@@@Z; NlFinishApiClientSession(_CLIENT_SESSION *,uchar,uchar,_CLIENT_API *)
0x180037d7a  mov     r13b, [rsp+2D0h+var_287]
0x180037d7f  xor     esi, esi
0x180037d81  test    al, al
0x180037d83  jnz     short loc_180037D9E
0x180037d85  mov     r9d, dword ptr [rsp+2D0h+var_28C]
0x180037d8a  lea     r8, aNlsessionsetup_0; "NlSessionSetup: Session setup: cannot F"...
0x180037d91  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180037d94  mov     ecx, 100h; unsigned int
0x180037d99  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180037d9e  mov     edx, dword ptr [rsp+2D0h+var_28C]; int
0x180037da2  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180037da5  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x180037daa  cmp     dword ptr [rsp+2D0h+var_28C], esi
0x180037dae  jl      loc_180037BA0
0x180037db4  jmp     short loc_180037DEC
0x180037db6  lea     rdx, [rsp+2D0h+var_288]; unsigned __int8 *
0x180037dbb  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180037dbe  call    ?NlSessionAuthenticationNetlogon@@YAJPEAU_CLIENT_SESSION@@PEAE@Z; NlSessionAuthenticationNetlogon(_CLIENT_SESSION *,uchar *)
0x180037dc3  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180037dc7  test    eax, eax
0x180037dc9  jns     short loc_180037DE7
0x180037dcb  mov     r9d, eax
0x180037dce  lea     r8, aNlsessionsetup_38; "NlSessionSetup: denying access due to b"...
0x180037dd5  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180037dd8  mov     ecx, 200h; unsigned int
0x180037ddd  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180037de2  jmp     loc_180037EBE
0x180037de7  mov     edi, 1
0x180037dec  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180037def  call    ?NlConfirmCapabilities@@YAJPEAU_CLIENT_SESSION@@@Z; NlConfirmCapabilities(_CLIENT_SESSION *)
0x180037df4  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180037df8  test    eax, eax
0x180037dfa  jns     short loc_180037E25
0x180037dfc  mov     r9d, eax
0x180037dff  lea     r8, aNlsessionsetup_10; "NlSessionSetup: denying access because "...
0x180037e06  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180037e09  mov     ecx, 200h; unsigned int
0x180037e0e  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180037e13  mov     dword ptr [rsp+2D0h+var_28C], 0C0000022h
0x180037e1b  mov     [rsp+2D0h+var_288], dil
0x180037e20  jmp     loc_180037BA0
  ... truncated ...
```
