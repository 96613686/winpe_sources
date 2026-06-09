# NlSitesUpdateSiteCoverageForRole_Old(_DOMAIN_INFO *,ulong,void *,_ISM_CONNECTIVITY *,ushort *,ulong,uchar *)

- ea: `0x18004643c`
- end: `0x1800473b6`
- name: `?NlSitesUpdateSiteCoverageForRole_Old@@YAKPEAU_DOMAIN_INFO@@KPEAXPEAU_ISM_CONNECTIVITY@@PEAGKPEAE@Z`
- size: `3962`
- prototype: `unsigned int __usercall@<eax>(struct _DOMAIN_INFO *@<rcx>, unsigned int@<edx>, void *@<r8>, struct _ISM_CONNECTIVITY *@<r9>, unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020480`

## callees

- `0x180007518`
- `0x18000e910`
- `0x1800110ac`
- `0x18001fdb4`
- `0x180025eb8`
- `0x1800276ac`
- `0x180041fbc`
- `0x180044c44`
- `0x18004643c`
- `0x1800473bc`
- `0x1800486b4`
- `0x18004952c`
- `0x1800892fc`
- `0x18008e644`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046735`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046929`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046a0f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046bea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046735`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046929`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046a0f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046bea`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180046cab`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180046cab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046561`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800465ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047197`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047256`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046561`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800465ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047197`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047256`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004716b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004722a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800472dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047367`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004716b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004722a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800472dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047367`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180047319`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180047319`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180046674`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180046674`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeDomainControllerInfoW` at `0x180047304`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeDomainControllerInfoW` at `0x180047304`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsGetDomainControllerInfoW` at `0x180046896`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsGetDomainControllerInfoW` at `0x180046896`
- `ntdll!RtlEqualUnicodeString` at `0x180046e7a`
- `ntdll!RtlEqualUnicodeString` at `0x180046fdc`
- `ntdll!RtlEqualUnicodeString` at `0x180046e7a`
- `ntdll!RtlEqualUnicodeString` at `0x180046fdc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800472c6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800472c6`
- `ntdll!RtlEnterCriticalSection` at `0x180046c72`
- `ntdll!RtlEnterCriticalSection` at `0x180046c72`
- `netutils!NetpwNameCompare` at `0x180046cf9`
- `netutils!NetpwNameCompare` at `0x180046cf9`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsFreeServersAndSitesForNetLogon` at `0x180047338`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsFreeServersAndSitesForNetLogon` at `0x180047338`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsGetServersAndSitesForNetLogon` at `0x1800469a9`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsGetServersAndSitesForNetLogon` at `0x1800469a9`

## string_xrefs

- `0x18004668e`: `NlSitesUpdateSiteCoverage: CrackNames failed: %ld\n`
- `0x180046701`: `NlSitesUpdateSiteCoverage: CrackNameStatus bad: %ws %ws: %ld\n`
- `0x1800468b0`: `NlSitesUpdateSiteCoverage: Cannot DsGetDomainControllerInfoW %ld.\n`
- `0x180046b0b`: `%hs: %ws: '%ws' has cheaper link costs than '%ws'\n`

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
  HLOCAL *v20; // rsi
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
  unsigned int v32; // ebx
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
  unsigned int v46; // ebx
  __int64 v47; // rcx
  int ServersAndSitesForNetLogon; // eax
  _QWORD *v49; // rbx
  unsigned int v50; // edi
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
    v17 = (wchar_t *)qword_1800F8208;
  }
  else if ( v10 )
  {
    v17 = (wchar_t *)qword_1800F8200;
  }
  else
  {
    Str = 0;
    if ( (a2 & 0x4000) == 0 )
      goto LABEL_19;
    v17 = (wchar_t *)qword_1800F8210;
  }
  Str = v17;
  if ( v17 )
  {
    v18 = NetpTStrArrayEntryCount();
    v12 = v18 + v19;
  }
