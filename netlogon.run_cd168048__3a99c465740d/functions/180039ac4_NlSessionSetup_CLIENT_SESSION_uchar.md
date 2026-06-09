# NlSessionSetup(_CLIENT_SESSION *,uchar)

- ea: `0x180039ac4`
- end: `0x18003a516`
- name: `?NlSessionSetup@@YAJPEAU_CLIENT_SESSION@@E@Z`
- size: `2642`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, unsigned __int8)`
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180039ac4`
- `0x18003a51c`

## callees

- `0x1800046b0`
- `0x180007518`
- `0x18000d7a0`
- `0x18000dd00`
- `0x18000e910`
- `0x18002a8e0`
- `0x1800369d0`
- `0x180038f68`
- `0x180039ac4`
- `0x18003b434`
- `0x18003b8d4`
- `0x180040f18`
- `0x180041fbc`
- `0x180050c2c`
- `0x180069290`
- `0x180069c60`
- `0x18006d2b0`
- `0x18006d794`
- `0x18006e50c`
- `0x180090008`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a29b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a29b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180039de1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180039de1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003a134`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003a134`
- `logoncli!I_NetServerAuthenticateKerberos` at `0x180039ee9`
- `logoncli!I_NetServerAuthenticateKerberos` at `0x180039ee9`
- `ntdll!RtlLeaveCriticalSection` at `0x18003a147`
- `ntdll!RtlLeaveCriticalSection` at `0x18003a147`
- `ntdll!RtlEnterCriticalSection` at `0x18003a124`
- `ntdll!RtlEnterCriticalSection` at `0x18003a124`
- `netutils!NetApiBufferFree` at `0x180039d20`
- `netutils!NetApiBufferFree` at `0x18003a0c0`
- `netutils!NetApiBufferFree` at `0x180039d20`
- `netutils!NetApiBufferFree` at `0x18003a0c0`
- `CRYPTBASE!SystemFunction036` at `0x180039d6a`
- `CRYPTBASE!SystemFunction036` at `0x180039d6a`

## string_xrefs

- `0x180039b5b`: `ClientSession->CsFlags & CS_WRITER`
- `0x180039b32`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180039b54`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180039c0e`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180039c65`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180039f0b`: `NlSessionSetup: Denied access as we could not authenticate with Kerberos 0x%lX\n`
- `0x180039f2f`: `NlSessionSetup: Denied access as we could not authenticate with Kerberos (translated status) 0x%lX\n`
- `0x180039fd6`: `NlSessionSetup: denying access due to being unable to authenticate with Netlogon 0x%lX\n`
- `0x18003a007`: `NlSessionSetup: denying access because of unmatching capabilities 0x%lX\n`
- `0x18003a055`: `NlSessionSetup: NlUpdateDomainInfo failed 0x%lX\n`

## pseudocode

