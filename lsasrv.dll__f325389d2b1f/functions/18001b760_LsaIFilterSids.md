# LsaIFilterSids

- ea: `0x18001b760`
- end: `0x18001c4cc`
- name: `LsaIFilterSids`
- size: `3436`
- prototype: `__int64 __fastcall(int, int, int, int, void *, int, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180108350`

## callees

- `0x180009330`
- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x18001b464`
- `0x18001b56c`
- `0x18001b760`
- `0x18001c4d4`
- `0x18001ddc0`
- `0x180095c98`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bc040`
- `0x1800bc2c4`
- `0x180105f04`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18001b91c`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18001bfcc`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18001b91c`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18001bfcc`
- `ntdll!RtlCopySid` at `0x18001c1a2`
- `ntdll!RtlCopySid` at `0x18001c333`
- `ntdll!RtlCopySid` at `0x18001c1a2`
- `ntdll!RtlCopySid` at `0x18001c333`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c16f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c1b5`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c2c9`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c348`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c16f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c1b5`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c2c9`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c348`
- `ntdll!RtlSubAuthoritySid` at `0x18001c1d3`
- `ntdll!RtlSubAuthoritySid` at `0x18001c375`
- `ntdll!RtlSubAuthoritySid` at `0x18001c1d3`
- `ntdll!RtlSubAuthoritySid` at `0x18001c375`
- `ntdll!RtlLengthRequiredSid` at `0x18001c181`
- `ntdll!RtlLengthRequiredSid` at `0x18001c2de`
- `ntdll!RtlLengthRequiredSid` at `0x18001c181`
- `ntdll!RtlLengthRequiredSid` at `0x18001c2de`
- `ntdll!RtlInitUnicodeString` at `0x18001b87f`
- `ntdll!RtlInitUnicodeString` at `0x18001b87f`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledBySubCategory` at `0x18001c13b`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledBySubCategory` at `0x18001c13b`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditSidFiltration` at `0x18001c418`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditSidFiltration` at `0x18001c418`

## pseudocode

