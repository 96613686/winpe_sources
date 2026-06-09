# NlpUserValidateHigher(_CLIENT_SESSION *,uchar,_NETLOGON_LOGON_INFO_CLASS,uchar *,_NETLOGON_VALIDATION_INFO_CLASS,uchar * *,uchar *,ulong *)

- ea: `0x18002fdb4`
- end: `0x180030d7f`
- name: `?NlpUserValidateHigher@@YAJPEAU_CLIENT_SESSION@@EW4_NETLOGON_LOGON_INFO_CLASS@@PEAEW4_NETLOGON_VALIDATION_INFO_CLASS@@PEAPEAE2PEAK@Z`
- size: `4043`
- prototype: ``
- caller_count: `3`
- callee_count: `35`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e730`
- `0x180030d88`
- `0x180059e9c`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x18000edf4`
- `0x18002cb3c`
- `0x18002cc78`
- `0x18002cd6c`
- `0x18002fdb4`
- `0x180035368`
- `0x18003e208`
- `0x18003e294`
- `0x18003e71c`
- `0x18003e7dc`
- `0x18003f034`
- `0x18003f054`
- `0x18003f540`
- `0x18003f684`
- `0x18004fc34`
- `0x18004fcf8`
- `0x18004ff38`
- `0x18004ffd8`
- `0x18005f358`
- `0x18005f79c`
- `0x180060734`
- `0x180063c50`
- `0x180064228`
- `0x18006515c`
- `0x1800655e4`
- `0x1800675c0`
- `0x180068458`
- `0x1800688e0`
- `0x1800694d0`
- `0x18006c0ec`
- `0x18006c144`
- `0x18006c554`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003063b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003094b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030aae`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003063b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003094b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030aae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002fe49`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002fff0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002fe49`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002fff0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800301b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180030c9d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800301b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180030c9d`
- `logoncli!I_NetLogonSamLogon` at `0x1800305ab`
- `logoncli!I_NetLogonSamLogon` at `0x1800305ab`
- `logoncli!I_NetLogonSamLogonWithFlags` at `0x18003054e`
- `logoncli!I_NetLogonSamLogonWithFlags` at `0x18003054e`
- `logoncli!I_NetLogonSamLogonEx` at `0x1800304b2`
- `logoncli!I_NetLogonSamLogonEx` at `0x1800304b2`
- `LSASRV!LsaIFilterSids` at `0x180030a17`
- `LSASRV!LsaIFilterSids` at `0x180030a66`
- `LSASRV!LsaIFilterSids` at `0x180030a17`
- `LSASRV!LsaIFilterSids` at `0x180030a66`
- `ntdll!RtlAcquireResourceShared` at `0x180030c8c`
- `ntdll!RtlAcquireResourceShared` at `0x180030c8c`
- `ntdll!RtlEqualDomainName` at `0x180030921`
- `ntdll!RtlEqualDomainName` at `0x180030921`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ff2e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800300b8`
- `ntdll!RtlLeaveCriticalSection` at `0x180030a29`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ff2e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800300b8`
- `ntdll!RtlLeaveCriticalSection` at `0x180030a29`
- `ntdll!RtlEnterCriticalSection` at `0x18002ff07`
- `ntdll!RtlEnterCriticalSection` at `0x180030091`
- `ntdll!RtlEnterCriticalSection` at `0x1800309b7`
- `ntdll!RtlEnterCriticalSection` at `0x18002ff07`
- `ntdll!RtlEnterCriticalSection` at `0x180030091`
- `ntdll!RtlEnterCriticalSection` at `0x1800309b7`
- `ntdll!RtlEqualSid` at `0x180030939`
- `ntdll!RtlEqualSid` at `0x180030939`
- `ntdll!RtlReleaseResource` at `0x180030d50`
- `ntdll!RtlReleaseResource` at `0x180030d50`
- `netutils!NetApiBufferFree` at `0x18002ffe5`
- `netutils!NetApiBufferFree` at `0x1800301ad`
- `netutils!NetApiBufferFree` at `0x18002ffe5`
- `netutils!NetApiBufferFree` at `0x1800301ad`

## string_xrefs

