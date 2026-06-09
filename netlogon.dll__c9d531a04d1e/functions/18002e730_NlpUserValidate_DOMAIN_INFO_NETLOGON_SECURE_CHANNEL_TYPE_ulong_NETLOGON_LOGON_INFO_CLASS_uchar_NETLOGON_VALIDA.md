# NlpUserValidate(_DOMAIN_INFO *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,_NETLOGON_LOGON_INFO_CLASS,uchar *,_NETLOGON_VALIDATION_INFO_CLASS,uchar * *,uchar *,ulong *,uchar,ushort *,_UNICODE_STRING *,ulong,ulong,void *,_SERVER_SESSION *,_SECPKG_NTLM_TARGETINFO *,int)

- ea: `0x18002e730`
- end: `0x18002fdac`
- name: `?NlpUserValidate@@YAJPEAU_DOMAIN_INFO@@W4_NETLOGON_SECURE_CHANNEL_TYPE@@KW4_NETLOGON_LOGON_INFO_CLASS@@PEAEW4_NETLOGON_VALIDATION_INFO_CLASS@@PEAPEAE3PEAKEPEAGPEAU_UNICODE_STRING@@KKPEAXPEAU_SERVER_SESSION@@PEAU_SECPKG_NTLM_TARGETINFO@@H@Z`
- size: `5756`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `29`
- tags: `loader_planting, service_task`

## callers

- `0x18002d3c0`
- `0x18002e730`

## callees