```c
__int64 __fastcall LsaIFilterSids(
        __m128i *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        void *a5,
        int a6,
        __int64 a7,
        void *a8,
        _DWORD *a9,
        __int64 a10)
{
  unsigned int v10; // r13d
  unsigned int v12; // edi
  LsaHandleCache *v14; // rcx
  __int64 v15; // rdx
  __m128i v16; // xmm0
  unsigned __int16 v17; // dx
  void *v18; // rcx
  BOOL WindowsAccountDomainSid; // ebx
  bool WindowsAccountCloudDomainSid; // r15
  __int64 v21; // rdx
  LsaHandleCache *v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // eax
  LsaHandleCache *v25; // rcx
  __int64 v26; // rdx
  __int64 result; // rax
  unsigned int v28; // ecx
  unsigned int v29; // ebx
  __int64 v30; // rcx
  int v31; // eax
  int v32; // eax
  __int64 v33; // r9
  int v34; // ebx
  unsigned __int8 v35; // dl
  int v36; // r12d
  __int64 v37; // r8
  __int64 i; // r15
  unsigned __int64 v39; // rcx
  __int64 v40; // rax
  unsigned int v41; // ebx
  int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdx
  int v46; // r15d
  unsigned int v47; // r12d
  unsigned int v48; // eax
  unsigned __int64 v49; // r15
  unsigned int *v50; // rbx
  unsigned __int64 v51; // rcx
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rcx
  void *v54; // rsp
  void *v55; // rsp
  unsigned __int64 v56; // rcx
  unsigned int *v57; // rax
  const struct _NETLOGON_SID_AND_ATTRIBUTES *v58; // rdx
  unsigned int v59; // r13d
  unsigned int v60; // ecx
  int v61; // edx
  __int64 j; // r15
  unsigned int v63; // ecx
  __int64 v64; // rcx
  unsigned int v65; // r8d
  int v66; // r13d
  unsigned int v67; // eax
  unsigned int v68; // ecx
  __int128 v69; // xmm1
  unsigned int v70; // r11d
  __int64 v71; // rdx
  __int128 v72; // xmm0
  unsigned int v73; // eax
  unsigned int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // rax
  __int128 v77; // xmm0
  LsaHandleCache *v78; // rcx
  __int64 v79; // rdx
  PSID v80; // rax
  __int64 v81; // r9
  __int64 k; // rbx
  unsigned int v83; // edx
  ULONG v84; // edi
  ULONG v85; // eax
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // r9
  PUCHAR v89; // rax
  ULONG v90; // ebx
  int v91; // ecx
  unsigned int v92; // eax
  unsigned int v93; // eax
  unsigned int *v94; // rbx
  unsigned __int64 v95; // rdi
  unsigned __int64 v96; // rcx
  __int64 v97; // rcx
  unsigned __int64 v98; // rcx
  void *v99; // rsp
  void *v100; // rsp
  unsigned int *v101; // rax
  __int64 v102; // r13
  unsigned int m; // esi
  __int64 v104; // rax
  void *v105; // rdx
  PUCHAR v106; // rax
  ULONG v107; // ebx
  PULONG v108; // rax
  int v109; // r9d
  int v110; // ecx
  unsigned int v111; // r10d
  __int64 v112; // r8
  __int64 v113; // rdx
  unsigned int v114; // ebx
  struct _RTL_BALANCED_NODE *v115; // rcx
  _BYTE v116[32]; // [rsp+0h] [rbp-40h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+20h] [rbp-20h]
  struct _NETLOGON_SID_AND_ATTRIBUTES *v118; // [rsp+28h] [rbp-18h]
  unsigned int v119; // [rsp+40h] [rbp+0h] BYREF
  int v120; // [rsp+44h] [rbp+4h] BYREF
  unsigned int v121; // [rsp+48h] [rbp+8h] BYREF
  unsigned int v122; // [rsp+4Ch] [rbp+Ch]
  __int128 v123; // [rsp+50h] [rbp+10h] BYREF
  int v124; // [rsp+60h] [rbp+20h]
  DWORD v125; // [rsp+64h] [rbp+24h] BYREF
  ULONG SubAuthority; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbDomainSid; // [rsp+6Ch] [rbp+2Ch] BYREF
  unsigned int v128; // [rsp+70h] [rbp+30h]
  __int64 v129; // [rsp+78h] [rbp+38h]
  void *v130; // [rsp+80h] [rbp+40h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp+48h] BYREF
  unsigned int v132; // [rsp+9Ch] [rbp+5Ch]
  unsigned int v133; // [rsp+A0h] [rbp+60h]
  _DWORD *v134; // [rsp+A8h] [rbp+68h]
  PSID pSid[2]; // [rsp+B0h] [rbp+70h] BYREF
  __int64 v136; // [rsp+C0h] [rbp+80h]
  char pDomainSid; // [rsp+C8h] [rbp+88h] BYREF
  unsigned __int8 v138; // [rsp+C9h] [rbp+89h]
  _DWORD v139[16]; // [rsp+D0h] [rbp+90h]
  _BYTE DestinationSid[80]; // [rsp+110h] [rbp+D0h] BYREF

  v10 = 0;
  v12 = a4;
  pSid[0] = a8;
  v134 = a9;
  v128 = a4;
  v132 = a3;
  v133 = a2;
  v130 = a5;
  v129 = a10;
  v121 = 0;
  SubAuthority = 0;
  HIDWORD(v123) = 0;
  cbDomainSid = 0;
  v120 = 0;
  DestinationString = 0;
  if ( a3 == 3 )
    return 3221225883LL;
  if ( a5 )
  {
    if ( (a2 & 2) == 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
      {
        v15 = 13;
LABEL_182:
        WPP_SF_(*((_QWORD *)v14 + 12), v15, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids);
        return 3221225485LL;
      }
      return 3221225485LL;
    }
  }
  else if ( a2 || a3 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
    {
      v15 = 14;
      goto LABEL_182;
    }
    return 3221225485LL;
  }
  if ( ((a6 - 2) & 0xFFFFFFFA) != 0 || a6 == 7 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
    {
      v15 = 15;
      goto LABEL_182;
    }
    return 3221225485LL;
  }
  if ( (int)LsapLoadLsaDbExtensionDll() < 0 || !(*((unsigned __int8 (**)(void))g_pLsaExtensionTableLsaDb + 29))() )
  {
    v12 &= ~8u;
    v128 = v12;
  }
  if ( a1 )
  {
    v16 = *a1;
    v17 = _mm_cvtsi128_si32(*a1);
    DestinationString = (struct _UNICODE_STRING)*a1;
    if ( v17 >> 1 && *(_WORD *)(_mm_srli_si128(v16, 8).m128i_u64[0] + 2LL * (v17 >> 1) - 2) == 46 )
      DestinationString.Length = v17 - 2;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, 0);
  }
  if ( a5 )
  {
    if ( (int)LsapLoadLsaDbExtensionDll() >= 0 )
      (*((void (__fastcall **)(void *, _QWORD, _QWORD, unsigned int *))g_pLsaExtensionTableLsaDb + 9))(
        a5,
        a3,
        v12,
        &v121);
  }
  else
  {
    v121 = 5;
  }
  v18 = *(void **)(a7 + 224);
  *(_QWORD *)&v123 = &pDomainSid;
  DWORD2(v123) = 0;
  cbDomainSid = 68;
  WindowsAccountDomainSid = GetWindowsAccountDomainSid(v18, &pDomainSid, &cbDomainSid);
  WindowsAccountCloudDomainSid = WindowsAccountDomainSid;
  LOBYTE(v21) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers>::GetImpl'::`2'::impl,
    v21);
  if ( !WindowsAccountDomainSid )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids);
    WindowsAccountCloudDomainSid = GetWindowsAccountCloudDomainSid(*(PSID *)(a7 + 224), &pDomainSid, &cbDomainSid);
  }
  if ( !WindowsAccountCloudDomainSid )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
    {
      v23 = 18;
LABEL_115:
      WPP_SF_(*((_QWORD *)v22 + 12), v23, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids);
      return 3221225883LL;
    }
    return 3221225883LL;
  }
  v24 = v138;
  if ( v138 >= 0xFu )
  {
    v25 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) == 0 )
      return 3221225883LL;
    v26 = 19;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v25 + 12), v26, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids, v24);
    return 3221225883LL;
  }
  v28 = *(_DWORD *)(a7 + 148);
  if ( v28 )
  {
    result = LsapSidFilterCheckById(
               v28,
               &pDomainSid,
               v121,
               a5,
               &DestinationString,
               (struct _NETLOGON_SID_AND_ATTRIBUTES *)&v123,
               &v120);
    if ( (int)result < 0 )
      return result;
    v125 = 0;
    if ( !v120 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
      {
        v23 = 20;
        goto LABEL_115;
      }
      return 3221225883LL;
    }
    LOBYTE(v24) = v138;
  }
  else
  {
    v125 = 1;
  }
  v29 = v121;
  v30 = (unsigned __int8)v24;
  v31 = *(_DWORD *)(a7 + 152);
  v119 = 0;
  v139[v30] = v31;
  ++v138;
  LsapClassifySids(1u, (const struct _NETLOGON_SID_AND_ATTRIBUTES *)&v123, &v119);
  v32 = LsapSidFilterCheck(&pDomainSid, v29, v119, a5, &DestinationString, &v120);
  v34 = v32;
  if ( v32 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) == 0 )
      goto LABEL_46;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      10,
      WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids,
      (unsigned int)v32);
  }
  v22 = WPP_GLOBAL_Control;