- `0x18002fe61`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18003042a`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x1800305d3`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030660`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x1800306a8`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030a84`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030b3f`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030b61`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030bea`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030c0c`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x1800301db`: `NlpUserValidateHigher: Can't become writer of client session.\n`
- `0x18003061a`: `NlpUserValidateHigher: Can't become writer (again) of client session.\n`
- `0x1800307c5`: `NlpUserValidateHigher: denying access after status: 0x%lx %lx\n`
- `0x180030a8b`: `!"[NETLOGON] LsaIFilterSids failed"`
- `0x180030a9a`: `NlpUserValidateHigher: LsaIFilterSids failed 0x%lx\n`

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
  char *v15; // r9
  unsigned __int16 *v16; // r15
  int v17; // r14d
  const unsigned __int16 *v18; // rdx
  PWSTR v19; // rcx
  PWSTR v20; // rcx
  const unsigned __int16 *v21; // rax
  ULONGLONG v22; // r9
  unsigned __int64 v23; // r9
  char *v24; // r9
  unsigned __int16 *v25; // r15
  int v26; // r14d
  const unsigned __int16 *v27; // rdx
  unsigned __int16 *v28; // rcx
  PWSTR v29; // rcx
  const unsigned __int16 *v30; // rax
  bool v31; // r13
  int v32; // ecx
  int v33; // eax
  char *v34; // r9
  __int128 v35; // xmm0
  int v36; // edx
  int v37; // r13d
  struct _CLIENT_API *v38; // rax
  int v39; // eax
  unsigned int v40; // eax
  char *v41; // r9
  unsigned int v42; // edx
  __int64 v43; // r8
  int v44; // eax
  char *v45; // r9
  int v46; // eax
  __int64 v47; // rdx
  int v48; // eax
  const char *v49; // rcx
  __int64 v50; // rdx
  bool v51; // sf
  unsigned __int64 v52; // rax
  __int64 v53; // rcx
  int v54; // edx
  unsigned __int8 v55; // al
  BOOL v56; // r14d
  unsigned __int16 *v57; // r8
  int v58; // eax
  PSID *v59; // r14
  int v60; // ecx
  bool v61; // zf
  struct _NETLOGON_VALIDATION_TICKET_LOGON *v62; // r14
  struct _NETLOGON_TICKET_LOGON_INFO *v63; // r15
  __int64 v64; // r8
  int v65; // eax
  __int128 *v66; // rax
  __int64 v67; // rcx
  __int64 v68; // r14
  LONGLONG v69; // rbx
  unsigned __int16 **v71; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v72; // [rsp+20h] [rbp-E0h]
  unsigned int v73[2]; // [rsp+28h] [rbp-D8h]
  unsigned __int8 *v74; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v75; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v76; // [rsp+51h] [rbp-AFh] BYREF
  bool v77; // [rsp+52h] [rbp-AEh]
  char v78; // [rsp+53h] [rbp-ADh]
  char v79; // [rsp+54h] [rbp-ACh]
  char v80; // [rsp+55h] [rbp-ABh]
  unsigned __int8 v81[2]; // [rsp+56h] [rbp-AAh] BYREF
  enum _NETLOGON_LOGON_INFO_CLASS v82; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v83; // [rsp+60h] [rbp-A0h] BYREF
  struct _NETLOGON_TICKET_LOGON_INFO *v84; // [rsp+68h] [rbp-98h]
  unsigned int v85; // [rsp+70h] [rbp-90h]
  struct _CLIENT_API *v86; // [rsp+78h] [rbp-88h]
  unsigned int *v87; // [rsp+80h] [rbp-80h]
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-78h] BYREF
  struct _CLIENT_API *ClientApi; // [rsp+90h] [rbp-70h]
  LARGE_INTEGER v90; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING v91; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v92; // [rsp+B0h] [rbp-50h] BYREF
  struct _CYPHER_BLOCK v93; // [rsp+C0h] [rbp-40h] BYREF
  int v94; // [rsp+C8h] [rbp-38h]
  __int128 v95; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v96; // [rsp+E0h] [rbp-20h]
  __int64 v97; // [rsp+E8h] [rbp-18h] BYREF
  int v98; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v99[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v100; // [rsp+108h] [rbp+8h]
  __int128 v101; // [rsp+118h] [rbp+18h]
  wchar_t v102[8]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v103; // [rsp+138h] [rbp+38h]
  wchar_t *v104; // [rsp+148h] [rbp+48h]
  wchar_t Buffer[20]; // [rsp+150h] [rbp+50h] BYREF

  v87 = a8;
  v84 = (struct _NETLOGON_TICKET_LOGON_INFO *)a4;
  v97 = 0;
  v98 = 0;
  v10 = a3;
  v93 = 0;
  v11 = 0;
  v94 = 0;
  v96 = 0;
  v82 = a3;
  v78 = a2;
  v95 = 0;
  v76 = 0;
  v81[0] = 1;
  v90.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v91 = 0;
  v92 = 0;
  TickCount64 = GetTickCount64();
  if ( !*(_DWORD *)(a1 + 328) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
      1599,
      v13);
  ClientApi = NlAllocateClientApi((struct _CLIENT_SESSION *)a1, dwMilliseconds, v81, v13);
  if ( !ClientApi )
  {
    v104 = 0;
    v83 = 0;
    *(_OWORD *)v102 = 0;
    v103 = 0;
    NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlpUserValidateHigher: Can't allocate Client API slot.\n");
    *a7 = 1;
    started = -1073741730;
    NlDuplicateUnicodeString((struct _UNICODE_STRING *)(a4 + 32), &v91);
    NlDuplicateUnicodeString((struct _UNICODE_STRING *)a4, &v92);
    NlCaptureServerClientSession((struct _CLIENT_SESSION *)a1, (LPVOID *)&v83, 0, v15);
    v16 = v83;
    if ( v83 )
    {
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 344));
      v17 = *(_DWORD *)(a1 + 392);
      if ( v17 )
        ++*(_DWORD *)(a1 + 396);
      else
        *(_DWORD *)(a1 + 392) = 1;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 344));
      if ( !v17 )
      {
        v18 = L"(null)";
        *(_QWORD *)&v103 = v16;
        v19 = (PWSTR)L"(null)";
        if ( v91.Buffer )
          v19 = v91.Buffer;
        *(_QWORD *)v102 = v19;
        v20 = (PWSTR)L"(null)";
        if ( v92.Buffer )
          v20 = v92.Buffer;
        v21 = *(const unsigned __int16 **)(a1 + 184);
        *(_QWORD *)&v102[4] = v20;
        if ( v21 )
          v18 = v21;
        *((_QWORD *)&v103 + 1) = v18;
        swprintf_s(Buffer, 0x14u, L"%lu", dword_1800F113C / 0x3Cu);
        v104 = Buffer;
        NlpWriteEventlogEx(0x16B8u, 1u, 0x20000000u, 0xFFFFFFFF, (unsigned __int16 **)v102, 5u, 0, 0);
      }
    }
    NetApiBufferFree(v16);
    goto LABEL_194;
  }
  v22 = GetTickCount64();
  if ( dword_1800F1140 )
  {
    v23 = v22 - TickCount64;
    if ( v23 > (unsigned int)(1000 * dword_1800F1140) )
    {
      v83 = 0;
      NlPrintCsRoutine(
        2u,
        (struct _CLIENT_SESSION *)a1,
        L"NlpUserValidateHigher: Warning Event: It took %I64d seconds to acquire a Client API slot\n",
        v23 / 0x3E8);
      NlDuplicateUnicodeString((struct _UNICODE_STRING *)(a4 + 32), &v91);
      NlDuplicateUnicodeString((struct _UNICODE_STRING *)a4, &v92);
      NlCaptureServerClientSession((struct _CLIENT_SESSION *)a1, (LPVOID *)&v83, 0, v24);
      v25 = v83;
      if ( v83 )
      {
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 344));
        v26 = *(_DWORD *)(a1 + 400);
        if ( v26 )
          ++*(_DWORD *)(a1 + 404);
        else
          *(_DWORD *)(a1 + 400) = 1;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 344));
        if ( !v26 )
        {
          *(_OWORD *)v99 = 0;
          v100 = 0;
          v101 = 0;
          swprintf_s(Buffer, 0x14u, L"%lu", (unsigned int)dword_1800F1140);
          v27 = L"(null)";
          *((_QWORD *)&v100 + 1) = v25;
          v28 = L"(null)";
          v99[0] = Buffer;
          if ( v91.Buffer )
            v28 = v91.Buffer;
          v99[1] = v28;
          v29 = (PWSTR)L"(null)";
          if ( v92.Buffer )
            v29 = v92.Buffer;
          v30 = *(const unsigned __int16 **)(a1 + 184);
          *(_QWORD *)&v100 = v29;
          if ( v30 )
            v27 = v30;
          *(_QWORD *)&v101 = v27;
          swprintf_s(v102, 0x14u, L"%lu", dword_1800F113C / 0x3Cu);
          *((_QWORD *)&v101 + 1) = v102;
          NlpWriteEventlogEx(0x16BAu, 2u, 0x20000000u, 0xFFFFFFFF, v99, 6u, 0, 0);
        }
        v10 = v82;
      }
      NetApiBufferFree(v25);
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
  v80 = 1;
  v75 = 1;
  v77 = v10 == NetlogonGenericInformation || a5 - 4 <= 1;
  if ( v10 == NetlogonGenericInformation || v10 <= 0 || (v79 = 1, v10 >= 8) )
    v79 = 0;
  while ( 2 )
  {
    v31 = v77;
    if ( v77 || v78 || *v87 )
      v32 = 4;
    else
      v32 = 0;
    v33 = NlEnsureSessionAuthenticated(
            (struct _CLIENT_SESSION *)a1,
            v32 | (unsigned int)(((v10 - 1) & 0xFFFFFFFB) == 0 ? 8 : 0));
    started = v33;
    if ( v33 < 0 )
    {
      if ( v33 != -1073741790
        && v33 != -1073741730
        && (unsigned int)(v33 + 1073741430) > 1
        && !NlpIsNtStatusResourceError(v33) )
      {
        started = -1073741730;
      }
      *a7 = 1;
      goto LABEL_187;
    }
    v35 = *(_OWORD *)(a1 + 440);
    v96 = *(_DWORD *)(a1 + 316);
    v36 = ((v96 & 0x80000) != 0 ? 3 : 0) | 0xC;
    v95 = v35;
    if ( (v96 & 0x200000) == 0 )
      v36 = (v96 & 0x80000) != 0 ? 3 : 0;
    if ( (~v36 & *v87) != 0 )
    {
      LODWORD(v71) = v36;
      NlPrintCsRoutine(
        0x100u,
        (struct _CLIENT_SESSION *)a1,
        L"NlpUserValidateHigher: Can't pass these ExtraFlags to old DC: %lx %lx\n",
        *v87,
        v71);
      started = -1073741730;
      goto LABEL_164;
    }
    if ( (v96 & 0x400) == 0 && (v31 || v78) )
    {
      *a7 = 1;
      v57 = L"NlpUserValidateHigher: Can't do generic passthru to NT 4 DC.\n";
      if ( !v31 )
        v57 = L"NlpUserValidateHigher: Can't do transitive trust to NT 4 DC.\n";
      NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, v57);
      started = v31 ? -1073741821 : -1073741730;
LABEL_187:
      if ( started < 0 )
        goto LABEL_193;
      goto LABEL_188;
    }
    if ( !v79 )
      goto LABEL_63;
    if ( (v96 & 0x40) != 0 )
    {
      if ( (v96 & 0x80000) == 0 || (v96 & 0x40000000) == 0 )
      {
        v37 = 3;
        goto LABEL_64;
      }
LABEL_63:
      v37 = a5;
      goto LABEL_64;
    }
    v37 = 2;