- `0x180005420`
- `0x180007278`
- `0x18000bd98`
- `0x18000d710`
- `0x18000da94`
- `0x18002707c`
- `0x1800270c8`
- `0x18002c070`
- `0x18002e004`
- `0x18002e1b4`
- `0x18002e730`
- `0x18002fdb4`
- `0x180030d88`
- `0x1800317ec`
- `0x180031944`
- `0x18003c6a4`
- `0x18003c81c`
- `0x18003e71c`
- `0x180051050`
- `0x18005113c`
- `0x180064f64`
- `0x180065ff0`
- `0x18006c0ec`
- `0x18006c31c`
- `0x18006c3b0`
- `0x18006c838`
- `0x180083180`
- `0x1800844d0`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f8e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f8e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9fb`
- `LSASRV!LsaIFreeReturnBuffer` at `0x18002f1bb`
- `LSASRV!LsaIFreeReturnBuffer` at `0x18002f1bb`
- `LSASRV!LsaICallPackagePassthrough` at `0x18002f13b`
- `LSASRV!LsaICallPackagePassthrough` at `0x18002f13b`
- `LSASRV!LsaINoMoreWin2KDomain` at `0x18002fd1f`
- `LSASRV!LsaINoMoreWin2KDomain` at `0x18002fd1f`
- `ntdll!RtlEqualDomainName` at `0x18002e8c8`
- `ntdll!RtlEqualDomainName` at `0x18002e8c8`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f6c4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002fa46`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f6c4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002fa46`
- `ntdll!RtlEnterCriticalSection` at `0x18002f6ad`
- `ntdll!RtlEnterCriticalSection` at `0x18002f6ad`
- `ntdll!RtlInitUnicodeString` at `0x18002e9eb`
- `ntdll!RtlInitUnicodeString` at `0x18002ea70`
- `ntdll!RtlInitUnicodeString` at `0x18002eb88`
- `ntdll!RtlInitUnicodeString` at `0x18002f475`
- `ntdll!RtlInitUnicodeString` at `0x18002f4ec`
- `ntdll!RtlInitUnicodeString` at `0x18002f68e`
- `ntdll!RtlInitUnicodeString` at `0x18002f787`
- `ntdll!RtlInitUnicodeString` at `0x18002f861`
- `ntdll!RtlInitUnicodeString` at `0x18002f926`
- `ntdll!RtlInitUnicodeString` at `0x18002e9eb`
- `ntdll!RtlInitUnicodeString` at `0x18002ea70`
- `ntdll!RtlInitUnicodeString` at `0x18002eb88`
- `ntdll!RtlInitUnicodeString` at `0x18002f475`
- `ntdll!RtlInitUnicodeString` at `0x18002f4ec`
- `ntdll!RtlInitUnicodeString` at `0x18002f68e`
- `ntdll!RtlInitUnicodeString` at `0x18002f787`
- `ntdll!RtlInitUnicodeString` at `0x18002f861`
- `ntdll!RtlInitUnicodeString` at `0x18002f926`
- `netutils!NetApiBufferFree` at `0x18002fc16`
- `netutils!NetApiBufferFree` at `0x18002fc28`
- `netutils!NetApiBufferFree` at `0x18002fc16`
- `netutils!NetApiBufferFree` at `0x18002fc28`

## string_xrefs

- `0x18002ebfe`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002ec1f`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002ed0b`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002ed2c`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002f0e5`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002f260`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002f27e`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002f310`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002f331`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002fa2b`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002fb29`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002fb4a`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002fbd7`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`

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
  __int64 v90; // [rsp+98h] [rbp-80h] BYREF
  int v91; // [rsp+A0h] [rbp-78h]
  int v92; // [rsp+A4h] [rbp-74h] BYREF
  char v93; // [rsp+A8h] [rbp-70h]
  unsigned int v94; // [rsp+ACh] [rbp-6Ch] BYREF
  bool v95; // [rsp+B0h] [rbp-68h]
  HLOCAL hMem; // [rsp+B8h] [rbp-60h] BYREF
  PCWSTR v97; // [rsp+C0h] [rbp-58h] BYREF
  size_t Size; // [rsp+C8h] [rbp-50h] BYREF
  void *Src; // [rsp+D0h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-40h] BYREF
  PCWSTR v101; // [rsp+E8h] [rbp-30h] BYREF
  struct _NETLOGON_LOGON_IDENTITY_INFO *v102; // [rsp+F0h] [rbp-28h]
  struct _UNICODE_STRING v103; // [rsp+F8h] [rbp-20h] BYREF
  struct _UNICODE_STRING v104; // [rsp+108h] [rbp-10h] BYREF
  struct _UNICODE_STRING v105; // [rsp+118h] [rbp+0h] BYREF
  struct _UNICODE_STRING v106; // [rsp+128h] [rbp+10h] BYREF
  char v111; // [rsp+1C8h] [rbp+B0h]

  v18 = a2;
  v19 = 3;
  WORD1(v90) = 0;
  v20 = a4;
  v91 = 3;
  v21 = *a9;
  v22 = a1;
  v23 = (*a9 & 2) == 0;
  v24 = *a9 & 2;
  v101 = 0;
  v97 = 0;
  v95 = !v23;
  v94 = 0;
  if ( (v21 & 4) == 0 || (v25 = 1, NlGlobalCDC) )
    v25 = 0;
  if ( (v21 & 8) == 0 || (BYTE4(v90) = 1, NlGlobalCDC) )
    BYTE4(v90) = 0;
  v26 = a4 - 2;
  v27 = 4294967291LL;
  if ( (v26 & 0xFFFFFFFB) != 0 )
  {
    v111 = 0;
  }
  else
  {
    v111 = 1;
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
  BYTE1(v90) = v30;
  v93 = 0;
  if ( v30 || ((v20 - 4) & 0xFFFFFFFB) == 0 )
  {
    v102 = (struct _NETLOGON_LOGON_IDENTITY_INFO *)DomainName1;
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
      v34 = v111;
LABEL_84:
      v18 = a2;
LABEL_85:
      v20 = a4;
LABEL_86:
      v19 = v91;
      goto LABEL_87;
    }
    hMem = 0;
    v92 = v21 & 0x1000;
    v32 = -1073741724;
    v35 = 0;
    v36 = v21 & 1;
    LOBYTE(v27) = RtlEqualDomainName(DomainName1, (PUNICODE_STRING)(a1 + 168))
               || *(_DWORD *)(a1 + 588) != 3
               && (unsigned int)NlEqualDnsNameU(DomainName1, (struct _UNICODE_STRING *)(a1 + 128));
    v18 = a2;
    BYTE2(v90) = v27;
    if ( a2 - 6 > 1 )
    {
      v25 = 0;
      BYTE4(v90) = 0;
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
            4250,
            (char *)v27);
        if ( v24 )
          NlAssertFailed(
            "!CrossForestHop",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            4251,
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
        v65 = NlpUserValidateHigher((__int64)v64, 0, a4, (__int64)DomainName1, a6, a7, a8, &v94);
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
              4274,
              (char *)v27);
          if ( !*a7 )
            NlAssertFailed(
              "!NT_SUCCESS(Status) || *ValidationInformation != NULL",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
              4275,
              (char *)v27);
        }
        if ( *a8 )
        {
          if ( v65 == -1073741730 )
          {
            if ( !BYTE1(v90) || DomainName1->Length || v35 != 1 )
            {
              v34 = v111;
              if ( !v111 || NlIsDomainTrusted(DomainName1) )
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
            v34 = v111;
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
            4908,
            (char *)v27);
        goto LABEL_74;
      }
      LOBYTE(v90) = 0;
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
        if ( (dword_1800F11BC & 4) == 0 || a2 != 2 || !BYTE1(v90) || v92 )
        {
          if ( (dword_1800F11C0 & 4) != 0 && a2 == 2 && BYTE1(v90) && !v92 )
          {
            v104 = 0;
            RtlInitUnicodeString(&v104, SourceString);
            v33 = DomainName1;
            NlpLogNTLMDCBlocked(&v104, DomainName1 + 2, DomainName1, DomainName1 + 3, 2u, 0x1F45u);
          }
          else
          {
            v33 = DomainName1;
          }
          v31 = a8;
          v44 = a7;
          v34 = v111;
          v32 = NlpUserValidateHigher((__int64)v43, 0, a4, (__int64)v33, a6, a7, a8, (unsigned int *)&hMem);
LABEL_77:
          if ( v32 >= 0 )
          {
            if ( v32 )
              NlAssertFailed(
                "!NT_SUCCESS(DefaultStatus) || DefaultStatus == STATUS_SUCCESS",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                4911,
                (char *)v27);
            if ( !*v44 )
              NlAssertFailed(
                "!NT_SUCCESS(DefaultStatus) || *ValidationInformation != NULL",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                4912,
                (char *)v27);
          }
LABEL_82:
          if ( !v43 )
            goto LABEL_84;
LABEL_83:
          NlUnrefClientSession(v43);
          goto LABEL_84;
        }
        v104 = 0;
        RtlInitUnicodeString(&v104, SourceString);
        v33 = DomainName1;
        NlpLogNTLMDCBlocked(&v104, DomainName1 + 2, DomainName1, DomainName1 + 3, 2u, 0xFA5u);
        v31 = a8;
        v32 = -1073740776;
        *a8 = 1;
LABEL_236:
        v34 = v111;
        goto LABEL_83;
      }
      if ( (unsigned int)(v18 - 3) <= 1 && v29 )
      {
        v33 = DomainName1;
        v32 = -1073741724;
        v31 = a8;
        v22 = a1;
        v34 = v111;
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
          v94 |= 1u;
          v33 = DomainName1;
          LODWORD(v18) = a2;
LABEL_257:
          v67 = BYTE1(v90);
          if ( !BYTE1(v90) && a4 != 8 )
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
          LOBYTE(v88) = v95;
          LOBYTE(v87) = v36;
          if ( (int)NlPickDomainWithAccount(a1, &v33[2], v33, 16, v18, v87, v88, &v101, &v97, &v94) < 0 )
            goto LABEL_302;
          if ( (v94 & 2) != 0 )
          {
            v103 = 0;
            RtlInitUnicodeString(&v103, v97);
            NamedClientSession = NlFindNamedClientSession((struct _DOMAIN_INFO *)a1, &v103, 1u, (unsigned __int8 *)&v90);
            v43 = NamedClientSession;
            if ( !NamedClientSession )
            {
              NlPrintDomRoutine(
                0x100u,
                (struct _DOMAIN_INFO *)a1,
                L"NlpUserValidate: %wZ\\%wZ: Can't find trusted forest '%wZ'\n",
                v33,
                &v33[2],
                &v103);
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
                &v103);
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
                &v103);
              goto LABEL_274;
            }
            v67 = BYTE1(v90);
