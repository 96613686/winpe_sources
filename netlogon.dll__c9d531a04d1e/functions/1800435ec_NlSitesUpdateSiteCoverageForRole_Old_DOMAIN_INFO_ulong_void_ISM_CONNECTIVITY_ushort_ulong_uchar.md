# NlSitesUpdateSiteCoverageForRole_Old(_DOMAIN_INFO *,ulong,void *,_ISM_CONNECTIVITY *,ushort *,ulong,uchar *)

- ea: `0x1800435ec`
- end: `0x1800444d5`
- name: `?NlSitesUpdateSiteCoverageForRole_Old@@YAKPEAU_DOMAIN_INFO@@KPEAXPEAU_ISM_CONNECTIVITY@@PEAGKPEAE@Z`
- size: `3817`
- prototype: `unsigned int __usercall@<eax>(struct _DOMAIN_INFO *@<rcx>, unsigned int@<edx>, void *@<r8>, struct _ISM_CONNECTIVITY *@<r9>, unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001f5f0`

## callees

- `0x180007278`
- `0x18000e270`
- `0x1800109fc`
- `0x18001ef7c`
- `0x180024e80`
- `0x18002647c`
- `0x18003f684`
- `0x180041f98`
- `0x1800435ec`
- `0x1800444dc`
- `0x18004575c`
- `0x1800464ec`
- `0x18008315c`
- `0x180088078`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800438d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043abb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043b95`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d6a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800438d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043abb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043b95`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d6a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180043e1f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180043e1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043711`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043796`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800442ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800443a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043711`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043796`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800442ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800443a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800442c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004437a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004441b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004448d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800442c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004437a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004441b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004448d`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x18004444b`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x18004444b`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180043818`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180043818`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeDomainControllerInfoW` at `0x18004443c`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeDomainControllerInfoW` at `0x18004443c`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsGetDomainControllerInfoW` at `0x180043a2e`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsGetDomainControllerInfoW` at `0x180043a2e`
- `ntdll!RtlEqualUnicodeString` at `0x180043fe2`
- `ntdll!RtlEqualUnicodeString` at `0x18004413e`
- `ntdll!RtlEqualUnicodeString` at `0x180043fe2`
- `ntdll!RtlEqualUnicodeString` at `0x18004413e`
- `ntdll!RtlLeaveCriticalSection` at `0x18004440a`
- `ntdll!RtlLeaveCriticalSection` at `0x18004440a`
- `ntdll!RtlEnterCriticalSection` at `0x180043dec`
- `ntdll!RtlEnterCriticalSection` at `0x180043dec`
- `netutils!NetpwNameCompare` at `0x180043e67`
- `netutils!NetpwNameCompare` at `0x180043e67`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsFreeServersAndSitesForNetLogon` at `0x180044464`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsFreeServersAndSitesForNetLogon` at `0x180044464`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsGetServersAndSitesForNetLogon` at `0x180043b35`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsGetServersAndSitesForNetLogon` at `0x180043b35`

## string_xrefs

- `0x18004382c`: `NlSitesUpdateSiteCoverage: CrackNames failed: %ld\n`
- `0x18004389f`: `NlSitesUpdateSiteCoverage: CrackNameStatus bad: %ws %ws: %ld\n`
- `0x180043a42`: `NlSitesUpdateSiteCoverage: Cannot DsGetDomainControllerInfoW %ld.\n`
- `0x180043c8b`: `%hs: %ws: '%ws' has cheaper link costs than '%ws'\n`

## pseudocode

```c
__int64 __fastcall NlSitesUpdateSiteCoverageForRole_Old(
        struct _DOMAIN_INFO *a1,
        int a2,
        void *a3,
        struct _ISM_CONNECTIVITY *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned __int8 *a7)
{
  int v7; // r13d
  struct _DOMAIN_INFO *v8; // r15
  int v10; // ecx
  struct _ISM_CONNECTIVITY *v11; // r14
  int v12; // r10d
  char v13; // r12
  unsigned int v14; // edi
  const char *v15; // rax
  const char *v16; // rcx
  wchar_t *v17; // rcx
  int v18; // eax
  int v19; // r10d
  volatile signed __int32 **v20; // rsi
  unsigned int v21; // r12d
  _DWORD *v22; // rax
  DWORD v23; // esi
  DWORD v24; // eax
  PDS_NAME_RESULTW v25; // rcx
  int v26; // r14d
  PDS_NAME_RESULT_ITEMW rItems; // rax
  LPWSTR pName; // rdi
  LPWSTR pDomain; // r12
  PDS_NAME_RESULT_ITEMW v30; // rcx
  unsigned int v31; // eax
  int v32; // ebx
  int v33; // esi
  const char *v34; // r13
  __int64 v35; // rbx
  unsigned int v36; // r15d
  unsigned int v37; // esi
  unsigned int v38; // r12d
  __int64 v39; // rdi
  unsigned int v40; // r10d
  __int64 v41; // r14
  unsigned __int16 *v42; // rdx
  DWORD DomainControllerInfoW; // eax
  DWORD v44; // eax
  __int64 v45; // rdi
  int v46; // ebx
  __int64 v47; // rcx
  int ServersAndSitesForNetLogon; // eax
  _QWORD *v49; // rbx
  int v50; // edi
  __int64 v51; // rcx
  int v52; // r12d
  unsigned int v53; // r9d
  unsigned int v54; // r8d
  __int64 v55; // rax
  __int64 v56; // r9
  wchar_t *v57; // rdi
  const char *v58; // r14
  struct _NL_COVERED_SITE *v59; // r13
  wchar_t *v60; // rax
  wchar_t *v61; // rbx
  unsigned __int16 *v62; // rdx
  __int64 v63; // rax
  _QWORD *v64; // rbx
  unsigned __int16 *v65; // rsi
  __int64 v66; // rdx
  unsigned int v67; // r12d
  unsigned int v68; // r14d
  int v69; // r13d
  __int64 v70; // rax
  unsigned int v71; // ebx
  _QWORD *v72; // r13
  int v73; // eax
  unsigned int v74; // ecx
  unsigned __int16 *v75; // rax
  unsigned int v76; // ecx
  int v77; // r13d
  __int64 v78; // r14
  unsigned int v79; // ebx
  _QWORD *v80; // r13
  int v81; // eax
  char v82; // r8
  unsigned int v83; // ebx
  WCHAR *v84; // rax
  __int64 v85; // r9
  unsigned int v86; // ebx
  void *v87; // rsi
  void *v88; // rcx
  HLOCAL v89; // rax
  unsigned int i; // ebx
  void *v91; // rcx
  HLOCAL v92; // rax
  unsigned int j; // ebx
  unsigned int k; // ebx
  DWORD cNames[2]; // [rsp+20h] [rbp-E0h]
  char v97; // [rsp+40h] [rbp-C0h]
  unsigned int v98; // [rsp+44h] [rbp-BCh]
  unsigned int v99; // [rsp+44h] [rbp-BCh]
  char v100; // [rsp+48h] [rbp-B8h]
  __int64 v102; // [rsp+50h] [rbp-B0h]
  _DWORD *hMem; // [rsp+58h] [rbp-A8h]
  int v104; // [rsp+60h] [rbp-A0h]
  int v105; // [rsp+64h] [rbp-9Ch]
  unsigned int v106; // [rsp+68h] [rbp-98h] BYREF
  int v107; // [rsp+6Ch] [rbp-94h]
  int v108; // [rsp+70h] [rbp-90h]
  int v109; // [rsp+74h] [rbp-8Ch]
  void *Src; // [rsp+78h] [rbp-88h]
  DWORD pcOut; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *Str; // [rsp+88h] [rbp-78h]
  LPCWSTR rpNames; // [rsp+90h] [rbp-70h] BYREF
  struct _DOMAIN_INFO *v114; // [rsp+98h] [rbp-68h]
  const char *v115; // [rsp+A0h] [rbp-60h]
  void *ppInfo; // [rsp+A8h] [rbp-58h] BYREF
  PDS_NAME_RESULTW pResult; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v118; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR *v119; // [rsp+C0h] [rbp-40h]
  _QWORD *v120; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 *v121; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v122[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v123; // [rsp+E8h] [rbp-18h]
  WCHAR DomainName[256]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v125[256]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v7 = 0;
  v8 = a1;
  v114 = a1;
  v121 = a7;
  v109 = a2;
  v10 = a2 & 0x2000;
  v118 = a5;
  v97 = 0;
  v11 = a4;
  ppInfo = 0;
  v12 = 0;
  pcOut = 0;
  v13 = 0;
  pResult = 0;
  v14 = 0;
  v120 = 0;
  v106 = 0;
  v105 = a2 & 0x8000;
  v107 = v10;
  if ( (a2 & 0x8000) != 0 )
  {
    v15 = "GC";
LABEL_5:
    v115 = v15;
    goto LABEL_9;
  }
  if ( (a2 & 0x2000) != 0 )
  {
    v15 = "DC";
    goto LABEL_5;
  }
  v16 = "NDNC";
  if ( (a2 & 0x4000) == 0 )
    v16 = 0;
  v115 = v16;
  v10 = v107;
LABEL_9:
  if ( a4 )
    v12 = *(_DWORD *)a4;
  if ( (a2 & 0x8000) != 0 )
  {
    v17 = (wchar_t *)qword_1800F1208;
  }
  else if ( v10 )
  {
    v17 = (wchar_t *)qword_1800F1200;
  }
  else
  {
    Str = 0;
    if ( (a2 & 0x4000) == 0 )
      goto LABEL_19;
    v17 = (wchar_t *)qword_1800F1210;
  }
  Str = v17;
  if ( v17 )
  {
    v18 = NetpTStrArrayEntryCount();
    v12 = v18 + v19;
  }
LABEL_19:
  Src = LocalAlloc(0x40u, 16LL * (unsigned int)(v12 + 1));
  v20 = (volatile signed __int32 **)Src;
  if ( !Src )
  {
LABEL_20:
    v7 = 8;
    goto LABEL_230;
  }
  v21 = 0;
  hMem = 0;
  v98 = 0;
  v104 = 0;
  v100 = 0;
  NlCaptureDomainInfo(v8, DomainName, 0);
  NlCaptureDnsForestName(v125);
  v22 = 0;
  if ( dword_1800F1218 && v11 && *(_DWORD *)v11 )
  {
    v98 = *(_DWORD *)v11;
    v21 = *(_DWORD *)v11;
    v22 = LocalAlloc(0x40u, 4LL * *(unsigned int *)v11);
    hMem = v22;
    if ( !v22 )
    {
      v13 = 0;
      goto LABEL_20;
    }
    v23 = 0;
    if ( a3 )
    {
      if ( v105 )
      {
        rpNames = L".";
        if ( (NlGetDomainFlags(v8) & 4) == 0 )
        {
          NlPrintRoutine(0x8000000u, L"GC: This DC isn't a GC. So it doesn't auto cover any sites as a GC.\n");
LABEL_84:
          v52 = v105;
          v33 = v105;
          v108 = v105;
          goto LABEL_115;
        }
        v24 = DsCrackNamesW(a3, DS_NAME_NO_FLAGS, (DS_NAME_FORMAT)-15, (DS_NAME_FORMAT)-15, 1u, &rpNames, &pResult);
        v104 = v24;
        v7 = v24;
        if ( v24 )
        {
          NlPrintRoutine(0x100u, L"NlSitesUpdateSiteCoverage: CrackNames failed: %ld\n", v24);
          goto LABEL_84;
        }
        v25 = pResult;
        v26 = 0;
        if ( pResult->cItems )
        {
LABEL_33:
          rItems = v25->rItems;
          pName = rItems[v26].pName;
          pDomain = rItems[v26].pDomain;
          NlPrintRoutine(0x20u, L"GC list: %ws %ws\n", pName, pDomain);
          v30 = pResult->rItems;
          if ( v30[v26].status )
          {
            cNames[0] = v30[v26].status;
            NlPrintRoutine(
              0x100u,
              L"NlSitesUpdateSiteCoverage: CrackNameStatus bad: %ws %ws: %ld\n",
              pName,
              pDomain,
              *(_QWORD *)cNames);
            goto LABEL_41;
          }
          v31 = v98;
          v32 = 0;
          if ( !v98 )
          {
LABEL_40:
            NlPrintRoutine(0x100u, L"GC: %ws %ws: isn't a site returned from ISM. (ignored)\n", pName, pDomain);
            goto LABEL_41;
          }
          while ( 1 )
          {
            if ( pName )
            {
              if ( !(unsigned int)_o__wcsicmp(pName) )
              {
                ++hMem[v32];
                v100 = 1;
LABEL_41:
                v25 = pResult;
                if ( ++v26 >= pResult->cItems )
                {
                  v8 = v114;
                  v11 = a4;
                  v21 = v98;
                  goto LABEL_43;
                }
                goto LABEL_33;
              }
              v31 = v98;
            }
            if ( ++v32 >= v31 )
              goto LABEL_40;
          }
        }
      }
      else
      {
        if ( !v107 )
        {
          if ( (v109 & 0x4000) == 0 )
            goto LABEL_44;
          if ( !(unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent() )
          {
            v7 = 50;
            v104 = 50;
            goto LABEL_84;
          }
          ServersAndSitesForNetLogon = DsGetServersAndSitesForNetLogon(DomainName, &v120);
          v104 = ServersAndSitesForNetLogon;
          v7 = ServersAndSitesForNetLogon;
          if ( !ServersAndSitesForNetLogon && (v49 = v120) != 0 )
          {
            while ( *v49 )
            {
              NlPrintRoutine(0x20u, L"NDNC list: %ws %ws\n", v49[1]);
              v50 = 0;
              if ( v21 )
              {
                while ( 1 )
                {
                  v51 = v49[1];
                  if ( v51 )
                  {
                    if ( !(unsigned int)_o__wcsicmp(v51) )
                      break;
                  }
                  if ( ++v50 >= v21 )
                    goto LABEL_79;
                }
                v22 = hMem;
                v100 = 1;
                ++hMem[v50];
              }
              else
              {
LABEL_79:
                NlPrintRoutine(0x100u, L"NDNC: %ws %ws: isn't a site returned from ISM. (ignored)\n", v49[1], *v49);
                v22 = hMem;
              }
              v49 += 2;
              if ( !v49 )
                goto LABEL_44;
            }
          }
          else
          {
            v104 = ServersAndSitesForNetLogon;
          }
          goto LABEL_43;
        }
        DomainControllerInfoW = DsGetDomainControllerInfoW(a3, DomainName, 3u, &pcOut, &ppInfo);
        v104 = DomainControllerInfoW;
        v7 = DomainControllerInfoW;
        if ( DomainControllerInfoW )
        {
          NlPrintRoutine(
            0x100u,
            L"NlSitesUpdateSiteCoverage: Cannot DsGetDomainControllerInfoW %ld.\n",
            DomainControllerInfoW);
          v44 = 0;
          pcOut = 0;
        }
        else
        {
          v44 = pcOut;
        }
        if ( !v44 )
        {
LABEL_43:
          v22 = hMem;
          goto LABEL_44;
        }
        do
        {
          v45 = 136LL * v23;
          NlPrintRoutine(
            0x20u,
            L"DC list: %ws %ws\n",
            *(_QWORD *)((char *)ppInfo + v45 + 16),
            *(_QWORD *)((char *)ppInfo + v45 + 8));
          v46 = 0;
          if ( v21 )
          {
            while ( 1 )
            {
              v47 = *(_QWORD *)((char *)ppInfo + v45 + 16);
              if ( v47 )
              {
                if ( !(unsigned int)_o__wcsicmp(v47) )
                  break;
              }
              if ( ++v46 >= v21 )
                goto LABEL_64;
            }
            ++hMem[v46];
            v100 = 1;
          }
          else
          {
LABEL_64:
            NlPrintRoutine(
              0x100u,
              L"DC: %ws %ws: isn't a site returned from ISM. (ignored)\n",
              *(_QWORD *)((char *)ppInfo + v45 + 16),
              *(_QWORD *)((char *)ppInfo + v45 + 8));
          }
          ++v23;
        }
        while ( v23 < pcOut );
        v8 = v114;
      }
      v11 = a4;
      goto LABEL_43;
    }
  }
LABEL_44:
  v33 = v105;
  v108 = v105;
  if ( v100 && v21 )
  {
    v34 = v115;
    v35 = 0;
    v36 = 0;
    while ( 1 )
    {
      if ( v22[v35] )
        goto LABEL_112;
      if ( !(unsigned int)NlValidateSiteName_Old(*(PCWSTR *)(*((_QWORD *)v11 + 1) + 8 * v35)) )
        goto LABEL_111;
      NlPrintRoutine(0x8000000u, L"%hs: %ws: Site has no %hss\n", v34, *(_QWORD *)(*((_QWORD *)v11 + 1) + 8 * v35), v34);
      v37 = -1;
      v38 = 0;
      v39 = 0;
      LODWORD(rpNames) = v98 * v36;
      v40 = v98;
      do
      {
        if ( v36 == v38 )
          goto LABEL_101;
        v41 = *((_QWORD *)v11 + 2);
        if ( !(unsigned int)NlValidateSiteName_Old(*(PCWSTR *)(*((_QWORD *)a4 + 1) + 8 * v39)) )
        {
          v42 = L"%hs: %ws: Site '%ws' is invalid.\n";
LABEL_53:
          v11 = a4;
          NlPrintRoutine(
            0x8000000u,
            v42,
            v34,
            *(_QWORD *)(*((_QWORD *)v11 + 1) + 8 * v35),
            *(_QWORD *)(*((_QWORD *)v11 + 1) + 8 * v39));
          goto LABEL_100;
        }
        v53 = *(_DWORD *)(v41 + 12LL * ((unsigned int)rpNames + v38));
        if ( v53 == -1 )
        {
          v42 = L"%hs: %ws: Site '%ws' has infinite cost.\n";
          goto LABEL_53;
        }
        v11 = a4;
        v54 = hMem[v39];
        if ( v54 )
        {
          if ( v37 == -1 )
          {
            NlPrintRoutine(
              0x8000000u,
              L"%hs: %ws: Site '%ws' is the first valid site.\n",
              v34,
              *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v35),
              *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v39));
LABEL_92:
            v37 = v38;
            goto LABEL_100;
          }
          v55 = *((_QWORD *)a4 + 2);
          if ( v53 < *(_DWORD *)(v55 + 12LL * ((unsigned int)rpNames + v37)) )
          {
            NlPrintRoutine(
              0x8000000u,
              L"%hs: %ws: '%ws' has cheaper link costs than '%ws'\n",
              v34,
              *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v35),
              *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v39),
              *(_QWORD *)(*((_QWORD *)a4 + 1) + 8LL * v37));
            goto LABEL_92;
          }
          if ( v53 == *(_DWORD *)(v55 + 12LL * ((unsigned int)rpNames + v37)) )
          {
            if ( v54 > hMem[v37] )
            {
              NlPrintRoutine(
                0x8000000u,
                L"%hs: %ws: '%ws' has more DCs than '%ws'\n",
                v34,
                *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v35),
                *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v39),
                *(_QWORD *)(*((_QWORD *)a4 + 1) + 8LL * v37));
              goto LABEL_98;
            }
            if ( v54 == hMem[v37] && (int)_o__wcsicmp(*(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v39)) < 0 )
            {
              NlPrintRoutine(
                0x8000000u,
                L"%hs: %ws: '%ws' is alphabetically before '%ws'\n",
                v34,
                *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v35),
                *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v39),
                *(_QWORD *)(*((_QWORD *)a4 + 1) + 8LL * v37));
LABEL_98:
              v37 = v38;
            }
            v11 = a4;
          }
        }
        else
        {
          NlPrintRoutine(
            0x8000000u,
            L"%hs: %ws: Site '%ws' has no Dcs.\n",
            v34,
            *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v35),
            *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v39));
        }
