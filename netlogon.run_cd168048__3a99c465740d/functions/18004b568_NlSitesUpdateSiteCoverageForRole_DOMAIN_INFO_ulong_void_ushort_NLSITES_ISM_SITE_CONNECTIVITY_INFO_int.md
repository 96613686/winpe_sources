# NlSitesUpdateSiteCoverageForRole(_DOMAIN_INFO *,ulong,void *,ushort *,_NLSITES_ISM_SITE_CONNECTIVITY_INFO *,int *)

- ea: `0x18004b568`
- end: `0x18004c8bc`
- name: `?NlSitesUpdateSiteCoverageForRole@@YAKPEAU_DOMAIN_INFO@@KPEAXPEAGPEAU_NLSITES_ISM_SITE_CONNECTIVITY_INFO@@PEAH@Z`
- size: `4948`
- prototype: `unsigned int(struct _DOMAIN_INFO *, unsigned int, void *, unsigned __int16 *, struct _NLSITES_ISM_SITE_CONNECTIVITY_INFO *, int *)`
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020480`

## callees

- `0x18000e910`
- `0x1800110ac`
- `0x180018f38`
- `0x180018f68`
- `0x180019154`
- `0x18001af4c`
- `0x18001b134`
- `0x18001fdb4`
- `0x180025eb8`
- `0x1800276ac`
- `0x180041fbc`
- `0x1800486b4`
- `0x18004952c`
- `0x180049fb4`
- `0x18004b568`
- `0x18004ca10`
- `0x18004d0a4`
- `0x18004d150`
- `0x18004d240`
- `0x18004d374`
- `0x18004f390`
- `0x1800892fc`
- `0x18008e644`
- `0x18008e678`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004c05c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004c05c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c160`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c160`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c7d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c7d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c2b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c2b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b70a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b72b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b70a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b72b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004b667`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004b667`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b6b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b755`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b804`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004c653`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004c73d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b6b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b755`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b804`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004c653`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004c73d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c711`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c7f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c874`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c883`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c711`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c7f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c874`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c883`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x18004c826`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x18004c826`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x18004b8e0`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x18004b8e0`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeDomainControllerInfoW` at `0x18004c811`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeDomainControllerInfoW` at `0x18004c811`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsGetDomainControllerInfoW` at `0x18004ba85`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsGetDomainControllerInfoW` at `0x18004ba85`
- `ntdll!RtlEqualUnicodeString` at `0x18004c359`
- `ntdll!RtlEqualUnicodeString` at `0x18004c496`
- `ntdll!RtlEqualUnicodeString` at `0x18004c359`
- `ntdll!RtlEqualUnicodeString` at `0x18004c496`
- `netutils!NetpwNameCompare` at `0x18004c1b2`
- `netutils!NetpwNameCompare` at `0x18004c1b2`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsFreeServersAndSitesForNetLogon` at `0x18004c845`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsFreeServersAndSitesForNetLogon` at `0x18004c845`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsGetServersAndSitesForNetLogon` at `0x18004bbf5`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsGetServersAndSitesForNetLogon` at `0x18004bbf5`

## pseudocode

```c
__int64 __fastcall NlSitesUpdateSiteCoverageForRole(
        struct _DOMAIN_INFO *a1,
        int a2,
        void *a3,
        unsigned __int16 *a4,
        RTL_SRWLOCK *a5,
        int *a6)
{
  int v7; // r15d
  int v8; // r13d
  struct _DOMAIN_INFO *v9; // rsi
  int v10; // ebx
  unsigned int v11; // edi
  _DWORD *Ptr; // r12
  const char *v13; // rax
  bool v14; // cf
  const char *v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // esi
  wchar_t *v18; // r13
  HLOCAL *v19; // r15
  unsigned int v20; // esi
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  int v23; // r15d
  unsigned int v24; // esi
  __int64 v25; // r12
  _DWORD *v26; // rcx
  DWORD v27; // eax
  int v28; // esi
  ScannerInfoNameMappings *v29; // r10
  PSRWLOCK v30; // r12
  PDS_NAME_RESULT_ITEMW rItems; // rdx
  unsigned __int16 *pName; // rbx
  __int64 pDomain; // r14
  DWORD status; // eax
  int v35; // esi
  int v36; // edi
  DWORD DomainControllerInfoW; // eax
  ScannerInfoNameMappings *v38; // r10
  unsigned int v39; // ebx
  PSRWLOCK v40; // r12
  __int64 v41; // rdi
  unsigned __int16 *v42; // rdx
  int ServersAndSitesForNetLogon; // eax
  __int64 *v44; // rbx
  ScannerInfoNameMappings *v45; // rcx
  PSRWLOCK v46; // r12
  unsigned __int16 *v47; // rdx
  unsigned int v48; // r13d
  __int64 v49; // rax
  _DWORD *v50; // rdi
  __int64 v51; // r15
  unsigned int v52; // r8d
  ScannerInfoNameMappings *v53; // r10
  unsigned int v54; // eax
  unsigned int v55; // ebx
  __int64 v56; // rsi
  int v57; // r12d
  __int64 v58; // rdi
  int v59; // r14d
  int v60; // edx
  unsigned int v61; // r9d
  __int64 v62; // rax
  int v63; // edx
  __int64 v64; // rcx
  int v65; // r14d
  wchar_t *v66; // rbx
  wchar_t *v67; // rax
  int v68; // r8d
  wchar_t *v69; // rsi
  unsigned __int16 *v70; // rdx
  __int64 v71; // rax
  _QWORD *v72; // rbx
  struct _DOMAIN_INFO *v73; // r15
  int v74; // r8d
  unsigned int v75; // r13d
  unsigned int v76; // r14d
  __int64 v77; // rax
  unsigned int v78; // ebx
  _QWORD *v79; // r15
  int v80; // eax
  unsigned int v81; // ecx
  unsigned __int16 *v82; // rax
  unsigned int v83; // r15d
  __int64 v84; // r14
  unsigned int v85; // ebx
  _QWORD *v86; // r13
  int v87; // eax
  unsigned int v88; // ecx
  unsigned int v89; // ebx
  unsigned __int16 *v90; // rax
  unsigned int v91; // ebx
  struct _DOMAIN_INFO *v92; // r14
  void *v93; // rcx
  HLOCAL v94; // rax
  unsigned int i; // ebx
  struct _DOMAIN_INFO *v96; // r14
  void *v97; // rcx
  HLOCAL v98; // rax
  unsigned int j; // ebx
  PDS_NAME_RESULTW v100; // rcx
  unsigned int k; // ebx
  unsigned int v103; // [rsp+40h] [rbp-C0h]
  unsigned int v104; // [rsp+44h] [rbp-BCh] BYREF
  int v105; // [rsp+48h] [rbp-B8h]
  HLOCAL hMem; // [rsp+50h] [rbp-B0h]
  int v107; // [rsp+58h] [rbp-A8h]
  const char *v108; // [rsp+60h] [rbp-A0h]
  _DWORD *v109; // [rsp+68h] [rbp-98h]
  int v110; // [rsp+70h] [rbp-90h]
  unsigned int v111; // [rsp+74h] [rbp-8Ch] BYREF
  int v112; // [rsp+78h] [rbp-88h]
  int v113; // [rsp+7Ch] [rbp-84h]
  LPCWSTR rpNames; // [rsp+80h] [rbp-80h] BYREF
  void *Src; // [rsp+88h] [rbp-78h]
  DWORD pcOut; // [rsp+90h] [rbp-70h] BYREF
  struct _DOMAIN_INFO *v117; // [rsp+98h] [rbp-68h]
  wchar_t *Str; // [rsp+A0h] [rbp-60h]
  PDS_NAME_RESULTW pResult; // [rsp+A8h] [rbp-58h] BYREF
  PSRWLOCK SRWLock; // [rsp+B0h] [rbp-50h]
  void *ppInfo; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v122; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v123; // [rsp+C8h] [rbp-38h]
  __int64 *v124; // [rsp+D0h] [rbp-30h] BYREF
  int *v125; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v126[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v127; // [rsp+F0h] [rbp-10h]
  WCHAR DomainName[256]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v129[256]; // [rsp+300h] [rbp+200h] BYREF

  v122 = a4;
  v117 = a1;
  v7 = a2 & 0x8000;
  v110 = a2;
  v125 = a6;
  v8 = a2 & 0x2000;
  *a6 = 0;
  v104 = 0;
  v9 = a1;
  v10 = 0;
  SRWLock = a5;
  v11 = 0;
  hMem = 0;
  Ptr = 0;
  ppInfo = 0;
  pcOut = 0;
  pResult = 0;
  v124 = 0;
  Str = 0;
  v111 = 0;
  v109 = 0;
  v107 = v7;
  v113 = v8;
  if ( (a2 & 0x8000) != 0 )
  {
    v13 = "GC";
LABEL_5:
    v108 = v13;
    goto LABEL_9;
  }
  if ( (a2 & 0x2000) != 0 )
  {
    v13 = "DC";
    goto LABEL_5;
  }
  v14 = (a2 & 0x4000) != 0;
  v15 = "NDNC";
  if ( !v14 )
    v15 = 0;
  v108 = v15;
LABEL_9:
  if ( a5 )
  {
    Ptr = a5->Ptr;
    v109 = Ptr;
    if ( Ptr )
      v10 = *Ptr;
  }
  AcquireSRWLockShared(&gNlSiteCoverageParameterLock);
  if ( v7 )
  {
    v16 = qword_1800F8208;
  }
  else if ( v8 )
  {
    v16 = qword_1800F8200;
  }
  else
  {
    if ( (v110 & 0x4000) == 0 )
    {
LABEL_25:
      v18 = 0;
      goto LABEL_26;
    }
    v16 = qword_1800F8210;
  }
  if ( !v16 )
    goto LABEL_25;
  v17 = NetpTStrArraySize();
  Str = (wchar_t *)LocalAlloc(0x40u, v17);
  v18 = Str;
  if ( !Str )
  {
    v19 = 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, v17);
    v20 = 8;
    ReleaseSRWLockShared(&gNlSiteCoverageParameterLock);
    goto LABEL_314;
  }
  v9 = v117;
LABEL_26:
  ReleaseSRWLockShared(&gNlSiteCoverageParameterLock);
  if ( v18 )
    v10 += NetpTStrArrayEntryCount(v18);
  v21 = 16 * (v10 + 1);
  Src = LocalAlloc(0x40u, v21);
  v19 = (HLOCAL *)Src;
  if ( !Src )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, v21);
    v20 = 8;
    goto LABEL_314;
  }
  v22 = 0;
  v112 = 0;
  v103 = 0;
  v23 = 0;
  NlCaptureDomainInfo(v9, DomainName, 0);
  NlCaptureDnsForestName(v129);
  if ( !dword_1800F8218 || !Ptr )
  {
    v26 = 0;
LABEL_116:
    v25 = 0;
    goto LABEL_117;
  }
  v24 = *Ptr;
  v25 = 0;
  LODWORD(rpNames) = v24;
  if ( !v24 )
  {
    v26 = 0;
    goto LABEL_117;
  }
  hMem = LocalAlloc(0x40u, 4 * v24);
  v26 = hMem;
  if ( !hMem )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, 4 * v24);
    v20 = 8;
    goto LABEL_313;
  }
  v22 = v24;
  v103 = v24;
  if ( a3 )
  {
    if ( v107 )
    {
      rpNames = L".";
      if ( (NlGetDomainFlags(v117) & 4) == 0 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids);
LABEL_68:
          v35 = v107;
          v36 = v107;
          v105 = v107;
          v104 = 0;
          goto LABEL_186;
        }
        goto LABEL_110;
      }
      v27 = DsCrackNamesW(a3, DS_NAME_NO_FLAGS, (DS_NAME_FORMAT)-15, (DS_NAME_FORMAT)-15, 1u, &rpNames, &pResult);
      v112 = v27;
      if ( v27 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, v27);
          goto LABEL_68;
        }
        goto LABEL_110;
      }
      v28 = 0;
      if ( pResult->cItems )
      {
        v29 = WPP_GLOBAL_Control;
        v30 = SRWLock;
        while ( 1 )
        {
          rItems = pResult->rItems;
          pName = rItems[v28].pName;
          pDomain = (__int64)rItems[v28].pDomain;
          if ( (*((_BYTE *)v29 + 28) & 0x20) != 0 && *((_BYTE *)v29 + 25) >= 4u )
          {
            WPP_SF_SS(
              *((_QWORD *)v29 + 2),
              42,
              (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids,
              (_DWORD)pName,
              pDomain);
            v29 = WPP_GLOBAL_Control;
          }
          status = pResult->rItems[v28].status;
          if ( status )
            break;
          if ( pName )
          {
            if ( (unsigned int)CNlIsmSiteNameIndexCache::QuerySiteIndex(
                                 (CNlIsmSiteNameIndexCache *)v30[3].Ptr,
                                 pName,
                                 &v104) )
            {
              v23 = 1;
              v26 = hMem;
              v22 = v103;
              ++*((_DWORD *)hMem + v104);
              goto LABEL_116;
            }
            v29 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                44,
                (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids,
                (_DWORD)pName,
                pDomain);
LABEL_65:
              v29 = WPP_GLOBAL_Control;
            }
          }
LABEL_66:
          if ( ++v28 >= pResult->cItems )
            goto LABEL_67;
        }
        if ( (*((_BYTE *)v29 + 28) & 0x20) == 0 || *((_BYTE *)v29 + 25) < 2u )
          goto LABEL_66;
        WPP_SF_SSd(
          *((_QWORD *)v29 + 2),
          43,
          (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids,
          (_DWORD)pName,
          pDomain,
          status);
        goto LABEL_65;
      }
LABEL_110:
      v26 = hMem;
      goto LABEL_117;
    }
    if ( v113 )
    {
      DomainControllerInfoW = DsGetDomainControllerInfoW(a3, DomainName, 3u, &pcOut, &ppInfo);
      v112 = DomainControllerInfoW;
      if ( DomainControllerInfoW )
      {
        v38 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SDd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids,
            (unsigned int)DomainName,
            DomainControllerInfoW,
            DomainControllerInfoW);
          v38 = WPP_GLOBAL_Control;
        }
        pcOut = 0;
      }
      else
      {
        v38 = WPP_GLOBAL_Control;
      }
      v39 = 0;
      if ( pcOut )
      {
        v40 = SRWLock;
        while ( 1 )
        {
          if ( (*((_BYTE *)v38 + 28) & 0x20) != 0 && *((_BYTE *)v38 + 25) >= 4u )
          {
            WPP_SF_SS(
              *((_QWORD *)v38 + 2),
              46,
              (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids,
              *((_QWORD *)ppInfo + 17 * v39 + 2),
              *((_QWORD *)ppInfo + 17 * v39 + 1));
            v38 = WPP_GLOBAL_Control;
          }
          v41 = 136LL * v39;
          v42 = *(unsigned __int16 **)((char *)ppInfo + v41 + 16);
          if ( v42 )
          {
            if ( (unsigned int)CNlIsmSiteNameIndexCache::QuerySiteIndex(
                                 (CNlIsmSiteNameIndexCache *)v40[3].Ptr,
                                 v42,
                                 &v104) )
            {
              v23 = 1;
              v26 = hMem;
              v22 = v24;
              ++*((_DWORD *)hMem + v104);
              goto LABEL_116;
            }
            v38 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids,
                *(_QWORD *)((char *)ppInfo + v41 + 16),
                *(_QWORD *)((char *)ppInfo + v41 + 8));
              v38 = WPP_GLOBAL_Control;
            }
          }
          if ( ++v39 >= pcOut )
          {
LABEL_67:
            v25 = 0;
            goto LABEL_68;
          }
        }
      }
      goto LABEL_109;
    }
    if ( (v110 & 0x4000) == 0 )
      goto LABEL_117;
    v36 = v107;
    v105 = v107;
    if ( !(unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent(hMem) )
    {
      v112 = 50;
      goto LABEL_106;
    }
    ServersAndSitesForNetLogon = DsGetServersAndSitesForNetLogon(DomainName, &v124);
    v112 = ServersAndSitesForNetLogon;
    if ( ServersAndSitesForNetLogon )
    {
      v112 = ServersAndSitesForNetLogon;
      goto LABEL_110;
    }
    v44 = v124;
    if ( !v124 )
    {
      v112 = 0;
LABEL_109:
      v22 = v24;
      goto LABEL_110;
    }
    v45 = WPP_GLOBAL_Control;
    v46 = SRWLock;
    while ( *v44 )
    {
      if ( (*((_BYTE *)v45 + 28) & 0x20) != 0 && *((_BYTE *)v45 + 25) >= 4u )
      {
        WPP_SF_SS(*((_QWORD *)v45 + 2), 48, (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, v44[1], *v44);
        v45 = WPP_GLOBAL_Control;
      }
      v47 = (unsigned __int16 *)v44[1];
      if ( v47 )
      {
        if ( (unsigned int)CNlIsmSiteNameIndexCache::QuerySiteIndex((CNlIsmSiteNameIndexCache *)v46[3].Ptr, v47, &v104) )
        {
          v22 = v24;
          v26 = hMem;
          ++*((_DWORD *)hMem + v104);
          v25 = 0;
          v104 = 0;
          goto LABEL_119;
        }
        v45 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids,
            v44[1],
            *v44);
          v45 = WPP_GLOBAL_Control;
        }
      }
      v44 += 2;
      if ( !v44 )
      {
        v25 = 0;
LABEL_106:
        v104 = 0;
        v35 = v36;
        v105 = v36;
        goto LABEL_186;
      }
    }
    v26 = hMem;
    v22 = v24;
    goto LABEL_116;
  }