```c
__int64 __fastcall NlSessionSetup(struct _CLIENT_SESSION *a1, __int64 a2, __int64 a3, char *a4)
{
  bool v4; // si
  unsigned __int8 v5; // di
  char v7; // r12
  bool v8; // r13
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
  const wchar_t *v19; // r8
  __int64 v20; // r8
  char *v21; // r9
  bool v22; // di
  __int64 v23; // rcx
  DWORD v24; // edi
  int v25; // ecx
  __int64 v26; // r9
  unsigned int v27; // eax
  unsigned __int64 v28; // rax
  __int64 v29; // rdx
  unsigned __int8 v30; // al
  __int64 v31; // r8
  char *v32; // r9
  int v33; // eax
  int v34; // eax
  int updated; // eax
  __int64 v36; // rax
  int ForestTrustInfoHigher; // eax
  int v38; // r9d
  const char *v39; // r9
  unsigned int v40; // edx
  unsigned __int8 v41; // dl
  int v42; // eax
  const char *v44; // r9
  __int64 v45; // r8
  char *v46; // r9
  __int64 v47; // rcx
  unsigned int v48; // ecx
  int v49; // edx
  char v50; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v51[4]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int8 v52; // [rsp+48h] [rbp-B8h] BYREF
  bool v53; // [rsp+49h] [rbp-B7h]
  char v54; // [rsp+4Ah] [rbp-B6h]
  unsigned __int8 v55; // [rsp+4Bh] [rbp-B5h]
  LPVOID Buffer; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v57[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v58; // [rsp+68h] [rbp-98h]
  __int64 v59; // [rsp+78h] [rbp-88h]
  _BYTE v60[528]; // [rsp+80h] [rbp-80h] BYREF

  v4 = 0;
  v55 = a2;
  v5 = a2;
  v7 = 0;
  *(_DWORD *)v51 = 0;
  v8 = 0;
  v53 = 0;
  v9 = 0;
  v52 = 0;
  v10 = 0;
  v50 = 0;
  v54 = 0;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      0x1134u,
      a4);
  if ( (*((_BYTE *)a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      0x1135u,
      a4);
  if ( v5 )
  {
    if ( !dword_1800F82A4 )
    {
      *(_DWORD *)v51 = -1073741811;
      goto LABEL_70;
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
        0x115Bu,
        v12);
    v7 = 1;
    *(_DWORD *)v51 = NlDiscoverDc(a1, 2, 0);
    if ( *(int *)v51 >= 0 )
    {
      if ( !*((_DWORD *)a1 + 71) )
        NlAssertFailed(
          "ClientSession->CsState != CS_IDLE",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
          0x1179u,
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
    *(_DWORD *)v51 = -1073741430;
  }
LABEL_70:
  if ( *(int *)v51 >= 0 )
  {
    NlSetStatusClientSession(a1, *(int *)v51, a3, a4);
    v38 = *((_DWORD *)a1 + 79);
    *((_DWORD *)a1 + 80) = 0;
    *((_QWORD *)a1 + 53) = 0;
    if ( v38 != v10 )
      NlPrintCsRoutine(0x200u, a1, L"NlSessionSetup: negotiated %lx flags rather than %lx\n");
    goto LABEL_73;
  }
  while ( 1 )
  {
    if ( (*((_DWORD *)a1 + 73) & 0x80000) != 0 )
      goto LABEL_73;
    v19 = (const wchar_t *)*((_QWORD *)a1 + 63);
    v59 = 0;
    *(_OWORD *)v57 = 0;
    v58 = 0;
    if ( !v19 )
      v19 = L"<Unknown>";
    _o_wcscpy_s(v60, 258, v19);
    if ( !v52 )
      goto LABEL_94;
    v22 = 0;
    if ( !v7 )
      v4 = NlTimeToRediscover(a1, 0) != 0;
    if ( !v8 && (*(_DWORD *)v51 == -1073741724 || *(_DWORD *)v51 == -1073741429) )
      v22 = NlTimeToRediscover(a1, 1u) != 0;
    if ( v4 )
    {
      v4 = 0;
    }
    else
    {
      v4 = 0;
      if ( !v22 )
        goto LABEL_94;
    }
    v44 = "with";
    if ( !v22 )
      v44 = "without";
    NlPrintCsRoutine(
      0x200u,
      a1,
      L"NlSessionSetup: Retry failed session setup (%hs account) since discovery wasn't recent.\n",
      v44);
    NlSetStatusClientSession(a1, -1073741730, v45, v46);
    if ( (int)NlDiscoverDc(a1, 2, 0) < 0 )
      break;
    if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)a1 + 63), v60) )
    {
      NlPrintCsRoutine(0x200u, a1, L"NlSessionSetup: Skip retry failed session setup since same DC discovered.\n");
      goto LABEL_94;
    }
    v8 = v22;
    v53 = v22;
    v5 = v55;
    v7 = 1;
LABEL_19:
    if ( NlGlobalMemberWorkstation && (*((_BYTE *)a1 + 408) & 4) == 0 && (*((_BYTE *)a1 + 292) & 4) != 0 )
    {
      Buffer = 0;
      v50 = 1;
      NlPrintCsRoutine(0x100u, a1, L"NlSessionSetup: Only downlevel DC available\n");
      DcNameEx2 = DsrGetDcNameEx2(0, 0, 0, 0x81u, (__int64)&Buffer);
      v15 = Buffer;
      if ( !DcNameEx2 && (*((_BYTE *)Buffer + 56) & 0x10) == 0 )
      {
        v54 = 1;
        NlPrintCsRoutine(0x100u, a1, L"NlSessionSetup: NT5 domain has been downgraded.\n");
        v15 = Buffer;
      }
      if ( v15 )
        NetApiBufferFree(v15);
      *(_DWORD *)v51 = -1073741730;
      v9 = 1;
      v52 = 1;
    }
    else
    {
      if ( !v5 )
      {
        v33 = NlSessionAuthenticationNetlogon(a1, &v52);
        *(_DWORD *)v51 = v33;
        if ( v33 < 0 )
        {
          NlPrintCsRoutine(
            0x200u,
            a1,
            L"NlSessionSetup: denying access due to being unable to authenticate with Netlogon 0x%lX\n",
            (unsigned int)v33);
          goto LABEL_69;
        }
LABEL_57:
        v34 = NlConfirmCapabilities(a1);
        *(_DWORD *)v51 = v34;
        if ( v34 >= 0 )
        {
          if ( (*((_DWORD *)a1 + 73) & 0x20000) == 0 )
          {
            if ( NlGlobalMemberWorkstation )
            {
              updated = NlUpdateDomainInfo(a1);
              *(_DWORD *)v51 = updated;
              if ( updated < 0 )
              {
                NlPrintCsRoutine(
                  0x100u,
                  a1,
                  L"NlSessionSetup: NlUpdateDomainInfo failed 0x%lX\n",
                  (unsigned int)updated);
                goto LABEL_63;
              }
            }
            else
            {
              v36 = *((_QWORD *)a1 + 34);
              Buffer = 0;
              if ( *(_DWORD *)(v36 + 588) == 1 && (*((_BYTE *)a1 + 296) & 8) != 0 )
              {
                ForestTrustInfoHigher = NlpGetForestTrustInfoHigher(
                                          a1,
                                          1u,
                                          0,
                                          1u,
                                          (struct _LSA_FOREST_TRUST_INFORMATION **)&Buffer);
                *(_DWORD *)v51 = ForestTrustInfoHigher;
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
LABEL_63:
                  v52 = 1;
                }
              }
            }
          }
LABEL_69:
          v9 = v50;
          goto LABEL_70;
        }
        NlPrintCsRoutine(
          0x200u,
          a1,
          L"NlSessionSetup: denying access because of unmatching capabilities 0x%lX\n",
          (unsigned int)v34);
        *(_DWORD *)v51 = -1073741790;
        v52 = 1;
        goto LABEL_31;
      }
      *((_DWORD *)a1 + 71) = 2;
      *((_DWORD *)a1 + 79) = -1073741824;
      if ( !SystemFunction036((char *)a1 + 440, 0x10u) )
      {
        NlPrintCsRoutine(0x100u, a1, L"RtlGenRandom failed.\n");
        v4 = 0;
        *(_DWORD *)v51 = -1073741595;
        goto LABEL_31;
      }
      v23 = dword_1800F823C != 0 ? 0x2000 : 0;
      v10 = v23 | (dword_1800F8238 != 0 ? -516956161 : -516960257);
      if ( !*((_QWORD *)a1 + 63) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v23, v16, v17, v18);
      *((_DWORD *)a1 + 79) |= v10;
      v24 = 0;
      *((_DWORD *)a1 + 78) = v10;
      v25 = -1073610748;
      *(_DWORD *)v51 = -1073610748;
      do
      {
        *(_DWORD *)v51 = NlStartApiClientSession(a1, 1, v24, v25, (struct _CLIENT_SESSION *)((char *)a1 + 680));
        v25 = *(_DWORD *)v51;
        if ( *(int *)v51 >= 0 )
        {
          if ( (*((_DWORD *)a1 + 73) & 0x40000) != 0 )
            v26 = *((_QWORD *)a1 + 27);
          else
            v26 = *(_QWORD *)(*((_QWORD *)a1 + 34) + 264LL);
          v27 = I_NetServerAuthenticateKerberos(
                  *((_QWORD *)a1 + 63),
                  *((_QWORD *)a1 + 25),
                  *((unsigned int *)a1 + 70),
                  v26,
                  (char *)a1 + 316,
                  (char *)a1 + 488);
          *(_DWORD *)v51 = v27;
          v25 = v27;
          if ( v27 )
          {
            NlPrintCsRoutine(
              0x200u,
              a1,
              L"NlSessionSetup: Denied access as we could not authenticate with Kerberos 0x%lX\n",
              v27);
            *(_DWORD *)v51 = NetpApiStatusToNtStatus(*(unsigned int *)v51);
            NlPrintCsRoutine(
              0x200u,
              a1,
              L"NlSessionSetup: Denied access as we could not authenticate with Kerberos (translated status) 0x%lX\n",
              *(unsigned int *)v51);
            v25 = *(_DWORD *)v51;
          }
          else
          {
            *((_DWORD *)a1 + 176) |= 0x14u;
          }
        }
        v28 = (unsigned int)(v25 + 1073610748);
        if ( (unsigned int)v28 > 0x32 )
          break;
        v29 = 0x4000000080001LL;
        if ( !_bittest64(&v29, v28) )
          break;
        ++v24;
      }
      while ( v24 < 2 );
      v30 = NlFinishApiClientSession(a1, 1u, 1u, (struct _CLIENT_SESSION *)((char *)a1 + 680));
      v8 = v53;
      v4 = 0;
      if ( !v30 )
        NlPrintCsRoutine(
          0x100u,
          a1,
          L"NlSessionSetup: Session setup: cannot FinishApiClientSession for I_NetServerAuthenticateKerberos 0x%lx\n",
          *(unsigned int *)v51);
      NlSetStatusClientSession(a1, *(int *)v51, v31, v32);
      if ( *(int *)v51 >= 0 )
        goto LABEL_57;
LABEL_31:
      v9 = v50;
    }
  }
  NlPrintCsRoutine(0x100u, a1, L"NlSessionSetup: Session setup: cannot re-pick trusted DC\n");
LABEL_94:
  switch ( *(_DWORD *)v51 )
  {
    case 0xC0000022:
      v57[0] = *((unsigned __int16 **)a1 + 23);
      v57[1] = (unsigned __int16 *)v60;
      *(_QWORD *)&v58 = 0;
      NlpWriteEventlogEx(0xC8Au, 1u, 0, 0xFFFFFFFF, v57, 2u, v51, 4u);
      goto LABEL_113;
    case 0xC000005E:
      goto LABEL_102;
    case 0xC000018A:
      if ( !NlGlobalCDC || *((_DWORD *)a1 + 70) == 7 )
      {
        v57[0] = (unsigned __int16 *)v60;
        v57[1] = *((unsigned __int16 **)a1 + 23);
        v58 = *(unsigned __int64 *)(*((_QWORD *)a1 + 34) + 264LL);
        NlpWriteEventlogEx(0x1658u, 1u, 0, 0xFFFFFFFF, v57, 3u, v51, 4u);
        goto LABEL_113;
      }
      break;
    case 0xC000018B:
      v57[0] = (unsigned __int16 *)v60;
      v57[1] = *((unsigned __int16 **)a1 + 23);
      v47 = *(_QWORD *)(*((_QWORD *)a1 + 34) + 264LL);
      *((_QWORD *)&v58 + 1) = *((_QWORD *)a1 + 25);
      *(_QWORD *)&v58 = v47;
      v59 = 0;
      NlpWriteEventlogEx(0x1659u, 1u, 0, 0xFFFFFFFF, v57, 4u, v51, 4u);
      goto LABEL_113;
    default:
LABEL_102:
      v57[0] = *((unsigned __int16 **)a1 + 23);
      v57[1] = (unsigned __int16 *)*(int *)v51;
      if ( v54 )
      {
        v48 = 5791;
        goto LABEL_110;
      }
      if ( v9 )
      {
        v48 = 5790;
        goto LABEL_110;
      }
      if ( NlGlobalWinsockPnpAddressSize || NlGlobalV6WinsockPnpAddressSize )
      {
        v48 = 5719;
LABEL_110:
        NlpWriteEventlogEx(v48, 1u, 0x80000000, 0xFFFFFFFF, v57, 2u, v51, 4u);
      }
      else
      {
        NlPrintRoutine(0x200u, L"No IP addresses present, skipping No DC event log\n");
      }
      v57[0] = *((unsigned __int16 **)a1 + 23);
      v57[1] = (unsigned __int16 *)v60;
      *(_QWORD *)&v58 = 0;
LABEL_113:
      *((_DWORD *)a1 + 80) = (*((_DWORD *)a1 + 80) + 1) % 0xAu;
      break;
  }
  if ( *(_DWORD *)v51 == -1073741790 || (unsigned int)(*(_DWORD *)v51 + 1073741430) <= 1 )
    v49 = *(_DWORD *)v51;
  else
    v49 = -1073741730;
  NlSetStatusClientSession(a1, v49, v20, v21);
LABEL_73:
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  GetSystemTimeAsFileTime((LPFILETIME)a1 + 2);
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  v39 = "Succeeded";
  if ( *((int *)a1 + 72) < 0 )
    v39 = "Failed";
  NlPrintCsRoutine(0x200u, a1, L"NlSessionSetup: Session setup %hs\n", v39);
  if ( *(_DWORD *)v51 == -1073741790 && (*((_DWORD *)a1 + 73) & 0xC0000) == 0x40000 )
  {
    v41 = v55;
    *((_DWORD *)a1 + 73) |= 0x80000u;
    v42 = NlSessionSetup(a1, v41);
    *((_DWORD *)a1 + 73) &= ~0x80000u;
    *(_DWORD *)v51 = v42;
  }
  NlpTraceEvent(2u, v40);
  return *(unsigned int *)v51;
}

```