LABEL_100:
        v40 = v98;
LABEL_101:
        ++v38;
        ++v39;
      }
      while ( v38 < v40 );
      v56 = *((_QWORD *)v11 + 1);
      if ( v37 == a6 )
      {
        NlPrintRoutine(0x20u, L"%hs: %ws: Site is auto covered by our site.\n", v34, *(_QWORD *)(v56 + 8 * v35));
        NlSitesAddCloseSite_Old(
          *(unsigned __int16 **)(*((_QWORD *)v11 + 1) + 8 * v35),
          (struct _NL_COVERED_SITE *)Src,
          &v106,
          1u);
      }
      else if ( v37 == -1 )
      {
        NlPrintRoutine(0x20u, L"%hs: %ws: Site is not auto covered by any site.\n", v34, *(_QWORD *)(v56 + 8 * v35));
      }
      else
      {
        NlPrintRoutine(
          0x20u,
          L"%hs: %ws: Site is auto covered by site '%ws'.\n",
          v34,
          *(_QWORD *)(v56 + 8 * v35),
          *(_QWORD *)(v56 + 8LL * v37));
      }
      v21 = v98;
LABEL_111:
      v22 = hMem;
LABEL_112:
      ++v36;
      ++v35;
      if ( v36 >= v21 )
      {
        v8 = v114;
        v7 = v104;
        v33 = v108;
        break;
      }
    }
  }
  v52 = v33;