LABEL_64:
    if ( (v96 & 0x40000800) == 0x40000800 )
    {
      v38 = ClientApi;
    }
    else
    {
      if ( v10 == 8 )
      {
        started = -1073741821;
        goto LABEL_164;
      }
      v38 = (struct _CLIENT_API *)(a1 + 680);
    }
    v86 = v38;
    v83 = (unsigned __int16 *)(((__int64)v38 - a1 - 680) / 560);
    if ( !(_DWORD)v83 )
    {
      v39 = NlBuildAuthenticator(
              (struct _CYPHER_BLOCK *)(a1 + 432),
              (struct _NETLOGON_SESSION_KEY *)(a1 + 440),
              (struct _NETLOGON_AUTHENTICATOR *)&v97,
              v96);
      started = v39;
      if ( v39 < 0 )
      {
        NlPrintRoutine(
          0x100u,
          L"NlpUserValidateHigher: NlBuildAuthenticator failed with status: 0x%lx\n",
          (unsigned int)v39);
        goto LABEL_193;
      }
    }
    NlpEncryptLogonInformation(v10, (unsigned __int8 *)v84, (struct _SESSION_INFO *)&v95);
    v40 = 0;
    v76 = 0;
    v85 = 0;
    started = -1073610748;
    while ( 1 )
    {
      started = NlStartApiClientSession((struct _CLIENT_SESSION *)a1, 1u, v40, started, v86);
      if ( started < 0 )
        goto LABEL_106;
      v42 = v96;
      v76 = 0;
      if ( (v96 & 0x8000) == 0 )
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
        v82 = v10;
      }
