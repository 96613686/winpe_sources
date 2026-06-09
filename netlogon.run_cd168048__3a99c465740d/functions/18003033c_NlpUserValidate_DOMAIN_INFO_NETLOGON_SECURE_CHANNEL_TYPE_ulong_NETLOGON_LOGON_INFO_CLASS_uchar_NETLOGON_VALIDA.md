# NlpUserValidate(_DOMAIN_INFO *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,_NETLOGON_LOGON_INFO_CLASS,uchar *,_NETLOGON_VALIDATION_INFO_CLASS,uchar * *,uchar *,ulong *,uchar,ushort *,_UNICODE_STRING *,ulong,ulong,void *,_SERVER_SESSION *,_SECPKG_NTLM_TARGETINFO *,int)

- ea: `0x18003033c`
- end: `0x180031a35`
- name: `?NlpUserValidate@@YAJPEAU_DOMAIN_INFO@@W4_NETLOGON_SECURE_CHANNEL_TYPE@@KW4_NETLOGON_LOGON_INFO_CLASS@@PEAEW4_NETLOGON_VALIDATION_INFO_CLASS@@PEAPEAE3PEAKEPEAGPEAU_UNICODE_STRING@@KKPEAXPEAU_SERVER_SESSION@@PEAU_SECPKG_NTLM_TARGETINFO@@H@Z`
- size: `5881`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `loader_planting, service_task`

## callers

- `0x18002eed0`
- `0x18003033c`

## callees

- `0x1800055d4`
- `0x180007518`
- `0x18000c440`
- `0x18000dd00`
- `0x18000e0e0`
- `0x1800283ec`
- `0x180028448`
- `0x18002da78`
- `0x18002fbac`
- `0x18002fd9c`
- `0x18003033c`
- `0x180031a3c`
- `0x180032aa4`
- `0x180033598`
- `0x180033710`
- `0x18003ecf4`
- `0x18003ee6c`
- `0x180040f18`
- `0x1800548a0`
- `0x1800549a4`
- `0x180069a30`
- `0x18006ac28`
- `0x180071260`
- `0x1800714b0`
- `0x180071554`
- `0x1800719f4`
- `0x180089328`
- `0x18008a5c0`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031546`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031546`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031665`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031665`
- `LSASRV!LsaIFreeReturnBuffer` at `0x180030de5`
- `LSASRV!LsaIFreeReturnBuffer` at `0x180030de5`
- `LSASRV!LsaICallPackagePassthrough` at `0x180030d5f`
- `LSASRV!LsaICallPackagePassthrough` at `0x180030d5f`
- `LSASRV!LsaINoMoreWin2KDomain` at `0x1800319a1`
- `LSASRV!LsaINoMoreWin2KDomain` at `0x1800319a1`
- `ntdll!RtlEqualDomainName` at `0x1800304d4`
- `ntdll!RtlEqualDomainName` at `0x1800304d4`
- `ntdll!RtlLeaveCriticalSection` at `0x18003130c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800316b6`
- `ntdll!RtlLeaveCriticalSection` at `0x18003130c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800316b6`
- `ntdll!RtlEnterCriticalSection` at `0x1800312ef`
- `ntdll!RtlEnterCriticalSection` at `0x1800312ef`
- `ntdll!RtlInitUnicodeString` at `0x1800305fd`
- `ntdll!RtlInitUnicodeString` at `0x180030688`
- `ntdll!RtlInitUnicodeString` at `0x1800307a6`
- `ntdll!RtlInitUnicodeString` at `0x1800310a5`
- `ntdll!RtlInitUnicodeString` at `0x180031122`
- `ntdll!RtlInitUnicodeString` at `0x1800312ca`
- `ntdll!RtlInitUnicodeString` at `0x1800313d9`
- `ntdll!RtlInitUnicodeString` at `0x1800314b9`
- `ntdll!RtlInitUnicodeString` at `0x18003158a`
- `ntdll!RtlInitUnicodeString` at `0x1800305fd`
- `ntdll!RtlInitUnicodeString` at `0x180030688`
- `ntdll!RtlInitUnicodeString` at `0x1800307a6`
- `ntdll!RtlInitUnicodeString` at `0x1800310a5`
- `ntdll!RtlInitUnicodeString` at `0x180031122`
- `ntdll!RtlInitUnicodeString` at `0x1800312ca`
- `ntdll!RtlInitUnicodeString` at `0x1800313d9`
- `ntdll!RtlInitUnicodeString` at `0x1800314b9`
- `ntdll!RtlInitUnicodeString` at `0x18003158a`
- `netutils!NetApiBufferFree` at `0x18003188c`
- `netutils!NetApiBufferFree` at `0x1800318a4`
- `netutils!NetApiBufferFree` at `0x18003188c`
- `netutils!NetApiBufferFree` at `0x1800318a4`

## string_xrefs