LABEL_117:
  v35 = v107;
  v36 = v107;
  v105 = v107;
  v104 = 0;
  if ( !v23 )
    goto LABEL_186;
  v24 = v22;
  LODWORD(rpNames) = v22;
LABEL_119:
  v48 = 0;
  if ( !v22 )
    goto LABEL_185;
  v49 = 0;
  do
  {
    if ( v26[v49] )
      goto LABEL_183;
    v50 = v109;
    v51 = (unsigned int)v25;
    if ( !(unsigned int)NlValidateSiteName(*(PCWSTR *)(*((_QWORD *)v109 + 1) + 8LL * (unsigned int)v25)) )
      goto LABEL_182;
    v53 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_sSs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids,
        (_DWORD)v108,
        *(_QWORD *)(*((_QWORD *)v50 + 1) + 8LL * (unsigned int)v25),
        (__int64)v108);
      v53 = WPP_GLOBAL_Control;
    }
    v54 = v103;
    v55 = -1;
    v56 = 0;
    v57 = (_DWORD)rpNames * v25;
    do
    {
      if ( v48 != (_DWORD)v56 )
      {
        v58 = *((_QWORD *)v50 + 2);
        if ( !(unsigned int)NlValidateSiteName(*(PCWSTR *)(*((_QWORD *)v109 + 1) + 8 * v56)) )
        {
          v53 = WPP_GLOBAL_Control;
          v50 = v109;
          v59 = (int)v108;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            goto LABEL_141;
          v60 = 52;
LABEL_140:
          WPP_SF_sSS(
            *((_QWORD *)v53 + 2),
            v60,
            v52,
            v59,
            *(_QWORD *)(*((_QWORD *)v50 + 1) + 8 * v51),
            *(_QWORD *)(*((_QWORD *)v50 + 1) + 8 * v56));
          v53 = WPP_GLOBAL_Control;
LABEL_141:
          v54 = v103;
          goto LABEL_150;
        }
        v61 = *(_DWORD *)(v58 + 12LL * (unsigned int)(v57 + v56));
        if ( v61 == -1 )
        {
          v53 = WPP_GLOBAL_Control;
          v50 = v109;
          v59 = (int)v108;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
            goto LABEL_141;
          v60 = 53;
          goto LABEL_140;
        }
        v52 = *((_DWORD *)hMem + v56);
        if ( !v52 )
        {
          v53 = WPP_GLOBAL_Control;
          v50 = v109;
          v59 = (int)v108;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
            goto LABEL_141;
          v60 = 54;
          goto LABEL_140;
        }
        if ( v55 == -1 )
        {
          v53 = WPP_GLOBAL_Control;
          v50 = v109;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            goto LABEL_147;
          WPP_SF_sSS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            55,
            v52,
            (_DWORD)v108,
            *(_QWORD *)(*((_QWORD *)v109 + 1) + 8 * v51),
            *(_QWORD *)(*((_QWORD *)v109 + 1) + 8 * v56));
          goto LABEL_146;
        }
        v50 = v109;
        v62 = *((_QWORD *)v109 + 2);
        if ( v61 < *(_DWORD *)(v62 + 12LL * (v57 + v55)) )
        {
          v53 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            goto LABEL_147;
          WPP_SF_sSSS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            v52,
            (_DWORD)v108,
            *(_QWORD *)(*((_QWORD *)v109 + 1) + 8 * v51),
            *(_QWORD *)(*((_QWORD *)v109 + 1) + 8 * v56),
            *(_QWORD *)(*((_QWORD *)v109 + 1) + 8LL * v55));
LABEL_146:
          v53 = WPP_GLOBAL_Control;
LABEL_147:
          v55 = v56;
LABEL_148:
          v54 = v103;
          goto LABEL_149;
        }
        if ( v61 == *(_DWORD *)(v62 + 12LL * (v57 + v55)) )
        {
          if ( v52 > *((_DWORD *)hMem + v55) )
          {
            v53 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
              goto LABEL_166;
            v63 = 57;
            v64 = *((_QWORD *)v109 + 1);
LABEL_165:
            WPP_SF_sSSS(
              *((_QWORD *)v53 + 2),
              v63,
              v52,
              (_DWORD)v108,
              *(_QWORD *)(v64 + 8 * v51),
              *(_QWORD *)(v64 + 8 * v56),
              *(_QWORD *)(v64 + 8LL * v55));
            v53 = WPP_GLOBAL_Control;
LABEL_166:
            v50 = v109;
            goto LABEL_147;
          }
          if ( v52 == *((_DWORD *)hMem + v55)
            && (int)_o__wcsicmp(
                      *(_QWORD *)(*((_QWORD *)v109 + 1) + 8 * v56),
                      *(_QWORD *)(*((_QWORD *)v109 + 1) + 8LL * v55)) < 0 )
          {
            v53 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
              goto LABEL_166;
            v63 = 58;
            v64 = *((_QWORD *)v109 + 1);
            goto LABEL_165;
          }
          v50 = v109;
        }
        v53 = WPP_GLOBAL_Control;
        goto LABEL_148;
      }