LABEL_115:
  RtlEnterCriticalSection(&NlGlobalSiteCritSect);
  v57 = Str;
  if ( !Str )
    goto LABEL_137;
  v58 = v115;
  v59 = (struct _NL_COVERED_SITE *)Src;
  while ( *v57 )
  {
    v60 = wcsstr(v57, L"\\");
    v61 = v60;
    if ( !v60 )
    {
      NlPrintRoutine(0x20u, L"%hs: %ws: Site is covered by our site (regkey).\n", v58, v57);
      NlSitesAddCloseSite_Old(v57, v59, &v106, 0);
      goto LABEL_133;
    }
    *v60 = 0;
    if ( v33 )
    {
      v62 = v125;
      goto LABEL_127;
    }
    if ( !v107 )
    {
      if ( (v109 & 0x4000) == 0 )
        goto LABEL_128;
      v62 = DomainName;
LABEL_127:
      if ( (unsigned int)NlEqualDnsName(v57, v62) )
        goto LABEL_128;
      goto LABEL_131;
    }
    if ( (unsigned int)NlEqualDnsName(v57, DomainName) || !(unsigned int)NetpwNameCompare(v57, (char *)v8 + 72, 6) )
    {
LABEL_128:
      if ( v61[1] )
      {
        NlPrintRoutine(0x20u, L"%hs: %ws: Site is covered by our site (regkey).\n", v58, v61 + 1);
        NlSitesAddCloseSite_Old(v61 + 1, v59, &v106, 0);
      }
      v57 = Str;
    }
LABEL_131:
    *v61 = 92;
LABEL_133:
    v63 = -1;
    do
      ++v63;
    while ( v57[v63] );
    v57 += (unsigned int)(v63 + 1);
    Str = v57;
  }
  v7 = v104;
  v52 = v105;