- `0x180030822`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030843`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18003092f`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030950`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030d09`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030e90`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030eae`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030f40`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x180030f61`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18003169b`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18003179f`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x1800317c0`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18003184d`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`

## pseudocode

```c
__int64 __fastcall NlpUserValidate(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        enum _NETLOGON_LOGON_INFO_CLASS a4,
        PUNICODE_STRING DomainName1,
        unsigned int a6,
        void **a7,
        unsigned __int8 *a8,
        int *a9,
        char a10,
        const WCHAR *SourceString,
        struct _UNICODE_STRING *a12,
        unsigned int a13,
        unsigned int a14,
        void *a15,
        struct _SERVER_SESSION *a16,
        struct _SECPKG_NTLM_TARGETINFO *a17,
        int a18)
{
  __int64 v18; // r8
  int v19; // edx
  enum _NETLOGON_LOGON_INFO_CLASS v20; // r10d
  int v21; // esi
  __int64 v22; // r13
  bool v23; // zf
  int v24; // r12d
  char v25; // r14
  __int32 v26; // eax
  __int64 v27; // r9
  char v28; // cl
  bool v29; // r15
  char v30; // di
  unsigned __int8 *v31; // r12
  int v32; // ebx
  struct _UNICODE_STRING *v33; // r15
  char v34; // si
  char v35; // r13
  char v36; // si
  struct _NETLOGON_TICKET_LOGON_INFO *v37; // rax
  unsigned int v38; // edx
  int v39; // ecx
  unsigned int v40; // eax
  unsigned int v41; // ebx
  unsigned __int8 *v42; // rdi
  struct _CLIENT_SESSION *v43; // r14
  void **v44; // rdi
  struct _NETLOGON_VALIDATION_TICKET_LOGON **v45; // r14
  unsigned int v46; // eax
  __int64 v47; // rcx
  int v48; // eax
  char *v49; // r9
  int v50; // edi
  int v51; // eax
  int v52; // eax
  char v53; // cl
  char v54; // al
  unsigned __int8 *v55; // rsi
  unsigned __int8 v56; // r14
  int v57; // eax
  int v58; // eax
  int v59; // edi
  __int64 v60; // r9
  PWSTR Buffer; // r8
  _QWORD *v62; // rdi
  unsigned int v63; // eax
  struct _CLIENT_SESSION *v64; // rax
  int v65; // edi
  struct _CLIENT_SESSION *v66; // rax
  char v67; // di
  unsigned int v68; // ecx
  struct _RTL_CRITICAL_SECTION *v69; // rcx
  struct _CLIENT_SESSION *NamedClientSession; // rax
  int v71; // esi
  USHORT Length; // ax
  SIZE_T v73; // rbx
  struct _UNICODE_STRING *v74; // rax
  struct _UNICODE_STRING *v75; // rdi
  struct _UNICODE_STRING *v76; // rbx
  struct _UNICODE_STRING v77; // xmm0
  int v78; // eax
  void *v79; // rdi
  const UNICODE_STRING *v80; // rcx
  char v81; // di
  struct _NETLOGON_VALIDATION_TICKET_LOGON *v82; // rdi
  int v83; // esi
  int v84; // eax
  int v85; // eax
  int v87; // [rsp+30h] [rbp-E8h]
  int v88; // [rsp+38h] [rbp-E0h]
  int v89; // [rsp+50h] [rbp-C8h]
  unsigned __int8 v90; // [rsp+98h] [rbp-80h] BYREF
  char v91; // [rsp+99h] [rbp-7Fh]
  _WORD v92[5]; // [rsp+9Ah] [rbp-7Eh] BYREF
  int v93; // [rsp+A4h] [rbp-74h] BYREF
  char v94; // [rsp+A8h] [rbp-70h]
  unsigned int v95; // [rsp+ACh] [rbp-6Ch] BYREF
  bool v96; // [rsp+B0h] [rbp-68h]
  HLOCAL hMem; // [rsp+B8h] [rbp-60h] BYREF
  PCWSTR v98; // [rsp+C0h] [rbp-58h] BYREF
  size_t Size; // [rsp+C8h] [rbp-50h] BYREF
  void *Src; // [rsp+D0h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-40h] BYREF
  PCWSTR v102; // [rsp+E8h] [rbp-30h] BYREF
  struct _NETLOGON_LOGON_IDENTITY_INFO *v103; // [rsp+F0h] [rbp-28h]
  struct _UNICODE_STRING v104; // [rsp+F8h] [rbp-20h] BYREF
  struct _UNICODE_STRING v105; // [rsp+108h] [rbp-10h] BYREF
  struct _UNICODE_STRING v106; // [rsp+118h] [rbp+0h] BYREF
  struct _UNICODE_STRING v107; // [rsp+128h] [rbp+10h] BYREF
  char v112; // [rsp+1C8h] [rbp+B0h]

  v18 = a2;
  v19 = 3;
  v92[0] = 0;
  v20 = a4;
  *(_DWORD *)&v92[3] = 3;
  v21 = *a9;
  v22 = a1;
  v23 = (*a9 & 2) == 0;
  v24 = *a9 & 2;
  v102 = 0;
  v98 = 0;
  v96 = !v23;
  v95 = 0;
  if ( (v21 & 4) == 0 || (v25 = 1, NlGlobalCDC) )
    v25 = 0;
  if ( (v21 & 8) == 0 || (LOBYTE(v92[1]) = 1, NlGlobalCDC) )
    LOBYTE(v92[1]) = 0;
  v26 = a4 - 2;
  v27 = 4294967291LL;
  if ( (v26 & 0xFFFFFFFB) != 0 )
  {
    v112 = 0;
  }
  else
  {
    v112 = 1;
    if ( v20 == NetlogonNetworkTransitiveInformation )
    {
LABEL_11:
      v28 = 1;
      goto LABEL_12;
    }
  }
  v28 = 0;
  if ( ((v20 - 5) & 0xFFFFFFFD) == 0 )
    goto LABEL_11;
LABEL_12:
  v29 = (unsigned int)(v20 - 1) <= 2;
  if ( v28 || (v30 = 0, (unsigned int)(v20 - 1) <= 2) )
    v30 = 1;
  v91 = v30;
  v94 = 0;
  if ( v30 || ((v20 - 4) & 0xFFFFFFFB) == 0 )
  {
    v103 = (struct _NETLOGON_LOGON_IDENTITY_INFO *)DomainName1;
    *a8 = 0;
    if ( v20 == 8 && !DomainName1->Length )
    {
      NlPrintRoutine(
        0x100u,
        L"LogonDomainName is mandatory for Kerberos network ticket logon; the unencrypted part of the ticket always provid"
         "es the fully qualified name of the issuing realm.",
        v18);
      v31 = a8;
      v32 = -1073741811;
      v33 = DomainName1;
      *a8 = 1;
LABEL_21:
      v34 = v112;
LABEL_84:
      v18 = a2;
LABEL_85:
      v20 = a4;
LABEL_86:
      v19 = *(_DWORD *)&v92[3];
      goto LABEL_87;
    }
    hMem = 0;
    v93 = v21 & 0x1000;
    v32 = -1073741724;
    v35 = 0;
    v36 = v21 & 1;
    LOBYTE(v27) = RtlEqualDomainName(DomainName1, (PUNICODE_STRING)(a1 + 168))
               || *(_DWORD *)(a1 + 588) != 3
               && (unsigned int)NlEqualDnsNameU(DomainName1, (struct _UNICODE_STRING *)(a1 + 128));
    v18 = a2;
    LOBYTE(v92[0]) = v27;
    if ( a2 - 6 > 1 )
    {
      v25 = 0;
      LOBYTE(v92[1]) = 0;
    }
    v37 = (struct _NETLOGON_TICKET_LOGON_INFO *)DomainName1;
    if ( NlGlobalMemberWorkstation )
    {
      if ( !DomainName1->Length )
      {
        v38 = DomainName1[2].Length >> 1;
        if ( v38 )
        {
          v39 = 0;
          while ( DomainName1[2].Buffer[v39] != 64 )
          {
            if ( ++v39 >= v38 )
              goto LABEL_37;
          }
          v35 = 1;
LABEL_37:
          v18 = a2;
          v37 = (struct _NETLOGON_TICKET_LOGON_INFO *)DomainName1;
        }
      }
    }
    if ( v36 || v25 )
    {
LABEL_191:
      if ( (_BYTE)v27 && DomainName1->Length && !v36 && !v25 )
      {
        v43 = (struct _CLIENT_SESSION *)hMem;
        v33 = DomainName1;
        goto LABEL_302;
      }
      v18 = a2;
LABEL_196:
      if ( NlGlobalMemberWorkstation )
      {
        if ( v36 )
          NlAssertFailed(
            "!ExpediteToRoot",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            0x109Bu,
            (char *)v27);
        if ( v24 )
          NlAssertFailed(
            "!CrossForestHop",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            0x109Cu,
            (char *)v27);
        v64 = NlRefDomClientSession((struct _DOMAIN_INFO *)a1);
        v31 = a8;
        v33 = DomainName1;
        v43 = v64;
        if ( !v64 )
        {
          *a8 = 0;
          goto LABEL_74;
        }
        v65 = NlpUserValidateHigher((__int64)v64, 0, a4, (__int64)DomainName1, a6, a7, a8, &v95);
        NlUnrefClientSession(v43);
        v43 = 0;
        if ( v65 < 0 )
        {
          if ( v65 == -1073741429 || v65 == -1073741790 )
            v65 = -1073741427;
        }
        else
        {
          if ( v65 )
            NlAssertFailed(
              "!NT_SUCCESS(Status) || Status == STATUS_SUCCESS",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
              0x10B3u,
              (char *)v27);
          if ( !*a7 )
            NlAssertFailed(
              "!NT_SUCCESS(Status) || *ValidationInformation != NULL",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
              0x10B4u,
              (char *)v27);
        }
        if ( *a8 )
        {
          if ( v65 == -1073741730 )
          {
            if ( !v91 || DomainName1->Length || v35 != 1 )
            {
              v34 = v112;
              if ( !v112 || NlIsDomainTrusted(DomainName1) )
              {
                v22 = a1;
                v32 = -1073741730;
                goto LABEL_84;
              }
              v22 = a1;
              *a8 = 0;
              goto LABEL_76;
            }
            v22 = a1;
            v32 = -1073741730;
LABEL_217:
            v34 = v112;
            goto LABEL_84;
          }
          v22 = a1;
          v32 = v65;
          v44 = a7;
          goto LABEL_223;
        }
        if ( v65 != -1073741724 )
          v32 = v65;
LABEL_303:
        if ( *v31 )
          NlAssertFailed(
            "! *Authoritative",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            0x132Du,
            (char *)v27);
        goto LABEL_74;
      }
      v90 = 0;
      if ( NlGlobalCDC )
      {
        LODWORD(hMem) = 4;
        if ( (_DWORD)v18 == 1 )
          LODWORD(hMem) = 12;
        v22 = a1;
        v43 = NlRefDomClientSession((struct _DOMAIN_INFO *)a1);
        if ( !v43 )
        {
          v33 = DomainName1;
          v32 = -1073741602;
          v31 = a8;
          goto LABEL_217;
        }
        if ( (dword_1800F81BC & 4) == 0 || a2 != 2 || !v91 || v93 )
        {
          if ( (dword_1800F81C0 & 4) != 0 && a2 == 2 && v91 && !v93 )
          {
            v105 = 0;
            RtlInitUnicodeString(&v105, SourceString);
            v33 = DomainName1;
            NlpLogNTLMDCBlocked(&v105, DomainName1 + 2, DomainName1, DomainName1 + 3, 2u, 0x1F45u);
          }
          else
          {
            v33 = DomainName1;
          }
          v31 = a8;
          v44 = a7;
          v34 = v112;
          v32 = NlpUserValidateHigher((__int64)v43, 0, a4, (__int64)v33, a6, a7, a8, (unsigned int *)&hMem);
LABEL_77:
          if ( v32 >= 0 )
          {
            if ( v32 )
              NlAssertFailed(
                "!NT_SUCCESS(DefaultStatus) || DefaultStatus == STATUS_SUCCESS",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                0x1330u,
                (char *)v27);
            if ( !*v44 )
              NlAssertFailed(
                "!NT_SUCCESS(DefaultStatus) || *ValidationInformation != NULL",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                0x1331u,
                (char *)v27);
          }
LABEL_82:
          if ( !v43 )
            goto LABEL_84;
LABEL_83:
          NlUnrefClientSession(v43);
          goto LABEL_84;
        }
        v105 = 0;
        RtlInitUnicodeString(&v105, SourceString);
        v33 = DomainName1;
        NlpLogNTLMDCBlocked(&v105, DomainName1 + 2, DomainName1, DomainName1 + 3, 2u, 0xFA5u);
        v31 = a8;
        v32 = -1073740776;
        *a8 = 1;
LABEL_236:
        v34 = v112;
        goto LABEL_83;
      }
      if ( (unsigned int)(v18 - 3) <= 1 && v29 )
      {
        v33 = DomainName1;
        v32 = -1073741724;
        v31 = a8;
        v22 = a1;
        v34 = v112;
        goto LABEL_85;
      }
      v22 = a1;
      if ( v36 )
      {
        if ( (*(_DWORD *)(a1 + 592) & 0x10000) == 0 )
        {
          v43 = NlRefDomParentClientSession((struct _DOMAIN_INFO *)a1);
          if ( !v43 )
          {
            NlPrintDomRoutine(
              4u,
              (struct _DOMAIN_INFO *)a1,
              L"NlpUserValidate: Can't find parent domain in forest '%wZ'\n",
              &NlGlobalUnicodeDnsForestNameString);
            v33 = DomainName1;
LABEL_251:
            v31 = a8;
            v32 = -1073741724;
            goto LABEL_21;
          }
          v95 |= 1u;
          v33 = DomainName1;
          LODWORD(v18) = a2;
LABEL_257:
          v67 = v91;
          if ( !v91 && a4 != 8 )
          {
            if ( v43 )
              goto LABEL_260;
LABEL_302:
            v31 = a8;
            goto LABEL_303;
          }
          if ( v43 )
            goto LABEL_260;
          if ( (unsigned int)(v18 - 3) <= 1 && !v36 && !v24 )
            goto LABEL_302;
          if ( a10 )
            goto LABEL_302;
          LOBYTE(v88) = v96;
          LOBYTE(v87) = v36;
          if ( (int)NlPickDomainWithAccount(a1, &v33[2], v33, 16, v18, v87, v88, &v102, &v98, &v95) < 0 )
            goto LABEL_302;
          if ( (v95 & 2) != 0 )
          {
            v104 = 0;
            RtlInitUnicodeString(&v104, v98);
            NamedClientSession = NlFindNamedClientSession((struct _DOMAIN_INFO *)a1, &v104, 1u, &v90);
            v43 = NamedClientSession;
            if ( !NamedClientSession )
            {
              NlPrintDomRoutine(
                0x100u,
                (struct _DOMAIN_INFO *)a1,
                L"NlpUserValidate: %wZ\\%wZ: Can't find trusted forest '%wZ'\n",
                v33,
                &v33[2],
                &v104);
              goto LABEL_251;
            }
            if ( (*((_BYTE *)NamedClientSession + 296) & 8) == 0 )
            {
              NlPrintCsRoutine(
                0x100u,
                NamedClientSession,
                L"NlpUserValidate: %wZ\\%wZ: trusted forest '%wZ' doesn't have F bit set.\n",
                v33,
                &v33[2],
                &v104);
LABEL_274:
              v31 = a8;
              v32 = -1073741724;
              goto LABEL_236;
            }
            if ( (*((_DWORD *)NamedClientSession + 73) & 0x4000) != 0 )
            {
              NlPrintCsRoutine(
                0x100u,
                NamedClientSession,
                L"NlpUserValidate: %wZ\\%wZ: trusted forest '%wZ' is in my forest\n",
                v33,
                &v33[2],
                &v104);
              goto LABEL_274;
            }
            v67 = v91;
LABEL_260:
            v107 = 0;
            RtlInitUnicodeString(&v107, SourceString);
            v68 = a2;
            if ( a2 - 3 <= 1 )
            {
              RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 400));
              v69 = (struct _RTL_CRITICAL_SECTION *)(a1 + 400);
              if ( (*((_BYTE *)v43 + 292) & 4) == 0 )
              {
                RtlLeaveCriticalSection(v69);
                NlPrintCsRoutine(4u, v43, L"SamLogon: Avoid transitive trust on NT 4 trust.");
                v31 = a8;
                v32 = -1073741724;
LABEL_263:
                v34 = v112;
                goto LABEL_82;
              }
              RtlLeaveCriticalSection(v69);
              v68 = a2;
            }
            if ( (dword_1800F81BC & 4) != 0 && v68 == 2 && v67 && !v93 )
            {
              NlpLogNTLMDCBlocked(&v107, v33 + 2, v33, v33 + 3, 2u, 0xFA5u);
              v31 = a8;
              v32 = -1073740776;
              *a8 = 1;
              goto LABEL_263;
            }
            if ( (dword_1800F81C0 & 4) != 0 && v68 == 2 && v67 && !v93 )
              NlpLogNTLMDCBlocked(&v107, v33 + 2, v33, v33 + 3, 2u, 0x1F45u);
            v31 = a8;
            v44 = a7;
            v78 = NlpUserValidateHigher((__int64)v43, v90, a4, (__int64)v33, a6, a7, a8, &v95);
            v32 = v78;
            if ( v78 < 0 )
            {
              if ( (unsigned int)(v78 + 1073741430) <= 1 || v78 == -1073741790 )
              {
                v32 = -1073741428;
                goto LABEL_223;
              }
            }
            else
            {
              if ( v78 )
                NlAssertFailed(
                  "!NT_SUCCESS(Status) || Status == STATUS_SUCCESS",
                  "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                  0x12FFu,
                  (char *)v27);
              if ( !*a7 )
              {
                NlAssertFailed(
                  "!NT_SUCCESS(Status) || *ValidationInformation != NULL",
                  "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                  0x1300u,
                  (char *)v27);
LABEL_223:
                v34 = v112;
                goto LABEL_77;
              }
            }
            if ( v32 == -1073741724 )
              *a8 = 1;
            goto LABEL_223;
          }
          if ( !v102 || !v98 || (v95 & 1) != 0 )
          {
            v75 = 0;
            v76 = v33;
            goto LABEL_298;
          }
          v106 = 0;
          v71 = 0;
          RtlInitUnicodeString(&v106, v102);
          v20 = a4;
          if ( a4 == NetlogonInteractiveInformation )
            goto LABEL_293;
          if ( a4 != NetlogonNetworkInformation )
          {
            switch ( a4 )
            {
              case NetlogonServiceInformation:
                goto LABEL_293;
              case NetlogonGenericInformation:
LABEL_289:
                v31 = a8;
                v18 = a2;
                v32 = -1073741811;
                v34 = v112;
                *a8 = 0;
                goto LABEL_86;
              case NetlogonInteractiveTransitiveInformation:
                goto LABEL_293;
            }
            if ( a4 != NetlogonNetworkTransitiveInformation )
            {
              if ( a4 != NetlogonServiceTransitiveInformation )
                goto LABEL_289;
LABEL_293:
              v73 = 96;
LABEL_294:
              v74 = (struct _UNICODE_STRING *)LocalAlloc(0, v73);
              v75 = v74;
              if ( !v74 )
              {
                v31 = a8;
                v32 = -1073741670;
                *a8 = 0;
                goto LABEL_217;
              }
              memcpy_0(v74, v33, v73);
              v76 = v75;
              RtlInitUnicodeString(v75, v98);
              v77 = v106;
              *(_DWORD *)&v75[1].Length |= v71;
              v75[2] = v77;
LABEL_298:
              v31 = a8;
              LOBYTE(v89) = 1;
              v32 = NlpUserValidate(
                      a1,
                      a2,
                      a3,
                      (unsigned int)a4,
                      v76,
                      a6,
                      a7,
                      a8,
                      &v95,
                      v89,
                      SourceString,
                      a12,
                      a13,
                      a14,
                      a15,
                      a16,
                      a17,
                      a18);
              if ( v75 )
                LocalFree(v75);
              *(_DWORD *)&v92[3] = 0;
              goto LABEL_75;
            }
          }
          Length = v33->Length;
          if ( !v33->Length )
            v106 = v33[2];
          v73 = 104;
          v71 = Length == 0 ? 0x8000 : 0;
          goto LABEL_294;
        }
        v33 = DomainName1;
      }
      else
      {
        v33 = DomainName1;
        if ( DomainName1->Length )
        {
          v66 = NlFindNamedClientSession((struct _DOMAIN_INFO *)a1, DomainName1, v24 != 0 ? 10 : 2, &v90);
          LODWORD(v18) = a2;
          v43 = v66;
          goto LABEL_257;
        }
      }
      v43 = (struct _CLIENT_SESSION *)hMem;
      goto LABEL_257;
    }
    if ( (*(_WORD *)v37 || v24) && !(_BYTE)v27 )
    {
      if ( (unsigned int)(v18 - 6) > 1 )
        goto LABEL_196;
      v37 = (struct _NETLOGON_TICKET_LOGON_INFO *)DomainName1;
    }
    if ( v91 )
    {
      *(_DWORD *)&v92[3] = 2;
      if ( v35 )
        goto LABEL_64;
      v94 = 1;
      if ( (dword_1800F81BC & 1) != 0 && (_DWORD)v18 == 2 && !v93
        || (dword_1800F81BC & 2) != 0 && (unsigned int)(v18 - 3) <= 1 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, SourceString);
        v40 = 4004;
        v33 = DomainName1;
        if ( a2 != 2 )
          v40 = 4006;
        NlpLogNTLMDCBlocked(&DestinationString, DomainName1 + 2, DomainName1, DomainName1 + 3, a2, v40);
        v31 = a8;
        v32 = -1073740776;
        *a8 = 1;
        goto LABEL_55;
      }
      if ( (dword_1800F81C0 & 1) != 0 && (_DWORD)v18 == 2 && !v93 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, SourceString);
        NlpLogNTLMDCBlocked(&DestinationString, DomainName1 + 2, DomainName1, DomainName1 + 3, 2u, 0x1F44u);
      }
      else if ( (dword_1800F81C0 & 2) != 0 && (unsigned int)(v18 - 3) <= 1 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, SourceString);
        v41 = a2;
        NlpLogNTLMDCBlocked(&DestinationString, DomainName1 + 2, DomainName1, DomainName1 + 3, a2, 0x1F46u);
        goto LABEL_61;
      }
      v41 = a2;