LABEL_260:
            v106 = 0;
            RtlInitUnicodeString(&v106, SourceString);
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
                v34 = v111;
                goto LABEL_82;
              }
              RtlLeaveCriticalSection(v69);
              v68 = a2;
            }
            if ( (dword_1800F11BC & 4) != 0 && v68 == 2 && v67 && !v92 )
            {
              NlpLogNTLMDCBlocked(&v106, v33 + 2, v33, v33 + 3, 2u, 0xFA5u);
              v31 = a8;
              v32 = -1073740776;
              *a8 = 1;
              goto LABEL_263;
            }
            if ( (dword_1800F11C0 & 4) != 0 && v68 == 2 && v67 && !v92 )
              NlpLogNTLMDCBlocked(&v106, v33 + 2, v33, v33 + 3, 2u, 0x1F45u);
            v31 = a8;
            v44 = a7;
            v78 = NlpUserValidateHigher((__int64)v43, v90, a4, (__int64)v33, a6, a7, a8, &v94);
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
                  4862,
                  (char *)v27);
              if ( !*a7 )
              {
                NlAssertFailed(
                  "!NT_SUCCESS(Status) || *ValidationInformation != NULL",
                  "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                  4863,
                  (char *)v27);
LABEL_223:
                v34 = v111;
                goto LABEL_77;
              }
            }
            if ( v32 == -1073741724 )
              *a8 = 1;
            goto LABEL_223;
          }
          if ( !v101 || !v97 || (v94 & 1) != 0 )
          {
            v75 = 0;
            v76 = v33;
            goto LABEL_298;
          }
          v105 = 0;
          v71 = 0;
          RtlInitUnicodeString(&v105, v101);
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
                v34 = v111;
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
              RtlInitUnicodeString(v75, v97);
              v77 = v105;
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
                      &v94,
                      v89,
                      SourceString,
                      a12,
                      a13,
                      a14,
                      a15,
                      a16,
                      a17,
                      a18,
                      v90);
              if ( v75 )
                LocalFree(v75);
              v91 = 0;
              goto LABEL_75;
            }
          }
          Length = v33->Length;
          if ( !v33->Length )
            v105 = v33[2];
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
          v66 = NlFindNamedClientSession(
                  (struct _DOMAIN_INFO *)a1,
                  DomainName1,
                  v24 != 0 ? 10 : 2,
                  (unsigned __int8 *)&v90);
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
    if ( BYTE1(v90) )
    {
      v91 = 2;
      if ( v35 )
        goto LABEL_64;
      v93 = 1;
      if ( (dword_1800F11BC & 1) != 0 && (_DWORD)v18 == 2 && !v92
        || (dword_1800F11BC & 2) != 0 && (unsigned int)(v18 - 3) <= 1 )
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
      if ( (dword_1800F11C0 & 1) != 0 && (_DWORD)v18 == 2 && !v92 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, SourceString);
        NlpLogNTLMDCBlocked(&DestinationString, DomainName1 + 2, DomainName1, DomainName1 + 3, 2u, 0x1F44u);
      }
      else if ( (dword_1800F11C0 & 2) != 0 && (unsigned int)(v18 - 3) <= 1 )
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
              (char *)&v90 + 3,
              1);
      if ( BYTE3(v90) )
        NlpZeroBadPasswordCountOnPdc((struct _DOMAIN_INFO *)a1, a4, (unsigned __int8 *)DomainName1);
      LOBYTE(v27) = BYTE2(v90);
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
        v34 = v111;
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
            LOBYTE(v90) = 0;
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
              v34 = v111;
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
      LOBYTE(v27) = BYTE2(v90);
      goto LABEL_129;
    }
    if ( a4 != NetlogonGenericInformation )
      NlAssertFailed(
        "GenericPassthrough",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
        4051,
        (char *)v27);
    v33 = DomainName1;
    Size = 0;
    v60 = *(unsigned int *)&DomainName1[5].Length;
    Buffer = DomainName1[5].Buffer;
    v92 = 0;
    Src = 0;
    v31 = a8;
    v32 = LsaICallPackagePassthrough(&DomainName1[4], 0, Buffer, v60, &Src, &Size, &v92);
    if ( v32 >= 0 )
      v32 = v92;
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
  v34 = v111;
  v102 = 0;
  *a8 = 1;