LABEL_137:
  v64 = Src;
  v65 = v118;
  NlSitesAddCloseSite_Old(v118, (struct _NL_COVERED_SITE *)Src, &v106, 0);
  if ( v52 )
  {
    v66 = *((_QWORD *)v8 + 78);
    v67 = *((_DWORD *)v8 + 158);
  }
  else if ( v107 || (v109 & 0x4000) != 0 )
  {
    v66 = *((_QWORD *)v8 + 76);
    v67 = *((_DWORD *)v8 + 154);
  }
  else
  {
    v66 = 0;
    v67 = 0;
  }
  v14 = v106;
  v68 = 0;
  v102 = v66;
  v99 = v67;
  if ( v106 )
  {
    v69 = v108;
    while ( 1 )
    {
      v122[0] = v65;
      v123 = 0;
      v70 = v64[2 * v68];
      v71 = 0;
      v122[1] = (unsigned __int16 *)(v70 + 40);
      if ( v67 )
      {
        v72 = Src;
        do
        {
          if ( RtlEqualUnicodeString(
                 (PCUNICODE_STRING)(v72[2 * v68] + 24LL),
                 (PCUNICODE_STRING)(*(_QWORD *)(v102 + 16LL * v71) + 24LL),
                 1u) )
          {
            break;
          }
          ++v71;
        }
        while ( v71 < v67 );
        v14 = v106;
        v8 = v114;
        v69 = v108;
      }
      v73 = *((_DWORD *)Src + 4 * v68 + 2);
      if ( v71 == v67 )
        break;
      v66 = v102;
      if ( v73 && !*(_DWORD *)(v102 + 16LL * v71 + 8) )
      {
        if ( v69 )
        {
          v74 = 5796;
LABEL_155:
          v75 = v125;
LABEL_170:
          v123 = v75;
          NlpWriteEventlogEx(v74, 4u, 0x20000000u, 0xFFFFFFFF, v122, 3u, 0, 0);
LABEL_171:
          v66 = v102;
          goto LABEL_172;
        }
        if ( v107 )
        {
          v74 = 5794;
          goto LABEL_158;
        }
        if ( (v109 & 0x4000) == 0 )
          goto LABEL_172;
        v74 = 5798;
LABEL_169:
        v75 = DomainName;
        goto LABEL_170;
      }
LABEL_172:
      v65 = v118;
      if ( ++v68 >= v14 )
      {
        v7 = v104;
        goto LABEL_174;
      }
      v64 = Src;
    }
    v97 = 1;
    if ( !v73 )
      goto LABEL_171;
    if ( v69 )
    {
      v74 = 5786;
      goto LABEL_155;
    }
    if ( v107 )
    {
      v74 = 5784;
LABEL_158:
      v75 = (unsigned __int16 *)((char *)v8 + 72);
      goto LABEL_170;
    }
    if ( (v109 & 0x4000) == 0 )
      goto LABEL_171;
    v74 = 5792;
    goto LABEL_169;
  }
