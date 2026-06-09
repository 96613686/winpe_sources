# NlpUserValidateHigher(_CLIENT_SESSION *,uchar,_NETLOGON_LOGON_INFO_CLASS,uchar *,_NETLOGON_VALIDATION_INFO_CLASS,uchar * *,uchar *,ulong *)

- ea: `0x180031a3c`
- end: `0x180032a9c`
- name: `?NlpUserValidateHigher@@YAJPEAU_CLIENT_SESSION@@EW4_NETLOGON_LOGON_INFO_CLASS@@PEAEW4_NETLOGON_VALIDATION_INFO_CLASS@@PEAPEAE2PEAK@Z`
- size: `4192`
- prototype: ``
- caller_count: `3`
- callee_count: `35`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003033c`
- `0x180032aa4`
- `0x18005dfe0`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x18000f4a4`
- `0x18002e5fc`
- `0x18002e74c`
- `0x18002e84c`
- `0x180031a3c`
- `0x180037344`
- `0x180040928`
- `0x1800409c4`
- `0x180040f18`
- `0x180040fe4`
- `0x180041924`
- `0x180041944`
- `0x180041e68`
- `0x180041fbc`
- `0x180053360`
- `0x18005342c`
- `0x180053684`
- `0x180053728`
- `0x1800637d0`
- `0x180063c38`
- `0x180064c90`
- `0x1800685c4`
- `0x180068c10`
- `0x180069c60`
- `0x18006a158`
- `0x18006c2e8`
- `0x18006d2b0`
- `0x18006d794`
- `0x18006e444`
- `0x180071260`
- `0x1800712d8`
- `0x180071710`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003230f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032631`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800327b2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003230f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032631`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800327b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180031ad1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180031c90`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180031ad1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180031c90`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180031e6f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800329ad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180031e6f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800329ad`
- `logoncli!I_NetLogonSamLogon` at `0x180032275`
- `logoncli!I_NetLogonSamLogon` at `0x180032275`
- `logoncli!I_NetLogonSamLogonWithFlags` at `0x180032212`
- `logoncli!I_NetLogonSamLogonWithFlags` at `0x180032212`
- `logoncli!I_NetLogonSamLogonEx` at `0x180032170`
- `logoncli!I_NetLogonSamLogonEx` at `0x180032170`
- `LSASRV!LsaIFilterSids` at `0x180032709`
- `LSASRV!LsaIFilterSids` at `0x180032764`
- `LSASRV!LsaIFilterSids` at `0x180032709`
- `LSASRV!LsaIFilterSids` at `0x180032764`
- `ntdll!RtlAcquireResourceShared` at `0x180032996`
- `ntdll!RtlAcquireResourceShared` at `0x180032996`
- `ntdll!RtlEqualDomainName` at `0x1800325fb`
- `ntdll!RtlEqualDomainName` at `0x1800325fb`
- `ntdll!RtlLeaveCriticalSection` at `0x180031bc2`
- `ntdll!RtlLeaveCriticalSection` at `0x180031d64`
- `ntdll!RtlLeaveCriticalSection` at `0x180032721`
- `ntdll!RtlLeaveCriticalSection` at `0x180031bc2`
- `ntdll!RtlLeaveCriticalSection` at `0x180031d64`
- `ntdll!RtlLeaveCriticalSection` at `0x180032721`
- `ntdll!RtlEnterCriticalSection` at `0x180031b95`
- `ntdll!RtlEnterCriticalSection` at `0x180031d37`
- `ntdll!RtlEnterCriticalSection` at `0x1800326a3`
- `ntdll!RtlEnterCriticalSection` at `0x180031b95`
- `ntdll!RtlEnterCriticalSection` at `0x180031d37`
- `ntdll!RtlEnterCriticalSection` at `0x1800326a3`
- `ntdll!RtlEqualSid` at `0x180032619`
- `ntdll!RtlEqualSid` at `0x180032619`
- `ntdll!RtlReleaseResource` at `0x180032a66`
- `ntdll!RtlReleaseResource` at `0x180032a66`
- `netutils!NetApiBufferFree` at `0x180031c7f`
- `netutils!NetApiBufferFree` at `0x180031e5f`
- `netutils!NetApiBufferFree` at `0x180031c7f`
- `netutils!NetApiBufferFree` at `0x180031e5f`

## string_xrefs

- `0x180031aef`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x1800320e8`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x1800322a3`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18003233a`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180032382`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180032788`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180032849`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18003286b`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x1800328f4`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180032916`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180031e99`: `NlpUserValidateHigher: Can't become writer of client session.\n`
- `0x1800322ee`: `NlpUserValidateHigher: Can't become writer (again) of client session.\n`
- `0x18003249f`: `NlpUserValidateHigher: denying access after status: 0x%lx %lx\n`
- `0x18003278f`: `!"[NETLOGON] LsaIFilterSids failed"`
- `0x18003279e`: `NlpUserValidateHigher: LsaIFilterSids failed 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlpUserValidateHigher(
        __int64 a1,
        char a2,
        enum _NETLOGON_LOGON_INFO_CLASS a3,
        __int64 a4,
        unsigned int a5,
        void **a6,
        _BYTE *a7,
        unsigned int *a8)
{
  enum _NETLOGON_LOGON_INFO_CLASS v10; // r14d
  unsigned __int8 v11; // r13
  ULONGLONG TickCount64; // rdi
  char *v13; // r9
  int started; // edi
  unsigned __int16 *v15; // r15
  int v16; // r14d
  const unsigned __int16 *v17; // rdx
  PWSTR v18; // rcx
  PWSTR v19; // rcx
  const unsigned __int16 *v20; // rax
  ULONGLONG v21; // r9
  unsigned __int64 v22; // r9
  unsigned __int16 *v23; // r15
  int v24; // r14d
  const unsigned __int16 *v25; // rdx
  unsigned __int16 *v26; // rcx
  PWSTR v27; // rcx
  const unsigned __int16 *v28; // rax
  bool v29; // r13
  int v30; // ecx
  int v31; // eax
  char *v32; // r9
  __int128 v33; // xmm0
  int v34; // edx
  int v35; // r13d
  struct _CLIENT_API *v36; // rax
  int v37; // eax
  unsigned int v38; // eax
  char *v39; // r9
  unsigned int v40; // edx
  __int64 v41; // r8
  int v42; // eax
  char *v43; // r9
  int v44; // eax
  __int64 v45; // rdx
  int v46; // eax
  const char *v47; // rcx
  __int64 v48; // rdx
  bool v49; // sf
  unsigned __int64 v50; // rax
  __int64 v51; // rcx
  int v52; // edx
  unsigned __int8 v53; // al
  BOOL v54; // r14d
  unsigned __int16 *v55; // r8
  int v56; // eax
  PSID *v57; // r14
  int v58; // ecx
  bool v59; // zf
  struct _NETLOGON_VALIDATION_TICKET_LOGON *v60; // r14
  struct _NETLOGON_TICKET_LOGON_INFO *v61; // r15
  int v62; // eax
  __int128 *v63; // rax
  __int64 v64; // rcx
  __int64 v65; // r14
  LONGLONG v66; // rbx
  unsigned __int16 **v68; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v69; // [rsp+20h] [rbp-E0h]
  unsigned int v70[2]; // [rsp+28h] [rbp-D8h]
  unsigned __int8 *v71; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v72; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v73; // [rsp+51h] [rbp-AFh] BYREF
  bool v74; // [rsp+52h] [rbp-AEh]
  char v75; // [rsp+53h] [rbp-ADh]
  char v76; // [rsp+54h] [rbp-ACh]
  char v77; // [rsp+55h] [rbp-ABh]
  unsigned __int8 v78[2]; // [rsp+56h] [rbp-AAh] BYREF
  enum _NETLOGON_LOGON_INFO_CLASS v79; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v80; // [rsp+60h] [rbp-A0h] BYREF
  struct _NETLOGON_TICKET_LOGON_INFO *v81; // [rsp+68h] [rbp-98h]
  unsigned int v82; // [rsp+70h] [rbp-90h]
  struct _CLIENT_API *v83; // [rsp+78h] [rbp-88h]
  unsigned int *v84; // [rsp+80h] [rbp-80h]
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-78h] BYREF
  struct _CLIENT_API *ClientApi; // [rsp+90h] [rbp-70h]
  LARGE_INTEGER v87; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING v88; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v89; // [rsp+B0h] [rbp-50h] BYREF
  struct _CYPHER_BLOCK v90; // [rsp+C0h] [rbp-40h] BYREF
  int v91; // [rsp+C8h] [rbp-38h]
  __int128 v92; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v93; // [rsp+E0h] [rbp-20h]
  __int64 v94; // [rsp+E8h] [rbp-18h] BYREF
  int v95; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v96[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v97; // [rsp+108h] [rbp+8h]
  __int128 v98; // [rsp+118h] [rbp+18h]
  wchar_t v99[8]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v100; // [rsp+138h] [rbp+38h]
  wchar_t *v101; // [rsp+148h] [rbp+48h]
  wchar_t Buffer[20]; // [rsp+150h] [rbp+50h] BYREF

  v84 = a8;
  v81 = (struct _NETLOGON_TICKET_LOGON_INFO *)a4;
  v94 = 0;
  v95 = 0;
  v10 = a3;
  v90 = 0;
  v11 = 0;
  v91 = 0;
  v93 = 0;
  v79 = a3;
  v75 = a2;
  v92 = 0;
  v73 = 0;
  v78[0] = 1;
  v87.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v88 = 0;
  v89 = 0;
  TickCount64 = GetTickCount64();
  if ( !*(_DWORD *)(a1 + 328) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
      0x640u,
      v13);
  ClientApi = NlAllocateClientApi((struct _CLIENT_SESSION *)a1, dwMilliseconds, v78);
  if ( !ClientApi )
  {
    v101 = 0;
    v80 = 0;
    *(_OWORD *)v99 = 0;
    v100 = 0;
    NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlpUserValidateHigher: Can't allocate Client API slot.\n");
    *a7 = 1;
    started = -1073741730;
    NlDuplicateUnicodeString((struct _UNICODE_STRING *)(a4 + 32), &v88);
    NlDuplicateUnicodeString((struct _UNICODE_STRING *)a4, &v89);
    NlCaptureServerClientSession((struct _CLIENT_SESSION *)a1, &v80, 0);
    v15 = v80;
    if ( v80 )
    {
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 344));
      v16 = *(_DWORD *)(a1 + 392);
      if ( v16 )
        ++*(_DWORD *)(a1 + 396);
      else
        *(_DWORD *)(a1 + 392) = 1;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 344));
      if ( !v16 )
      {
        v17 = L"(null)";
        *(_QWORD *)&v100 = v15;
        v18 = (PWSTR)L"(null)";
        if ( v88.Buffer )
          v18 = v88.Buffer;
        *(_QWORD *)v99 = v18;
        v19 = (PWSTR)L"(null)";
        if ( v89.Buffer )
          v19 = v89.Buffer;
        v20 = *(const unsigned __int16 **)(a1 + 184);
        *(_QWORD *)&v99[4] = v19;
        if ( v20 )
          v17 = v20;
        *((_QWORD *)&v100 + 1) = v17;
        swprintf_s(Buffer, 0x14u, L"%lu", dword_1800F813C / 0x3Cu);
        v101 = Buffer;
        NlpWriteEventlogEx(0x16B8u, 1u, 0x20000000u, 0xFFFFFFFF, (unsigned __int16 **)v99, 5u, 0, 0);
      }
    }
    NetApiBufferFree(v15);
    goto LABEL_194;
  }
  v21 = GetTickCount64();
  if ( dword_1800F8140 )
  {
    v22 = v21 - TickCount64;
    if ( v22 > (unsigned int)(1000 * dword_1800F8140) )
    {
      v80 = 0;
      NlPrintCsRoutine(
        2u,
        (struct _CLIENT_SESSION *)a1,
        L"NlpUserValidateHigher: Warning Event: It took %I64d seconds to acquire a Client API slot\n",
        v22 / 0x3E8);
      NlDuplicateUnicodeString((struct _UNICODE_STRING *)(a4 + 32), &v88);
      NlDuplicateUnicodeString((struct _UNICODE_STRING *)a4, &v89);
      NlCaptureServerClientSession((struct _CLIENT_SESSION *)a1, &v80, 0);
      v23 = v80;
      if ( v80 )
      {
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 344));
        v24 = *(_DWORD *)(a1 + 400);
        if ( v24 )
          ++*(_DWORD *)(a1 + 404);
        else
          *(_DWORD *)(a1 + 400) = 1;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 344));
        if ( !v24 )
        {
          *(_OWORD *)v96 = 0;
          v97 = 0;
          v98 = 0;
          swprintf_s(Buffer, 0x14u, L"%lu", (unsigned int)dword_1800F8140);
          v25 = L"(null)";
          *((_QWORD *)&v97 + 1) = v23;
          v26 = L"(null)";
          v96[0] = Buffer;
          if ( v88.Buffer )
            v26 = v88.Buffer;
          v96[1] = v26;
          v27 = (PWSTR)L"(null)";
          if ( v89.Buffer )
            v27 = v89.Buffer;
          v28 = *(const unsigned __int16 **)(a1 + 184);
          *(_QWORD *)&v97 = v27;
          if ( v28 )
            v25 = v28;
          *(_QWORD *)&v98 = v25;
          swprintf_s(v99, 0x14u, L"%lu", dword_1800F813C / 0x3Cu);
          *((_QWORD *)&v98 + 1) = v99;
          NlpWriteEventlogEx(0x16BAu, 2u, 0x20000000u, 0xFFFFFFFF, v96, 6u, 0, 0);
        }
        v10 = v79;
      }
      NetApiBufferFree(v23);
    }
  }
  if ( !QueryPerformanceCounter(&PerformanceCount) )
    PerformanceCount.QuadPart = 0;
  if ( !(unsigned int)NlTimeoutSetWriterClientSession((struct _CLIENT_SESSION *)a1, dwMilliseconds) )
  {
    NlPrintCsRoutine(
      0x100u,
      (struct _CLIENT_SESSION *)a1,
      L"NlpUserValidateHigher: Can't become writer of client session.\n");
    *a7 = 1;
    started = -1073741730;
    goto LABEL_194;
  }
  v77 = 1;
  v72 = 1;
  v74 = v10 == NetlogonGenericInformation || a5 - 4 <= 1;
  if ( v10 == NetlogonGenericInformation || v10 <= 0 || (v76 = 1, v10 >= 8) )
    v76 = 0;
  while ( 2 )
  {
    v29 = v74;
    if ( v74 || v75 || *v84 )
      v30 = 4;
    else
      v30 = 0;
    v31 = NlEnsureSessionAuthenticated(
            (struct _CLIENT_SESSION *)a1,
            v30 | (unsigned int)(((v10 - 1) & 0xFFFFFFFB) == 0 ? 8 : 0));
    started = v31;
    if ( v31 < 0 )
    {
      if ( v31 != -1073741790
        && v31 != -1073741730
        && (unsigned int)(v31 + 1073741430) > 1
        && !NlpIsNtStatusResourceError(v31) )
      {
        started = -1073741730;
      }
      *a7 = 1;
      goto LABEL_187;
    }
    v33 = *(_OWORD *)(a1 + 440);
    v93 = *(_DWORD *)(a1 + 316);
    v34 = ((v93 & 0x80000) != 0 ? 3 : 0) | 0xC;
    v92 = v33;
    if ( (v93 & 0x200000) == 0 )
      v34 = (v93 & 0x80000) != 0 ? 3 : 0;
    if ( (~v34 & *v84) != 0 )
    {
      LODWORD(v68) = v34;
      NlPrintCsRoutine(
        0x100u,
        (struct _CLIENT_SESSION *)a1,
        L"NlpUserValidateHigher: Can't pass these ExtraFlags to old DC: %lx %lx\n",
        *v84,
        v68);
      started = -1073741730;
      goto LABEL_164;
    }
    if ( (v93 & 0x400) == 0 && (v29 || v75) )
    {
      *a7 = 1;
      v55 = L"NlpUserValidateHigher: Can't do generic passthru to NT 4 DC.\n";
      if ( !v29 )
        v55 = L"NlpUserValidateHigher: Can't do transitive trust to NT 4 DC.\n";
      NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, v55);
      started = v29 ? -1073741821 : -1073741730;
LABEL_187:
      if ( started < 0 )
        goto LABEL_193;
      goto LABEL_188;
    }
    if ( !v76 )
      goto LABEL_63;
    if ( (v93 & 0x40) != 0 )
    {
      if ( (v93 & 0x80000) == 0 || (v93 & 0x40000000) == 0 )
      {
        v35 = 3;
        goto LABEL_64;
      }
LABEL_63:
      v35 = a5;
      goto LABEL_64;
    }
    v35 = 2;
LABEL_64:
    if ( (v93 & 0x40000800) == 0x40000800 )
    {
      v36 = ClientApi;
    }
    else
    {
      if ( v10 == 8 )
      {
        started = -1073741821;
        goto LABEL_164;
      }
      v36 = (struct _CLIENT_API *)(a1 + 680);
    }
    v83 = v36;
    v80 = (unsigned __int16 *)(((__int64)v36 - a1 - 680) / 560);
    if ( !(_DWORD)v80 )
    {
      v37 = NlBuildAuthenticator(
              (struct _CYPHER_BLOCK *)(a1 + 432),
              (struct _NETLOGON_SESSION_KEY *)(a1 + 440),
              (struct _NETLOGON_AUTHENTICATOR *)&v94,
              v93);
      started = v37;
      if ( v37 < 0 )
      {
        NlPrintRoutine(
          0x100u,
          L"NlpUserValidateHigher: NlBuildAuthenticator failed with status: 0x%lx\n",
          (unsigned int)v37);
        goto LABEL_193;
      }
    }
    NlpEncryptLogonInformation(v10, (unsigned __int8 *)v81, (struct _SESSION_INFO *)&v92);
    v38 = 0;
    v73 = 0;
    v82 = 0;
    started = -1073610748;
    while ( 1 )
    {
      started = NlStartApiClientSession((struct _CLIENT_SESSION *)a1, 1u, v38, started, v83);
      if ( started < 0 )
        goto LABEL_106;
      v40 = v93;
      v73 = 0;
      if ( (v93 & 0x8000) == 0 )
      {
        switch ( v10 )
        {
          case NetlogonInteractiveTransitiveInformation:
            v10 = NetlogonInteractiveInformation;
            break;
          case NetlogonNetworkTransitiveInformation:
            v10 = NetlogonNetworkInformation;
            break;
          case NetlogonServiceTransitiveInformation:
            v10 = NetlogonServiceInformation;
            break;
          default:
            goto LABEL_80;
        }
        v79 = v10;
      }
LABEL_80:
      if ( !*(_QWORD *)(a1 + 504) )
      {
        NlAssertFailed(
          "ClientSession->CsUncServerName != NULL",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
          0x7E1u,
          v39);
        v40 = v93;
      }
      if ( (_DWORD)v80 )
        break;
      v44 = *(_DWORD *)(a1 + 292) & 0x40000;
      if ( (v40 & 0x80000) != 0 )
      {
        if ( v44 )
          v45 = *(_QWORD *)(a1 + 216);
        else
          v45 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
        LODWORD(v71) = v35;
        v46 = I_NetLogonSamLogonWithFlags(*(_QWORD *)(a1 + 504), v45, &v94, &v90, v10, v81, v71, a6, a7, v84);
        started = v46;
        if ( v46 < 0 )
        {
          v47 = "I_NetLogonSamLogonWithFlags";
LABEL_101:
          NlPrintRpcDebug(v47, v46);
LABEL_102:
          if ( started < 0 )
            goto LABEL_106;
        }
      }
      else
      {
        if ( v44 )
          v48 = *(_QWORD *)(a1 + 216);
        else
          v48 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
        v46 = I_NetLogonSamLogon(*(_QWORD *)(a1 + 504), v48, &v94, &v90, v10, v81, v35, a6, a7);
        started = v46;
        if ( v46 < 0 )
        {
          v47 = "I_NetLogonSamLogon";
          goto LABEL_101;
        }
      }
      v49 = started < 0;
      if ( started )
      {
        NlAssertFailed(
          "!NT_SUCCESS(Status) || Status == STATUS_SUCCESS",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
          0x842u,
          v43);
        v49 = started < 0;
      }
      if ( !v49 )
      {
        if ( !*a6 )
          NlAssertFailed(
            "!NT_SUCCESS(Status) || *ValidationInformation != NULL",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            0x843u,
            v43);
        goto LABEL_115;
      }
LABEL_106:
      v50 = (unsigned int)(started + 1073610748);
      if ( (unsigned int)v50 <= 0x32 )
      {
        v51 = 0x4000000080001LL;
        if ( _bittest64(&v51, v50) )
        {
          v38 = v82 + 1;
          v82 = v38;
          if ( v38 < 2 )
            continue;
        }
      }
      goto LABEL_115;
    }
    NlResetWriterClientSession((struct _CLIENT_SESSION *)a1);
    if ( (*(_DWORD *)(a1 + 292) & 0x40000) != 0 )
      v41 = *(_QWORD *)(a1 + 216);
    else
      v41 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
    v70[0] = v35;
    v42 = I_NetLogonSamLogonEx(
            *((_QWORD *)v83 + 4),
            (char *)v83 + 44,
            v41,
            (unsigned int)v10,
            v81,
            *(_QWORD *)v70,
            a6,
            a7,
            v84,
            &v73);
    started = v42;
    if ( v42 < 0 )
      NlPrintRpcDebug("I_NetLogonSamLogonEx", v42);
    if ( (unsigned int)NlTimeoutSetWriterClientSession((struct _CLIENT_SESSION *)a1, dwMilliseconds) )
    {
      v72 = 1;
      goto LABEL_102;
    }
    v72 = 0;
    NlPrintCsRoutine(
      0x100u,
      (struct _CLIENT_SESSION *)a1,
      L"NlpUserValidateHigher: Can't become writer (again) of client session.\n");
    if ( *a6 )
    {
      free(*a6);
      *a6 = 0;
    }
    *a7 = 1;
    started = -1073741730;
LABEL_115:
    NlFinishApiClientSession((struct _CLIENT_SESSION *)a1, 1u, v72, v83);
    NlpDecryptLogonInformation(v10, (unsigned __int8 *)v81, (struct _SESSION_INFO *)&v92);
    if ( started >= 0 && !*a6 )
      NlAssertFailed(
        "*ValidationInformation != NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
        0x84Cu,
        v32);
    if ( !v72 )
      goto LABEL_187;
    NlPrintRoutine(0x4000000u, L"NlpUserValidateHigher: Seed = ");
    NlpDumpBuffer(0x4000000u, (void *)(a1 + 432), 8u);
    NlPrintRoutine(0x4000000u, L"NlpUserValidateHigher: SessionKey = ");
    NlpDumpBuffer(0x4000000u, (void *)(a1 + 440), 0x10u);
    if ( !(_DWORD)v80 )
    {
      NlPrintRoutine(0x4000000u, L"NlpUserValidateHigher: Return Authenticator = ");
      NlpDumpBuffer(0x4000000u, &v90, 8u);
    }
    if ( NlpDidDcFail(started) )
    {
LABEL_126:
      v53 = v73;
LABEL_127:
      v54 = (started == -1073545204 || started == -1073741821) && a5 == 7;
      LODWORD(v69) = v53;
      NlPrintCsRoutine(
        0x100u,
        (struct _CLIENT_SESSION *)a1,
        L"NlpUserValidateHigher: denying access after status: 0x%lx %lx\n",
        (unsigned int)started,
        v69);
      if ( started >= 0 )
        started = -1073741790;
      if ( *((_DWORD *)v83 + 10) == *(_DWORD *)(a1 + 324) && !v54 )
        NlSetStatusClientSession((struct _CLIENT_SESSION *)a1, started);
      if ( !v77 )
      {
        *a7 = 1;
        goto LABEL_193;
      }
      v10 = v79;
      v77 = 0;
      continue;
    }
    break;
  }
  v53 = v73;
  if ( v73 )
    goto LABEL_127;
  if ( !v52
    && (unsigned int)NlCheckRpcAuthIsNetlogon((struct _CLIENT_SESSION *)a1)
    && !(unsigned int)NlUpdateSeed((PUCHAR)(a1 + 432), &v90, (PUCHAR)(a1 + 440), *(_DWORD *)(a1 + 316)) )
  {
    goto LABEL_126;
  }
  if ( started < 0 )
    goto LABEL_193;
  NlpDecryptValidationInformation((unsigned int)v79, (unsigned int)v35, *a6, &v92);
  if ( ((a5 - 2) & 0xFFFFFFFA) != 0 )
    goto LABEL_173;
  if ( a5 == 7 )
  {
LABEL_174:
    v60 = (struct _NETLOGON_VALIDATION_TICKET_LOGON *)*a6;
    v61 = v81;
    started = IsTicketLogonReplySupported(
                v81,
                (struct _NETLOGON_VALIDATION_TICKET_LOGON *const)*a6,
                (*v84 & 0x2000) != 0);
    if ( started < 0 )
    {
LABEL_175:
      FreeTicketValidationInformation(v60);
      *a6 = 0;
      goto LABEL_193;
    }
    v62 = TransformKerberosTicketLogonInbound(v61, v60, (struct _CLIENT_SESSION *)a1);
    started = v62;
    if ( v62 < 0 )
    {
      NlPrintRoutine(0x100u, L"TransformKerberosTicketLogonInbound 0x%lx\n", (unsigned int)v62);
      goto LABEL_175;
    }
LABEL_188:
    v59 = started == 0;
LABEL_189:
    if ( v59
      || (NlAssertFailed(
            "!NT_SUCCESS(Status) || Status == STATUS_SUCCESS",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            0x96Bu,
            v32),
          started >= 0) )
    {
      if ( !*a6 )
        NlAssertFailed(
          "!NT_SUCCESS(Status) || *ValidationInformation != NULL",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
          0x96Cu,
          v32);
    }
    goto LABEL_193;
  }
  if ( ((v35 - 2) & 0xFFFFFFFA) == 0 && v35 != 7 && (int)a5 > v35 )
  {
    v56 = NlpAddResourceGroupsToSamInfo(v35, (unsigned __int8 *)a6, 0);
    if ( v56 < 0 )
    {
      *a6 = 0;
      started = v56;
      *a7 = 0;
      goto LABEL_193;
    }
  }
  if ( ((a5 - 2) & 0xFFFFFFFA) != 0 )
  {
LABEL_173:
    if ( a5 != 7 )
      goto LABEL_188;
    goto LABEL_174;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 280) - 2) <= 2 )
  {
    if ( *(_QWORD *)(a1 + 120) )
    {
      v57 = (PSID *)*a6;
      if ( RtlEqualDomainName((PUNICODE_STRING)*a6 + 13, (PUNICODE_STRING)(a1 + 112)) )
      {
        if ( !RtlEqualSid(v57[28], *(PSID *)(a1 + 264)) )
        {
          started = -1073741413;
          free(*a6);
          *a6 = 0;
          *a7 = 1;
        }
      }
    }
  }
  v58 = *(_DWORD *)(a1 + 280);
  if ( (unsigned int)(v58 - 3) <= 1 && *a6 )
  {
    if ( (*(_BYTE *)(a1 + 296) & 0x10) != 0 && (a5 == 3 || a5 == 6) )
    {
      started = NlpAddOtherOrganizationSid(a5, a6);
      if ( started < 0 )
        goto LABEL_163;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)(a1 + 272) + 400LL));
    v70[0] = a5;
    started = LsaIFilterSids(
                (a1 + 152) & -(__int64)(*(_WORD *)(a1 + 152) != 0),
                2,
                (unsigned int)((*(_DWORD *)(a1 + 292) & 4) != 0) + 1,
                *(unsigned int *)(a1 + 296),
                *(_QWORD *)(a1 + 264),
                *(_QWORD *)v70,
                *a6,
                0,
                0,
                0);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)(a1 + 272) + 400LL));
  }
  else if ( v58 == 2 && *a6 )
  {
    v70[0] = a5;
    started = LsaIFilterSids(0, 0, 0, 0, 0, *(_QWORD *)v70, *a6, 0, 0, 0);
  }
  v59 = started == 0;
  if ( started >= 0 )
    goto LABEL_189;
  if ( started == -1073741413 )
    NlAssertFailed(
      "!\"[NETLOGON] LsaIFilterSids failed\"",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
      0x944u,
      v32);
  NlPrintRoutine(0x100u, L"NlpUserValidateHigher: LsaIFilterSids failed 0x%lx\n", (unsigned int)started);
  free(*a6);
LABEL_163:
  *a6 = 0;
LABEL_164:
  *a7 = 1;
LABEL_193:
  v11 = v72;
LABEL_194:
  v63 = &v92;
  v64 = 16;
  do
  {
    *(_BYTE *)v63 = 0;
    v63 = (__int128 *)((char *)v63 + 1);
    --v64;
  }
  while ( v64 );
  if ( v11 )
    NlResetWriterClientSession((struct _CLIENT_SESSION *)a1);
  NlFreeUnicodeString(&v88);
  NlFreeUnicodeString(&v89);
  if ( ClientApi )
  {
    v65 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 352LL);
    NlFreeClientApi((struct _CLIENT_SESSION *)a1, ClientApi, v78[0]);
    RtlAcquireResourceShared(&NlPcGlobalLock, 1u);
    if ( PerformanceCount.QuadPart && QueryPerformanceCounter(&v87) )
    {
      v66 = v87.QuadPart - PerformanceCount.QuadPart;
      NlPcIncrement64(*(_QWORD *)(a1 + 672), 4, v87.QuadPart - PerformanceCount.QuadPart);
      NlPcIncrement64(v65, 4, v66);
      NlPcIncrement64(NlPcGlobalTotalInstance, 4, v66);
    }
    NlPcIncrement64(*(_QWORD *)(a1 + 672), 2, 1);
    NlPcIncrement64(v65, 2, 1);
    NlPcIncrement64(NlPcGlobalTotalInstance, 2, 1);
    NlPcIncrement32(*(_QWORD *)(a1 + 672), 5);
    NlPcIncrement32(v65, 5);
    NlPcIncrement32(NlPcGlobalTotalInstance, 5);
    RtlReleaseResource(&NlPcGlobalLock);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180031a3c  mov     [rsp-8+arg_8], rbx
0x180031a41  push    rbp
0x180031a42  push    rsi
0x180031a43  push    rdi
0x180031a44  push    r12
0x180031a46  push    r13
0x180031a48  push    r14
0x180031a4a  push    r15
0x180031a4c  lea     rbp, [rsp-80h]
0x180031a51  sub     rsp, 180h
0x180031a58  mov     rax, cs:__security_cookie
0x180031a5f  xor     rax, rsp
0x180031a62  mov     [rbp+0B0h+var_38], rax
0x180031a66  mov     rax, [rbp+0B0h+arg_38]
0x180031a6d  xorps   xmm0, xmm0
0x180031a70  mov     rbx, [rbp+0B0h+arg_28]
0x180031a77  mov     rsi, rcx
0x180031a7a  mov     r12, [rbp+0B0h+arg_30]
0x180031a81  xor     ecx, ecx
0x180031a83  mov     [rbp+0B0h+var_130], rax
0x180031a87  xorps   xmm1, xmm1
0x180031a8a  xor     eax, eax
0x180031a8c  mov     [rsp+1B0h+var_148], r9
0x180031a91  mov     [rbp+0B0h+var_C8], rax
0x180031a95  mov     r15, r9
0x180031a98  mov     [rbp+0B0h+var_C0], eax
0x180031a9b  mov     r14d, r8d
0x180031a9e  mov     qword ptr [rbp+0B0h+var_F0.data], rax
0x180031aa2  mov     r13b, cl
0x180031aa5  mov     [rbp+0B0h+var_E8], eax
0x180031aa8  mov     [rbp+0B0h+var_D0], eax
0x180031aab  mov     [rsp+1B0h+var_158], r8d
0x180031ab0  mov     [rsp+1B0h+var_15D], dl
0x180031ab4  movups  [rbp+0B0h+var_E0], xmm0
0x180031ab8  mov     [rsp+1B0h+var_15F], cl
0x180031abc  mov     [rsp+1B0h+var_15A], 1
0x180031ac1  mov     qword ptr [rbp+0B0h+var_118], rcx
0x180031ac5  mov     qword ptr [rbp+0B0h+PerformanceCount], rcx
0x180031ac9  movups  xmmword ptr [rbp+0B0h+var_110.Length], xmm0
0x180031acd  movups  xmmword ptr [rbp+0B0h+var_100.Length], xmm1
0x180031ad1  call    cs:__imp_GetTickCount64
0x180031ad8  nop     dword ptr [rax+rax+00h]
0x180031add  cmp     dword ptr [rsi+148h], 0
0x180031ae4  mov     rdi, rax
0x180031ae7  ja      short loc_180031B02
0x180031ae9  mov     r8d, 640h; unsigned int
0x180031aef  lea     rdx, aOnecoreDsNetap_15; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180031af6  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180031afd  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180031b02  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x180031b08  lea     r8, [rsp+1B0h+var_15A]; unsigned __int8 *
0x180031b0d  mov     rcx, rsi; struct _CLIENT_SESSION *
0x180031b10  call    ?NlAllocateClientApi@@YAPEAU_CLIENT_API@@PEAU_CLIENT_SESSION@@KPEAE@Z; NlAllocateClientApi(_CLIENT_SESSION *,ulong,uchar *)
0x180031b15  mov     [rbp+0B0h+var_120], rax
0x180031b19  test    rax, rax
0x180031b1c  jnz     loc_180031C90
0x180031b22  xorps   xmm0, xmm0
0x180031b25  mov     [rbp+0B0h+var_68], rax
0x180031b29  lea     r8, aNlpuservalidat_11; "NlpUserValidateHigher: Can't allocate C"...
0x180031b30  mov     [rsp+1B0h+var_150], rax
0x180031b35  mov     rdx, rsi; struct _CLIENT_SESSION *
0x180031b38  mov     ecx, 100h; unsigned int
0x180031b3d  movups  xmmword ptr [rbp+0B0h+var_88], xmm0
0x180031b41  movups  [rbp+0B0h+var_78], xmm0
0x180031b45  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180031b4a  lea     rcx, [r15+20h]; struct _UNICODE_STRING *
0x180031b4e  mov     byte ptr [r12], 1
0x180031b53  lea     rdx, [rbp+0B0h+var_110]; struct _UNICODE_STRING *
0x180031b57  mov     edi, 0C000005Eh
0x180031b5c  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180031b61  lea     rdx, [rbp+0B0h+var_100]; struct _UNICODE_STRING *
0x180031b65  mov     rcx, r15; struct _UNICODE_STRING *
0x180031b68  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180031b6d  xor     r8d, r8d; unsigned int *
0x180031b70  lea     rdx, [rsp+1B0h+var_150]; unsigned __int16 **
0x180031b75  mov     rcx, rsi; struct _CLIENT_SESSION *
0x180031b78  call    ?NlCaptureServerClientSession@@YAJPEAU_CLIENT_SESSION@@PEAPEAGPEAK@Z; NlCaptureServerClientSession(_CLIENT_SESSION *,ushort * *,ulong *)
0x180031b7d  mov     r15, [rsp+1B0h+var_150]
0x180031b82  test    r15, r15
0x180031b85  jz      loc_180031C7C
0x180031b8b  lea     rbx, [rsi+158h]
0x180031b92  mov     rcx, rbx; CriticalSection
0x180031b95  call    cs:__imp_RtlEnterCriticalSection
0x180031b9c  nop     dword ptr [rax+rax+00h]
0x180031ba1  mov     r14d, [rsi+188h]
0x180031ba8  test    r14d, r14d
0x180031bab  jnz     short loc_180031BB9
0x180031bad  mov     dword ptr [rsi+188h], 1
0x180031bb7  jmp     short loc_180031BBF
0x180031bb9  inc     dword ptr [rsi+18Ch]
0x180031bbf  mov     rcx, rbx; CriticalSection
0x180031bc2  call    cs:__imp_RtlLeaveCriticalSection
0x180031bc9  nop     dword ptr [rax+rax+00h]
0x180031bce  test    r14d, r14d
0x180031bd1  jnz     loc_180031C7C
0x180031bd7  mov     rax, [rbp+0B0h+var_110.Buffer]
0x180031bdb  lea     rdx, aNull_0; "(null)"
0x180031be2  test    rax, rax
0x180031be5  mov     qword ptr [rbp+0B0h+var_78], r15
0x180031be9  mov     rcx, rdx
0x180031bec  lea     r8, aLu_0; "%lu"
0x180031bf3  cmovnz  rcx, rax
0x180031bf7  mov     rax, [rbp+0B0h+var_100.Buffer]
0x180031bfb  test    rax, rax
0x180031bfe  mov     qword ptr [rbp+0B0h+var_88], rcx
0x180031c02  mov     rcx, rdx
0x180031c05  cmovnz  rcx, rax
0x180031c09  mov     rax, [rsi+0B8h]
0x180031c10  test    rax, rax
0x180031c13  mov     qword ptr [rbp+0B0h+var_88+8], rcx
0x180031c17  lea     rcx, [rbp+0B0h+Buffer]; Buffer
0x180031c1b  cmovnz  rdx, rax
0x180031c1f  mov     eax, 88888889h
0x180031c24  mov     qword ptr [rbp+0B0h+var_78+8], rdx
0x180031c28  mul     cs:dword_1800F813C
0x180031c2e  shr     edx, 5
0x180031c31  mov     r9d, edx
0x180031c34  lea     edx, [r14+14h]; BufferCount
0x180031c38  call    swprintf_s
0x180031c3d  mov     [rsp+1B0h+var_178], r14d; unsigned int
0x180031c42  lea     rax, [rbp+0B0h+Buffer]
0x180031c46  mov     [rbp+0B0h+var_68], rax
0x180031c4a  lea     edx, [r14+1]; unsigned int
0x180031c4e  lea     rax, [rbp+0B0h+var_88]
0x180031c52  mov     [rsp+1B0h+var_180], 0; unsigned __int8 *
0x180031c5b  mov     [rsp+1B0h+var_188], 5; unsigned int
0x180031c63  or      r9d, 0FFFFFFFFh; unsigned int
0x180031c67  mov     ecx, 16B8h; unsigned int
0x180031c6c  mov     [rsp+1B0h+var_190], rax; unsigned __int16 **
0x180031c71  mov     r8d, 20000000h; unsigned int
0x180031c77  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180031c7c  mov     rcx, r15; Buffer
0x180031c7f  call    cs:__imp_NetApiBufferFree
0x180031c86  nop     dword ptr [rax+rax+00h]
0x180031c8b  jmp     loc_18003292E
0x180031c90  call    cs:__imp_GetTickCount64
0x180031c97  nop     dword ptr [rax+rax+00h]
0x180031c9c  mov     r9, rax
0x180031c9f  mov     eax, cs:dword_1800F8140
0x180031ca5  test    eax, eax
0x180031ca7  jz      loc_180031E6B
0x180031cad  imul    ecx, eax, 3E8h
0x180031cb3  sub     r9, rdi
0x180031cb6  cmp     r9, rcx
0x180031cb9  jbe     loc_180031E6B
0x180031cbf  mov     rax, 624DD2F1A9FBE77h
0x180031cc9  mov     [rsp+1B0h+var_150], 0
0x180031cd2  mul     r9
0x180031cd5  lea     r8, aNlpuservalidat_3; "NlpUserValidateHigher: Warning Event: I"...
0x180031cdc  mov     ecx, 2; unsigned int
0x180031ce1  sub     r9, rdx
0x180031ce4  shr     r9, 1
0x180031ce7  add     r9, rdx
0x180031cea  mov     rdx, rsi; struct _CLIENT_SESSION *
0x180031ced  shr     r9, 9
0x180031cf1  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180031cf6  lea     rcx, [r15+20h]; struct _UNICODE_STRING *
0x180031cfa  lea     rdx, [rbp+0B0h+var_110]; struct _UNICODE_STRING *
0x180031cfe  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180031d03  lea     rdx, [rbp+0B0h+var_100]; struct _UNICODE_STRING *
0x180031d07  mov     rcx, r15; struct _UNICODE_STRING *
0x180031d0a  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180031d0f  xor     r8d, r8d; unsigned int *
0x180031d12  lea     rdx, [rsp+1B0h+var_150]; unsigned __int16 **
0x180031d17  mov     rcx, rsi; struct _CLIENT_SESSION *
0x180031d1a  call    ?NlCaptureServerClientSession@@YAJPEAU_CLIENT_SESSION@@PEAPEAGPEAK@Z; NlCaptureServerClientSession(_CLIENT_SESSION *,ushort * *,ulong *)
0x180031d1f  mov     r15, [rsp+1B0h+var_150]
0x180031d24  test    r15, r15
0x180031d27  jz      loc_180031E5C
0x180031d2d  lea     rdi, [rsi+158h]
0x180031d34  mov     rcx, rdi; CriticalSection
0x180031d37  call    cs:__imp_RtlEnterCriticalSection
0x180031d3e  nop     dword ptr [rax+rax+00h]
0x180031d43  mov     r14d, [rsi+190h]
0x180031d4a  test    r14d, r14d
0x180031d4d  jnz     short loc_180031D5B
0x180031d4f  mov     dword ptr [rsi+190h], 1
0x180031d59  jmp     short loc_180031D61
0x180031d5b  inc     dword ptr [rsi+194h]
0x180031d61  mov     rcx, rdi; CriticalSection
0x180031d64  call    cs:__imp_RtlLeaveCriticalSection
0x180031d6b  nop     dword ptr [rax+rax+00h]
0x180031d70  test    r14d, r14d
0x180031d73  jnz     loc_180031E57
0x180031d79  mov     r9d, cs:dword_1800F8140
0x180031d80  lea     r8, aLu_0; "%lu"
0x180031d87  xorps   xmm0, xmm0
0x180031d8a  lea     rcx, [rbp+0B0h+Buffer]; Buffer
0x180031d8e  mov     r14d, 14h
0x180031d94  mov     edx, r14d; BufferCount
0x180031d97  movups  xmmword ptr [rbp+0B0h+var_B8], xmm0
0x180031d9b  movups  [rbp+0B0h+var_A8], xmm0
0x180031d9f  movups  [rbp+0B0h+var_98], xmm0
0x180031da3  call    swprintf_s
0x180031da8  lea     rdx, aNull_0; "(null)"
0x180031daf  mov     qword ptr [rbp+0B0h+var_A8+8], r15
0x180031db3  mov     rcx, rdx
0x180031db6  lea     rax, [rbp+0B0h+Buffer]
0x180031dba  mov     [rbp+0B0h+var_B8], rax
0x180031dbe  lea     r8, aLu_0; "%lu"
0x180031dc5  mov     rax, [rbp+0B0h+var_110.Buffer]
0x180031dc9  test    rax, rax
0x180031dcc  cmovnz  rcx, rax
0x180031dd0  mov     rax, [rbp+0B0h+var_100.Buffer]
0x180031dd4  test    rax, rax
0x180031dd7  mov     [rbp+0B0h+var_B8+8], rcx
0x180031ddb  mov     rcx, rdx
0x180031dde  cmovnz  rcx, rax
0x180031de2  mov     rax, [rsi+0B8h]
0x180031de9  test    rax, rax
0x180031dec  mov     qword ptr [rbp+0B0h+var_A8], rcx
0x180031df0  lea     rcx, [rbp+0B0h+var_88]; Buffer
0x180031df4  cmovnz  rdx, rax
0x180031df8  mov     eax, 88888889h
0x180031dfd  mov     qword ptr [rbp+0B0h+var_98], rdx
0x180031e01  mul     cs:dword_1800F813C
0x180031e07  shr     edx, 5
0x180031e0a  mov     r9d, edx
0x180031e0d  mov     edx, r14d; BufferCount
0x180031e10  call    swprintf_s
0x180031e15  mov     [rsp+1B0h+var_178], 0; unsigned int
0x180031e1d  lea     rax, [rbp+0B0h+var_88]
0x180031e21  mov     qword ptr [rbp+0B0h+var_98+8], rax
0x180031e25  lea     edx, [r14-12h]; unsigned int
0x180031e29  lea     rax, [rbp+0B0h+var_B8]
0x180031e2d  mov     [rsp+1B0h+var_180], 0; unsigned __int8 *
0x180031e36  mov     [rsp+1B0h+var_188], 6; unsigned int
0x180031e3e  or      r9d, 0FFFFFFFFh; unsigned int
0x180031e42  mov     ecx, 16BAh; unsigned int
0x180031e47  mov     [rsp+1B0h+var_190], rax; unsigned __int16 **
0x180031e4c  mov     r8d, 20000000h; unsigned int
0x180031e52  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180031e57  mov     r14d, [rsp+1B0h+var_158]
0x180031e5c  mov     rcx, r15; Buffer
0x180031e5f  call    cs:__imp_NetApiBufferFree
0x180031e66  nop     dword ptr [rax+rax+00h]
0x180031e6b  lea     rcx, [rbp+0B0h+PerformanceCount]; lpPerformanceCount
0x180031e6f  call    cs:__imp_QueryPerformanceCounter
0x180031e76  nop     dword ptr [rax+rax+00h]
0x180031e7b  test    eax, eax
0x180031e7d  jnz     short loc_180031E87
0x180031e7f  mov     qword ptr [rbp+0B0h+PerformanceCount], 0
0x180031e87  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x180031e8d  mov     rcx, rsi; struct _CLIENT_SESSION *
0x180031e90  call    ?NlTimeoutSetWriterClientSession@@YAHPEAU_CLIENT_SESSION@@K@Z; NlTimeoutSetWriterClientSession(_CLIENT_SESSION *,ulong)
0x180031e95  test    eax, eax
0x180031e97  jnz     short loc_180031EBC
0x180031e99  lea     r8, aNlpuservalidat_5; "NlpUserValidateHigher: Can't become wri"...
0x180031ea0  mov     rdx, rsi; struct _CLIENT_SESSION *
0x180031ea3  mov     ecx, 100h; unsigned int
0x180031ea8  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180031ead  mov     byte ptr [r12], 1
0x180031eb2  mov     edi, 0C000005Eh
0x180031eb7  jmp     loc_18003292E
0x180031ebc  mov     r15d, [rbp+0B0h+arg_20]
0x180031ec3  mov     [rsp+1B0h+var_15B], 1
0x180031ec8  mov     [rsp+1B0h+var_160], 1
0x180031ecd  cmp     r14d, 4
0x180031ed1  jz      short loc_180031EE4
0x180031ed3  lea     eax, [r15-4]
0x180031ed7  cmp     eax, 1
0x180031eda  jbe     short loc_180031EE4
0x180031edc  xor     al, al
0x180031ede  mov     [rsp+1B0h+var_15E], al
0x180031ee2  jmp     short loc_180031EE9
0x180031ee4  mov     [rsp+1B0h+var_15E], 1
0x180031ee9  cmp     r14d, 4
0x180031eed  jz      short loc_180031EFF
0x180031eef  test    r14d, r14d
0x180031ef2  jle     short loc_180031EFF
0x180031ef4  mov     [rsp+1B0h+var_15C], 1
0x180031ef9  cmp     r14d, 8
0x180031efd  jl      short loc_180031F04
0x180031eff  mov     [rsp+1B0h+var_15C], r13b
0x180031f04  mov     r13b, [rsp+1B0h+var_15E]
0x180031f09  test    r13b, r13b
0x180031f0c  jnz     short loc_180031F22
0x180031f0e  cmp     [rsp+1B0h+var_15D], r13b
0x180031f13  jnz     short loc_180031F22
0x180031f15  mov     rax, [rbp+0B0h+var_130]
0x180031f19  cmp     dword ptr [rax], 0
0x180031f1c  jnz     short loc_180031F22
0x180031f1e  xor     ecx, ecx
0x180031f20  jmp     short loc_180031F27
0x180031f22  mov     ecx, 4
0x180031f27  lea     eax, [r14-1]
0x180031f2b  and     eax, 0FFFFFFFBh
0x180031f2e  neg     eax
0x180031f30  sbb     edx, edx
0x180031f32  not     edx
0x180031f34  and     edx, 8
0x180031f37  or      edx, ecx; unsigned int
0x180031f39  mov     rcx, rsi; struct _CLIENT_SESSION *
0x180031f3c  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x180031f41  mov     edi, eax
0x180031f43  test    eax, eax
0x180031f45  js      loc_1800328AF
0x180031f4b  mov     r9d, [rsi+13Ch]; unsigned int
0x180031f52  lea     r10, [rsi+1B8h]
0x180031f59  movups  xmm0, xmmword ptr [r10]
  ... truncated ...
```