## disassembly

```asm
0x180039ac4  mov     [rsp-8+arg_10], rbx
0x180039ac9  push    rbp
0x180039aca  push    rsi
0x180039acb  push    rdi
0x180039acc  push    r12
0x180039ace  push    r13
0x180039ad0  push    r14
0x180039ad2  push    r15
0x180039ad4  lea     rbp, [rsp-1A0h]
0x180039adc  sub     rsp, 2A0h
0x180039ae3  mov     rax, cs:__security_cookie
0x180039aea  xor     rax, rsp
0x180039aed  mov     [rbp+1D0h+var_40], rax
0x180039af4  xor     esi, esi
0x180039af6  mov     [rsp+2D0h+var_285], dl
0x180039afa  mov     dil, dl
0x180039afd  mov     rbx, rcx
0x180039b00  mov     r12b, sil
0x180039b03  mov     dword ptr [rsp+2D0h+var_28C], esi
0x180039b07  mov     r13b, sil
0x180039b0a  mov     [rsp+2D0h+var_287], sil
0x180039b0f  mov     r14b, sil
0x180039b12  mov     [rsp+2D0h+var_288], sil
0x180039b17  mov     r15d, esi
0x180039b1a  mov     [rsp+2D0h+var_290], sil
0x180039b1f  mov     [rsp+2D0h+var_286], sil
0x180039b24  cmp     [rcx+148h], esi
0x180039b2a  ja      short loc_180039B45
0x180039b2c  mov     r8d, 1134h; unsigned int
0x180039b32  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180039b39  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180039b40  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180039b45  test    byte ptr [rbx+124h], 8
0x180039b4c  jnz     short loc_180039B67
0x180039b4e  mov     r8d, 1135h; unsigned int
0x180039b54  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180039b5b  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x180039b62  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180039b67  test    dil, dil
0x180039b6a  jz      short loc_180039B82
0x180039b6c  cmp     cs:dword_1800F82A4, esi
0x180039b72  jz      short loc_180039BD2
0x180039b74  mov     dl, 1
0x180039b76  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos> `wil::Feature<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::GetImpl(void)'::`2'::impl
0x180039b7d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180039b82  lea     r8, aNlsessionsetup_2; "NlSessionSetup: Try Session setup\n"
0x180039b89  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180039b8c  mov     ecx, 200h; unsigned int
0x180039b91  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180039b96  mov     ecx, 1; unsigned int
0x180039b9b  call    ?NlpTraceEvent@@YAXKK@Z; NlpTraceEvent(ulong,ulong)
0x180039ba0  cmp     cs:?NlGlobalCDC@@3HA, esi; int NlGlobalCDC
0x180039ba6  jz      short loc_180039BDF
0x180039ba8  cmp     dword ptr [rbx+118h], 7
0x180039baf  jz      short loc_180039BDF
0x180039bb1  lea     r8, aNlsessionsetup_15; "NlSessionSetup: RODC is asked to establ"...
0x180039bb8  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180039bbb  mov     ecx, 200h; unsigned int
0x180039bc0  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180039bc5  mov     dword ptr [rsp+2D0h+var_28C], 0C000018Ah
0x180039bcd  jmp     loc_18003A0D1
0x180039bd2  mov     dword ptr [rsp+2D0h+var_28C], 0C000000Dh
0x180039bda  jmp     loc_18003A0D1
0x180039bdf  mov     r8d, [rbx+11Ch]
0x180039be6  lea     rdx, aNlsessionsetup_28; "NlSessionSetup: ClientSession->CsState "...
0x180039bed  mov     ecx, 80000h; unsigned int
0x180039bf2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180039bf7  cmp     [rbx+11Ch], esi
0x180039bfd  jnz     short loc_180039C78
0x180039bff  cmp     [rbx+1F8h], rsi
0x180039c06  jz      short loc_180039C21
0x180039c08  mov     r8d, 115Bh; unsigned int
0x180039c0e  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180039c15  lea     rcx, aClientsessionC; "ClientSession->CsUncServerName == NULL"
0x180039c1c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180039c21  xor     r9d, r9d
0x180039c24  xor     r8d, r8d
0x180039c27  mov     rcx, rbx
0x180039c2a  mov     r12b, 1
0x180039c2d  lea     edx, [r9+2]
0x180039c31  call    ?NlDiscoverDc@@YAJPEAU_CLIENT_SESSION@@W4_DISCOVERY_TYPE@@EE@Z; NlDiscoverDc(_CLIENT_SESSION *,_DISCOVERY_TYPE,uchar,uchar)
0x180039c36  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180039c3a  test    eax, eax
0x180039c3c  jns     short loc_180039C57
0x180039c3e  lea     r8, aNlsessionsetup_1; "NlSessionSetup: Session setup: cannot p"...
0x180039c45  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180039c48  mov     ecx, 100h; unsigned int
0x180039c4d  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180039c52  jmp     loc_18003A0D1
0x180039c57  cmp     [rbx+11Ch], esi
0x180039c5d  jnz     short loc_180039C78
0x180039c5f  mov     r8d, 1179h; unsigned int
0x180039c65  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180039c6c  lea     rcx, aClientsessionC_7; "ClientSession->CsState != CS_IDLE"
0x180039c73  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180039c78  cmp     cs:?NlGlobalMemberWorkstation@@3HA, esi; int NlGlobalMemberWorkstation
0x180039c7e  jz      loc_180039D3E
0x180039c84  test    byte ptr [rbx+198h], 4
0x180039c8b  jnz     loc_180039D3E
0x180039c91  test    byte ptr [rbx+124h], 4
0x180039c98  jz      loc_180039D3E
0x180039c9e  mov     r14d, 100h
0x180039ca4  mov     [rsp+2D0h+Buffer], rsi
0x180039ca9  mov     edi, 1
0x180039cae  lea     r8, aNlsessionsetup_18; "NlSessionSetup: Only downlevel DC avail"...
0x180039cb5  mov     ecx, r14d; unsigned int
0x180039cb8  mov     [rsp+2D0h+var_290], dil
0x180039cbd  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180039cc0  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180039cc5  lea     rax, [rsp+2D0h+Buffer]
0x180039cca  xor     r9d, r9d
0x180039ccd  mov     qword ptr [rsp+2D0h+var_298], rax
0x180039cd2  xor     r8d, r8d
0x180039cd5  mov     dword ptr [rsp+2D0h+var_2A0], 81h
0x180039cdd  xor     edx, edx
0x180039cdf  mov     qword ptr [rsp+2D0h+var_2A8], rsi
0x180039ce4  xor     ecx, ecx
0x180039ce6  mov     [rsp+2D0h+var_2B0], rsi
0x180039ceb  call    DsrGetDcNameEx2
0x180039cf0  mov     rcx, [rsp+2D0h+Buffer]
0x180039cf5  test    eax, eax
0x180039cf7  jnz     short loc_180039D1B
0x180039cf9  test    byte ptr [rcx+38h], 10h
0x180039cfd  jnz     short loc_180039D1B
0x180039cff  lea     r8, aNlsessionsetup_9; "NlSessionSetup: NT5 domain has been dow"...
0x180039d06  mov     [rsp+2D0h+var_286], dil
0x180039d0b  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180039d0e  mov     ecx, r14d; unsigned int
0x180039d11  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180039d16  mov     rcx, [rsp+2D0h+Buffer]; Buffer
0x180039d1b  test    rcx, rcx
0x180039d1e  jz      short loc_180039D2C
0x180039d20  call    cs:__imp_NetApiBufferFree
0x180039d27  nop     dword ptr [rax+rax+00h]
0x180039d2c  mov     dword ptr [rsp+2D0h+var_28C], 0C000005Eh
0x180039d34  mov     r14b, dil
0x180039d37  mov     [rsp+2D0h+var_288], dil
0x180039d3c  jmp     short loc_180039DA1
0x180039d3e  test    dil, dil
0x180039d41  jz      loc_180039FBE
0x180039d47  lea     rsi, [rbx+13Ch]
0x180039d4e  mov     dword ptr [rbx+11Ch], 2
0x180039d58  lea     rcx, [rbx+1B8h]; RandomBuffer
0x180039d5f  mov     dword ptr [rsi], 0C0000000h
0x180039d65  mov     edx, 10h; RandomBufferLength
0x180039d6a  call    cs:__imp_SystemFunction036
0x180039d71  nop     dword ptr [rax+rax+00h]
0x180039d76  test    al, al
0x180039d78  jnz     loc_180039E21
0x180039d7e  lea     r8, aRtlgenrandomFa; "RtlGenRandom failed.\n"
0x180039d85  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180039d88  mov     ecx, 100h; unsigned int
0x180039d8d  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180039d92  xor     esi, esi
0x180039d94  mov     dword ptr [rsp+2D0h+var_28C], 0C00000E5h
0x180039d9c  mov     r14b, [rsp+2D0h+var_290]
0x180039da1  test    dword ptr [rbx+124h], 80000h
0x180039dab  jnz     loc_18003A11D
0x180039db1  mov     r8, [rbx+1F8h]
0x180039db8  lea     rcx, [rbp+1D0h+var_250]
0x180039dbc  xor     eax, eax
0x180039dbe  xorps   xmm0, xmm0
0x180039dc1  mov     [rsp+2D0h+var_258], rax
0x180039dc6  mov     edx, 102h
0x180039dcb  movups  xmmword ptr [rsp+2D0h+var_278], xmm0
0x180039dd0  movups  [rsp+2D0h+var_268], xmm0
0x180039dd5  test    r8, r8
0x180039dd8  jnz     short loc_180039DE1
0x180039dda  lea     r8, aUnknown_5; "<Unknown>"
0x180039de1  call    cs:__imp__o_wcscpy_s
0x180039de8  nop     dword ptr [rax+rax+00h]
0x180039ded  cmp     [rsp+2D0h+var_288], sil
0x180039df2  jz      loc_18003A2E2
0x180039df8  xor     dil, dil
0x180039dfb  test    r12b, r12b
0x180039dfe  jnz     loc_18003A1FC
0x180039e04  xor     edx, edx; unsigned __int8
0x180039e06  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180039e09  call    ?NlTimeToRediscover@@YAEPEAU_CLIENT_SESSION@@E@Z; NlTimeToRediscover(_CLIENT_SESSION *,uchar)
0x180039e0e  test    al, al
0x180039e10  movzx   esi, sil
0x180039e14  mov     edx, 1
0x180039e19  cmovnz  esi, edx
0x180039e1c  jmp     loc_18003A201
0x180039e21  mov     eax, cs:dword_1800F8238
0x180039e27  neg     eax
0x180039e29  mov     eax, cs:dword_1800F823C
0x180039e2f  sbb     r15d, r15d
0x180039e32  and     r15d, 1000h
0x180039e39  add     r15d, 0E12FCFFFh
0x180039e40  neg     eax
0x180039e42  sbb     ecx, ecx
0x180039e44  and     ecx, 2000h
0x180039e4a  or      r15d, ecx
0x180039e4d  cmp     qword ptr [rbx+1F8h], 0
0x180039e55  jnz     short loc_180039E5C
0x180039e57  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039e5c  or      [rsi], r15d
0x180039e5f  lea     r14, [rbx+2A8h]
0x180039e66  xor     edi, edi
0x180039e68  mov     [rbx+138h], r15d
0x180039e6f  mov     ecx, 0C0020004h
0x180039e74  mov     dword ptr [rsp+2D0h+var_28C], ecx
0x180039e78  lea     r13d, [rdi+1]
0x180039e7c  mov     r9d, ecx; int
0x180039e7f  mov     [rsp+2D0h+var_2B0], r14; struct _CLIENT_API *
0x180039e84  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180039e87  mov     r8d, edi; unsigned int
0x180039e8a  mov     dl, r13b; unsigned __int8
0x180039e8d  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x180039e92  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180039e96  mov     ecx, eax
0x180039e98  test    eax, eax
0x180039e9a  js      loc_180039F47
0x180039ea0  test    dword ptr [rbx+124h], 40000h
0x180039eaa  lea     rcx, [rbx+1E8h]
0x180039eb1  jz      short loc_180039EBC
0x180039eb3  mov     r9, [rbx+0D8h]
0x180039eba  jmp     short loc_180039ECA
0x180039ebc  mov     rax, [rbx+110h]
0x180039ec3  mov     r9, [rax+108h]
0x180039eca  mov     r8d, [rbx+118h]
0x180039ed1  mov     rdx, [rbx+0C8h]
0x180039ed8  mov     qword ptr [rsp+2D0h+var_2A8], rcx
0x180039edd  mov     rcx, [rbx+1F8h]
0x180039ee4  mov     [rsp+2D0h+var_2B0], rsi
0x180039ee9  call    cs:__imp_I_NetServerAuthenticateKerberos
0x180039ef0  nop     dword ptr [rax+rax+00h]
0x180039ef5  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180039ef9  mov     ecx, eax
0x180039efb  test    eax, eax
0x180039efd  jnz     short loc_180039F08
0x180039eff  or      dword ptr [rbx+2C0h], 14h
0x180039f06  jmp     short loc_180039F47
0x180039f08  mov     r9d, eax
0x180039f0b  lea     r8, aNlsessionsetup_27; "NlSessionSetup: Denied access as we cou"...
0x180039f12  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180039f15  mov     ecx, 200h; unsigned int
0x180039f1a  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180039f1f  mov     ecx, dword ptr [rsp+2D0h+var_28C]
0x180039f23  call    NetpApiStatusToNtStatus
0x180039f28  mov     r9d, eax
0x180039f2b  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180039f2f  lea     r8, aNlsessionsetup_36; "NlSessionSetup: Denied access as we cou"...
0x180039f36  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180039f39  mov     ecx, 200h; unsigned int
0x180039f3e  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180039f43  mov     ecx, dword ptr [rsp+2D0h+var_28C]
0x180039f47  lea     eax, [rcx+3FFDFFFCh]
0x180039f4d  cmp     eax, 32h ; '2'
0x180039f50  ja      short loc_180039F6E
0x180039f52  mov     rdx, 4000000080001h
0x180039f5c  bt      rdx, rax
0x180039f60  jnb     short loc_180039F6E
0x180039f62  add     edi, r13d
0x180039f65  cmp     edi, 2
0x180039f68  jb      loc_180039E7C
0x180039f6e  mov     r9, r14; struct _CLIENT_API *
0x180039f71  mov     r8b, r13b; unsigned __int8
0x180039f74  mov     dl, r13b; unsigned __int8
0x180039f77  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180039f7a  mov     edi, r13d
0x180039f7d  call    ?NlFinishApiClientSession@@YAEPEAU_CLIENT_SESSION@@EEPEAU_CLIENT_API@@@Z; NlFinishApiClientSession(_CLIENT_SESSION *,uchar,uchar,_CLIENT_API *)
0x180039f82  mov     r13b, [rsp+2D0h+var_287]
0x180039f87  xor     esi, esi
0x180039f89  test    al, al
0x180039f8b  jnz     short loc_180039FA6
0x180039f8d  mov     r9d, dword ptr [rsp+2D0h+var_28C]
0x180039f92  lea     r8, aNlsessionsetup_0; "NlSessionSetup: Session setup: cannot F"...
0x180039f99  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180039f9c  mov     ecx, 100h; unsigned int
0x180039fa1  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180039fa6  mov     edx, dword ptr [rsp+2D0h+var_28C]; int
0x180039faa  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180039fad  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x180039fb2  cmp     dword ptr [rsp+2D0h+var_28C], esi
0x180039fb6  jl      loc_180039D9C
0x180039fbc  jmp     short loc_180039FF4
0x180039fbe  lea     rdx, [rsp+2D0h+var_288]; unsigned __int8 *
0x180039fc3  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180039fc6  call    ?NlSessionAuthenticationNetlogon@@YAJPEAU_CLIENT_SESSION@@PEAE@Z; NlSessionAuthenticationNetlogon(_CLIENT_SESSION *,uchar *)
0x180039fcb  mov     dword ptr [rsp+2D0h+var_28C], eax
0x180039fcf  test    eax, eax
0x180039fd1  jns     short loc_180039FEF
0x180039fd3  mov     r9d, eax
0x180039fd6  lea     r8, aNlsessionsetup_38; "NlSessionSetup: denying access due to b"...
0x180039fdd  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180039fe0  mov     ecx, 200h; unsigned int
0x180039fe5  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180039fea  jmp     loc_18003A0CC
0x180039fef  mov     edi, 1
0x180039ff4  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180039ff7  call    ?NlConfirmCapabilities@@YAJPEAU_CLIENT_SESSION@@@Z; NlConfirmCapabilities(_CLIENT_SESSION *)
0x180039ffc  mov     dword ptr [rsp+2D0h+var_28C], eax
0x18003a000  test    eax, eax
0x18003a002  jns     short loc_18003A02D
0x18003a004  mov     r9d, eax
0x18003a007  lea     r8, aNlsessionsetup_10; "NlSessionSetup: denying access because "...
0x18003a00e  mov     rdx, rbx; struct _CLIENT_SESSION *
0x18003a011  mov     ecx, 200h; unsigned int
  ... truncated ...
```