LABEL_149:
      v59 = (int)v108;
LABEL_150:
      v56 = (unsigned int)(v56 + 1);
    }
    while ( (unsigned int)v56 < v54 );
    if ( v55 == HIDWORD(SRWLock[1].Ptr) )
    {
      if ( (*((_BYTE *)v53 + 28) & 0x20) != 0 && *((_BYTE *)v53 + 25) >= 4u )
        WPP_SF_sS(*((_QWORD *)v53 + 2), 59, v52, v59, *(_QWORD *)(*((_QWORD *)v50 + 1) + 8 * v51));
      NlSitesAddCloseSite(
        *(unsigned __int16 **)(*((_QWORD *)v50 + 1) + 8 * v51),
        (struct _NL_COVERED_SITE *)Src,
        &v111,
        1);
    }
    else if ( v55 == -1 )
    {
      if ( (*((_BYTE *)v53 + 28) & 0x20) != 0 && *((_BYTE *)v53 + 25) >= 5u )
        WPP_SF_sS(*((_QWORD *)v53 + 2), 60, v52, v59, *(_QWORD *)(*((_QWORD *)v50 + 1) + 8 * v51));
    }
    else if ( (*((_BYTE *)v53 + 28) & 0x20) != 0 && *((_BYTE *)v53 + 25) >= 5u )
    {
      WPP_SF_sSS(
        *((_QWORD *)v53 + 2),
        61,
        v52,
        v59,
        *(_QWORD *)(*((_QWORD *)v50 + 1) + 8 * v51),
        *(_QWORD *)(*((_QWORD *)v50 + 1) + 8LL * v55));
    }
    v24 = (unsigned int)rpNames;