LABEL_174:
  v76 = 0;
  v106 = 0;
  if ( !v67 )
  {
    v87 = hMem;
    goto LABEL_207;
  }
  v77 = v108;
  v78 = 0;
  do
  {
    v119 = 0;
    v79 = 0;
    v118 = (unsigned __int16 *)(*(_QWORD *)(v66 + 16 * v78) + 40LL);
    if ( v14 )
    {
      v80 = Src;
      do
      {
        if ( RtlEqualUnicodeString(
               (PCUNICODE_STRING)(*(_QWORD *)(v102 + 16 * v78) + 24LL),
               (PCUNICODE_STRING)(v80[2 * v79] + 24LL),
               1u) )
        {
          break;
        }
        ++v79;
      }
      while ( v79 < v14 );
      v8 = v114;
      v67 = v99;
      v76 = v106;
      v66 = v102;
      v77 = v108;
    }
    v81 = *(_DWORD *)(v66 + 16 * v78 + 8);
    if ( v79 == v14 )
    {
      v82 = 1;
      v97 = 1;
      if ( !v81 )
        goto LABEL_202;
      if ( v77 )
      {
        v83 = 5787;
        goto LABEL_185;
      }
      if ( v107 )
      {
        v83 = 5785;
LABEL_188:
        v84 = (WCHAR *)((char *)v8 + 72);
        goto LABEL_200;
      }
      if ( (v109 & 0x4000) == 0 )
        goto LABEL_202;
      v83 = 5793;
LABEL_199:
      v84 = DomainName;
      goto LABEL_200;
    }
    if ( !v81 || *((_DWORD *)Src + 4 * v79 + 2) )
      goto LABEL_201;
    if ( v77 )
    {
      v83 = 5797;
LABEL_185:
      v84 = v125;
LABEL_200:
      v85 = *(_QWORD *)(v66 + 16 * v78);
      v119 = v84;
      NlPrintRoutine(0x20u, L"%hs: %ws: Site is no longer auto covered by our site.\n", v115, v85 + 40);
      NlpWriteEventlogEx(v83, 4u, 0x20000000u, 0xFFFFFFFF, &v118, 2u, 0, 0);
      v76 = v106;
      v66 = v102;
      goto LABEL_201;
    }
    if ( v107 )
    {
      v83 = 5795;
      goto LABEL_188;
    }
    if ( (v109 & 0x4000) != 0 )
    {
      v83 = 5799;
      goto LABEL_199;
    }
LABEL_201:
    v82 = v97;
LABEL_202:
    ++v76;
    ++v78;
    v106 = v76;
  }
  while ( v76 < v67 );
  v7 = v104;
  v86 = 0;
  v87 = hMem;
  v97 = v82;
  do
  {
    NlDerefSiteEntry(*(volatile signed __int32 **)(v66 + 16LL * v86));
    v66 = v102;
    ++v86;
  }
  while ( v86 < v67 );
LABEL_207:
  if ( v105 )
  {
    v88 = (void *)*((_QWORD *)v8 + 78);
    if ( v88 )
    {
      LocalFree(v88);
      *((_QWORD *)v8 + 78) = 0;
      *((_DWORD *)v8 + 158) = 0;
    }
    if ( v14 )
    {
      v89 = LocalAlloc(0, 16LL * v14);
      *((_QWORD *)v8 + 78) = v89;
      if ( v89 )
      {
        memcpy_0(v89, Src, 16LL * v14);
        *((_DWORD *)v8 + 158) = v14;
      }
      else
      {
        v7 = 8;
      }
    }
    for ( i = 0; i < *((_DWORD *)v8 + 158); ++i )
      NlRefSiteEntry(*(struct _NL_SITE_ENTRY **)(*((_QWORD *)v8 + 78) + 16LL * i));
  }
  else if ( v107 || (v109 & 0x4000) != 0 )
  {
    v91 = (void *)*((_QWORD *)v8 + 76);
    if ( v91 )
    {
      LocalFree(v91);
      *((_QWORD *)v8 + 76) = 0;
      *((_DWORD *)v8 + 154) = 0;
    }
    if ( v14 )
    {
      v92 = LocalAlloc(0, 16LL * v14);
      *((_QWORD *)v8 + 76) = v92;
      if ( v92 )
      {
        memcpy_0(v92, Src, 16LL * v14);
        *((_DWORD *)v8 + 154) = v14;
      }
      else
      {
        v7 = 8;
      }
    }
    for ( j = 0; j < *((_DWORD *)v8 + 154); ++j )
      NlRefSiteEntry(*(struct _NL_SITE_ENTRY **)(*((_QWORD *)v8 + 76) + 16LL * j));
  }
  RtlLeaveCriticalSection(&NlGlobalSiteCritSect);
  if ( v87 )
    LocalFree(v87);
  v13 = v97;
  v20 = (volatile signed __int32 **)Src;