LABEL_46:
  v35 = --v138;
  if ( v34 < 0 )
    return (unsigned int)v34;
  if ( !v120 )
  {
    if ( (*((_DWORD *)v22 + 27) & 0x200) != 0 )
    {
      v23 = 21;
      goto LABEL_115;
    }
    return 3221225883LL;
  }
  v36 = 0;
  v37 = 0xFFFFFFFFLL;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v39 = *(unsigned int *)(a7 + 156);
    if ( (unsigned int)i >= *(_DWORD *)(a7 + 156) - v36 )
      break;
    v40 = *(_QWORD *)(a7 + 160);
    v41 = v121;
    v119 = 0;
    v139[v35] = *(_DWORD *)(v40 + 8 * i);
    ++v138;
    LsapClassifySids(1u, (const struct _NETLOGON_SID_AND_ATTRIBUTES *)&v123, &v119);
    v42 = LsapSidFilterCheck(&pDomainSid, v41, v119, v130, &DestinationString, &v120);
    v34 = v42;
    if ( v42 < 0 && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        10,
        WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids,
        (unsigned int)v42);
    v35 = --v138;
    if ( v34 < 0 )
      return (unsigned int)v34;
    if ( v120 )
    {
      v37 = 0xFFFFFFFFLL;
      ++v10;
    }
    else
    {
      v33 = (unsigned int)(*(_DWORD *)(a7 + 156) + ~v36);
      if ( (_DWORD)i != (_DWORD)v33 )
      {
        v43 = *(_QWORD *)(a7 + 160);
        v44 = *(_QWORD *)(v43 + 8 * i);
        *(_QWORD *)(v43 + 8 * i) = *(_QWORD *)(v43 + 8 * v33);
        *(_QWORD *)(*(_QWORD *)(a7 + 160) + 8 * v33) = v44;
        v35 = v138;
      }
      v37 = 0xFFFFFFFFLL;
      ++v36;
      LODWORD(i) = i - 1;
    }
  }
  v45 = 0;
  v46 = 0;
  *(_DWORD *)(a7 + 156) = v10;
  v119 = 0;
  v47 = v10 < (unsigned int)v39 ? v39 : 0;
  if ( (a6 == 6 || a6 == 3) && (v48 = *(_DWORD *)(a7 + 272)) != 0 )
  {
    v49 = 4LL * v48;
    if ( v49 <= 0xFFFFFFFF )
    {
      v50 = 0;
      if ( !(_DWORD)v49 )
        goto LABEL_75;
      if ( (unsigned int)v49 > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_75;
      v51 = (unsigned int)v49 + g_ulAdditionalProbeSize + 8;
      if ( v51 < (unsigned int)v49 || !(unsigned int)VerifyStackAvailable(v51, 0, 0xFFFFFFFFLL, v33) )
        goto LABEL_75;
      v52 = (unsigned int)v49 + 23LL;
      if ( v52 <= (unsigned __int64)(unsigned int)v49 + 8 )
        v52 = 0xFFFFFFFFFFFFFF0LL;
      v53 = v52 & 0xFFFFFFFFFFFFFFF0uLL;
      v54 = alloca(v53);
      v55 = alloca(v53);
      v50 = &v119;
      if ( v116 == (_BYTE *)-64LL || (v119 = 1801679955, (v50 = &v121) == 0) )
      {
LABEL_75:
        v56 = (unsigned int)v49 + 8LL;
        if ( v56 >= (unsigned int)v49 )
        {
          v57 = (unsigned int *)((__int64 (__fastcall *)(unsigned __int64, __int64, __int64))g_pfnAllocate)(
                                  v56,
                                  v45,
                                  v37);
          v50 = v57;
          if ( v57 )
          {
            *v57 = 1885431112;
            v50 = v57 + 2;
          }
        }
      }
      if ( !v50 )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids);
        return 3221225626LL;
      }
      v58 = *(const struct _NETLOGON_SID_AND_ATTRIBUTES **)(a7 + 280);
      v59 = 0;
      v60 = *(_DWORD *)(a7 + 272);
      v122 = 0;
      LsapClassifySids(v60, v58, v50);
      v61 = 0;
      v124 = 0;
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        v63 = *(_DWORD *)(a7 + 272);
        if ( (unsigned int)j >= v63 - v61 )
        {
          *(_DWORD *)(a7 + 272) = v59;
          v46 = v59 < v63 ? v63 : 0;
          v39 = (unsigned __int64)(v50 - 2);
          if ( *(v50 - 2) == 1885431112 )
            ((void (*)(void))g_pfnFree)();
          v45 = v119;
          goto LABEL_104;
        }
        v64 = *(_QWORD *)(a7 + 280);
        v118 = (struct _NETLOGON_SID_AND_ATTRIBUTES *)&v120;
        p_DestinationString = &DestinationString;
        v65 = v50[j];
        *(_QWORD *)&v123 = &v50[j];
        v136 = 16LL * (unsigned int)j;
        v66 = LsapSidFilterCheck(*(PSID *)(v64 + v136), v121, v65, v130, &DestinationString, &v120);
        if ( v66 < 0 )
          break;
        if ( v120 )
        {
          v74 = v119;
          if ( !(_DWORD)j )
            v74 = 1;
          v75 = *(_QWORD *)(a7 + 280);
          v119 = v74;
          v76 = 2LL * v122;
          v59 = v122 + 1;
          v77 = *(_OWORD *)(v136 + v75);
          v61 = v124;
          ++v122;
          *(_OWORD *)(v75 + 8 * v76) = v77;
        }
        else
        {
          v61 = v124 + 1;
          v67 = *(_DWORD *)(a7 + 272) - 1;
          ++v124;
          if ( (unsigned int)j < v67 )
          {
            v68 = j;
            v69 = *(_OWORD *)(*(_QWORD *)(a7 + 280) + v136);
            v70 = *(_DWORD *)v123;
            do
            {
              v71 = *(_QWORD *)(a7 + 280);
              v37 = v68;
              v72 = *(_OWORD *)(v71 + 16LL * ++v68);
              *(_OWORD *)(v71 + 16LL * (unsigned int)v37) = v72;
              v50[v37] = v50[v68];
              v73 = *(_DWORD *)(a7 + 272) - 1;
            }
            while ( v68 < v73 );
            v61 = v124;
            *(_OWORD *)(*(_QWORD *)(a7 + 280) + 16LL * v73) = v69;
            v50[*(_DWORD *)(a7 + 272) - 1] = v70;
            LODWORD(j) = j - 1;
          }
          v59 = v122;
        }
      }
      if ( *(v50 - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      v78 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
      {
        v79 = 24;
        goto LABEL_99;
      }
      return (unsigned int)v66;
    }
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids, 3221225621LL);
    return 3221225621LL;
  }
  else
  {
LABEL_104:
    if ( v125 && !(_DWORD)v45 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
      {
        v23 = 25;
        goto LABEL_115;
      }
      return 3221225883LL;
    }
    v80 = pSid[0];
    if ( pSid[0] )
    {
      pSid[1] = 0;
      pSid[0] = &pDomainSid;
      v125 = 68;
      if ( !GetWindowsAccountDomainSid(v80, &pDomainSid, &v125) )
      {
        v22 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0 )
        {
          v23 = 26;
          goto LABEL_115;
        }
        return 3221225883LL;
      }
      v24 = v138;
      if ( v138 >= 0xFu )
      {
        v25 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) == 0 )
          return 3221225883LL;
        v26 = 27;
        goto LABEL_32;
      }
      v37 = (__int64)v134;
      if ( v134 )
      {
        v81 = v129;
        if ( v129 )
        {
          v45 = 0;
          v122 = v138;
          v39 = v138;
          v119 = 0;
          ++v138;
          for ( k = 0; ; k = (unsigned int)(k + 1) )
          {
            if ( (unsigned int)k >= *(_DWORD *)v37 )
            {
              --v138;
              *(_DWORD *)v37 = v45;
              goto LABEL_132;
            }
            v139[(int)v39] = *(_DWORD *)(v81 + 8 * k);
            LsapClassifySids(1u, (const struct _NETLOGON_SID_AND_ATTRIBUTES *)pSid, &SubAuthority);
            v66 = LsapSidFilterCheck(&pDomainSid, v121, SubAuthority, v130, &DestinationString, &v120);
            if ( v66 < 0 )
              break;
            v37 = (__int64)v134;
            v81 = v129;
            if ( v120 && (unsigned int)k < *v134 )
            {
              v83 = v119;
              *(_QWORD *)(v129 + 8LL * v119) = *(_QWORD *)(v129 + 8 * k);
              v45 = v83 + 1;
              v119 = v45;
            }
            else
            {
              v45 = v119;
            }
            v39 = v122;
          }
          v78 = WPP_GLOBAL_Control;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) == 0 )
            return (unsigned int)v66;
          v79 = 28;