LABEL_182:
    v26 = hMem;
LABEL_183:
    v49 = ++v48;
    LODWORD(v25) = v48;
  }
  while ( v48 < v24 );
  v36 = v105;
  v25 = 0;
LABEL_185:
  v35 = v107;
LABEL_186:
  if ( !Str )
    goto LABEL_214;
  v65 = (int)v108;
  v66 = Str;
  while ( 2 )
  {
    if ( *v66 )
    {
      v67 = wcsstr(v66, L"\\");
      v69 = v67;
      if ( v67 )
      {
        *v67 = 0;
        if ( v36 )
        {
          v70 = v129;
          goto LABEL_198;
        }
        if ( v113 )
        {
          if ( !(unsigned int)NlEqualDnsName(v66, DomainName)
            && (unsigned int)NetpwNameCompare(v66, (char *)v117 + 72, 6) )
          {
            goto LABEL_205;
          }
LABEL_199:
          if ( v69[1] )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, v68, v65, (__int64)(v69 + 1));
            NlSitesAddCloseSite(v69 + 1, (struct _NL_COVERED_SITE *)Src, &v111, 0);
          }
          v36 = v105;
        }
        else
        {
          if ( (v110 & 0x4000) == 0 )
            goto LABEL_199;
          v70 = DomainName;
LABEL_198:
          if ( (unsigned int)NlEqualDnsName(v66, v70) )
            goto LABEL_199;
        }
LABEL_205:
        *v69 = 92;
      }
      else
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, v68, v65, (__int64)v66);
        NlSitesAddCloseSite(v66, (struct _NL_COVERED_SITE *)Src, &v111, 0);
      }
      v71 = -1;
      do
        ++v71;
      while ( v66[v71] );
      v66 += (unsigned int)(v71 + 1);
      continue;
    }
    break;
  }
  v35 = v107;