LABEL_87:
  if ( v34 && ((_DWORD)v18 == 1 || BYTE4(v90)) )
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
      LOBYTE(v90) = 0;
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
              (char *)&v90 + 3,
              v46);
      v50 = v48;
      if ( v48 >= 0 )
      {
        if ( v48 )
          NlAssertFailed(
            "!NT_SUCCESS(Status) || Status == STATUS_SUCCESS",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            4984,
            v49);
        if ( !*a7 )
          NlAssertFailed(
            "!NT_SUCCESS(Status) || *ValidationInformation != NULL",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
            4985,
            v49);
      }
      if ( BYTE3(v90) )
        NlpZeroBadPasswordCountOnPdc((struct _DOMAIN_INFO *)v22, a4, (unsigned __int8 *)v33);
      if ( (_BYTE)v90 )
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
            NlpZeroBadPasswordCountLocally((struct _DOMAIN_INFO *)v22, &v102->UserName, v50 == -1073740943);
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
            5073,
            (char *)v27);
        v80 = (const UNICODE_STRING *)NlGlobalDomainInfo;
        *(_BYTE *)v79 |= 1u;
        *((_DWORD *)v79 + 3) = v32;
        NlpCopyUnicodeString(v80 + 17, (PUNICODE_STRING)v79 + 1);
        v32 = 0;
      }
    }
  }
  if ( v101 )
    NetApiBufferFree((LPVOID)v101);
  if ( v97 )
    NetApiBufferFree((LPVOID)v97);
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
                BYTE2(v90),
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
      else if ( a2 - 1 <= 1 && BYTE1(v90) && !NlGlobalMemberWorkstation )
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
    if ( v111 && v93 && a16 && *((_DWORD *)a16 + 8) != 2 )
      NlpNtlmlessLogAccountDomain(v102, a16, a17, a18, v32);
  }
  return (unsigned int)v32;
}