LABEL_61:
      v32 = NlpSamValidate(
              *(_QWORD *)(a1 + 376),
              a1,
              v41,
              a1 + 256,
              a1 + 168,
              *(_QWORD *)(a1 + 184),
              a4,
              DomainName1,
              a6,
              a7,
              a8,
              (char *)v92 + 1,
              1);
      if ( HIBYTE(v92[0]) )
        NlpZeroBadPasswordCountOnPdc((struct _DOMAIN_INFO *)a1, a4, (unsigned __int8 *)DomainName1);
      LOBYTE(v27) = v92[0];
LABEL_64:
      if ( (_BYTE)v27 && v32 == -1073741724 || v32 == -1073740943 )
      {
        v42 = a8;
        *a8 = 1;
      }
      else
      {
        v42 = a8;
      }
      if ( a2 == 6 )
      {
        v33 = DomainName1;
        v43 = (struct _CLIENT_SESSION *)hMem;
        v31 = a8;
LABEL_74:
        v22 = a1;
LABEL_75:
        v34 = v112;
LABEL_76:
        v44 = a7;
        goto LABEL_77;
      }
LABEL_129:
      if ( *v42 )
      {
        if ( a4 == 8 && *a7 )
        {
          v53 = *((_BYTE *)*a7 + 4) & 1;
          if ( *((_DWORD *)*a7 + 2) == -1073740943 )
          {
            v54 = 1;
LABEL_136:
            if ( !v53
              && !v54
              && v32 != -1073741718
              && v32 != -1073741711
              && v32 != -1073741276
              && v32 != -1073741260
              && v32 != -1073740943 )
            {
              v33 = DomainName1;
              v22 = a1;
LABEL_170:
              NlpRemoveBadPasswordCacheEntry((struct _DOMAIN_INFO *)v22, (unsigned __int8 *)v33);
              v43 = (struct _CLIENT_SESSION *)hMem;
              v31 = a8;
              goto LABEL_75;
            }
            v55 = (unsigned __int8 *)*a7;
            v90 = 0;
            if ( v32 == -1073740943 )
            {
              v56 = 1;
            }
            else
            {
              v56 = 0;
              if ( !v54 )
              {
                v57 = 0;
                goto LABEL_148;
              }
            }
            v57 = 1;
LABEL_148:
            v33 = DomainName1;
            v22 = a1;
            v58 = NlpUserValidateOnDc(a1, (unsigned int)a4, DomainName1, a6, 1, v57, a7, &v90);
            v59 = v58;
            if ( v56 || v58 >= 0 || v58 == -1073741718 || v58 == -1073741711 || v58 == -1073741276 || v58 == -1073741260 )
            {
              v32 = v58;
              *a8 = v90;
              if ( v55 != *a7 )
                FreeValidationInformation(v55, a6);
              if ( (v59 >= 0 || v59 == -1073741711 || v59 == -1073741276) && a4 != 8 && !NlGlobalMemberWorkstation )
                NlpZeroBadPasswordCountLocally((struct _DOMAIN_INFO *)a1, DomainName1 + 2, v56);
            }
            else if ( v55 != *a7 )
            {
              FreeValidationInformation((unsigned __int8 *)*a7, a6);
              *a7 = v55;
            }
            if ( v32 == -1073741718 )
            {
              v43 = (struct _CLIENT_SESSION *)hMem;
              v31 = a8;
              goto LABEL_75;
            }
            if ( v32 == -1073741711 || v32 == -1073741276 || v32 == -1073741260 )
            {
              v43 = (struct _CLIENT_SESSION *)hMem;
              v34 = v112;
              v31 = a8;
              goto LABEL_76;
            }
            goto LABEL_170;
          }
        }
        else
        {
          v53 = 0;
        }
        v54 = 0;
        goto LABEL_136;
      }
      goto LABEL_191;
    }
    if ( a4 == 8 )
    {
      v42 = a8;
      v52 = PerformKerberosTicketLogon(v37, (struct _NETLOGON_VALIDATION_TICKET_LOGON **)a7, a8);
      v32 = v52;
      if ( v52 < 0 )
      {
        NlPrintRoutine(4u, L"Kerberos ticket logon failed with 0x%08X", (unsigned int)v52);
        v33 = DomainName1;
        v31 = a8;
LABEL_55:
        v22 = a1;
        goto LABEL_21;
      }
      LOBYTE(v27) = v92[0];
      goto LABEL_129;
    }
    if ( a4 != NetlogonGenericInformation )
      NlAssertFailed(
        "GenericPassthrough",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
        0xFD4u,
        (char *)v27);
    v33 = DomainName1;
    Size = 0;
    v60 = *(unsigned int *)&DomainName1[5].Length;
    Buffer = DomainName1[5].Buffer;
    v93 = 0;
    Src = 0;
    v31 = a8;
    v32 = LsaICallPackagePassthrough(&DomainName1[4], 0, Buffer, v60, &Src, &Size, &v93);
    if ( v32 >= 0 )
      v32 = v93;
    *a8 = 1;
    if ( v32 < 0 )
    {
      if ( NlGlobalCDC )
      {
        v22 = a1;
        if ( v32 == -1073740943 )
        {
          v32 = NlpUserValidateOnDc(a1, (unsigned int)a4, DomainName1, a6, 0, 1, a7, a8);
          *a8 = 1;
        }
        goto LABEL_187;
      }
    }
    else
    {
      v62 = MIDL_user_allocate((unsigned int)(Size + 16));
      if ( v62 )
      {
        v63 = Size;
        if ( (_DWORD)Size && Src )
        {
          *(_DWORD *)v62 = Size;
          v62[1] = v62 + 2;
          memcpy_0(v62 + 2, Src, v63);
        }
        else
        {
          *(_DWORD *)v62 = 0;
          v62[1] = 0;
        }
        *a7 = v62;
      }
      else
      {
        v32 = -1073741670;
      }
      if ( Src )
        LsaIFreeReturnBuffer();
    }
    v22 = a1;