LABEL_214:
  v72 = Src;
  NlSitesAddCloseSite(v122, (struct _NL_COVERED_SITE *)Src, &v111, 0);
  v73 = v117;
  SRWLock = (PSRWLOCK)((char *)v117 + 600);
  AcquireSRWLockExclusive((PSRWLOCK)v117 + 75);
  if ( v35 )
  {
    v25 = *((_QWORD *)v73 + 78);
    v75 = *((_DWORD *)v73 + 158);
    goto LABEL_220;
  }
  if ( v113 || (v110 & 0x4000) != 0 )
  {
    v25 = *((_QWORD *)v73 + 76);
    v75 = *((_DWORD *)v73 + 154);
LABEL_220:
    LODWORD(rpNames) = v75;
  }
  else
  {
    v75 = 0;
    LODWORD(rpNames) = 0;
  }
  v11 = v111;
  v76 = 0;
  if ( v111 )
  {
    while ( 2 )
    {
      v126[0] = v122;
      v127 = 0;
      v77 = v72[2 * v76];
      v78 = 0;
      v126[1] = (unsigned __int16 *)(v77 + 40);
      if ( v75 )
      {
        v79 = Src;
        do
        {
          if ( RtlEqualUnicodeString(
                 (PCUNICODE_STRING)(v79[2 * v76] + 24LL),
                 (PCUNICODE_STRING)(*(_QWORD *)(v25 + 16LL * v78) + 24LL),
                 1u) )
          {
            break;
          }
          ++v78;
        }
        while ( v78 < v75 );
        v11 = v111;
        v73 = v117;
      }
      v80 = *((_DWORD *)Src + 4 * v76 + 2);
      if ( v78 == v75 )
      {
        v104 = 1;
        if ( v80 )
        {
          if ( v105 )
          {
            v81 = 5786;
            goto LABEL_233;
          }
          if ( v113 )
          {
            v81 = 5784;
            goto LABEL_236;
          }
          if ( (v110 & 0x4000) != 0 )
          {
            v81 = 5792;
            goto LABEL_247;
          }
        }
LABEL_249:
        if ( ++v76 >= v11 )
          goto LABEL_250;
        v72 = Src;
        continue;
      }
      break;
    }
    if ( !v80 || *(_DWORD *)(v25 + 16LL * v78 + 8) )
      goto LABEL_249;
    if ( v105 )
    {
      v81 = 5796;
LABEL_233:
      v82 = v129;
    }
    else if ( v113 )
    {
      v81 = 5794;
LABEL_236:
      v82 = (unsigned __int16 *)((char *)v73 + 72);
    }
    else
    {
      if ( (v110 & 0x4000) == 0 )
        goto LABEL_249;
      v81 = 5798;
LABEL_247:
      v82 = DomainName;
    }
    v127 = v82;
    NlpWriteEventlogEx(v81, 4u, 0x20000000u, 0xFFFFFFFF, v126, 3u, 0, 0);
    goto LABEL_249;
  }
LABEL_250:
  v111 = 0;
  v83 = 0;
  if ( !v75 )
  {
    v20 = v112;
    goto LABEL_286;
  }
  v84 = 0;
  while ( 2 )
  {
    v123 = 0;
    v85 = 0;
    v122 = (unsigned __int16 *)(*(_QWORD *)(v25 + 16 * v84) + 40LL);
    if ( v11 )
    {
      v86 = Src;
      do
      {
        if ( RtlEqualUnicodeString(
               (PCUNICODE_STRING)(*(_QWORD *)(v25 + 16 * v84) + 24LL),
               (PCUNICODE_STRING)(v86[2 * v85] + 24LL),
               1u) )
        {
          break;
        }
        ++v85;
      }
      while ( v85 < v11 );
      v83 = v111;
      v75 = (unsigned int)rpNames;
    }
    v87 = *(_DWORD *)(v25 + 16 * v84 + 8);
    if ( v85 != v11 )
    {
      if ( v87 && !*((_DWORD *)Src + 4 * v85 + 2) )
      {
        if ( v105 )
        {
          v89 = 5797;
LABEL_261:
          v90 = v129;
LABEL_276:
          v123 = v90;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, v74, (_DWORD)v108, *(_QWORD *)(v25 + 16 * v84) + 40LL);
          NlpWriteEventlogEx(v89, 4u, 0x20000000u, 0xFFFFFFFF, &v122, 2u, 0, 0);
          goto LABEL_280;
        }
        if ( v113 )
        {
          v89 = 5795;
LABEL_264:
          v90 = (unsigned __int16 *)((char *)v117 + 72);
          goto LABEL_276;
        }
        if ( (v110 & 0x4000) != 0 )
        {
          v89 = 5799;
LABEL_275:
          v90 = DomainName;
          goto LABEL_276;
        }
      }
LABEL_280:
      v88 = v104;
      goto LABEL_281;
    }
    v88 = 1;
    v104 = 1;
    if ( v87 )
    {
      if ( v105 )
      {
        v89 = 5787;
        goto LABEL_261;
      }
      if ( v113 )
      {
        v89 = 5785;
        goto LABEL_264;
      }
      if ( (v110 & 0x4000) != 0 )
      {
        v89 = 5793;
        goto LABEL_275;
      }
    }
LABEL_281:
    ++v83;
    ++v84;
    v111 = v83;
    if ( v83 < v75 )
      continue;
    break;
  }
  v91 = 0;
  v20 = v112;
  v104 = v88;
  do
    NlDerefSiteEntry(*(HLOCAL *)(v25 + 16LL * v91++));
  while ( v91 < v75 );