LABEL_99:
          WPP_SF_d(*((_QWORD *)v78 + 12), v79, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids, (unsigned int)v66);
          return (unsigned int)v66;
        }
      }
    }
LABEL_132:
    if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(v39, v45, v37)
      && (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent()
      && (v46 || v47)
      && (unsigned __int8)LsapAdtAuditingEnabledBySubCategory(105) )
    {
      v123 = 0;
      memset_0(DestinationSid, 0, 0x44u);
      v84 = *RtlSubAuthorityCountSid(*(PSID *)(a7 + 224));
      v85 = RtlLengthRequiredSid(v84 + 1);
      if ( v85 <= 0x44 )
      {
        RtlCopySid(v85, DestinationSid, *(PSID *)(a7 + 224));
        v89 = RtlSubAuthorityCountSid(DestinationSid);
        ++*v89;
        v90 = *(_DWORD *)(a7 + 148);
        *RtlSubAuthoritySid(DestinationSid, v84) = v90;
      }
      if ( v46 )
        v91 = v46 - *(_DWORD *)(a7 + 272);
      else
        v91 = 0;
      if ( v47 )
        v92 = v47 - *(_DWORD *)(a7 + 156);
      else
        v92 = 0;
      v93 = v91 + v92;
      v94 = 0;
      v95 = 16LL * v93;
      LODWORD(v123) = v93;
      if ( !v95 )
        goto LABEL_186;
      if ( v95 > g_ulMaxStackAllocSize )
        goto LABEL_186;
      v96 = v95 + g_ulAdditionalProbeSize + 8;
      if ( v96 < v95 || !(unsigned int)VerifyStackAvailable(v96, v86, v87, v88) )
        goto LABEL_186;
      v97 = v95 + 23;
      if ( v95 + 23 <= v95 + 8 )
        v97 = 0xFFFFFFFFFFFFFF0LL;
      v98 = v97 & 0xFFFFFFFFFFFFFFF0uLL;
      v99 = alloca(v98);
      v100 = alloca(v98);
      v94 = &v119;
      if ( v116 == (_BYTE *)-64LL || (v119 = 1801679955, (v94 = &v121) == 0) )
      {
LABEL_186:
        if ( v95 + 8 >= v95 )
        {
          v101 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
          v94 = v101;
          if ( v101 )
          {
            *v101 = 1885431112;
            v94 = v101 + 2;
          }
        }
      }
      *((_QWORD *)&v123 + 1) = v94;
      if ( v94 )
      {
        memset_0(v94, 0, 16LL * (unsigned int)v123);
        if ( v47 )
        {
          SubAuthority = *RtlSubAuthorityCountSid(*(PSID *)(a7 + 224));
          v102 = RtlLengthRequiredSid(SubAuthority + 1);
          for ( m = 0; m < v47 - *(_DWORD *)(a7 + 156); ++m )
          {
            v104 = LsapAllocate(v102);
            *(_QWORD *)(*((_QWORD *)&v123 + 1) + 16LL * m + 8) = v104;
            v105 = *(void **)(*((_QWORD *)&v123 + 1) + 16LL * m + 8);
            if ( !v105 )
              goto LABEL_170;
            RtlCopySid(v102, v105, *(PSID *)(a7 + 224));
            v106 = RtlSubAuthorityCountSid(*(PSID *)(*((_QWORD *)&v123 + 1) + 16LL * m + 8));
            ++*v106;
            v107 = *(_DWORD *)(*(_QWORD *)(a7 + 160) + 8LL * (m + *(_DWORD *)(a7 + 156)));
            v108 = RtlSubAuthoritySid(*(PSID *)(*((_QWORD *)&v123 + 1) + 16LL * m + 8), SubAuthority);
            *v108 = v107;
          }
        }
        if ( v46 )
        {
          v109 = v47 ? v47 - *(_DWORD *)(a7 + 156) : 0;
          v110 = *(_DWORD *)(a7 + 272);
          if ( v46 != v110 )
          {
            v111 = 0;
            do
            {
              v112 = 2LL * (v111 + v110);
              v113 = 2LL * (v111 + v109);
              ++v111;
              *(_QWORD *)(*((_QWORD *)&v123 + 1) + 8 * v113 + 8) = *(_QWORD *)(*(_QWORD *)(a7 + 280) + 8 * v112);
              v110 = *(_DWORD *)(a7 + 272);
            }
            while ( v111 < v46 - v110 );
          }
        }
        LsapAdtAuditSidFiltration(DestinationSid, 0, 0, v133, v128, v132, v130, &v123);
        if ( v47 )
        {
LABEL_170:
          v114 = 0;
          if ( v47 != *(_DWORD *)(a7 + 156) )
          {
            do
            {
              v115 = *(struct _RTL_BALANCED_NODE **)(*((_QWORD *)&v123 + 1) + 16LL * v114 + 8);
              if ( v115 )
                LsapSubProv_FreeRoutine(v115, v105);
              ++v114;
            }
            while ( v114 < v47 - *(_DWORD *)(a7 + 156) );
          }
        }
        if ( *((_QWORD *)&v123 + 1) && *(_DWORD *)(*((_QWORD *)&v123 + 1) - 8LL) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18001b760  push    rbp
0x18001b762  push    rbx
0x18001b763  push    rsi
0x18001b764  push    rdi
0x18001b765  push    r12
0x18001b767  push    r13
0x18001b769  push    r14
0x18001b76b  push    r15
0x18001b76d  sub     rsp, 178h
0x18001b774  lea     rbp, [rsp+40h]
0x18001b779  mov     rax, cs:__security_cookie
0x18001b780  xor     rax, rbp
0x18001b783  mov     [rbp+170h+var_50], rax
0x18001b78a  mov     rax, [rbp+170h+arg_38]
0x18001b791  xor     r13d, r13d
0x18001b794  mov     r12, [rbp+170h+arg_20]
0x18001b79b  mov     rbx, rcx
0x18001b79e  mov     rcx, [rbp+170h+arg_48]
0x18001b7a5  xorps   xmm0, xmm0
0x18001b7a8  mov     r14, [rbp+170h+arg_30]
0x18001b7af  mov     edi, r9d
0x18001b7b2  mov     [rbp+170h+pSid], rax
0x18001b7b6  mov     esi, r8d
0x18001b7b9  mov     rax, [rbp+170h+arg_40]
0x18001b7c0  mov     [rbp+170h+var_108], rax
0x18001b7c4  mov     [rbp+170h+var_140], r9d
0x18001b7c8  mov     [rbp+170h+var_114], r8d
0x18001b7cc  mov     [rbp+170h+var_110], edx
0x18001b7cf  mov     [rbp+170h+var_130], r12
0x18001b7d3  mov     [rbp+170h+var_138], rcx
0x18001b7d7  mov     [rbp+170h+var_168], r13d
0x18001b7db  mov     [rbp+170h+SubAuthority], r13d
0x18001b7df  mov     dword ptr [rbp+170h+var_160+0Ch], r13d
0x18001b7e3  mov     [rbp+170h+cbDomainSid], r13d
0x18001b7e7  mov     [rbp+170h+var_16C], r13d
0x18001b7eb  movups  xmmword ptr [rbp+170h+DestinationString.Length], xmm0
0x18001b7ef  cmp     r8d, 3
0x18001b7f3  jz      loc_18001B9C9
0x18001b7f9  test    r12, r12
0x18001b7fc  jz      short loc_18001B821
0x18001b7fe  test    dl, 2
0x18001b801  jnz     short loc_18001B831
0x18001b803  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b80a  mov     edi, 200h
0x18001b80f  test    [rcx+6Ch], edi
0x18001b812  jz      loc_18001C4C2
0x18001b818  lea     edx, [r13+0Dh]
0x18001b81c  jmp     loc_18001C4B2
0x18001b821  test    edx, edx
0x18001b823  jnz     loc_18001C49C
0x18001b829  test    esi, esi
0x18001b82b  jnz     loc_18001C49C
0x18001b831  mov     ecx, [rbp+170h+arg_28]
0x18001b837  lea     eax, [rcx-2]
0x18001b83a  test    eax, 0FFFFFFFAh
0x18001b83f  jnz     loc_18001C484
0x18001b845  cmp     ecx, 7
0x18001b848  jz      loc_18001C484
0x18001b84e  call    ?LsapLoadLsaDbExtensionDll@@YAJXZ; LsapLoadLsaDbExtensionDll(void)
0x18001b853  test    eax, eax
0x18001b855  js      short loc_18001B86E
0x18001b857  mov     rax, cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18001b85e  mov     rax, [rax+0E8h]
0x18001b865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b86a  test    al, al
0x18001b86c  jnz     short loc_18001B874
0x18001b86e  and     edi, 0FFFFFFF7h
0x18001b871  mov     [rbp+170h+var_140], edi
0x18001b874  test    rbx, rbx
0x18001b877  jnz     short loc_18001B88D
0x18001b879  xor     edx, edx; SourceString
0x18001b87b  lea     rcx, [rbp+170h+DestinationString]; DestinationString
0x18001b87f  call    cs:__imp_RtlInitUnicodeString
0x18001b886  nop     dword ptr [rax+rax+00h]
0x18001b88b  jmp     short loc_18001B8C1
0x18001b88d  movups  xmm0, xmmword ptr [rbx]
0x18001b890  movd    edx, xmm0
0x18001b894  movups  xmmword ptr [rbp+170h+DestinationString.Length], xmm0
0x18001b898  movzx   eax, dx
0x18001b89b  shr     ax, 1
0x18001b89e  jz      short loc_18001B8C1
0x18001b8a0  movzx   ecx, ax
0x18001b8a3  psrldq  xmm0, 8
0x18001b8a8  movq    rax, xmm0
0x18001b8ad  cmp     word ptr [rax+rcx*2-2], 2Eh ; '.'
0x18001b8b3  jnz     short loc_18001B8C1
0x18001b8b5  mov     eax, 0FFFEh
0x18001b8ba  add     dx, ax
0x18001b8bd  mov     [rbp+170h+DestinationString.Length], dx
0x18001b8c1  test    r12, r12
0x18001b8c4  jnz     short loc_18001B8CF
0x18001b8c6  mov     [rbp+170h+var_168], 5
0x18001b8cd  jmp     short loc_18001B8F4
0x18001b8cf  call    ?LsapLoadLsaDbExtensionDll@@YAJXZ; LsapLoadLsaDbExtensionDll(void)
0x18001b8d4  test    eax, eax
0x18001b8d6  js      short loc_18001B8F4
0x18001b8d8  mov     rax, cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18001b8df  lea     r9, [rbp+170h+var_168]
0x18001b8e3  mov     r8d, edi
0x18001b8e6  mov     edx, esi
0x18001b8e8  mov     rcx, r12
0x18001b8eb  mov     rax, [rax+48h]
0x18001b8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8f4  mov     rcx, [r14+0E0h]; pSid
0x18001b8fb  lea     rax, [rbp+170h+pDomainSid]
0x18001b902  lea     r8, [rbp+170h+cbDomainSid]; cbDomainSid
0x18001b906  mov     qword ptr [rbp+170h+var_160], rax
0x18001b90a  lea     rdx, [rbp+170h+pDomainSid]; pDomainSid
0x18001b911  mov     dword ptr [rbp+170h+var_160+8], r13d
0x18001b915  mov     [rbp+170h+cbDomainSid], 44h ; 'D'
0x18001b91c  call    cs:__imp_GetWindowsAccountDomainSid
0x18001b923  nop     dword ptr [rax+rax+00h]
0x18001b928  test    eax, eax
0x18001b92a  mov     ebx, eax
0x18001b92c  setnz   r15b
0x18001b930  mov     dl, 1
0x18001b932  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers> `wil::Feature<__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers>::GetImpl(void)'::`2'::impl
0x18001b939  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001b93e  lea     rsi, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids
0x18001b945  mov     edi, 200h
0x18001b94a  test    ebx, ebx
0x18001b94c  jnz     short loc_18001B983
0x18001b94e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b955  test    [rcx+6Ch], edi
0x18001b958  jz      short loc_18001B969
0x18001b95a  mov     rcx, [rcx+60h]
0x18001b95e  lea     edx, [rbx+11h]
0x18001b961  mov     r8, rsi
0x18001b964  call    WPP_SF_
0x18001b969  mov     rcx, [r14+0E0h]; Sid
0x18001b970  lea     r8, [rbp+170h+cbDomainSid]; unsigned int *
0x18001b974  lea     rdx, [rbp+170h+pDomainSid]; PSID
0x18001b97b  call    ?GetWindowsAccountCloudDomainSid@@YA_NPEAX0PEAK@Z; GetWindowsAccountCloudDomainSid(void *,void *,ulong *)
0x18001b980  mov     r15b, al
0x18001b983  test    r15b, r15b
0x18001b986  jnz     short loc_18001B99E
0x18001b988  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b98f  test    [rcx+6Ch], edi
0x18001b992  jz      short loc_18001B9C9
0x18001b994  mov     edx, 12h
0x18001b999  jmp     loc_18001BFEF
0x18001b99e  movzx   eax, [rbp+170h+var_E7]
0x18001b9a5  cmp     al, 0Fh
0x18001b9a7  jb      short loc_18001B9F2
0x18001b9a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9b0  test    [rcx+6Ch], edi
0x18001b9b3  jz      short loc_18001B9C9
0x18001b9b5  mov     edx, 13h
0x18001b9ba  mov     rcx, [rcx+60h]
0x18001b9be  mov     r9d, eax
0x18001b9c1  mov     r8, rsi
0x18001b9c4  call    WPP_SF_d
0x18001b9c9  mov     eax, 0C000019Bh
0x18001b9ce  mov     rcx, [rbp+170h+var_50]
0x18001b9d5  xor     rcx, rbp; StackCookie
0x18001b9d8  call    __security_check_cookie
0x18001b9dd  lea     rsp, [rbp+138h]
0x18001b9e4  pop     r15
0x18001b9e6  pop     r14
0x18001b9e8  pop     r13
0x18001b9ea  pop     r12
0x18001b9ec  pop     rdi
0x18001b9ed  pop     rsi
0x18001b9ee  pop     rbx
0x18001b9ef  pop     rbp
0x18001b9f0  retn
0x18001b9f2  mov     ecx, [r14+94h]; unsigned int
0x18001b9f9  test    ecx, ecx
0x18001b9fb  jnz     short loc_18001BA06
0x18001b9fd  mov     [rbp+170h+var_14C], 1
0x18001ba04  jmp     short loc_18001BA62
0x18001ba06  mov     r8d, [rbp+170h+var_168]; unsigned int
0x18001ba0a  lea     rax, [rbp+170h+var_16C]
0x18001ba0e  mov     [rsp+1B0h+var_180], rax; int *
0x18001ba13  lea     rdx, [rbp+170h+pDomainSid]; void *
0x18001ba1a  lea     rax, [rbp+170h+var_160]
0x18001ba1e  mov     r9, r12; void *
0x18001ba21  mov     [rsp+1B0h+var_188], rax; struct _NETLOGON_SID_AND_ATTRIBUTES *
0x18001ba26  lea     rax, [rbp+170h+DestinationString]
0x18001ba2a  mov     [rsp+1B0h+var_190], rax; struct _UNICODE_STRING *
0x18001ba2f  call    ?LsapSidFilterCheckById@@YAJKPEAXK0PEAU_UNICODE_STRING@@PEAU_NETLOGON_SID_AND_ATTRIBUTES@@PEAH@Z; LsapSidFilterCheckById(ulong,void *,ulong,void *,_UNICODE_STRING *,_NETLOGON_SID_AND_ATTRIBUTES *,int *)
0x18001ba34  test    eax, eax
0x18001ba36  js      short loc_18001B9CE
0x18001ba38  mov     [rbp+170h+var_14C], r13d
0x18001ba3c  cmp     [rbp+170h+var_16C], r13d
0x18001ba40  jnz     short loc_18001BA5C
0x18001ba42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba49  test    [rcx+6Ch], edi
0x18001ba4c  jz      loc_18001B9C9
0x18001ba52  mov     edx, 14h
0x18001ba57  jmp     loc_18001BFEF
0x18001ba5c  mov     al, [rbp+170h+var_E7]
0x18001ba62  mov     ebx, [rbp+170h+var_168]
0x18001ba65  lea     r8, [rbp+170h+var_170]; unsigned int *
0x18001ba69  movzx   ecx, al
0x18001ba6c  lea     rdx, [rbp+170h+var_160]; struct _NETLOGON_SID_AND_ATTRIBUTES *
0x18001ba70  mov     eax, [r14+98h]
0x18001ba77  mov     [rbp+170h+var_170], r13d
0x18001ba7b  mov     [rbp+rcx*4+170h+var_E0], eax
0x18001ba82  mov     eax, 1
0x18001ba87  add     [rbp+170h+var_E7], al
0x18001ba8d  mov     ecx, eax; unsigned int
0x18001ba8f  call    ?LsapClassifySids@@YAXKPEBU_NETLOGON_SID_AND_ATTRIBUTES@@PEAK@Z; LsapClassifySids(ulong,_NETLOGON_SID_AND_ATTRIBUTES const *,ulong *)
0x18001ba94  mov     r8d, [rbp+170h+var_170]; unsigned int
0x18001ba98  lea     rax, [rbp+170h+var_16C]
0x18001ba9c  mov     [rsp+1B0h+var_188], rax; int *
0x18001baa1  lea     rcx, [rbp+170h+pDomainSid]; pSid1
0x18001baa8  lea     rax, [rbp+170h+DestinationString]
0x18001baac  mov     r9, r12; void *
0x18001baaf  mov     edx, ebx; unsigned int
0x18001bab1  mov     [rsp+1B0h+var_190], rax; struct _UNICODE_STRING *
0x18001bab6  call    ?LsapSidFilterCheck@@YAJPEAXKK0PEAU_UNICODE_STRING@@PEAH@Z; LsapSidFilterCheck(void *,ulong,ulong,void *,_UNICODE_STRING *,int *)
0x18001babb  mov     ebx, eax
0x18001babd  test    eax, eax
0x18001babf  jns     short loc_18001BAE1
0x18001bac1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bac8  test    [rcx+6Ch], edi
0x18001bacb  jz      short loc_18001BAE8
0x18001bacd  mov     rcx, [rcx+60h]
0x18001bad1  mov     edx, 0Ah
0x18001bad6  mov     r9d, eax
0x18001bad9  mov     r8, rsi
0x18001badc  call    WPP_SF_d
0x18001bae1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bae8  mov     dl, [rbp+170h+var_E7]
0x18001baee  add     dl, 0FFh
0x18001baf1  mov     [rbp+170h+var_E7], dl
0x18001baf7  test    ebx, ebx
0x18001baf9  jns     short loc_18001BB02
0x18001bafb  mov     eax, ebx
0x18001bafd  jmp     loc_18001B9CE
0x18001bb02  cmp     [rbp+170h+var_16C], r13d
0x18001bb06  jnz     short loc_18001BB1B
0x18001bb08  test    [rcx+6Ch], edi
0x18001bb0b  jz      loc_18001B9C9
0x18001bb11  mov     edx, 15h
0x18001bb16  jmp     loc_18001BFEF
0x18001bb1b  xor     r12d, r12d
0x18001bb1e  mov     r8d, 0FFFFFFFFh
0x18001bb24  xor     r15d, r15d
0x18001bb27  mov     ecx, [r14+9Ch]
0x18001bb2e  mov     eax, ecx
0x18001bb30  sub     eax, r12d
0x18001bb33  cmp     r15d, eax
0x18001bb36  jnb     loc_18001BC3F
0x18001bb3c  mov     rax, [r14+0A0h]
0x18001bb43  lea     r8, [rbp+170h+var_170]; unsigned int *
0x18001bb47  mov     ebx, [rbp+170h+var_168]
0x18001bb4a  movzx   ecx, dl
0x18001bb4d  lea     rdx, [rbp+170h+var_160]; struct _NETLOGON_SID_AND_ATTRIBUTES *
0x18001bb51  mov     [rbp+170h+var_170], 0
0x18001bb58  mov     eax, [rax+r15*8]
0x18001bb5c  mov     [rbp+rcx*4+170h+var_E0], eax
0x18001bb63  mov     eax, 1
0x18001bb68  add     [rbp+170h+var_E7], al
0x18001bb6e  mov     ecx, eax; unsigned int
0x18001bb70  call    ?LsapClassifySids@@YAXKPEBU_NETLOGON_SID_AND_ATTRIBUTES@@PEAK@Z; LsapClassifySids(ulong,_NETLOGON_SID_AND_ATTRIBUTES const *,ulong *)
0x18001bb75  mov     r9, [rbp+170h+var_130]; void *
0x18001bb79  lea     rax, [rbp+170h+var_16C]
0x18001bb7d  mov     r8d, [rbp+170h+var_170]; unsigned int
0x18001bb81  lea     rcx, [rbp+170h+pDomainSid]; pSid1
0x18001bb88  mov     [rsp+1B0h+var_188], rax; int *
0x18001bb8d  mov     edx, ebx; unsigned int
0x18001bb8f  lea     rax, [rbp+170h+DestinationString]
0x18001bb93  mov     [rsp+1B0h+var_190], rax; struct _UNICODE_STRING *
0x18001bb98  call    ?LsapSidFilterCheck@@YAJPEAXKK0PEAU_UNICODE_STRING@@PEAH@Z; LsapSidFilterCheck(void *,ulong,ulong,void *,_UNICODE_STRING *,int *)
0x18001bb9d  mov     ebx, eax
0x18001bb9f  test    eax, eax
0x18001bba1  jns     short loc_18001BBC3
0x18001bba3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbaa  test    [rcx+6Ch], edi
0x18001bbad  jz      short loc_18001BBC3
0x18001bbaf  mov     rcx, [rcx+60h]
0x18001bbb3  mov     edx, 0Ah
0x18001bbb8  mov     r9d, eax
0x18001bbbb  mov     r8, rsi
0x18001bbbe  call    WPP_SF_d
0x18001bbc3  mov     dl, [rbp+170h+var_E7]
0x18001bbc9  add     dl, 0FFh
0x18001bbcc  mov     [rbp+170h+var_E7], dl
0x18001bbd2  test    ebx, ebx
0x18001bbd4  js      loc_18001BAFB
0x18001bbda  cmp     [rbp+170h+var_16C], 0
0x18001bbde  jnz     short loc_18001BC29
0x18001bbe0  mov     r9d, r12d
0x18001bbe3  not     r9d
0x18001bbe6  add     r9d, [r14+9Ch]
0x18001bbed  cmp     r15d, r9d
0x18001bbf0  jz      short loc_18001BC16
0x18001bbf2  mov     rdx, [r14+0A0h]
0x18001bbf9  mov     rax, [rdx+r9*8]
0x18001bbfd  mov     r8, [rdx+r15*8]
0x18001bc01  mov     [rdx+r15*8], rax
0x18001bc05  mov     rax, [r14+0A0h]
0x18001bc0c  mov     [rax+r9*8], r8
0x18001bc10  mov     dl, [rbp+170h+var_E7]
0x18001bc16  mov     eax, 1
0x18001bc1b  mov     r8d, 0FFFFFFFFh
0x18001bc21  add     r12d, eax
0x18001bc24  add     r15d, r8d
  ... truncated ...
```