LABEL_187:
    v43 = (struct _CLIENT_SESSION *)hMem;
    goto LABEL_75;
  }
  v31 = a8;
  v32 = -1073741821;
  v33 = DomainName1;
  v34 = v112;
  v103 = 0;
  *a8 = 1;
LABEL_87:
  if ( v34 && ((_DWORD)v18 == 1 || LOBYTE(v92[1])) )
  {
    if ( v32 != -1073741724 && v32 != -1073741710 )
      v19 &= ~2u;
    v45 = (struct _NETLOGON_VALIDATION_TICKET_LOGON **)a7;
    v46 = v19 & 0xFFFFFFFE;
    if ( !*v31 )
      v46 = v19;
    if ( v46 )
    {
      v47 = *(_QWORD *)(v22 + 376);
      v90 = 0;
      v48 = NlpSamValidate(
              v47,
              v22 + 168,
              v18,
              v22 + 256,
              v22 + 168,
              *(_QWORD *)(v22 + 184),
              v20,
              v33,
              a6,
              a7,
              &v90,
              (char *)v92 + 1,
              v46);
      v50 = v48;
      if ( v48 >= 0 )
      {
        if ( v48 )
          NlAssertFailed(
            "!NT_SUCCESS(Status) || Status == STATUS_SUCCESS",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            0x1379u,
            v49);
        if ( !*a7 )
          NlAssertFailed(
            "!NT_SUCCESS(Status) || *ValidationInformation != NULL",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            0x137Au,
            v49);
      }
      if ( HIBYTE(v92[0]) )
        NlpZeroBadPasswordCountOnPdc((struct _DOMAIN_INFO *)v22, a4, (unsigned __int8 *)v33);
      if ( v90 )
      {
        *v31 = 1;
        v32 = v50;
        if ( v50 != -1073741718 && v50 != -1073741711 && v50 != -1073741276 && v50 != -1073741260 && v50 != -1073740943 )
          goto LABEL_124;
        v51 = NlpUserValidateOnDc(v22, (unsigned int)a4, v33, a6, 1, v50 == -1073740943, a7, &v90);
        if ( v50 == -1073740943
          || v51 >= 0
          || v51 == -1073741718
          || v51 == -1073741711
          || v51 == -1073741276
          || v51 == -1073741260 )
        {
          v32 = v51;
          *v31 = v90;
          if ( (v51 >= 0 || v51 == -1073741711 || v51 == -1073741276) && !NlGlobalMemberWorkstation )
            NlpZeroBadPasswordCountLocally((struct _DOMAIN_INFO *)v22, &v103->UserName, v50 == -1073740943);
        }
        if ( v32 != -1073741718 && v32 != -1073741711 && v32 != -1073741276 && v32 != -1073741260 )
LABEL_124:
          NlpRemoveBadPasswordCacheEntry((struct _DOMAIN_INFO *)v22, (unsigned __int8 *)v33);
      }
      else if ( v32 == -1073741724 )
      {
        v32 = v50;
      }
    }
  }
  else
  {
    v45 = (struct _NETLOGON_VALIDATION_TICKET_LOGON **)a7;
    if ( v20 == 8 && v32 < 0 )
    {
      v79 = *a7;
      if ( *a7 )
      {
        if ( (*(_BYTE *)v79 & 1) == 0 )
          NlAssertFailed(
            "TicketValidationInfo->LogonFailed == TRUE",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            0x13D2u,
            (char *)v27);
        v80 = (const UNICODE_STRING *)NlGlobalDomainInfo;
        *(_BYTE *)v79 |= 1u;
        *((_DWORD *)v79 + 3) = v32;
        NlpCopyUnicodeString(v80 + 17, (PUNICODE_STRING)v79 + 1);
        v32 = 0;
      }
    }
  }
  if ( v102 )
    NetApiBufferFree((LPVOID)v102);
  if ( v98 )
    NetApiBufferFree((LPVOID)v98);
  if ( !a10 )
  {
    if ( v32 >= 0 )
    {
      if ( a6 == 3 || (v81 = 0, a6 == 6) )
        v81 = 1;
      if ( a4 == 8 )
      {
        v82 = *v45;
        v83 = TransformKerberosTicketLogonOutbound(
                (struct _NETLOGON_TICKET_LOGON_INFO *)v33,
                *v45,
                (struct _DOMAIN_INFO *)v22,
                v31,
                a2 - 1 <= 1,
                v92[0],
                a3,
                a12,
                a13,
                a14,
                a15);
        if ( v83 < 0 )
        {
          FreeTicketValidationInformation(v82);
          v32 = v83;
          *v45 = 0;
        }
      }
      else if ( a2 - 1 <= 1 && v91 && !NlGlobalMemberWorkstation )
      {
        if ( v81 )
        {
          v84 = NlpExpandResourceGroupMembership(a6, v45, v22);
          if ( v84 < 0 )
            v32 = v84;
        }
        if ( a3 )
        {
          if ( (unsigned __int8)LsaINoMoreWin2KDomain() )
          {
            v85 = NlpVerifyAllowedToAuthenticate((struct _DOMAIN_INFO *)v22, a3, *v45, 0, 0, 0, v81 ^ 1u);
            if ( v85 < 0 )
              v32 = v85;
          }
        }
      }
    }
    if ( v112 && v94 && a16 && *((_DWORD *)a16 + 8) != 2 )
      NlpNtlmlessLogAccountDomain(v103, a16, a17, a18, v32);
  }
  return (unsigned int)v32;
}