LABEL_286:
  if ( v107 )
  {
    v92 = v117;
    v93 = (void *)*((_QWORD *)v117 + 78);
    if ( v93 )
    {
      LocalFree(v93);
      *((_QWORD *)v92 + 78) = 0;
      *((_DWORD *)v92 + 158) = 0;
    }
    if ( v11 )
    {
      v94 = LocalAlloc(0x40u, 16 * v11);
      *((_QWORD *)v92 + 78) = v94;
      if ( v94 )
      {
        memcpy_0(v94, Src, 16LL * v11);
        *((_DWORD *)v92 + 158) = v11;
      }
      else
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, 16 * v11);
        v20 = 8;
      }
    }
    for ( i = 0; i < *((_DWORD *)v92 + 158); ++i )
      NlRefSiteEntry(*(struct _NL_SITE_ENTRY **)(*((_QWORD *)v92 + 78) + 16LL * i));
  }
  else if ( v113 || (v110 & 0x4000) != 0 )
  {
    v96 = v117;
    v97 = (void *)*((_QWORD *)v117 + 76);
    if ( v97 )
    {
      LocalFree(v97);
      *((_QWORD *)v96 + 76) = 0;
      *((_DWORD *)v96 + 154) = 0;
    }
    if ( v11 )
    {
      v98 = LocalAlloc(0x40u, 16 * v11);
      *((_QWORD *)v96 + 76) = v98;
      if ( v98 )
      {
        memcpy_0(v98, Src, 16LL * v11);
        *((_DWORD *)v96 + 154) = v11;
      }
      else
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, 16 * v11);
        v20 = 8;
      }
    }
    for ( j = 0; j < *((_DWORD *)v96 + 154); ++j )
      NlRefSiteEntry(*(struct _NL_SITE_ENTRY **)(*((_QWORD *)v96 + 76) + 16LL * j));
  }
  ReleaseSRWLockExclusive(SRWLock);
  *v125 = v104;
LABEL_313:
  v18 = Str;
  v19 = (HLOCAL *)Src;
LABEL_314:
  LocalFree(hMem);
  if ( ppInfo )
    DsFreeDomainControllerInfoW(3u, pcOut, ppInfo);
  v100 = pResult;
  if ( pResult )
    DsFreeNameResultW(pResult);
  if ( v124 && (unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent(v100) )
    DsFreeServersAndSitesForNetLogon(v124);
  if ( v19 )
  {
    for ( k = 0; k < v11; ++k )
      NlDerefSiteEntry(v19[2 * k]);
    LocalFree(v19);
  }
  LocalFree(v18);
  return v20;
}