```

## disassembly

```asm
0x18002e730  mov     rax, rsp
0x18002e733  mov     [rax+20h], r9d
0x18002e737  mov     [rax+18h], r8d
0x18002e73b  mov     [rax+10h], edx
0x18002e73e  mov     [rax+8], rcx
0x18002e742  push    rbp
0x18002e743  push    rbx
0x18002e744  push    rsi
0x18002e745  push    rdi
0x18002e746  push    r12
0x18002e748  push    r13
0x18002e74a  push    r14
0x18002e74c  push    r15
0x18002e74e  lea     rbp, [rax-68h]
0x18002e752  sub     rsp, 138h
0x18002e759  mov     rax, [rbp+60h+arg_40]
0x18002e760  xor     r11d, r11d
0x18002e763  mov     r8d, edx
0x18002e766  mov     [rbp+60h+var_DE+1], r11b
0x18002e76a  mov     edx, 3
0x18002e76f  mov     [rbp+60h+var_DE], r11b
0x18002e773  mov     r10d, r9d
0x18002e776  mov     dword ptr [rbp+60h+var_DE+6], edx
0x18002e779  mov     esi, [rax]
0x18002e77b  mov     r13, rcx
0x18002e77e  mov     eax, cs:?NlGlobalCDC@@3HA; int NlGlobalCDC
0x18002e784  mov     r12d, esi
0x18002e787  and     r12d, 2
0x18002e78b  mov     [rbp+60h+var_90], r11
0x18002e78f  mov     [rbp+60h+var_B8], r11
0x18002e793  setnz   [rbp+60h+var_C8]
0x18002e797  mov     [rbp+60h+var_CC], r11d
0x18002e79b  test    sil, 4
0x18002e79f  jz      short loc_18002E7A8
0x18002e7a1  mov     r14b, 1
0x18002e7a4  test    eax, eax
0x18002e7a6  jz      short loc_18002E7AB
0x18002e7a8  mov     r14b, r11b
0x18002e7ab  test    sil, 8
0x18002e7af  jz      short loc_18002E7B9
0x18002e7b1  mov     [rbp+60h+var_DE+2], 1
0x18002e7b5  test    eax, eax
0x18002e7b7  jz      short loc_18002E7BD
0x18002e7b9  mov     [rbp+60h+var_DE+2], r11b
0x18002e7bd  lea     eax, [r9-2]
0x18002e7c1  mov     r9d, 0FFFFFFFBh
0x18002e7c7  test    r9d, eax
0x18002e7ca  jz      short loc_18002E7D5
0x18002e7cc  mov     byte ptr [rbp+60h+arg_40], r11b
0x18002e7d3  jmp     short loc_18002E7E2
0x18002e7d5  mov     byte ptr [rbp+60h+arg_40], 1
0x18002e7dc  cmp     r10d, 6
0x18002e7e0  jz      short loc_18002E7F0
0x18002e7e2  lea     eax, [r10-5]
0x18002e7e6  mov     cl, r11b
0x18002e7e9  test    eax, 0FFFFFFFDh
0x18002e7ee  jnz     short loc_18002E7F2
0x18002e7f0  mov     cl, 1
0x18002e7f2  lea     eax, [r10-1]
0x18002e7f6  cmp     eax, 2
0x18002e7f9  setbe   r15b
0x18002e7fd  test    cl, cl
0x18002e7ff  jnz     short loc_18002E809
0x18002e801  mov     dil, r11b
0x18002e804  test    r15b, r15b
0x18002e807  jz      short loc_18002E80C
0x18002e809  mov     dil, 1
0x18002e80c  mov     [rbp+60h+var_DF], dil
0x18002e810  mov     [rbp+60h+var_D0], r11b
0x18002e814  test    dil, dil
0x18002e817  jnz     short loc_18002E84A
0x18002e819  lea     eax, [r10-4]
0x18002e81d  test    r9d, eax
0x18002e820  jz      short loc_18002E84A
0x18002e822  mov     r12, [rbp+60h+arg_38]
0x18002e829  mov     ebx, 0C0000003h
0x18002e82e  mov     r15, [rbp+60h+DomainName1]
0x18002e835  mov     sil, byte ptr [rbp+60h+arg_40]
0x18002e83c  mov     [rbp+60h+var_88], r11
0x18002e840  mov     byte ptr [r12], 1
0x18002e845  jmp     loc_18002EC53
0x18002e84a  mov     rdx, [rbp+60h+arg_38]
0x18002e851  mov     rcx, [rbp+60h+DomainName1]; DomainName1
0x18002e858  mov     [rbp+60h+var_88], rcx
0x18002e85c  mov     [rdx], r11b
0x18002e85f  cmp     r10d, 8
0x18002e863  jnz     short loc_18002E8A0
0x18002e865  cmp     [rcx], r11w
0x18002e869  jnz     short loc_18002E8A0
0x18002e86b  lea     rdx, aLogondomainnam; "LogonDomainName is mandatory for Kerber"...
0x18002e872  mov     ecx, 100h; unsigned int
0x18002e877  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002e87c  mov     r12, [rbp+60h+arg_38]
0x18002e883  mov     ebx, 0C000000Dh
0x18002e888  mov     r15, [rbp+60h+DomainName1]
0x18002e88f  mov     byte ptr [r12], 1
0x18002e894  mov     sil, byte ptr [rbp+60h+arg_40]
0x18002e89b  jmp     loc_18002EC42
0x18002e8a0  mov     rdi, [rbp+60h+arg_0]
0x18002e8a4  mov     eax, esi
0x18002e8a6  and     eax, 1000h
0x18002e8ab  mov     [rbp+60h+hMem], r11
0x18002e8af  add     rdi, 0A8h
0x18002e8b6  mov     [rbp+60h+var_D4], eax
0x18002e8b9  mov     rdx, rdi; DomainName2
0x18002e8bc  mov     ebx, 0C0000064h
0x18002e8c1  mov     r13b, r11b
0x18002e8c4  and     sil, 1
0x18002e8c8  call    cs:__imp_RtlEqualDomainName
0x18002e8ce  xor     r11d, r11d
0x18002e8d1  test    al, al
0x18002e8d3  jnz     short loc_18002E901
0x18002e8d5  mov     rax, [rbp+60h+arg_0]
0x18002e8d9  cmp     dword ptr [rax+24Ch], 3
0x18002e8e0  jz      short loc_18002E8FC
0x18002e8e2  mov     rcx, [rbp+60h+DomainName1]; struct _UNICODE_STRING *
0x18002e8e9  lea     rdx, [rax+80h]; struct _UNICODE_STRING *
0x18002e8f0  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x18002e8f5  xor     r11d, r11d
0x18002e8f8  test    eax, eax
0x18002e8fa  jnz     short loc_18002E901
0x18002e8fc  mov     r9b, r11b
0x18002e8ff  jmp     short loc_18002E904
0x18002e901  mov     r9b, 1; char *
0x18002e904  mov     r8d, [rbp+60h+arg_8]
0x18002e908  mov     [rbp+60h+var_DE], r9b
0x18002e90c  lea     eax, [r8-6]
0x18002e910  cmp     eax, 1
0x18002e913  jbe     short loc_18002E91C
0x18002e915  mov     r14b, r11b
0x18002e918  mov     [rbp+60h+var_DE+2], r11b
0x18002e91c  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r11d; int NlGlobalMemberWorkstation
0x18002e923  mov     rax, [rbp+60h+DomainName1]
0x18002e92a  jz      short loc_18002E961
0x18002e92c  cmp     [rax], r11w
0x18002e930  jnz     short loc_18002E961
0x18002e932  movzx   edx, word ptr [rax+20h]
0x18002e936  shr     edx, 1
0x18002e938  jz      short loc_18002E961
0x18002e93a  mov     r8, [rax+28h]
0x18002e93e  mov     ecx, r11d
0x18002e941  mov     eax, ecx
0x18002e943  cmp     word ptr [r8+rax*2], 40h ; '@'
0x18002e949  jz      short loc_18002E953
0x18002e94b  inc     ecx
0x18002e94d  cmp     ecx, edx
0x18002e94f  jb      short loc_18002E941
0x18002e951  jmp     short loc_18002E956
0x18002e953  mov     r13b, 1
0x18002e956  mov     r8d, [rbp+60h+arg_8]
0x18002e95a  mov     rax, [rbp+60h+DomainName1]
0x18002e961  test    sil, sil
0x18002e964  jnz     loc_18002F224
0x18002e96a  test    r14b, r14b
0x18002e96d  jnz     loc_18002F224
0x18002e973  cmp     [rax], r11w
0x18002e977  jnz     short loc_18002E97E
0x18002e979  test    r12d, r12d
0x18002e97c  jz      short loc_18002E997
0x18002e97e  test    r9b, r9b
0x18002e981  jnz     short loc_18002E997
0x18002e983  lea     eax, [r8-6]
0x18002e987  cmp     eax, 1
0x18002e98a  ja      loc_18002F248
0x18002e990  mov     rax, [rbp+60h+DomainName1]
0x18002e997  cmp     [rbp+60h+var_DF], r11b
0x18002e99b  jz      loc_18002EE85
0x18002e9a1  mov     edx, 2
0x18002e9a6  mov     dword ptr [rbp+60h+var_DE+6], edx
0x18002e9a9  test    r13b, r13b
0x18002e9ac  jnz     loc_18002EB40
0x18002e9b2  mov     eax, cs:dword_1800F11BC
0x18002e9b8  mov     ecx, [rbp+60h+var_D4]
0x18002e9bb  mov     [rbp+60h+var_D0], 1
0x18002e9bf  test    al, 1
0x18002e9c1  jz      short loc_18002E9CC
0x18002e9c3  cmp     r8d, edx
0x18002e9c6  jnz     short loc_18002E9CC
0x18002e9c8  test    ecx, ecx
0x18002e9ca  jz      short loc_18002E9D9
0x18002e9cc  test    dl, al
0x18002e9ce  jz      short loc_18002EA3F
0x18002e9d0  lea     eax, [r8-3]
0x18002e9d4  cmp     eax, 1
0x18002e9d7  ja      short loc_18002EA3F
0x18002e9d9  mov     rdx, [rbp+60h+SourceString]; SourceString
0x18002e9e0  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x18002e9e4  xorps   xmm0, xmm0
0x18002e9e7  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x18002e9eb  call    cs:__imp_RtlInitUnicodeString
0x18002e9f1  mov     ecx, [rbp+60h+arg_8]
0x18002e9f4  mov     eax, 0FA4h
0x18002e9f9  mov     r15, [rbp+60h+DomainName1]
0x18002ea00  cmp     ecx, 2
0x18002ea03  mov     r8, r15; struct _UNICODE_STRING *
0x18002ea06  lea     edx, [rax+2]
0x18002ea09  cmovnz  eax, edx
0x18002ea0c  lea     r9, [r15+30h]; struct _UNICODE_STRING *
0x18002ea10  mov     dword ptr [rsp+170h+var_148], eax; unsigned int
0x18002ea14  lea     rdx, [r15+20h]; struct _UNICODE_STRING *
0x18002ea18  mov     dword ptr [rsp+170h+var_150], ecx; unsigned int
0x18002ea1c  lea     rcx, [rbp+60h+DestinationString]; struct _UNICODE_STRING *
0x18002ea20  call    ?NlpLogNTLMDCBlocked@@YAXPEAU_UNICODE_STRING@@000KK@Z; NlpLogNTLMDCBlocked(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong)
0x18002ea25  mov     r12, [rbp+60h+arg_38]
0x18002ea2c  mov     ebx, 0C0000418h
0x18002ea31  mov     byte ptr [r12], 1
0x18002ea36  mov     r13, [rbp+60h+arg_0]
0x18002ea3a  jmp     loc_18002E894
0x18002ea3f  mov     eax, cs:dword_1800F11C0
0x18002ea45  test    al, 1
0x18002ea47  jz      loc_18002EB61
0x18002ea4d  cmp     r8d, edx
0x18002ea50  jnz     loc_18002EB61
0x18002ea56  test    ecx, ecx
0x18002ea58  jnz     loc_18002EB61
0x18002ea5e  mov     rdx, [rbp+60h+SourceString]; SourceString
0x18002ea65  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x18002ea69  xorps   xmm0, xmm0
0x18002ea6c  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x18002ea70  call    cs:__imp_RtlInitUnicodeString
0x18002ea76  mov     rax, [rbp+60h+DomainName1]
0x18002ea7d  lea     rcx, [rbp+60h+DestinationString]; struct _UNICODE_STRING *
0x18002ea81  mov     dword ptr [rsp+170h+var_148], 1F44h; unsigned int
0x18002ea89  mov     r8, rax; struct _UNICODE_STRING *
0x18002ea8c  mov     dword ptr [rsp+170h+var_150], 2; unsigned int
0x18002ea94  lea     r9, [rax+30h]; struct _UNICODE_STRING *
0x18002ea98  lea     rdx, [rax+20h]; struct _UNICODE_STRING *
0x18002ea9c  call    ?NlpLogNTLMDCBlocked@@YAXPEAU_UNICODE_STRING@@000KK@Z; NlpLogNTLMDCBlocked(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong)
0x18002eaa1  mov     ebx, [rbp+60h+arg_8]
0x18002eaa4  mov     rdx, [rbp+60h+arg_0]
0x18002eaa8  lea     rax, [rbp+60h+var_DE+1]
0x18002eaac  mov     rcx, [rbp+60h+arg_30]
0x18002eab3  mov     r8d, ebx
0x18002eab6  mov     [rsp+170h+var_110], 1
0x18002eabe  mov     qword ptr [rsp+170h+var_118], rax
0x18002eac3  mov     rax, [rbp+60h+arg_38]
0x18002eaca  lea     r9, [rdx+100h]
0x18002ead1  mov     [rsp+170h+var_120], rax
0x18002ead6  mov     eax, [rbp+60h+arg_28]
0x18002eadc  mov     qword ptr [rsp+170h+var_128], rcx
0x18002eae1  mov     ecx, [rbp+60h+arg_18]
0x18002eae7  mov     [rsp+170h+var_130], eax
0x18002eaeb  mov     rax, [rbp+60h+DomainName1]
0x18002eaf2  mov     [rsp+170h+var_138], rax
0x18002eaf7  mov     rax, [rdx+0B8h]
0x18002eafe  mov     dword ptr [rsp+170h+var_140], ecx
0x18002eb02  mov     rcx, [rdx+178h]
0x18002eb09  mov     [rsp+170h+var_148], rax
0x18002eb0e  mov     [rsp+170h+var_150], rdi
0x18002eb13  call    ?NlpSamValidate@@YAJPEAXEW4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAU_UNICODE_STRING@@20W4_NETLOGON_LOGON_INFO_CLASS@@0W4_NETLOGON_VALIDATION_INFO_CLASS@@PEAPEAXPEAE6K@Z; NlpSamValidate(void *,uchar,_NETLOGON_SECURE_CHANNEL_TYPE,_UNICODE_STRING *,_UNICODE_STRING *,void *,_NETLOGON_LOGON_INFO_CLASS,void *,_NETLOGON_VALIDATION_INFO_CLASS,void * *,uchar *,uchar *,ulong)
0x18002eb18  xor     r11d, r11d
0x18002eb1b  mov     ebx, eax
0x18002eb1d  cmp     [rbp+60h+var_DE+1], r11b
0x18002eb21  jz      short loc_18002EB3C
0x18002eb23  mov     r8, [rbp+60h+DomainName1]; unsigned __int8 *
0x18002eb2a  mov     edx, [rbp+60h+arg_18]; enum _NETLOGON_LOGON_INFO_CLASS
0x18002eb30  mov     rcx, [rbp+60h+arg_0]; struct _DOMAIN_INFO *
0x18002eb34  call    ?NlpZeroBadPasswordCountOnPdc@@YAXPEAU_DOMAIN_INFO@@W4_NETLOGON_LOGON_INFO_CLASS@@PEAE@Z; NlpZeroBadPasswordCountOnPdc(_DOMAIN_INFO *,_NETLOGON_LOGON_INFO_CLASS,uchar *)
0x18002eb39  xor     r11d, r11d
0x18002eb3c  mov     r9b, [rbp+60h+var_DE]; char *
0x18002eb40  test    r9b, r9b
0x18002eb43  jz      short loc_18002EB4D
0x18002eb45  cmp     ebx, 0C0000064h
0x18002eb4b  jz      short loc_18002EB55
0x18002eb4d  cmp     ebx, 0C0000371h
0x18002eb53  jnz     short loc_18002EBBD
0x18002eb55  mov     rdi, [rbp+60h+arg_38]
0x18002eb5c  mov     byte ptr [rdi], 1
0x18002eb5f  jmp     short loc_18002EBC4
0x18002eb61  test    dl, al
0x18002eb63  jz      loc_18002EAA1
0x18002eb69  lea     eax, [r8-3]
0x18002eb6d  cmp     eax, 1
0x18002eb70  ja      loc_18002EAA1
0x18002eb76  mov     rdx, [rbp+60h+SourceString]; SourceString
0x18002eb7d  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x18002eb81  xorps   xmm0, xmm0
0x18002eb84  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x18002eb88  call    cs:__imp_RtlInitUnicodeString
0x18002eb8e  mov     rax, [rbp+60h+DomainName1]
0x18002eb95  lea     rcx, [rbp+60h+DestinationString]; struct _UNICODE_STRING *
0x18002eb99  mov     ebx, [rbp+60h+arg_8]
0x18002eb9c  mov     r8, rax; struct _UNICODE_STRING *
0x18002eb9f  mov     dword ptr [rsp+170h+var_148], 1F46h; unsigned int
0x18002eba7  mov     dword ptr [rsp+170h+var_150], ebx; unsigned int
0x18002ebab  lea     r9, [rax+30h]; struct _UNICODE_STRING *
0x18002ebaf  lea     rdx, [rax+20h]; struct _UNICODE_STRING *
0x18002ebb3  call    ?NlpLogNTLMDCBlocked@@YAXPEAU_UNICODE_STRING@@000KK@Z; NlpLogNTLMDCBlocked(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong)
0x18002ebb8  jmp     loc_18002EAA4
0x18002ebbd  mov     rdi, [rbp+60h+arg_38]
0x18002ebc4  cmp     [rbp+60h+arg_8], 6
0x18002ebc8  jnz     loc_18002EEDC
0x18002ebce  mov     r15, [rbp+60h+DomainName1]
0x18002ebd5  mov     r14, [rbp+60h+hMem]
0x18002ebd9  mov     r12, [rbp+60h+arg_38]
0x18002ebe0  mov     r13, [rbp+60h+arg_0]
0x18002ebe4  mov     sil, byte ptr [rbp+60h+arg_40]
0x18002ebeb  mov     rdi, [rbp+60h+arg_30]
0x18002ebf2  test    ebx, ebx
0x18002ebf4  js      short loc_18002EC35
  ... truncated ...
```