```

## disassembly

```asm
0x18003033c  mov     rax, rsp
0x18003033f  mov     [rax+20h], r9d
0x180030343  mov     [rax+18h], r8d
0x180030347  mov     [rax+10h], edx
0x18003034a  mov     [rax+8], rcx
0x18003034e  push    rbp
0x18003034f  push    rbx
0x180030350  push    rsi
0x180030351  push    rdi
0x180030352  push    r12
0x180030354  push    r13
0x180030356  push    r14
0x180030358  push    r15
0x18003035a  lea     rbp, [rax-68h]
0x18003035e  sub     rsp, 138h
0x180030365  mov     rax, [rbp+60h+arg_40]
0x18003036c  xor     r11d, r11d
0x18003036f  mov     r8d, edx
0x180030372  mov     [rbp+60h+var_DE+1], r11b
0x180030376  mov     edx, 3
0x18003037b  mov     [rbp+60h+var_DE], r11b
0x18003037f  mov     r10d, r9d
0x180030382  mov     dword ptr [rbp+60h+var_DE+6], edx
0x180030385  mov     esi, [rax]
0x180030387  mov     r13, rcx
0x18003038a  mov     eax, cs:?NlGlobalCDC@@3HA; int NlGlobalCDC
0x180030390  mov     r12d, esi
0x180030393  and     r12d, 2
0x180030397  mov     [rbp+60h+var_90], r11
0x18003039b  mov     [rbp+60h+var_B8], r11
0x18003039f  setnz   [rbp+60h+var_C8]
0x1800303a3  mov     [rbp+60h+var_CC], r11d
0x1800303a7  test    sil, 4
0x1800303ab  jz      short loc_1800303B4
0x1800303ad  mov     r14b, 1
0x1800303b0  test    eax, eax
0x1800303b2  jz      short loc_1800303B7
0x1800303b4  mov     r14b, r11b
0x1800303b7  test    sil, 8
0x1800303bb  jz      short loc_1800303C5
0x1800303bd  mov     [rbp+60h+var_DE+2], 1
0x1800303c1  test    eax, eax
0x1800303c3  jz      short loc_1800303C9
0x1800303c5  mov     [rbp+60h+var_DE+2], r11b
0x1800303c9  lea     eax, [r9-2]
0x1800303cd  mov     r9d, 0FFFFFFFBh
0x1800303d3  test    r9d, eax
0x1800303d6  jz      short loc_1800303E1
0x1800303d8  mov     byte ptr [rbp+60h+arg_40], r11b
0x1800303df  jmp     short loc_1800303EE
0x1800303e1  mov     byte ptr [rbp+60h+arg_40], 1
0x1800303e8  cmp     r10d, 6
0x1800303ec  jz      short loc_1800303FC
0x1800303ee  lea     eax, [r10-5]
0x1800303f2  mov     cl, r11b
0x1800303f5  test    eax, 0FFFFFFFDh
0x1800303fa  jnz     short loc_1800303FE
0x1800303fc  mov     cl, 1
0x1800303fe  lea     eax, [r10-1]
0x180030402  cmp     eax, 2
0x180030405  setbe   r15b
0x180030409  test    cl, cl
0x18003040b  jnz     short loc_180030415
0x18003040d  mov     dil, r11b
0x180030410  test    r15b, r15b
0x180030413  jz      short loc_180030418
0x180030415  mov     dil, 1
0x180030418  mov     [rbp+60h+var_DF], dil
0x18003041c  mov     [rbp+60h+var_D0], r11b
0x180030420  test    dil, dil
0x180030423  jnz     short loc_180030456
0x180030425  lea     eax, [r10-4]
0x180030429  test    r9d, eax
0x18003042c  jz      short loc_180030456
0x18003042e  mov     r12, [rbp+60h+arg_38]
0x180030435  mov     ebx, 0C0000003h
0x18003043a  mov     r15, [rbp+60h+DomainName1]
0x180030441  mov     sil, byte ptr [rbp+60h+arg_40]
0x180030448  mov     [rbp+60h+var_88], r11
0x18003044c  mov     byte ptr [r12], 1
0x180030451  jmp     loc_180030877
0x180030456  mov     rdx, [rbp+60h+arg_38]
0x18003045d  mov     rcx, [rbp+60h+DomainName1]; DomainName1
0x180030464  mov     [rbp+60h+var_88], rcx
0x180030468  mov     [rdx], r11b
0x18003046b  cmp     r10d, 8
0x18003046f  jnz     short loc_1800304AC
0x180030471  cmp     [rcx], r11w
0x180030475  jnz     short loc_1800304AC
0x180030477  lea     rdx, aLogondomainnam; "LogonDomainName is mandatory for Kerber"...
0x18003047e  mov     ecx, 100h; unsigned int
0x180030483  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180030488  mov     r12, [rbp+60h+arg_38]
0x18003048f  mov     ebx, 0C000000Dh
0x180030494  mov     r15, [rbp+60h+DomainName1]
0x18003049b  mov     byte ptr [r12], 1
0x1800304a0  mov     sil, byte ptr [rbp+60h+arg_40]
0x1800304a7  jmp     loc_180030866
0x1800304ac  mov     rdi, [rbp+60h+arg_0]
0x1800304b0  mov     eax, esi
0x1800304b2  and     eax, 1000h
0x1800304b7  mov     [rbp+60h+hMem], r11
0x1800304bb  add     rdi, 0A8h
0x1800304c2  mov     [rbp+60h+var_D4], eax
0x1800304c5  mov     rdx, rdi; DomainName2
0x1800304c8  mov     ebx, 0C0000064h
0x1800304cd  mov     r13b, r11b
0x1800304d0  and     sil, 1
0x1800304d4  call    cs:__imp_RtlEqualDomainName
0x1800304db  nop     dword ptr [rax+rax+00h]
0x1800304e0  xor     r11d, r11d
0x1800304e3  test    al, al
0x1800304e5  jnz     short loc_180030513
0x1800304e7  mov     rax, [rbp+60h+arg_0]
0x1800304eb  cmp     dword ptr [rax+24Ch], 3
0x1800304f2  jz      short loc_18003050E
0x1800304f4  mov     rcx, [rbp+60h+DomainName1]; struct _UNICODE_STRING *
0x1800304fb  lea     rdx, [rax+80h]; struct _UNICODE_STRING *
0x180030502  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x180030507  xor     r11d, r11d
0x18003050a  test    eax, eax
0x18003050c  jnz     short loc_180030513
0x18003050e  mov     r9b, r11b
0x180030511  jmp     short loc_180030516
0x180030513  mov     r9b, 1; char *
0x180030516  mov     r8d, [rbp+60h+arg_8]
0x18003051a  mov     [rbp+60h+var_DE], r9b
0x18003051e  lea     eax, [r8-6]
0x180030522  cmp     eax, 1
0x180030525  jbe     short loc_18003052E
0x180030527  mov     r14b, r11b
0x18003052a  mov     [rbp+60h+var_DE+2], r11b
0x18003052e  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r11d; int NlGlobalMemberWorkstation
0x180030535  mov     rax, [rbp+60h+DomainName1]
0x18003053c  jz      short loc_180030573
0x18003053e  cmp     [rax], r11w
0x180030542  jnz     short loc_180030573
0x180030544  movzx   edx, word ptr [rax+20h]
0x180030548  shr     edx, 1
0x18003054a  jz      short loc_180030573
0x18003054c  mov     r8, [rax+28h]
0x180030550  mov     ecx, r11d
0x180030553  mov     eax, ecx
0x180030555  cmp     word ptr [r8+rax*2], 40h ; '@'
0x18003055b  jz      short loc_180030565
0x18003055d  inc     ecx
0x18003055f  cmp     ecx, edx
0x180030561  jb      short loc_180030553
0x180030563  jmp     short loc_180030568
0x180030565  mov     r13b, 1
0x180030568  mov     r8d, [rbp+60h+arg_8]
0x18003056c  mov     rax, [rbp+60h+DomainName1]
0x180030573  test    sil, sil
0x180030576  jnz     loc_180030E54
0x18003057c  test    r14b, r14b
0x18003057f  jnz     loc_180030E54
0x180030585  cmp     [rax], r11w
0x180030589  jnz     short loc_180030590
0x18003058b  test    r12d, r12d
0x18003058e  jz      short loc_1800305A9
0x180030590  test    r9b, r9b
0x180030593  jnz     short loc_1800305A9
0x180030595  lea     eax, [r8-6]
0x180030599  cmp     eax, 1
0x18003059c  ja      loc_180030E78
0x1800305a2  mov     rax, [rbp+60h+DomainName1]
0x1800305a9  cmp     [rbp+60h+var_DF], r11b
0x1800305ad  jz      loc_180030AA9
0x1800305b3  mov     edx, 2
0x1800305b8  mov     dword ptr [rbp+60h+var_DE+6], edx
0x1800305bb  test    r13b, r13b
0x1800305be  jnz     loc_18003075E
0x1800305c4  mov     eax, cs:dword_1800F81BC
0x1800305ca  mov     ecx, [rbp+60h+var_D4]
0x1800305cd  mov     [rbp+60h+var_D0], 1
0x1800305d1  test    al, 1
0x1800305d3  jz      short loc_1800305DE
0x1800305d5  cmp     r8d, edx
0x1800305d8  jnz     short loc_1800305DE
0x1800305da  test    ecx, ecx
0x1800305dc  jz      short loc_1800305EB
0x1800305de  test    dl, al
0x1800305e0  jz      short loc_180030657
0x1800305e2  lea     eax, [r8-3]
0x1800305e6  cmp     eax, 1
0x1800305e9  ja      short loc_180030657
0x1800305eb  mov     rdx, [rbp+60h+SourceString]; SourceString
0x1800305f2  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1800305f6  xorps   xmm0, xmm0
0x1800305f9  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1800305fd  call    cs:__imp_RtlInitUnicodeString
0x180030604  nop     dword ptr [rax+rax+00h]
0x180030609  mov     ecx, [rbp+60h+arg_8]
0x18003060c  mov     eax, 0FA4h
0x180030611  mov     r15, [rbp+60h+DomainName1]
0x180030618  cmp     ecx, 2
0x18003061b  mov     r8, r15; struct _UNICODE_STRING *
0x18003061e  lea     edx, [rax+2]
0x180030621  cmovnz  eax, edx
0x180030624  lea     r9, [r15+30h]; struct _UNICODE_STRING *
0x180030628  mov     dword ptr [rsp+170h+var_148], eax; unsigned int
0x18003062c  lea     rdx, [r15+20h]; struct _UNICODE_STRING *
0x180030630  mov     dword ptr [rsp+170h+var_150], ecx; unsigned int
0x180030634  lea     rcx, [rbp+60h+DestinationString]; struct _UNICODE_STRING *
0x180030638  call    ?NlpLogNTLMDCBlocked@@YAXPEAU_UNICODE_STRING@@000KK@Z; NlpLogNTLMDCBlocked(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong)
0x18003063d  mov     r12, [rbp+60h+arg_38]
0x180030644  mov     ebx, 0C0000418h
0x180030649  mov     byte ptr [r12], 1
0x18003064e  mov     r13, [rbp+60h+arg_0]
0x180030652  jmp     loc_1800304A0
0x180030657  mov     eax, cs:dword_1800F81C0
0x18003065d  test    al, 1
0x18003065f  jz      loc_18003077F
0x180030665  cmp     r8d, edx
0x180030668  jnz     loc_18003077F
0x18003066e  test    ecx, ecx
0x180030670  jnz     loc_18003077F
0x180030676  mov     rdx, [rbp+60h+SourceString]; SourceString
0x18003067d  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x180030681  xorps   xmm0, xmm0
0x180030684  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x180030688  call    cs:__imp_RtlInitUnicodeString
0x18003068f  nop     dword ptr [rax+rax+00h]
0x180030694  mov     rax, [rbp+60h+DomainName1]
0x18003069b  lea     rcx, [rbp+60h+DestinationString]; struct _UNICODE_STRING *
0x18003069f  mov     dword ptr [rsp+170h+var_148], 1F44h; unsigned int
0x1800306a7  mov     r8, rax; struct _UNICODE_STRING *
0x1800306aa  mov     dword ptr [rsp+170h+var_150], 2; unsigned int
0x1800306b2  lea     r9, [rax+30h]; struct _UNICODE_STRING *
0x1800306b6  lea     rdx, [rax+20h]; struct _UNICODE_STRING *
0x1800306ba  call    ?NlpLogNTLMDCBlocked@@YAXPEAU_UNICODE_STRING@@000KK@Z; NlpLogNTLMDCBlocked(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong)
0x1800306bf  mov     ebx, [rbp+60h+arg_8]
0x1800306c2  mov     rdx, [rbp+60h+arg_0]
0x1800306c6  lea     rax, [rbp+60h+var_DE+1]
0x1800306ca  mov     rcx, [rbp+60h+arg_30]
0x1800306d1  mov     r8d, ebx
0x1800306d4  mov     [rsp+170h+var_110], 1
0x1800306dc  mov     qword ptr [rsp+170h+var_118], rax
0x1800306e1  mov     rax, [rbp+60h+arg_38]
0x1800306e8  lea     r9, [rdx+100h]
0x1800306ef  mov     [rsp+170h+var_120], rax
0x1800306f4  mov     eax, [rbp+60h+arg_28]
0x1800306fa  mov     qword ptr [rsp+170h+var_128], rcx
0x1800306ff  mov     ecx, [rbp+60h+arg_18]
0x180030705  mov     [rsp+170h+var_130], eax
0x180030709  mov     rax, [rbp+60h+DomainName1]
0x180030710  mov     [rsp+170h+var_138], rax
0x180030715  mov     rax, [rdx+0B8h]
0x18003071c  mov     dword ptr [rsp+170h+var_140], ecx
0x180030720  mov     rcx, [rdx+178h]
0x180030727  mov     [rsp+170h+var_148], rax
0x18003072c  mov     [rsp+170h+var_150], rdi
0x180030731  call    ?NlpSamValidate@@YAJPEAXEW4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAU_UNICODE_STRING@@20W4_NETLOGON_LOGON_INFO_CLASS@@0W4_NETLOGON_VALIDATION_INFO_CLASS@@PEAPEAXPEAE6K@Z; NlpSamValidate(void *,uchar,_NETLOGON_SECURE_CHANNEL_TYPE,_UNICODE_STRING *,_UNICODE_STRING *,void *,_NETLOGON_LOGON_INFO_CLASS,void *,_NETLOGON_VALIDATION_INFO_CLASS,void * *,uchar *,uchar *,ulong)
0x180030736  xor     r11d, r11d
0x180030739  mov     ebx, eax
0x18003073b  cmp     [rbp+60h+var_DE+1], r11b
0x18003073f  jz      short loc_18003075A
0x180030741  mov     r8, [rbp+60h+DomainName1]; unsigned __int8 *
0x180030748  mov     edx, [rbp+60h+arg_18]; enum _NETLOGON_LOGON_INFO_CLASS
0x18003074e  mov     rcx, [rbp+60h+arg_0]; struct _DOMAIN_INFO *
0x180030752  call    ?NlpZeroBadPasswordCountOnPdc@@YAXPEAU_DOMAIN_INFO@@W4_NETLOGON_LOGON_INFO_CLASS@@PEAE@Z; NlpZeroBadPasswordCountOnPdc(_DOMAIN_INFO *,_NETLOGON_LOGON_INFO_CLASS,uchar *)
0x180030757  xor     r11d, r11d
0x18003075a  mov     r9b, [rbp+60h+var_DE]; char *
0x18003075e  test    r9b, r9b
0x180030761  jz      short loc_18003076B
0x180030763  cmp     ebx, 0C0000064h
0x180030769  jz      short loc_180030773
0x18003076b  cmp     ebx, 0C0000371h
0x180030771  jnz     short loc_1800307E1
0x180030773  mov     rdi, [rbp+60h+arg_38]
0x18003077a  mov     byte ptr [rdi], 1
0x18003077d  jmp     short loc_1800307E8
0x18003077f  test    dl, al
0x180030781  jz      loc_1800306BF
0x180030787  lea     eax, [r8-3]
0x18003078b  cmp     eax, 1
0x18003078e  ja      loc_1800306BF
0x180030794  mov     rdx, [rbp+60h+SourceString]; SourceString
0x18003079b  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x18003079f  xorps   xmm0, xmm0
0x1800307a2  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1800307a6  call    cs:__imp_RtlInitUnicodeString
0x1800307ad  nop     dword ptr [rax+rax+00h]
0x1800307b2  mov     rax, [rbp+60h+DomainName1]
0x1800307b9  lea     rcx, [rbp+60h+DestinationString]; struct _UNICODE_STRING *
0x1800307bd  mov     ebx, [rbp+60h+arg_8]
0x1800307c0  mov     r8, rax; struct _UNICODE_STRING *
0x1800307c3  mov     dword ptr [rsp+170h+var_148], 1F46h; unsigned int
0x1800307cb  mov     dword ptr [rsp+170h+var_150], ebx; unsigned int
0x1800307cf  lea     r9, [rax+30h]; struct _UNICODE_STRING *
0x1800307d3  lea     rdx, [rax+20h]; struct _UNICODE_STRING *
0x1800307d7  call    ?NlpLogNTLMDCBlocked@@YAXPEAU_UNICODE_STRING@@000KK@Z; NlpLogNTLMDCBlocked(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong)
0x1800307dc  jmp     loc_1800306C2
0x1800307e1  mov     rdi, [rbp+60h+arg_38]
0x1800307e8  cmp     [rbp+60h+arg_8], 6
0x1800307ec  jnz     loc_180030B00
0x1800307f2  mov     r15, [rbp+60h+DomainName1]
0x1800307f9  mov     r14, [rbp+60h+hMem]
0x1800307fd  mov     r12, [rbp+60h+arg_38]
0x180030804  mov     r13, [rbp+60h+arg_0]
  ... truncated ...
```