```

## disassembly

```asm
0x18004b568  mov     [rsp-8+arg_8], rbx
0x18004b56d  push    rbp
0x18004b56e  push    rsi
0x18004b56f  push    rdi
0x18004b570  push    r12
0x18004b572  push    r13
0x18004b574  push    r14
0x18004b576  push    r15
0x18004b578  lea     rbp, [rsp-410h]
0x18004b580  sub     rsp, 510h
0x18004b587  mov     rax, cs:__security_cookie
0x18004b58e  xor     rax, rsp
0x18004b591  mov     [rbp+440h+var_40], rax
0x18004b598  mov     r14, r8
0x18004b59b  mov     [rbp+440h+var_480], r9
0x18004b59f  mov     r8, [rbp+440h+arg_28]
0x18004b5a6  xor     r9d, r9d
0x18004b5a9  mov     r15d, edx
0x18004b5ac  mov     [rbp+440h+var_4A8], rcx
0x18004b5b0  and     r15d, 8000h
0x18004b5b7  mov     [rsp+540h+var_4D0], edx
0x18004b5bb  mov     r13d, edx
0x18004b5be  mov     [rbp+440h+var_468], r8
0x18004b5c2  and     r13d, 2000h
0x18004b5c9  mov     [r8], r9d
0x18004b5cc  mov     [rsp+540h+var_4FC], r9d
0x18004b5d1  mov     rsi, rcx
0x18004b5d4  mov     rcx, [rbp+440h+arg_20]
0x18004b5db  mov     ebx, r9d
0x18004b5de  mov     [rbp+440h+SRWLock], rcx
0x18004b5e2  mov     edi, r9d
0x18004b5e5  mov     [rsp+540h+hMem], r9
0x18004b5ea  mov     r12d, r9d
0x18004b5ed  mov     [rbp+440h+ppInfo], r9
0x18004b5f1  mov     [rbp+440h+pcOut], r9d
0x18004b5f5  mov     [rbp+440h+pResult], r9
0x18004b5f9  mov     [rbp+440h+var_470], r9
0x18004b5fd  mov     [rbp+440h+Str], r9
0x18004b601  mov     [rsp+540h+var_4CC], r9d
0x18004b606  mov     [rsp+540h+var_4D8], r9
0x18004b60b  mov     [rsp+540h+var_4E8], r15d
0x18004b610  mov     [rsp+540h+var_4C4], r13d
0x18004b615  test    r15d, r15d
0x18004b618  jz      short loc_18004B623
0x18004b61a  lea     rax, aGc; "GC"
0x18004b621  jmp     short loc_18004B62F
0x18004b623  test    r13d, r13d
0x18004b626  jz      short loc_18004B636
0x18004b628  lea     rax, aDc_0; "DC"
0x18004b62f  mov     [rsp+540h+var_4E0], rax
0x18004b634  jmp     short loc_18004B64A
0x18004b636  bt      edx, 0Eh
0x18004b63a  lea     rdx, aNdnc; "NDNC"
0x18004b641  cmovnb  rdx, r9
0x18004b645  mov     [rsp+540h+var_4E0], rdx
0x18004b64a  test    rcx, rcx
0x18004b64d  jz      short loc_18004B660
0x18004b64f  mov     r12, [rcx]
0x18004b652  mov     [rsp+540h+var_4D8], r12
0x18004b657  test    r12, r12
0x18004b65a  jz      short loc_18004B660
0x18004b65c  mov     ebx, [r12]
0x18004b660  lea     rcx, ?gNlSiteCoverageParameterLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004b667  call    cs:__imp_AcquireSRWLockShared
0x18004b66e  nop     dword ptr [rax+rax+00h]
0x18004b673  test    r15d, r15d
0x18004b676  jz      short loc_18004B681
0x18004b678  mov     rcx, cs:qword_1800F8208
0x18004b67f  jmp     short loc_18004B6A4
0x18004b681  test    r13d, r13d
0x18004b684  jz      short loc_18004B68F
0x18004b686  mov     rcx, cs:qword_1800F8200
0x18004b68d  jmp     short loc_18004B6A4
0x18004b68f  test    [rsp+540h+var_4D0], 4000h
0x18004b697  jz      loc_18004B721
0x18004b69d  mov     rcx, cs:qword_1800F8210
0x18004b6a4  test    rcx, rcx
0x18004b6a7  jz      short loc_18004B721
0x18004b6a9  call    NetpTStrArraySize
0x18004b6ae  mov     edx, eax; uBytes
0x18004b6b0  mov     ecx, 40h ; '@'; uFlags
0x18004b6b5  mov     esi, eax
0x18004b6b7  call    cs:__imp_LocalAlloc
0x18004b6be  nop     dword ptr [rax+rax+00h]
0x18004b6c3  mov     [rbp+440h+Str], rax
0x18004b6c7  mov     r13, rax
0x18004b6ca  test    rax, rax
0x18004b6cd  jnz     short loc_18004B71B
0x18004b6cf  xor     r12d, r12d
0x18004b6d2  mov     r15d, r12d
0x18004b6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b6dc  test    byte ptr [rcx+1Ch], 20h
0x18004b6e0  jz      short loc_18004B6FE
0x18004b6e2  cmp     byte ptr [rcx+19h], 2
0x18004b6e6  jb      short loc_18004B6FE
0x18004b6e8  mov     rcx, [rcx+10h]
0x18004b6ec  lea     edx, [rax+25h]
0x18004b6ef  mov     r9d, esi
0x18004b6f2  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004b6f9  call    WPP_SF_d
0x18004b6fe  lea     rcx, ?gNlSiteCoverageParameterLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004b705  mov     esi, 8
0x18004b70a  call    cs:__imp_ReleaseSRWLockShared
0x18004b711  nop     dword ptr [rax+rax+00h]
0x18004b716  jmp     loc_18004C7EF
0x18004b71b  mov     rsi, [rbp+440h+var_4A8]
0x18004b71f  jmp     short loc_18004B724
0x18004b721  mov     r13, rdi
0x18004b724  lea     rcx, ?gNlSiteCoverageParameterLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004b72b  call    cs:__imp_ReleaseSRWLockShared
0x18004b732  nop     dword ptr [rax+rax+00h]
0x18004b737  test    r13, r13
0x18004b73a  jz      short loc_18004B746
0x18004b73c  mov     rcx, r13
0x18004b73f  call    NetpTStrArrayEntryCount
0x18004b744  add     ebx, eax
0x18004b746  lea     eax, [rbx+1]
0x18004b749  mov     ecx, 40h ; '@'; uFlags
0x18004b74e  shl     eax, 4
0x18004b751  mov     edx, eax; uBytes
0x18004b753  mov     ebx, eax
0x18004b755  call    cs:__imp_LocalAlloc
0x18004b75c  nop     dword ptr [rax+rax+00h]
0x18004b761  mov     [rbp+440h+Src], rax
0x18004b765  mov     r15, rax
0x18004b768  test    rax, rax
0x18004b76b  jnz     short loc_18004B7A3
0x18004b76d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b774  test    byte ptr [rcx+1Ch], 20h
0x18004b778  jz      short loc_18004B796
0x18004b77a  cmp     byte ptr [rcx+19h], 2
0x18004b77e  jb      short loc_18004B796
0x18004b780  mov     rcx, [rcx+10h]
0x18004b784  lea     edx, [rax+26h]
0x18004b787  mov     r9d, ebx
0x18004b78a  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004b791  call    WPP_SF_d
0x18004b796  mov     esi, 8
0x18004b79b  xor     r12d, r12d
0x18004b79e  jmp     loc_18004C7EF
0x18004b7a3  xor     eax, eax
0x18004b7a5  lea     rdx, [rbp+440h+DomainName]; unsigned __int16 *
0x18004b7a9  xor     ebx, ebx
0x18004b7ab  mov     [rsp+540h+var_4C8], eax
0x18004b7af  xor     r8d, r8d; struct _GUID *
0x18004b7b2  mov     [rsp+540h+var_500], ebx
0x18004b7b6  mov     rcx, rsi; struct _DOMAIN_INFO *
0x18004b7b9  xor     r15d, r15d
0x18004b7bc  call    ?NlCaptureDomainInfo@@YAPEAU_GUID@@PEAU_DOMAIN_INFO@@QEAGPEAU1@@Z; NlCaptureDomainInfo(_DOMAIN_INFO *,ushort * const,_GUID *)
0x18004b7c1  lea     rcx, [rbp+440h+var_240]; unsigned __int16 *
0x18004b7c8  call    ?NlCaptureDnsForestName@@YAXQEAG@Z; NlCaptureDnsForestName(ushort * const)
0x18004b7cd  cmp     cs:dword_1800F8218, ebx
0x18004b7d3  mov     r13b, 20h ; ' '
0x18004b7d6  jz      loc_18004BD17
0x18004b7dc  test    r12, r12
0x18004b7df  jz      loc_18004BD17
0x18004b7e5  mov     esi, [r12]
0x18004b7e9  xor     r12d, r12d
0x18004b7ec  mov     dword ptr [rbp+440h+var_4C0], esi
0x18004b7ef  test    esi, esi
0x18004b7f1  jz      loc_18004BD12
0x18004b7f7  lea     ebx, ds:0[rsi*4]
0x18004b7fe  mov     edx, ebx; uBytes
0x18004b800  lea     ecx, [r15+40h]; uFlags
0x18004b804  call    cs:__imp_LocalAlloc
0x18004b80b  nop     dword ptr [rax+rax+00h]
0x18004b810  mov     [rsp+540h+hMem], rax
0x18004b815  mov     rcx, rax
0x18004b818  test    rax, rax
0x18004b81b  jnz     short loc_18004B850
0x18004b81d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b824  test    [rcx+1Ch], r13b
0x18004b828  jz      short loc_18004B846
0x18004b82a  cmp     byte ptr [rcx+19h], 2
0x18004b82e  jb      short loc_18004B846
0x18004b830  mov     rcx, [rcx+10h]
0x18004b834  lea     edx, [rax+27h]
0x18004b837  mov     r9d, ebx
0x18004b83a  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004b841  call    WPP_SF_d
0x18004b846  mov     esi, 8
0x18004b84b  jmp     loc_18004C7E7
0x18004b850  mov     ebx, esi
0x18004b852  mov     [rsp+540h+var_500], ebx
0x18004b856  test    r14, r14
0x18004b859  jz      loc_18004BD1D
0x18004b85f  mov     eax, [rsp+540h+var_4E8]
0x18004b863  test    eax, eax
0x18004b865  jz      loc_18004BA60
0x18004b86b  mov     rcx, [rbp+440h+var_4A8]; struct _DOMAIN_INFO *
0x18004b86f  lea     rax, asc_1800A272C; "."
0x18004b876  mov     [rbp+440h+var_4C0], rax
0x18004b87a  call    ?NlGetDomainFlags@@YAKPEAU_DOMAIN_INFO@@@Z; NlGetDomainFlags(_DOMAIN_INFO *)
0x18004b87f  test    al, 4
0x18004b881  jnz     short loc_18004B8B8
0x18004b883  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b88a  test    [rcx+1Ch], r13b
0x18004b88e  jz      loc_18004BCF2
0x18004b894  cmp     byte ptr [rcx+19h], 4
0x18004b898  jb      loc_18004BCF2
0x18004b89e  mov     rcx, [rcx+10h]
0x18004b8a2  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004b8a9  mov     edx, 28h ; '('
0x18004b8ae  call    WPP_SF_
0x18004b8b3  jmp     loc_18004BA31
0x18004b8b8  lea     rax, [rbp+440h+pResult]
0x18004b8bc  mov     r8d, 0FFFFFFF1h; formatOffered
0x18004b8c2  mov     [rsp+540h+ppResult], rax; ppResult
0x18004b8c7  mov     r9d, r8d; formatDesired
0x18004b8ca  lea     rax, [rbp+440h+var_4C0]
0x18004b8ce  xor     edx, edx; flags
0x18004b8d0  mov     [rsp+540h+rpNames], rax; rpNames
0x18004b8d5  mov     rcx, r14; hDS
0x18004b8d8  mov     [rsp+540h+cNames], 1; cNames
0x18004b8e0  call    cs:__imp_DsCrackNamesW
0x18004b8e7  nop     dword ptr [rax+rax+00h]
0x18004b8ec  mov     [rsp+540h+var_4C8], eax
0x18004b8f0  test    eax, eax
0x18004b8f2  jz      short loc_18004B92C
0x18004b8f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b8fb  test    [rcx+1Ch], r13b
0x18004b8ff  jz      loc_18004BCF2
0x18004b905  cmp     byte ptr [rcx+19h], 2
0x18004b909  jb      loc_18004BCF2
0x18004b90f  mov     rcx, [rcx+10h]
0x18004b913  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004b91a  mov     edx, 29h ; ')'
0x18004b91f  mov     r9d, eax
0x18004b922  call    WPP_SF_d
0x18004b927  jmp     loc_18004BA31
0x18004b92c  mov     rax, [rbp+440h+pResult]
0x18004b930  mov     esi, r12d
0x18004b933  cmp     [rax], r12d
0x18004b936  jbe     loc_18004BCF2
0x18004b93c  mov     r10, cs:WPP_GLOBAL_Control
0x18004b943  mov     r12, [rbp+440h+SRWLock]
0x18004b947  mov     eax, esi
0x18004b949  lea     rdi, [rax+rax*2]
0x18004b94d  mov     rax, [rbp+440h+pResult]
0x18004b951  mov     rdx, [rax+8]
0x18004b955  mov     rbx, [rdx+rdi*8+10h]
0x18004b95a  mov     r14, [rdx+rdi*8+8]
0x18004b95f  test    [r10+1Ch], r13b
0x18004b963  jz      short loc_18004B990
0x18004b965  cmp     byte ptr [r10+19h], 4
0x18004b96a  jb      short loc_18004B990
0x18004b96c  mov     rcx, [r10+10h]
0x18004b970  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004b977  mov     edx, 2Ah ; '*'
0x18004b97c  mov     qword ptr [rsp+540h+cNames], r14
0x18004b981  mov     r9, rbx
0x18004b984  call    WPP_SF_SS
0x18004b989  mov     r10, cs:WPP_GLOBAL_Control
0x18004b990  mov     rax, [rbp+440h+pResult]
0x18004b994  mov     rcx, [rax+8]
0x18004b998  mov     eax, [rcx+rdi*8]
0x18004b99b  test    eax, eax
0x18004b99d  jz      short loc_18004B9CF
0x18004b99f  test    [r10+1Ch], r13b
0x18004b9a3  jz      short loc_18004BA20
0x18004b9a5  cmp     byte ptr [r10+19h], 2
0x18004b9aa  jb      short loc_18004BA20
0x18004b9ac  mov     rcx, [r10+10h]
0x18004b9b0  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004b9b7  mov     dword ptr [rsp+540h+rpNames], eax
0x18004b9bb  mov     edx, 2Bh ; '+'
0x18004b9c0  mov     r9, rbx
0x18004b9c3  mov     qword ptr [rsp+540h+cNames], r14
0x18004b9c8  call    WPP_SF_SSd
0x18004b9cd  jmp     short loc_18004BA19
0x18004b9cf  test    rbx, rbx
0x18004b9d2  jz      short loc_18004BA20
0x18004b9d4  mov     rcx, [r12+18h]; this
0x18004b9d9  lea     r8, [rsp+540h+var_4FC]; unsigned int *
0x18004b9de  mov     rdx, rbx; unsigned __int16 *
0x18004b9e1  call    ?QuerySiteIndex@CNlIsmSiteNameIndexCache@@QEAAHPEAGPEAK@Z; CNlIsmSiteNameIndexCache::QuerySiteIndex(ushort *,ulong *)
0x18004b9e6  test    eax, eax
0x18004b9e8  jnz     short loc_18004BA45
0x18004b9ea  mov     r10, cs:WPP_GLOBAL_Control
0x18004b9f1  test    [r10+1Ch], r13b
0x18004b9f5  jz      short loc_18004BA20
0x18004b9f7  cmp     byte ptr [r10+19h], 4
0x18004b9fc  jb      short loc_18004BA20
0x18004b9fe  mov     rcx, [r10+10h]
0x18004ba02  lea     edx, [rax+2Ch]
0x18004ba05  mov     r9, rbx
0x18004ba08  mov     qword ptr [rsp+540h+cNames], r14
0x18004ba0d  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x18004ba14  call    WPP_SF_SS
0x18004ba19  mov     r10, cs:WPP_GLOBAL_Control
0x18004ba20  mov     rax, [rbp+440h+pResult]
0x18004ba24  inc     esi
0x18004ba26  cmp     esi, [rax]
0x18004ba28  jb      loc_18004B947
0x18004ba2e  xor     r12d, r12d
0x18004ba31  mov     esi, [rsp+540h+var_4E8]
0x18004ba35  mov     edi, esi
0x18004ba37  mov     [rsp+540h+var_4F8], esi
0x18004ba3b  mov     [rsp+540h+var_4FC], r12d
0x18004ba40  jmp     loc_18004C137
  ... truncated ...
```