LABEL_230:
  if ( ppInfo )
    DsFreeDomainControllerInfoW(3u, pcOut, ppInfo);
  if ( pResult )
    DsFreeNameResultW(pResult);
  if ( v120 && (unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent() )
    DsFreeServersAndSitesForNetLogon(v120);
  if ( v20 )
  {
    for ( k = 0; k < v14; ++k )
      NlDerefSiteEntry(v20[2 * k]);
    LocalFree(v20);
  }
  if ( !v7 && v121 && v13 )
    *v121 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800435ec  mov     [rsp-8+arg_8], rbx
0x1800435f1  push    rbp
0x1800435f2  push    rsi
0x1800435f3  push    rdi
0x1800435f4  push    r12
0x1800435f6  push    r13
0x1800435f8  push    r14
0x1800435fa  push    r15
0x1800435fc  lea     rbp, [rsp-400h]
0x180043604  sub     rsp, 500h
0x18004360b  mov     rax, cs:__security_cookie
0x180043612  xor     rax, rsp
0x180043615  mov     [rbp+430h+var_40], rax
0x18004361c  mov     rax, [rbp+430h+arg_20]
0x180043623  xor     r13d, r13d
0x180043626  mov     r15, rcx
0x180043629  mov     [rbp+430h+var_498], rcx
0x18004362d  mov     rcx, [rbp+430h+arg_30]
0x180043634  mov     rbx, r8
0x180043637  mov     [rbp+430h+var_460], rcx
0x18004363b  mov     r8d, edx
0x18004363e  and     r8d, 8000h
0x180043645  mov     [rsp+530h+var_4E0], r9
0x18004364a  mov     ecx, edx
0x18004364c  mov     [rsp+530h+var_4BC], edx
0x180043650  and     ecx, 2000h
0x180043656  mov     [rbp+430h+var_478], rax
0x18004365a  mov     [rsp+530h+var_4F0], r13b
0x18004365f  mov     r14, r9
0x180043662  mov     [rbp+430h+ppInfo], r13
0x180043666  mov     r10d, r13d
0x180043669  mov     [rbp+430h+pcOut], r13d
0x18004366d  mov     r12b, r13b
0x180043670  mov     [rbp+430h+pResult], r13
0x180043674  mov     edi, r13d
0x180043677  mov     [rbp+430h+var_468], r13
0x18004367b  mov     [rsp+530h+var_4C8], r13d
0x180043680  mov     [rsp+530h+var_4CC], r8d
0x180043685  mov     [rsp+530h+var_4C4], ecx
0x180043689  test    r8d, r8d
0x18004368c  jz      short loc_180043697
0x18004368e  lea     rax, aGc; "GC"
0x180043695  jmp     short loc_1800436A2
0x180043697  test    ecx, ecx
0x180043699  jz      short loc_1800436A8
0x18004369b  lea     rax, aDc_0; "DC"
0x1800436a2  mov     [rbp+430h+var_490], rax
0x1800436a6  jmp     short loc_1800436BF
0x1800436a8  bt      edx, 0Eh
0x1800436ac  lea     rcx, aNdnc; "NDNC"
0x1800436b3  cmovnb  rcx, r13
0x1800436b7  mov     [rbp+430h+var_490], rcx
0x1800436bb  mov     ecx, [rsp+530h+var_4C4]
0x1800436bf  test    r14, r14
0x1800436c2  jz      short loc_1800436C7
0x1800436c4  mov     r10d, [r9]
0x1800436c7  test    r8d, r8d
0x1800436ca  jz      short loc_1800436D5
0x1800436cc  mov     rcx, cs:qword_1800F1208
0x1800436d3  jmp     short loc_1800436F3
0x1800436d5  test    ecx, ecx
0x1800436d7  jz      short loc_1800436E2
0x1800436d9  mov     rcx, cs:qword_1800F1200
0x1800436e0  jmp     short loc_1800436F3
0x1800436e2  bt      edx, 0Eh
0x1800436e6  mov     [rbp+430h+Str], r13
0x1800436ea  jnb     short loc_180043704
0x1800436ec  mov     rcx, cs:qword_1800F1210
0x1800436f3  mov     [rbp+430h+Str], rcx
0x1800436f7  test    rcx, rcx
0x1800436fa  jz      short loc_180043704
0x1800436fc  call    NetpTStrArrayEntryCount
0x180043701  add     r10d, eax
0x180043704  lea     edx, [r10+1]
0x180043708  mov     ecx, 40h ; '@'; uFlags
0x18004370d  shl     rdx, 4; uBytes
0x180043711  call    cs:__imp_LocalAlloc
0x180043717  mov     [rsp+530h+Src], rax
0x18004371c  mov     rsi, rax
0x18004371f  test    rax, rax
0x180043722  jnz     short loc_180043732
0x180043724  mov     r13d, 8
0x18004372a  xor     r14d, r14d
0x18004372d  jmp     loc_18004442B
0x180043732  xor     r12d, r12d
0x180043735  mov     [rsp+530h+hMem], r13
0x18004373a  xor     r8d, r8d; struct _GUID *
0x18004373d  mov     [rsp+530h+var_4EC], r12d
0x180043742  lea     rdx, [rbp+430h+DomainName]; unsigned __int16 *
0x180043746  mov     [rsp+530h+var_4D0], r13d
0x18004374b  mov     rcx, r15; struct _DOMAIN_INFO *
0x18004374e  mov     [rsp+530h+var_4E8], dil
0x180043753  call    ?NlCaptureDomainInfo@@YAPEAU_GUID@@PEAU_DOMAIN_INFO@@QEAGPEAU1@@Z; NlCaptureDomainInfo(_DOMAIN_INFO *,ushort * const,_GUID *)
0x180043758  lea     rcx, [rbp+430h+var_240]; unsigned __int16 *
0x18004375f  call    ?NlCaptureDnsForestName@@YAXQEAG@Z; NlCaptureDnsForestName(ushort * const)
0x180043764  xor     eax, eax
0x180043766  cmp     cs:dword_1800F1218, eax
0x18004376c  jz      loc_180043BFC
0x180043772  test    r14, r14
0x180043775  jz      loc_180043BFC
0x18004377b  cmp     [r14], eax
0x18004377e  jz      loc_180043BFC
0x180043784  mov     r12d, [r14]
0x180043787  lea     ecx, [rax+40h]; uFlags
0x18004378a  mov     edx, r12d
0x18004378d  mov     [rsp+530h+var_4EC], r12d
0x180043792  shl     rdx, 2; uBytes
0x180043796  call    cs:__imp_LocalAlloc
0x18004379c  mov     [rsp+530h+hMem], rax
0x1800437a1  test    rax, rax
0x1800437a4  jnz     short loc_1800437AE
0x1800437a6  mov     r12b, dil
0x1800437a9  jmp     loc_180043724
0x1800437ae  xor     esi, esi
0x1800437b0  test    rbx, rbx
0x1800437b3  jz      loc_180043927
0x1800437b9  cmp     [rsp+530h+var_4CC], esi
0x1800437bd  jz      loc_180043A0A
0x1800437c3  lea     rax, asc_18009B71C; "."
0x1800437ca  mov     rcx, r15; struct _DOMAIN_INFO *
0x1800437cd  mov     [rbp+430h+var_4A0], rax
0x1800437d1  call    ?NlGetDomainFlags@@YAKPEAU_DOMAIN_INFO@@@Z; NlGetDomainFlags(_DOMAIN_INFO *)
0x1800437d6  test    al, 4
0x1800437d8  jnz     short loc_1800437F0
0x1800437da  lea     rdx, aGcThisDcIsnTAG; "GC: This DC isn't a GC. So it doesn't a"...
0x1800437e1  mov     ecx, 8000000h; unsigned int
0x1800437e6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800437eb  jmp     loc_180043BEA
0x1800437f0  lea     rax, [rbp+430h+pResult]
0x1800437f4  mov     r8d, 0FFFFFFF1h; formatOffered
0x1800437fa  mov     [rsp+530h+ppResult], rax; ppResult
0x1800437ff  mov     r9d, r8d; formatDesired
0x180043802  lea     rax, [rbp+430h+var_4A0]
0x180043806  xor     edx, edx; flags
0x180043808  mov     [rsp+530h+rpNames], rax; rpNames
0x18004380d  mov     rcx, rbx; hDS
0x180043810  mov     [rsp+530h+cNames], 1; cNames
0x180043818  call    cs:__imp_DsCrackNamesW
0x18004381e  mov     [rsp+530h+var_4D0], eax
0x180043822  mov     r13d, eax
0x180043825  test    eax, eax
0x180043827  jz      short loc_180043842
0x180043829  mov     r8d, eax
0x18004382c  lea     rdx, aNlsitesupdates_1; "NlSitesUpdateSiteCoverage: CrackNames f"...
0x180043833  mov     ecx, 100h; unsigned int
0x180043838  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004383d  jmp     loc_180043BEA
0x180043842  mov     rcx, [rbp+430h+pResult]
0x180043846  mov     r14d, esi
0x180043849  cmp     [rcx], esi
0x18004384b  jbe     loc_180043AFD
0x180043851  mov     r15, [rsp+530h+hMem]
0x180043856  jmp     short loc_18004385A
0x180043858  xor     esi, esi
0x18004385a  mov     eax, r14d
0x18004385d  lea     rdx, aGcListWsWs; "GC list: %ws %ws\n"
0x180043864  lea     rbx, [rax+rax*2]
0x180043868  mov     rax, [rcx+8]
0x18004386c  mov     ecx, 20h ; ' '; unsigned int
0x180043871  mov     rdi, [rax+rbx*8+10h]
0x180043876  mov     r12, [rax+rbx*8+8]
0x18004387b  mov     r8, rdi
0x18004387e  mov     r9, r12
0x180043881  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180043886  mov     rax, [rbp+430h+pResult]
0x18004388a  mov     rcx, [rax+8]
0x18004388e  mov     eax, [rcx+rbx*8]
0x180043891  test    eax, eax
0x180043893  jz      short loc_1800438B2
0x180043895  mov     r9, r12
0x180043898  mov     [rsp+530h+cNames], eax
0x18004389c  mov     r8, rdi
0x18004389f  lea     rdx, aNlsitesupdates; "NlSitesUpdateSiteCoverage: CrackNameSta"...
0x1800438a6  mov     ecx, 100h; unsigned int
0x1800438ab  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800438b0  jmp     short loc_180043904
0x1800438b2  mov     eax, [rsp+530h+var_4EC]
0x1800438b6  mov     ebx, esi
0x1800438b8  test    eax, eax
0x1800438ba  jz      short loc_1800438ED
0x1800438bc  test    rdi, rdi
0x1800438bf  jz      short loc_1800438E7
0x1800438c1  mov     rax, [rsp+530h+var_4E0]
0x1800438c6  mov     rcx, rdi
0x1800438c9  mov     esi, ebx
0x1800438cb  mov     rdx, [rax+8]
0x1800438cf  mov     rdx, [rdx+rsi*8]
0x1800438d3  call    cs:__imp__o__wcsicmp
0x1800438d9  test    eax, eax
0x1800438db  jz      loc_1800439FC
0x1800438e1  mov     eax, [rsp+530h+var_4EC]
0x1800438e5  xor     esi, esi
0x1800438e7  inc     ebx
0x1800438e9  cmp     ebx, eax
0x1800438eb  jb      short loc_1800438BC
0x1800438ed  mov     r9, r12
0x1800438f0  lea     rdx, aGcWsWsIsnTASit; "GC: %ws %ws: isn't a site returned from"...
0x1800438f7  mov     r8, rdi
0x1800438fa  mov     ecx, 100h; unsigned int
0x1800438ff  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180043904  mov     rcx, [rbp+430h+pResult]
0x180043908  inc     r14d
0x18004390b  cmp     r14d, [rcx]
0x18004390e  jb      loc_180043858
0x180043914  mov     r15, [rbp+430h+var_498]
0x180043918  mov     r14, [rsp+530h+var_4E0]
0x18004391d  mov     r12d, [rsp+530h+var_4EC]
0x180043922  mov     rax, [rsp+530h+hMem]
0x180043927  cmp     [rsp+530h+var_4E8], 0
0x18004392c  mov     esi, [rsp+530h+var_4CC]
0x180043930  mov     [rsp+530h+var_4C0], esi
0x180043934  jz      loc_180043DE2
0x18004393a  test    r12d, r12d
0x18004393d  jz      loc_180043DE2
0x180043943  mov     r13, [rbp+430h+var_490]
0x180043947  xor     ebx, ebx
0x180043949  mov     r15d, ebx
0x18004394c  cmp     dword ptr [rax+rbx*4], 0
0x180043950  jnz     loc_180043DC6
0x180043956  mov     rcx, [r14+8]
0x18004395a  mov     rcx, [rcx+rbx*8]; pszName
0x18004395e  call    ?NlValidateSiteName_Old@@YAHPEAG@Z; NlValidateSiteName_Old(ushort *)
0x180043963  test    eax, eax
0x180043965  jz      loc_180043DC1
0x18004396b  mov     r9, [r14+8]
0x18004396f  lea     rdx, aHsWsSiteHasNoH; "%hs: %ws: Site has no %hss\n"
0x180043976  mov     r8, r13
0x180043979  mov     qword ptr [rsp+530h+cNames], r13
0x18004397e  mov     ecx, 8000000h; unsigned int
0x180043983  mov     r9, [r9+rbx*8]
0x180043987  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004398c  mov     r10d, r15d
0x18004398f  or      esi, 0FFFFFFFFh
0x180043992  imul    r10d, [rsp+530h+var_4EC]
0x180043998  xor     r12d, r12d
0x18004399b  xor     edi, edi
0x18004399d  mov     dword ptr [rbp+430h+var_4A0], r10d
0x1800439a1  mov     r10d, [rsp+530h+var_4EC]
0x1800439a6  cmp     r15d, r12d
0x1800439a9  jz      loc_180043D08
0x1800439af  mov     rax, [rsp+530h+var_4E0]
0x1800439b4  mov     r14, [r14+10h]
0x1800439b8  mov     rcx, [rax+8]
0x1800439bc  mov     rcx, [rcx+rdi*8]; pszName
0x1800439c0  call    ?NlValidateSiteName_Old@@YAHPEAG@Z; NlValidateSiteName_Old(ushort *)
0x1800439c5  test    eax, eax
0x1800439c7  jnz     loc_180043C01
0x1800439cd  lea     rdx, aHsWsSiteWsIsIn; "%hs: %ws: Site '%ws' is invalid.\n"
0x1800439d4  mov     r14, [rsp+530h+var_4E0]
0x1800439d9  mov     r9, [r14+8]
0x1800439dd  mov     r8, r13
0x1800439e0  mov     ecx, 8000000h; unsigned int
0x1800439e5  mov     rax, [r9+rdi*8]
0x1800439e9  mov     r9, [r9+rbx*8]
0x1800439ed  mov     qword ptr [rsp+530h+cNames], rax
0x1800439f2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800439f7  jmp     loc_180043D03
0x1800439fc  inc     dword ptr [r15+rsi*4]
0x180043a00  mov     [rsp+530h+var_4E8], 1
0x180043a05  jmp     loc_180043904
0x180043a0a  cmp     [rsp+530h+var_4C4], esi
0x180043a0e  jz      loc_180043B12
0x180043a14  lea     rax, [rbp+430h+ppInfo]
0x180043a18  mov     r8d, 3; InfoLevel
0x180043a1e  lea     r9, [rbp+430h+pcOut]; pcOut
0x180043a22  mov     qword ptr [rsp+530h+cNames], rax; ppInfo
0x180043a27  lea     rdx, [rbp+430h+DomainName]; DomainName
0x180043a2b  mov     rcx, rbx; hDs
0x180043a2e  call    cs:__imp_DsGetDomainControllerInfoW
0x180043a34  mov     [rsp+530h+var_4D0], eax
0x180043a38  mov     r13d, eax
0x180043a3b  test    eax, eax
0x180043a3d  jz      short loc_180043A5A
0x180043a3f  mov     r8d, eax
0x180043a42  lea     rdx, aNlsitesupdates_0; "NlSitesUpdateSiteCoverage: Cannot DsGet"...
0x180043a49  mov     ecx, 100h; unsigned int
0x180043a4e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180043a53  mov     eax, esi
0x180043a55  mov     [rbp+430h+pcOut], eax
0x180043a58  jmp     short loc_180043A5D
0x180043a5a  mov     eax, [rbp+430h+pcOut]
0x180043a5d  test    eax, eax
0x180043a5f  jz      loc_180043922
0x180043a65  mov     r15, [rsp+530h+hMem]
0x180043a6a  mov     r8, [rbp+430h+ppInfo]
0x180043a6e  lea     rdx, aDcListWsWs; "DC list: %ws %ws\n"
0x180043a75  mov     eax, esi
0x180043a77  mov     ecx, 20h ; ' '; unsigned int
0x180043a7c  imul    rdi, rax, 88h
0x180043a83  mov     r9, [rdi+r8+8]
0x180043a88  mov     r8, [rdi+r8+10h]
0x180043a8d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180043a92  xor     r14d, r14d
0x180043a95  mov     ebx, r14d
0x180043a98  test    r12d, r12d
0x180043a9b  jz      short loc_180043ACF
0x180043a9d  mov     rax, [rbp+430h+ppInfo]
0x180043aa1  mov     rcx, [rdi+rax+10h]
0x180043aa6  test    rcx, rcx
0x180043aa9  jz      short loc_180043AC8
  ... truncated ...
```