LABEL_80:
      if ( !*(_QWORD *)(a1 + 504) )
      {
        NlAssertFailed(
          "ClientSession->CsUncServerName != NULL",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
          2016,
          v41);
        v42 = v96;
      }
      if ( (_DWORD)v83 )
        break;
      v46 = *(_DWORD *)(a1 + 292) & 0x40000;
      if ( (v42 & 0x80000) != 0 )
      {
        if ( v46 )
          v47 = *(_QWORD *)(a1 + 216);
        else
          v47 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
        LODWORD(v74) = v37;
        v48 = I_NetLogonSamLogonWithFlags(*(_QWORD *)(a1 + 504), v47, &v97, &v93, v10, v84, v74, a6, a7, v87);
        started = v48;
        if ( v48 < 0 )
        {
          v49 = "I_NetLogonSamLogonWithFlags";
LABEL_101:
          NlPrintRpcDebug(v49, v48);
LABEL_102:
          if ( started < 0 )
            goto LABEL_106;
        }
      }
      else
      {
        if ( v46 )
          v50 = *(_QWORD *)(a1 + 216);
        else
          v50 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
        v48 = I_NetLogonSamLogon(*(_QWORD *)(a1 + 504), v50, &v97, &v93, v10, v84, v37, a6, a7);
        started = v48;
        if ( v48 < 0 )
        {
          v49 = "I_NetLogonSamLogon";
          goto LABEL_101;
        }
      }
      v51 = started < 0;
      if ( started )
      {
        NlAssertFailed(
          "!NT_SUCCESS(Status) || Status == STATUS_SUCCESS",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
          2113,
          v45);
        v51 = started < 0;
      }
      if ( !v51 )
      {
        if ( !*a6 )
          NlAssertFailed(
            "!NT_SUCCESS(Status) || *ValidationInformation != NULL",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            2114,
            v45);
        goto LABEL_115;
      }
LABEL_106:
      v52 = (unsigned int)(started + 1073610748);
      if ( (unsigned int)v52 <= 0x32 )
      {
        v53 = 0x4000000080001LL;
        if ( _bittest64(&v53, v52) )
        {
          v40 = v85 + 1;
          v85 = v40;
          if ( v40 < 2 )
            continue;
        }
      }
      goto LABEL_115;
    }
    NlResetWriterClientSession((struct _CLIENT_SESSION *)a1);
    if ( (*(_DWORD *)(a1 + 292) & 0x40000) != 0 )
      v43 = *(_QWORD *)(a1 + 216);
    else
      v43 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 264LL);
    v73[0] = v37;
    v44 = I_NetLogonSamLogonEx(
            *((_QWORD *)v86 + 4),
            (char *)v86 + 44,
            v43,
            (unsigned int)v10,
            v84,
            *(_QWORD *)v73,
            a6,
            a7,
            v87,
            &v76);
    started = v44;
    if ( v44 < 0 )
      NlPrintRpcDebug("I_NetLogonSamLogonEx", v44);
    if ( (unsigned int)NlTimeoutSetWriterClientSession((struct _CLIENT_SESSION *)a1, dwMilliseconds) )
    {
      v75 = 1;
      goto LABEL_102;
    }
    v75 = 0;
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
    NlFinishApiClientSession((struct _CLIENT_SESSION *)a1, 1u, v75, v86);
    NlpDecryptLogonInformation(v10, (unsigned __int8 *)v84, (struct _SESSION_INFO *)&v95);
    if ( started >= 0 && !*a6 )
      NlAssertFailed(
        "*ValidationInformation != NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
        2123,
        v34);
    if ( !v75 )
      goto LABEL_187;
    NlPrintRoutine(0x4000000u, L"NlpUserValidateHigher: Seed = ");
    NlpDumpBuffer(0x4000000u, (void *)(a1 + 432), 8u);
    NlPrintRoutine(0x4000000u, L"NlpUserValidateHigher: SessionKey = ");
    NlpDumpBuffer(0x4000000u, (void *)(a1 + 440), 0x10u);
    if ( !(_DWORD)v83 )
    {
      NlPrintRoutine(0x4000000u, L"NlpUserValidateHigher: Return Authenticator = ");
      NlpDumpBuffer(0x4000000u, &v93, 8u);
    }
    if ( NlpDidDcFail(started) )
    {
LABEL_126:
      v55 = v76;
LABEL_127:
      v56 = (started == -1073545204 || started == -1073741821) && a5 == 7;
      LODWORD(v72) = v55;
      NlPrintCsRoutine(
        0x100u,
        (struct _CLIENT_SESSION *)a1,
        L"NlpUserValidateHigher: denying access after status: 0x%lx %lx\n",
        (unsigned int)started,
        v72);
      if ( started >= 0 )
        started = -1073741790;
      if ( *((_DWORD *)v86 + 10) == *(_DWORD *)(a1 + 324) && !v56 )
        NlSetStatusClientSession((struct _CLIENT_SESSION *)a1, started);
      if ( !v80 )
      {
        *a7 = 1;
        goto LABEL_193;
      }
      v10 = v82;
      v80 = 0;
      continue;
    }
    break;
  }
  v55 = v76;
  if ( v76 )
    goto LABEL_127;
  if ( !v54
    && (unsigned int)NlCheckRpcAuthIsNetlogon((struct _CLIENT_SESSION *)a1)
    && !(unsigned int)NlUpdateSeed((PUCHAR)(a1 + 432), &v93, (PUCHAR)(a1 + 440), *(_DWORD *)(a1 + 316)) )
  {
    goto LABEL_126;
  }
  if ( started < 0 )
    goto LABEL_193;
  NlpDecryptValidationInformation((unsigned int)v82, (unsigned int)v37, *a6, &v95);
  if ( ((a5 - 2) & 0xFFFFFFFA) != 0 )
    goto LABEL_173;
  if ( a5 == 7 )
  {
LABEL_174:
    v62 = (struct _NETLOGON_VALIDATION_TICKET_LOGON *)*a6;
    v63 = v84;
    v64 = *v87 >> 13;
    LOBYTE(v64) = (*v87 & 0x2000) != 0;
    started = IsTicketLogonReplySupported(v84, (struct _NETLOGON_VALIDATION_TICKET_LOGON *const)*a6, v64);
    if ( started < 0 )
    {
LABEL_175:
      FreeTicketValidationInformation(v62);
      *a6 = 0;
      goto LABEL_193;
    }
    v65 = TransformKerberosTicketLogonInbound(v63, v62, (struct _CLIENT_SESSION *)a1);
    started = v65;
    if ( v65 < 0 )
    {
      NlPrintRoutine(0x100u, L"TransformKerberosTicketLogonInbound 0x%lx\n", (unsigned int)v65);
      goto LABEL_175;
    }
LABEL_188:
    v61 = started == 0;
LABEL_189:
    if ( v61
      || (NlAssertFailed(
            "!NT_SUCCESS(Status) || Status == STATUS_SUCCESS",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            2410,
            v34),
          started >= 0) )
    {
      if ( !*a6 )
        NlAssertFailed(
          "!NT_SUCCESS(Status) || *ValidationInformation != NULL",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
          2411,
          v34);
    }
    goto LABEL_193;
  }
  if ( ((v37 - 2) & 0xFFFFFFFA) == 0 && v37 != 7 && (int)a5 > v37 )
  {
    v58 = NlpAddResourceGroupsToSamInfo(v37, (unsigned __int8 *)a6, 0);
    if ( v58 < 0 )
    {
      *a6 = 0;
      started = v58;
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
      v59 = (PSID *)*a6;
      if ( RtlEqualDomainName((PUNICODE_STRING)*a6 + 13, (PUNICODE_STRING)(a1 + 112)) )
      {
        if ( !RtlEqualSid(v59[28], *(PSID *)(a1 + 264)) )
        {
          started = -1073741413;
          free(*a6);
          *a6 = 0;
          *a7 = 1;
        }
      }
    }
  }
  v60 = *(_DWORD *)(a1 + 280);
  if ( (unsigned int)(v60 - 3) <= 1 && *a6 )
  {
    if ( (*(_BYTE *)(a1 + 296) & 0x10) != 0 && (a5 == 3 || a5 == 6) )
    {
      started = NlpAddOtherOrganizationSid(a5, a6);
      if ( started < 0 )
        goto LABEL_163;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)(a1 + 272) + 400LL));
    v73[0] = a5;
    started = LsaIFilterSids(
                (a1 + 152) & -(__int64)(*(_WORD *)(a1 + 152) != 0),
                2,
                (unsigned int)((*(_DWORD *)(a1 + 292) & 4) != 0) + 1,
                *(unsigned int *)(a1 + 296),
                *(_QWORD *)(a1 + 264),
                *(_QWORD *)v73,
                *a6,
                0,
                0,
                0);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)(a1 + 272) + 400LL));
  }
  else if ( v60 == 2 && *a6 )
  {
    v73[0] = a5;
    started = LsaIFilterSids(0, 0, 0, 0, 0, *(_QWORD *)v73, *a6, 0, 0, 0);
  }
  v61 = started == 0;
  if ( started >= 0 )
    goto LABEL_189;
  if ( started == -1073741413 )
    NlAssertFailed(
      "!\"[NETLOGON] LsaIFilterSids failed\"",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
      2371,
      v34);
  NlPrintRoutine(0x100u, L"NlpUserValidateHigher: LsaIFilterSids failed 0x%lx\n", (unsigned int)started);
  free(*a6);