LABEL_19:
  Src = LocalAlloc(0x40u, 16LL * (unsigned int)(v12 + 1));
  v20 = (HLOCAL *)Src;
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
  if ( dword_1800F8218 && v11 && *(_DWORD *)v11 )
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
              if ( !(unsigned int)_o__wcsicmp(pName, *(_QWORD *)(*((_QWORD *)a4 + 1) + 8LL * v32)) )
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
                    if ( !(unsigned int)_o__wcsicmp(v51, *(_QWORD *)(*((_QWORD *)v11 + 1) + 8LL * v50)) )
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
                if ( !(unsigned int)_o__wcsicmp(v47, *(_QWORD *)(*((_QWORD *)a4 + 1) + 8LL * v46)) )
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
            if ( v54 == hMem[v37]
              && (int)_o__wcsicmp(
                        *(_QWORD *)(*((_QWORD *)a4 + 1) + 8 * v39),
                        *(_QWORD *)(*((_QWORD *)a4 + 1) + 8LL * v37)) < 0 )
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
    NlDerefSiteEntry(*(HLOCAL *)(v66 + 16LL * v86));
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
  v20 = (HLOCAL *)Src;
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
0x18004643c  mov     [rsp-8+arg_8], rbx
0x180046441  push    rbp
0x180046442  push    rsi
0x180046443  push    rdi
0x180046444  push    r12
0x180046446  push    r13
0x180046448  push    r14
0x18004644a  push    r15
0x18004644c  lea     rbp, [rsp-400h]
0x180046454  sub     rsp, 500h
0x18004645b  mov     rax, cs:__security_cookie
0x180046462  xor     rax, rsp
0x180046465  mov     [rbp+430h+var_40], rax
0x18004646c  mov     rax, [rbp+430h+arg_20]
0x180046473  xor     r13d, r13d
0x180046476  mov     r15, rcx
0x180046479  mov     [rbp+430h+var_498], rcx
0x18004647d  mov     rcx, [rbp+430h+arg_30]
0x180046484  mov     rbx, r8
0x180046487  mov     [rbp+430h+var_460], rcx
0x18004648b  mov     r8d, edx
0x18004648e  and     r8d, 8000h
0x180046495  mov     [rsp+530h+var_4E0], r9
0x18004649a  mov     ecx, edx
0x18004649c  mov     [rsp+530h+var_4BC], edx
0x1800464a0  and     ecx, 2000h
0x1800464a6  mov     [rbp+430h+var_478], rax
0x1800464aa  mov     [rsp+530h+var_4F0], r13b
0x1800464af  mov     r14, r9
0x1800464b2  mov     [rbp+430h+ppInfo], r13
0x1800464b6  mov     r10d, r13d
0x1800464b9  mov     [rbp+430h+pcOut], r13d
0x1800464bd  mov     r12b, r13b
0x1800464c0  mov     [rbp+430h+pResult], r13
0x1800464c4  mov     edi, r13d
0x1800464c7  mov     [rbp+430h+var_468], r13
0x1800464cb  mov     [rsp+530h+var_4C8], r13d
0x1800464d0  mov     [rsp+530h+var_4CC], r8d
0x1800464d5  mov     [rsp+530h+var_4C4], ecx
0x1800464d9  test    r8d, r8d
0x1800464dc  jz      short loc_1800464E7
0x1800464de  lea     rax, aGc; "GC"
0x1800464e5  jmp     short loc_1800464F2
0x1800464e7  test    ecx, ecx
0x1800464e9  jz      short loc_1800464F8
0x1800464eb  lea     rax, aDc_0; "DC"
0x1800464f2  mov     [rbp+430h+var_490], rax
0x1800464f6  jmp     short loc_18004650F
0x1800464f8  bt      edx, 0Eh
0x1800464fc  lea     rcx, aNdnc; "NDNC"
0x180046503  cmovnb  rcx, r13
0x180046507  mov     [rbp+430h+var_490], rcx
0x18004650b  mov     ecx, [rsp+530h+var_4C4]
0x18004650f  test    r14, r14
0x180046512  jz      short loc_180046517
0x180046514  mov     r10d, [r9]
0x180046517  test    r8d, r8d
0x18004651a  jz      short loc_180046525
0x18004651c  mov     rcx, cs:qword_1800F8208
0x180046523  jmp     short loc_180046543
0x180046525  test    ecx, ecx
0x180046527  jz      short loc_180046532
0x180046529  mov     rcx, cs:qword_1800F8200
0x180046530  jmp     short loc_180046543
0x180046532  bt      edx, 0Eh
0x180046536  mov     [rbp+430h+Str], r13
0x18004653a  jnb     short loc_180046554
0x18004653c  mov     rcx, cs:qword_1800F8210
0x180046543  mov     [rbp+430h+Str], rcx
0x180046547  test    rcx, rcx
0x18004654a  jz      short loc_180046554
0x18004654c  call    NetpTStrArrayEntryCount
0x180046551  add     r10d, eax
0x180046554  lea     edx, [r10+1]
0x180046558  mov     ecx, 40h ; '@'; uFlags
0x18004655d  shl     rdx, 4; uBytes
0x180046561  call    cs:__imp_LocalAlloc
0x180046568  nop     dword ptr [rax+rax+00h]
0x18004656d  mov     [rsp+530h+Src], rax
0x180046572  mov     rsi, rax
0x180046575  test    rax, rax
0x180046578  jnz     short loc_180046588
0x18004657a  mov     r13d, 8
0x180046580  xor     r14d, r14d
0x180046583  jmp     loc_1800472F3
0x180046588  xor     r12d, r12d
0x18004658b  mov     [rsp+530h+hMem], r13
0x180046590  xor     r8d, r8d; struct _GUID *
0x180046593  mov     [rsp+530h+var_4EC], r12d
0x180046598  lea     rdx, [rbp+430h+DomainName]; unsigned __int16 *
0x18004659c  mov     [rsp+530h+var_4D0], r13d
0x1800465a1  mov     rcx, r15; struct _DOMAIN_INFO *
0x1800465a4  mov     [rsp+530h+var_4E8], dil
0x1800465a9  call    ?NlCaptureDomainInfo@@YAPEAU_GUID@@PEAU_DOMAIN_INFO@@QEAGPEAU1@@Z; NlCaptureDomainInfo(_DOMAIN_INFO *,ushort * const,_GUID *)
0x1800465ae  lea     rcx, [rbp+430h+var_240]; unsigned __int16 *
0x1800465b5  call    ?NlCaptureDnsForestName@@YAXQEAG@Z; NlCaptureDnsForestName(ushort * const)
0x1800465ba  xor     eax, eax
0x1800465bc  cmp     cs:dword_1800F8218, eax
0x1800465c2  jz      loc_180046A7C
0x1800465c8  test    r14, r14
0x1800465cb  jz      loc_180046A7C
0x1800465d1  cmp     [r14], eax
0x1800465d4  jz      loc_180046A7C
0x1800465da  mov     r12d, [r14]
0x1800465dd  lea     ecx, [rax+40h]; uFlags
0x1800465e0  mov     edx, r12d
0x1800465e3  mov     [rsp+530h+var_4EC], r12d
0x1800465e8  shl     rdx, 2; uBytes
0x1800465ec  call    cs:__imp_LocalAlloc
0x1800465f3  nop     dword ptr [rax+rax+00h]
0x1800465f8  mov     [rsp+530h+hMem], rax
0x1800465fd  test    rax, rax
0x180046600  jnz     short loc_18004660A
0x180046602  mov     r12b, dil
0x180046605  jmp     loc_18004657A
0x18004660a  xor     esi, esi
0x18004660c  test    rbx, rbx
0x18004660f  jz      loc_18004678F
0x180046615  cmp     [rsp+530h+var_4CC], esi
0x180046619  jz      loc_180046872
0x18004661f  lea     rax, asc_1800A272C; "."
0x180046626  mov     rcx, r15; struct _DOMAIN_INFO *
0x180046629  mov     [rbp+430h+var_4A0], rax
0x18004662d  call    ?NlGetDomainFlags@@YAKPEAU_DOMAIN_INFO@@@Z; NlGetDomainFlags(_DOMAIN_INFO *)
0x180046632  test    al, 4
0x180046634  jnz     short loc_18004664C
0x180046636  lea     rdx, aGcThisDcIsnTAG; "GC: This DC isn't a GC. So it doesn't a"...
0x18004663d  mov     ecx, 8000000h; unsigned int
0x180046642  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180046647  jmp     loc_180046A6A
0x18004664c  lea     rax, [rbp+430h+pResult]
0x180046650  mov     r8d, 0FFFFFFF1h; formatOffered
0x180046656  mov     [rsp+530h+ppResult], rax; ppResult
0x18004665b  mov     r9d, r8d; formatDesired
0x18004665e  lea     rax, [rbp+430h+var_4A0]
0x180046662  xor     edx, edx; flags
0x180046664  mov     [rsp+530h+rpNames], rax; rpNames
0x180046669  mov     rcx, rbx; hDS
0x18004666c  mov     [rsp+530h+cNames], 1; cNames
0x180046674  call    cs:__imp_DsCrackNamesW
0x18004667b  nop     dword ptr [rax+rax+00h]
0x180046680  mov     [rsp+530h+var_4D0], eax
0x180046684  mov     r13d, eax
0x180046687  test    eax, eax
0x180046689  jz      short loc_1800466A4
0x18004668b  mov     r8d, eax
0x18004668e  lea     rdx, aNlsitesupdates_1; "NlSitesUpdateSiteCoverage: CrackNames f"...
0x180046695  mov     ecx, 100h; unsigned int
0x18004669a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004669f  jmp     loc_180046A6A
0x1800466a4  mov     rcx, [rbp+430h+pResult]
0x1800466a8  mov     r14d, esi
0x1800466ab  cmp     [rcx], esi
0x1800466ad  jbe     loc_180046971
0x1800466b3  mov     r15, [rsp+530h+hMem]
0x1800466b8  jmp     short loc_1800466BC
0x1800466ba  xor     esi, esi
0x1800466bc  mov     eax, r14d
0x1800466bf  lea     rdx, aGcListWsWs; "GC list: %ws %ws\n"
0x1800466c6  lea     rbx, [rax+rax*2]
0x1800466ca  mov     rax, [rcx+8]
0x1800466ce  mov     ecx, 20h ; ' '; unsigned int
0x1800466d3  mov     rdi, [rax+rbx*8+10h]
0x1800466d8  mov     r12, [rax+rbx*8+8]
0x1800466dd  mov     r8, rdi
0x1800466e0  mov     r9, r12
0x1800466e3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800466e8  mov     rax, [rbp+430h+pResult]
0x1800466ec  mov     rcx, [rax+8]
0x1800466f0  mov     eax, [rcx+rbx*8]
0x1800466f3  test    eax, eax
0x1800466f5  jz      short loc_180046714
0x1800466f7  mov     r9, r12
0x1800466fa  mov     [rsp+530h+cNames], eax
0x1800466fe  mov     r8, rdi
0x180046701  lea     rdx, aNlsitesupdates; "NlSitesUpdateSiteCoverage: CrackNameSta"...
0x180046708  mov     ecx, 100h; unsigned int
0x18004670d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180046712  jmp     short loc_18004676C
0x180046714  mov     eax, [rsp+530h+var_4EC]
0x180046718  mov     ebx, esi
0x18004671a  test    eax, eax
0x18004671c  jz      short loc_180046755
0x18004671e  test    rdi, rdi
0x180046721  jz      short loc_18004674F
0x180046723  mov     rax, [rsp+530h+var_4E0]
0x180046728  mov     rcx, rdi
0x18004672b  mov     esi, ebx
0x18004672d  mov     rdx, [rax+8]
0x180046731  mov     rdx, [rdx+rsi*8]
0x180046735  call    cs:__imp__o__wcsicmp
0x18004673c  nop     dword ptr [rax+rax+00h]
0x180046741  test    eax, eax
0x180046743  jz      loc_180046864
0x180046749  mov     eax, [rsp+530h+var_4EC]
0x18004674d  xor     esi, esi
0x18004674f  inc     ebx
0x180046751  cmp     ebx, eax
0x180046753  jb      short loc_18004671E
0x180046755  mov     r9, r12
0x180046758  lea     rdx, aGcWsWsIsnTASit; "GC: %ws %ws: isn't a site returned from"...
0x18004675f  mov     r8, rdi
0x180046762  mov     ecx, 100h; unsigned int
0x180046767  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004676c  mov     rcx, [rbp+430h+pResult]
0x180046770  inc     r14d
0x180046773  cmp     r14d, [rcx]
0x180046776  jb      loc_1800466BA
0x18004677c  mov     r15, [rbp+430h+var_498]
0x180046780  mov     r14, [rsp+530h+var_4E0]
0x180046785  mov     r12d, [rsp+530h+var_4EC]
0x18004678a  mov     rax, [rsp+530h+hMem]
0x18004678f  cmp     [rsp+530h+var_4E8], 0
0x180046794  mov     esi, [rsp+530h+var_4CC]
0x180046798  mov     [rsp+530h+var_4C0], esi
0x18004679c  jz      loc_180046C68
0x1800467a2  test    r12d, r12d
0x1800467a5  jz      loc_180046C68
0x1800467ab  mov     r13, [rbp+430h+var_490]
0x1800467af  xor     ebx, ebx
0x1800467b1  mov     r15d, ebx
0x1800467b4  cmp     dword ptr [rax+rbx*4], 0
0x1800467b8  jnz     loc_180046C4C
0x1800467be  mov     rcx, [r14+8]
0x1800467c2  mov     rcx, [rcx+rbx*8]; pszName
0x1800467c6  call    ?NlValidateSiteName_Old@@YAHPEAG@Z; NlValidateSiteName_Old(ushort *)
0x1800467cb  test    eax, eax
0x1800467cd  jz      loc_180046C47
0x1800467d3  mov     r9, [r14+8]
0x1800467d7  lea     rdx, aHsWsSiteHasNoH; "%hs: %ws: Site has no %hss\n"
0x1800467de  mov     r8, r13
0x1800467e1  mov     qword ptr [rsp+530h+cNames], r13
0x1800467e6  mov     ecx, 8000000h; unsigned int
0x1800467eb  mov     r9, [r9+rbx*8]
0x1800467ef  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800467f4  mov     r10d, r15d
0x1800467f7  or      esi, 0FFFFFFFFh
0x1800467fa  imul    r10d, [rsp+530h+var_4EC]
0x180046800  xor     r12d, r12d
0x180046803  xor     edi, edi
0x180046805  mov     dword ptr [rbp+430h+var_4A0], r10d
0x180046809  mov     r10d, [rsp+530h+var_4EC]
0x18004680e  cmp     r15d, r12d
0x180046811  jz      loc_180046B88
0x180046817  mov     rax, [rsp+530h+var_4E0]
0x18004681c  mov     r14, [r14+10h]
0x180046820  mov     rcx, [rax+8]
0x180046824  mov     rcx, [rcx+rdi*8]; pszName
0x180046828  call    ?NlValidateSiteName_Old@@YAHPEAG@Z; NlValidateSiteName_Old(ushort *)
0x18004682d  test    eax, eax
0x18004682f  jnz     loc_180046A81
0x180046835  lea     rdx, aHsWsSiteWsIsIn; "%hs: %ws: Site '%ws' is invalid.\n"
0x18004683c  mov     r14, [rsp+530h+var_4E0]
0x180046841  mov     r9, [r14+8]
0x180046845  mov     r8, r13
0x180046848  mov     ecx, 8000000h; unsigned int
0x18004684d  mov     rax, [r9+rdi*8]
0x180046851  mov     r9, [r9+rbx*8]
0x180046855  mov     qword ptr [rsp+530h+cNames], rax
0x18004685a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004685f  jmp     loc_180046B83
0x180046864  inc     dword ptr [r15+rsi*4]
0x180046868  mov     [rsp+530h+var_4E8], 1
0x18004686d  jmp     loc_18004676C
0x180046872  cmp     [rsp+530h+var_4C4], esi
0x180046876  jz      loc_180046986
0x18004687c  lea     rax, [rbp+430h+ppInfo]
0x180046880  mov     r8d, 3; InfoLevel
0x180046886  lea     r9, [rbp+430h+pcOut]; pcOut
0x18004688a  mov     qword ptr [rsp+530h+cNames], rax; ppInfo
0x18004688f  lea     rdx, [rbp+430h+DomainName]; DomainName
0x180046893  mov     rcx, rbx; hDs
0x180046896  call    cs:__imp_DsGetDomainControllerInfoW
0x18004689d  nop     dword ptr [rax+rax+00h]
0x1800468a2  mov     [rsp+530h+var_4D0], eax
0x1800468a6  mov     r13d, eax
0x1800468a9  test    eax, eax
0x1800468ab  jz      short loc_1800468C8
0x1800468ad  mov     r8d, eax
0x1800468b0  lea     rdx, aNlsitesupdates_0; "NlSitesUpdateSiteCoverage: Cannot DsGet"...
0x1800468b7  mov     ecx, 100h; unsigned int
0x1800468bc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800468c1  mov     eax, esi
0x1800468c3  mov     [rbp+430h+pcOut], eax
0x1800468c6  jmp     short loc_1800468CB
0x1800468c8  mov     eax, [rbp+430h+pcOut]
0x1800468cb  test    eax, eax
0x1800468cd  jz      loc_18004678A
0x1800468d3  mov     r15, [rsp+530h+hMem]
0x1800468d8  mov     r8, [rbp+430h+ppInfo]
0x1800468dc  lea     rdx, aDcListWsWs; "DC list: %ws %ws\n"
0x1800468e3  mov     eax, esi
0x1800468e5  mov     ecx, 20h ; ' '; unsigned int
0x1800468ea  imul    rdi, rax, 88h
0x1800468f1  mov     r9, [rdi+r8+8]
0x1800468f6  mov     r8, [rdi+r8+10h]
0x1800468fb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180046900  xor     r14d, r14d
0x180046903  mov     ebx, r14d
0x180046906  test    r12d, r12d
  ... truncated ...
```