LABEL_163:
  *a6 = 0;
LABEL_164:
  *a7 = 1;
LABEL_193:
  v11 = v75;
LABEL_194:
  v66 = &v95;
  v67 = 16;
  do
  {
    *(_BYTE *)v66 = 0;
    v66 = (__int128 *)((char *)v66 + 1);
    --v67;
  }
  while ( v67 );
  if ( v11 )
    NlResetWriterClientSession((struct _CLIENT_SESSION *)a1);
  NlFreeUnicodeString(&v91);
  NlFreeUnicodeString(&v92);
  if ( ClientApi )
  {
    v68 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 352LL);
    NlFreeClientApi((struct _CLIENT_SESSION *)a1, ClientApi, v81[0]);
    RtlAcquireResourceShared(&NlPcGlobalLock, 1u);
    if ( PerformanceCount.QuadPart && QueryPerformanceCounter(&v90) )
    {
      v69 = v90.QuadPart - PerformanceCount.QuadPart;
      NlPcIncrement64(*(_QWORD *)(a1 + 672), 4, v90.QuadPart - PerformanceCount.QuadPart);
      NlPcIncrement64(v68, 4, v69);
      NlPcIncrement64(NlPcGlobalTotalInstance, 4, v69);
    }
    NlPcIncrement64(*(_QWORD *)(a1 + 672), 2, 1);
    NlPcIncrement64(v68, 2, 1);
    NlPcIncrement64(NlPcGlobalTotalInstance, 2, 1);
    NlPcIncrement32(*(_QWORD *)(a1 + 672), 5);
    NlPcIncrement32(v68, 5);
    NlPcIncrement32(NlPcGlobalTotalInstance, 5);
    RtlReleaseResource(&NlPcGlobalLock);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18002fdb4  mov     [rsp-8+arg_8], rbx
0x18002fdb9  push    rbp
0x18002fdba  push    rsi
0x18002fdbb  push    rdi
0x18002fdbc  push    r12
0x18002fdbe  push    r13
0x18002fdc0  push    r14
0x18002fdc2  push    r15
0x18002fdc4  lea     rbp, [rsp-80h]
0x18002fdc9  sub     rsp, 180h
0x18002fdd0  mov     rax, cs:__security_cookie
0x18002fdd7  xor     rax, rsp
0x18002fdda  mov     [rbp+0B0h+var_38], rax
0x18002fdde  mov     rax, [rbp+0B0h+arg_38]
0x18002fde5  xorps   xmm0, xmm0
0x18002fde8  mov     rbx, [rbp+0B0h+arg_28]
0x18002fdef  mov     rsi, rcx
0x18002fdf2  mov     r12, [rbp+0B0h+arg_30]
0x18002fdf9  xor     ecx, ecx
0x18002fdfb  mov     [rbp+0B0h+var_130], rax
0x18002fdff  xorps   xmm1, xmm1
0x18002fe02  xor     eax, eax
0x18002fe04  mov     [rsp+1B0h+var_148], r9
0x18002fe09  mov     [rbp+0B0h+var_C8], rax
0x18002fe0d  mov     r15, r9
0x18002fe10  mov     [rbp+0B0h+var_C0], eax
0x18002fe13  mov     r14d, r8d
0x18002fe16  mov     qword ptr [rbp+0B0h+var_F0.data], rax
0x18002fe1a  mov     r13b, cl
0x18002fe1d  mov     [rbp+0B0h+var_E8], eax
0x18002fe20  mov     [rbp+0B0h+var_D0], eax
0x18002fe23  mov     [rsp+1B0h+var_158], r8d
0x18002fe28  mov     [rsp+1B0h+var_15D], dl
0x18002fe2c  movups  [rbp+0B0h+var_E0], xmm0
0x18002fe30  mov     [rsp+1B0h+var_15F], cl
0x18002fe34  mov     [rsp+1B0h+var_15A], 1
0x18002fe39  mov     qword ptr [rbp+0B0h+var_118], rcx
0x18002fe3d  mov     qword ptr [rbp+0B0h+PerformanceCount], rcx
0x18002fe41  movups  xmmword ptr [rbp+0B0h+var_110.Length], xmm0
0x18002fe45  movups  xmmword ptr [rbp+0B0h+var_100.Length], xmm1
0x18002fe49  call    cs:__imp_GetTickCount64
0x18002fe4f  cmp     dword ptr [rsi+148h], 0
0x18002fe56  mov     rdi, rax
0x18002fe59  ja      short loc_18002FE74
0x18002fe5b  mov     r8d, 63Fh; unsigned int
0x18002fe61  lea     rdx, aOnecoreDsNetap_15; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18002fe68  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18002fe6f  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18002fe74  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x18002fe7a  lea     r8, [rsp+1B0h+var_15A]; unsigned __int8 *
0x18002fe7f  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18002fe82  call    ?NlAllocateClientApi@@YAPEAU_CLIENT_API@@PEAU_CLIENT_SESSION@@KPEAE@Z; NlAllocateClientApi(_CLIENT_SESSION *,ulong,uchar *)
0x18002fe87  mov     [rbp+0B0h+var_120], rax
0x18002fe8b  test    rax, rax
0x18002fe8e  jnz     loc_18002FFF0
0x18002fe94  xorps   xmm0, xmm0
0x18002fe97  mov     [rbp+0B0h+var_68], rax
0x18002fe9b  lea     r8, aNlpuservalidat_11; "NlpUserValidateHigher: Can't allocate C"...
0x18002fea2  mov     [rsp+1B0h+var_150], rax
0x18002fea7  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18002feaa  mov     ecx, 100h; unsigned int
0x18002feaf  movups  xmmword ptr [rbp+0B0h+var_88], xmm0
0x18002feb3  movups  [rbp+0B0h+var_78], xmm0
0x18002feb7  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18002febc  lea     rcx, [r15+20h]; struct _UNICODE_STRING *
0x18002fec0  mov     byte ptr [r12], 1
0x18002fec5  lea     rdx, [rbp+0B0h+var_110]; struct _UNICODE_STRING *
0x18002fec9  mov     edi, 0C000005Eh
0x18002fece  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x18002fed3  lea     rdx, [rbp+0B0h+var_100]; struct _UNICODE_STRING *
0x18002fed7  mov     rcx, r15; struct _UNICODE_STRING *
0x18002feda  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x18002fedf  xor     r8d, r8d; unsigned int *
0x18002fee2  lea     rdx, [rsp+1B0h+var_150]; unsigned __int16 **
0x18002fee7  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18002feea  call    ?NlCaptureServerClientSession@@YAJPEAU_CLIENT_SESSION@@PEAPEAGPEAK@Z; NlCaptureServerClientSession(_CLIENT_SESSION *,ushort * *,ulong *)
0x18002feef  mov     r15, [rsp+1B0h+var_150]
0x18002fef4  test    r15, r15
0x18002fef7  jz      loc_18002FFE2
0x18002fefd  lea     rbx, [rsi+158h]
0x18002ff04  mov     rcx, rbx; CriticalSection
0x18002ff07  call    cs:__imp_RtlEnterCriticalSection
0x18002ff0d  mov     r14d, [rsi+188h]
0x18002ff14  test    r14d, r14d
0x18002ff17  jnz     short loc_18002FF25
0x18002ff19  mov     dword ptr [rsi+188h], 1
0x18002ff23  jmp     short loc_18002FF2B
0x18002ff25  inc     dword ptr [rsi+18Ch]
0x18002ff2b  mov     rcx, rbx; CriticalSection
0x18002ff2e  call    cs:__imp_RtlLeaveCriticalSection
0x18002ff34  test    r14d, r14d
0x18002ff37  jnz     loc_18002FFE2
0x18002ff3d  mov     rax, [rbp+0B0h+var_110.Buffer]
0x18002ff41  lea     rdx, aNull_0; "(null)"
0x18002ff48  test    rax, rax
0x18002ff4b  mov     qword ptr [rbp+0B0h+var_78], r15
0x18002ff4f  mov     rcx, rdx
0x18002ff52  lea     r8, aLu_0; "%lu"
0x18002ff59  cmovnz  rcx, rax
0x18002ff5d  mov     rax, [rbp+0B0h+var_100.Buffer]
0x18002ff61  test    rax, rax
0x18002ff64  mov     qword ptr [rbp+0B0h+var_88], rcx
0x18002ff68  mov     rcx, rdx
0x18002ff6b  cmovnz  rcx, rax
0x18002ff6f  mov     rax, [rsi+0B8h]
0x18002ff76  test    rax, rax
0x18002ff79  mov     qword ptr [rbp+0B0h+var_88+8], rcx
0x18002ff7d  lea     rcx, [rbp+0B0h+Buffer]; Buffer
0x18002ff81  cmovnz  rdx, rax
0x18002ff85  mov     eax, 88888889h
0x18002ff8a  mov     qword ptr [rbp+0B0h+var_78+8], rdx
0x18002ff8e  mul     cs:dword_1800F113C
0x18002ff94  shr     edx, 5
0x18002ff97  mov     r9d, edx
0x18002ff9a  lea     edx, [r14+14h]; BufferCount
0x18002ff9e  call    swprintf_s
0x18002ffa3  mov     [rsp+1B0h+var_178], r14d; unsigned int
0x18002ffa8  lea     rax, [rbp+0B0h+Buffer]
0x18002ffac  mov     [rbp+0B0h+var_68], rax
0x18002ffb0  lea     edx, [r14+1]; unsigned int
0x18002ffb4  lea     rax, [rbp+0B0h+var_88]
0x18002ffb8  mov     [rsp+1B0h+var_180], 0; unsigned __int8 *
0x18002ffc1  mov     [rsp+1B0h+var_188], 5; unsigned int
0x18002ffc9  or      r9d, 0FFFFFFFFh; unsigned int
0x18002ffcd  mov     ecx, 16B8h; unsigned int
0x18002ffd2  mov     [rsp+1B0h+var_190], rax; unsigned __int16 **
0x18002ffd7  mov     r8d, 20000000h; unsigned int
0x18002ffdd  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18002ffe2  mov     rcx, r15; Buffer
0x18002ffe5  call    cs:__imp_NetApiBufferFree
0x18002ffeb  jmp     loc_180030C24
0x18002fff0  call    cs:__imp_GetTickCount64
0x18002fff6  mov     r9, rax
0x18002fff9  mov     eax, cs:dword_1800F1140
0x18002ffff  test    eax, eax
0x180030001  jz      loc_1800301B3
0x180030007  imul    ecx, eax, 3E8h
0x18003000d  sub     r9, rdi
0x180030010  cmp     r9, rcx
0x180030013  jbe     loc_1800301B3
0x180030019  mov     rax, 624DD2F1A9FBE77h
0x180030023  mov     [rsp+1B0h+var_150], 0
0x18003002c  mul     r9
0x18003002f  lea     r8, aNlpuservalidat_3; "NlpUserValidateHigher: Warning Event: I"...
0x180030036  mov     ecx, 2; unsigned int
0x18003003b  sub     r9, rdx
0x18003003e  shr     r9, 1
0x180030041  add     r9, rdx
0x180030044  mov     rdx, rsi; struct _CLIENT_SESSION *
0x180030047  shr     r9, 9
0x18003004b  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180030050  lea     rcx, [r15+20h]; struct _UNICODE_STRING *
0x180030054  lea     rdx, [rbp+0B0h+var_110]; struct _UNICODE_STRING *
0x180030058  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x18003005d  lea     rdx, [rbp+0B0h+var_100]; struct _UNICODE_STRING *
0x180030061  mov     rcx, r15; struct _UNICODE_STRING *
0x180030064  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180030069  xor     r8d, r8d; unsigned int *
0x18003006c  lea     rdx, [rsp+1B0h+var_150]; unsigned __int16 **
0x180030071  mov     rcx, rsi; struct _CLIENT_SESSION *
0x180030074  call    ?NlCaptureServerClientSession@@YAJPEAU_CLIENT_SESSION@@PEAPEAGPEAK@Z; NlCaptureServerClientSession(_CLIENT_SESSION *,ushort * *,ulong *)
0x180030079  mov     r15, [rsp+1B0h+var_150]
0x18003007e  test    r15, r15
0x180030081  jz      loc_1800301AA
0x180030087  lea     rdi, [rsi+158h]
0x18003008e  mov     rcx, rdi; CriticalSection
0x180030091  call    cs:__imp_RtlEnterCriticalSection
0x180030097  mov     r14d, [rsi+190h]
0x18003009e  test    r14d, r14d
0x1800300a1  jnz     short loc_1800300AF
0x1800300a3  mov     dword ptr [rsi+190h], 1
0x1800300ad  jmp     short loc_1800300B5
0x1800300af  inc     dword ptr [rsi+194h]
0x1800300b5  mov     rcx, rdi; CriticalSection
0x1800300b8  call    cs:__imp_RtlLeaveCriticalSection
0x1800300be  test    r14d, r14d
0x1800300c1  jnz     loc_1800301A5
0x1800300c7  mov     r9d, cs:dword_1800F1140
0x1800300ce  lea     r8, aLu_0; "%lu"
0x1800300d5  xorps   xmm0, xmm0
0x1800300d8  lea     rcx, [rbp+0B0h+Buffer]; Buffer
0x1800300dc  mov     r14d, 14h
0x1800300e2  mov     edx, r14d; BufferCount
0x1800300e5  movups  xmmword ptr [rbp+0B0h+var_B8], xmm0
0x1800300e9  movups  [rbp+0B0h+var_A8], xmm0
0x1800300ed  movups  [rbp+0B0h+var_98], xmm0
0x1800300f1  call    swprintf_s
0x1800300f6  lea     rdx, aNull_0; "(null)"
0x1800300fd  mov     qword ptr [rbp+0B0h+var_A8+8], r15
0x180030101  mov     rcx, rdx
0x180030104  lea     rax, [rbp+0B0h+Buffer]
0x180030108  mov     [rbp+0B0h+var_B8], rax
0x18003010c  lea     r8, aLu_0; "%lu"
0x180030113  mov     rax, [rbp+0B0h+var_110.Buffer]
0x180030117  test    rax, rax
0x18003011a  cmovnz  rcx, rax
0x18003011e  mov     rax, [rbp+0B0h+var_100.Buffer]
0x180030122  test    rax, rax
0x180030125  mov     [rbp+0B0h+var_B8+8], rcx
0x180030129  mov     rcx, rdx
0x18003012c  cmovnz  rcx, rax
0x180030130  mov     rax, [rsi+0B8h]
0x180030137  test    rax, rax
0x18003013a  mov     qword ptr [rbp+0B0h+var_A8], rcx
0x18003013e  lea     rcx, [rbp+0B0h+var_88]; Buffer
0x180030142  cmovnz  rdx, rax
0x180030146  mov     eax, 88888889h
0x18003014b  mov     qword ptr [rbp+0B0h+var_98], rdx
0x18003014f  mul     cs:dword_1800F113C
0x180030155  shr     edx, 5
0x180030158  mov     r9d, edx
0x18003015b  mov     edx, r14d; BufferCount
0x18003015e  call    swprintf_s
0x180030163  mov     [rsp+1B0h+var_178], 0; unsigned int
0x18003016b  lea     rax, [rbp+0B0h+var_88]
0x18003016f  mov     qword ptr [rbp+0B0h+var_98+8], rax
0x180030173  lea     edx, [r14-12h]; unsigned int
0x180030177  lea     rax, [rbp+0B0h+var_B8]
0x18003017b  mov     [rsp+1B0h+var_180], 0; unsigned __int8 *
0x180030184  mov     [rsp+1B0h+var_188], 6; unsigned int
0x18003018c  or      r9d, 0FFFFFFFFh; unsigned int
0x180030190  mov     ecx, 16BAh; unsigned int
0x180030195  mov     [rsp+1B0h+var_190], rax; unsigned __int16 **
0x18003019a  mov     r8d, 20000000h; unsigned int
0x1800301a0  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x1800301a5  mov     r14d, [rsp+1B0h+var_158]
0x1800301aa  mov     rcx, r15; Buffer
0x1800301ad  call    cs:__imp_NetApiBufferFree
0x1800301b3  lea     rcx, [rbp+0B0h+PerformanceCount]; lpPerformanceCount
0x1800301b7  call    cs:__imp_QueryPerformanceCounter
0x1800301bd  test    eax, eax
0x1800301bf  jnz     short loc_1800301C9
0x1800301c1  mov     qword ptr [rbp+0B0h+PerformanceCount], 0
0x1800301c9  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x1800301cf  mov     rcx, rsi; struct _CLIENT_SESSION *
0x1800301d2  call    ?NlTimeoutSetWriterClientSession@@YAHPEAU_CLIENT_SESSION@@K@Z; NlTimeoutSetWriterClientSession(_CLIENT_SESSION *,ulong)
0x1800301d7  test    eax, eax
0x1800301d9  jnz     short loc_1800301FE
0x1800301db  lea     r8, aNlpuservalidat_5; "NlpUserValidateHigher: Can't become wri"...
0x1800301e2  mov     rdx, rsi; struct _CLIENT_SESSION *
0x1800301e5  mov     ecx, 100h; unsigned int
0x1800301ea  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800301ef  mov     byte ptr [r12], 1
0x1800301f4  mov     edi, 0C000005Eh
0x1800301f9  jmp     loc_180030C24
0x1800301fe  mov     r15d, [rbp+0B0h+arg_20]
0x180030205  mov     [rsp+1B0h+var_15B], 1
0x18003020a  mov     [rsp+1B0h+var_160], 1
0x18003020f  cmp     r14d, 4
0x180030213  jz      short loc_180030226
0x180030215  lea     eax, [r15-4]
0x180030219  cmp     eax, 1
0x18003021c  jbe     short loc_180030226
0x18003021e  xor     al, al
0x180030220  mov     [rsp+1B0h+var_15E], al
0x180030224  jmp     short loc_18003022B
0x180030226  mov     [rsp+1B0h+var_15E], 1
0x18003022b  cmp     r14d, 4
0x18003022f  jz      short loc_180030241
0x180030231  test    r14d, r14d
0x180030234  jle     short loc_180030241
0x180030236  mov     [rsp+1B0h+var_15C], 1
0x18003023b  cmp     r14d, 8
0x18003023f  jl      short loc_180030246
0x180030241  mov     [rsp+1B0h+var_15C], r13b
0x180030246  mov     r13b, [rsp+1B0h+var_15E]
0x18003024b  test    r13b, r13b
0x18003024e  jnz     short loc_180030264
0x180030250  cmp     [rsp+1B0h+var_15D], r13b
0x180030255  jnz     short loc_180030264
0x180030257  mov     rax, [rbp+0B0h+var_130]
0x18003025b  cmp     dword ptr [rax], 0
0x18003025e  jnz     short loc_180030264
0x180030260  xor     ecx, ecx
0x180030262  jmp     short loc_180030269
0x180030264  mov     ecx, 4
0x180030269  lea     eax, [r14-1]
0x18003026d  and     eax, 0FFFFFFFBh
0x180030270  neg     eax
0x180030272  sbb     edx, edx
0x180030274  not     edx
0x180030276  and     edx, 8
0x180030279  or      edx, ecx; unsigned int
0x18003027b  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18003027e  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x180030283  mov     edi, eax
0x180030285  test    eax, eax
0x180030287  js      loc_180030BA5
0x18003028d  mov     r9d, [rsi+13Ch]; unsigned int
0x180030294  lea     r10, [rsi+1B8h]
0x18003029b  movups  xmm0, xmmword ptr [r10]
0x18003029f  mov     eax, r9d
0x1800302a2  mov     [rbp+0B0h+var_D0], r9d
0x1800302a6  mov     r8d, 80000h
0x1800302ac  and     eax, r8d
0x1800302af  neg     eax
0x1800302b1  mov     rax, [rbp+0B0h+var_130]
0x1800302b5  sbb     ecx, ecx
0x1800302b7  and     ecx, 3
0x1800302ba  mov     edx, ecx
  ... truncated ...
```
