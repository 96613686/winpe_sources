# CDfwEngWriter::GenerateFwRule(_tag_FW_RULE *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *,ulong,ulong)

- ea: `0x18002b8b0`
- end: `0x18002c936`
- name: `?GenerateFwRule@CDfwEngWriter@@EEAAJPEAU_tag_FW_RULE@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@KK@Z`
- size: `4230`
- prototype: `__int64 __usercall@<rax>(CDfwEngWriter *__hidden this@<rcx>, struct _tag_FW_RULE *@<rdx>, struct _LIST_ENTRY *@<r8>, struct _tag_FW_OBJECT_METADATA *@<r9>, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a710`
- `0x18000a860`
- `0x18000e430`
- `0x180014a70`
- `0x1800192e0`
- `0x18002b8b0`
- `0x18002ca00`
- `0x18002cf08`
- `0x18003f928`
- `0x1800424c0`
- `0x1800472ac`
- `0x18006a710`
- `0x1800729c0`
- `0x180073488`
- `0x1800b0d04`
- `0x1800b21d0`
- `0x1800ec010`

## import_xrefs

- `ntdll!RtlCreateServiceSid` at `0x18002c1a3`
- `ntdll!RtlCreateServiceSid` at `0x18002c1a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002c09f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002c3f2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002c09f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002c3f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bad9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002baf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bad9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002baf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb40`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c249`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c2b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c325`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c249`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c2b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c325`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c399`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c421`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c399`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c421`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002bbf8`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002bd5d`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002be3a`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002befe`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002c05c`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002bbf8`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002bd5d`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002be3a`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002befe`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002c05c`
- `fwbase!FwNtStatusToHResult` at `0x18002c1b1`
- `fwbase!FwNtStatusToHResult` at `0x18002c1b1`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002c5df`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002c68e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002c5df`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002c68e`
- `fwbase!FwSidDestroy` at `0x18002baae`
- `fwbase!FwSidDestroy` at `0x18002bac1`
- `fwbase!FwSidDestroy` at `0x18002baae`
- `fwbase!FwSidDestroy` at `0x18002bac1`
- `fwbase!FwSidCreate` at `0x18002c0dc`
- `fwbase!FwSidCreate` at `0x18002c0dc`
- `fwbase!FwFree` at `0x18002ba49`
- `fwbase!FwFree` at `0x18002ba59`
- `fwbase!FwFree` at `0x18002ba79`
- `fwbase!FwFree` at `0x18002ba94`
- `fwbase!FwFree` at `0x18002bb62`
- `fwbase!FwFree` at `0x18002bb77`
- `fwbase!FwFree` at `0x18002ba49`
- `fwbase!FwFree` at `0x18002ba59`
- `fwbase!FwFree` at `0x18002ba79`
- `fwbase!FwFree` at `0x18002ba94`
- `fwbase!FwFree` at `0x18002bb62`
- `fwbase!FwFree` at `0x18002bb77`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18002ba38`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18002ba38`

## pseudocode

```c
__int64 __fastcall CDfwEngWriter::GenerateFwRule(
        CDfwEngWriter *this,
        struct _tag_FW_RULE *a2,
        struct _LIST_ENTRY *a3,
        struct _tag_FW_OBJECT_METADATA *a4,
        unsigned int a5,
        char a6)
{
  struct _tag_FW_OBJECT_METADATA *v8; // r13
  int v9; // ebx
  unsigned __int64 *p_Base; // r15
  int v11; // r14d
  signed int FwRule; // edi
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // ebx
  unsigned __int64 *v23; // rax
  size_t v24; // r8
  CDfwEngWriter *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned __int16 *v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  const WCHAR *v33; // rcx
  unsigned int i; // ebx
  WCHAR *v35; // rax
  __int64 v36; // rcx
  unsigned int v37; // eax
  const WCHAR *v38; // rcx
  const WCHAR *v39; // rcx
  const WCHAR *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rdx
  const WCHAR *v43; // rcx
  const WCHAR *v44; // rcx
  const WCHAR *v45; // rcx
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int64 v50; // r12
  _OWORD *v51; // rcx
  struct _tag_FW_RULE *v52; // rax
  __int64 v53; // rdx
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  __int128 v56; // xmm1
  __int128 v57; // xmm0
  __int128 v58; // xmm1
  __int128 v59; // xmm0
  __int128 v60; // xmm1
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  __int128 v64; // xmm0
  __int128 v65; // xmm1
  __int128 v66; // xmm0
  __int64 v67; // rax
  unsigned int j; // ebx
  struct _tag_FW_RULE *v69; // rcx
  _OWORD *v70; // rax
  __int64 v71; // rdx
  __int128 v72; // xmm1
  __int128 v73; // xmm0
  __int128 v74; // xmm1
  __int128 v75; // xmm0
  __int128 v76; // xmm1
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int128 v79; // xmm1
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  __int128 v84; // xmm0
  __int64 v85; // rax
  int ProfileTypeFromProfileIndex; // eax
  struct _tag_FW_OBJECT_METADATA *v87; // r9
  struct _LIST_ENTRY *v88; // r8
  CDfwEngWriter *v89; // rcx
  unsigned int v90; // ebx
  struct _LIST_ENTRY *v91; // r8
  CDfwEngWriter *v92; // rcx
  CDfwEngWriter *v93; // rdi
  __int64 v94; // rdx
  struct _tag_FW_RULE *v95; // rdx
  _OWORD *v96; // rax
  __int128 v97; // xmm1
  __int128 v98; // xmm0
  __int128 v99; // xmm1
  __int128 v100; // xmm0
  __int128 v101; // xmm1
  __int128 v102; // xmm0
  __int128 v103; // xmm1
  __int128 v104; // xmm1
  struct _LIST_ENTRY *v105; // r8
  __int128 v106; // xmm0
  __int128 v107; // xmm1
  __int128 v108; // xmm0
  __int128 v109; // xmm1
  __int128 v110; // xmm0
  __int64 v111; // rax
  struct _DFW_IP_PORT_RANGE *v112; // [rsp+30h] [rbp-D0h]
  int v113; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v114; // [rsp+54h] [rbp-ACh]
  unsigned __int64 *v115; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v116; // [rsp+60h] [rbp-A0h] BYREF
  struct _DFW_IP_PORT_RANGE *v117; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v118; // [rsp+70h] [rbp-90h]
  size_t v119; // [rsp+78h] [rbp-88h] BYREF
  CDfwEngWriter *v120; // [rsp+80h] [rbp-80h]
  __int64 *v121; // [rsp+88h] [rbp-78h] BYREF
  struct _LIST_ENTRY *v122; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v123; // [rsp+98h] [rbp-68h] BYREF
  struct _tag_FW_OBJECT_METADATA *v124; // [rsp+A0h] [rbp-60h]
  _BYTE v125[512]; // [rsp+B0h] [rbp-50h] BYREF
  HLOCAL Sid; // [rsp+2B0h] [rbp+1B0h] BYREF
  HLOCAL v127; // [rsp+2B8h] [rbp+1B8h] BYREF
  HLOCAL hMem; // [rsp+2C0h] [rbp+1C0h] BYREF
  HLOCAL SecurityDescriptor; // [rsp+2C8h] [rbp+1C8h] BYREF
  HLOCAL v130; // [rsp+2D0h] [rbp+1D0h] BYREF
  _UNICODE_STRING ServiceName; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v132[20]; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v133; // [rsp+304h] [rbp+204h]
  unsigned __int16 *v134; // [rsp+378h] [rbp+278h]
  HLOCAL v135; // [rsp+380h] [rbp+280h]
  HLOCAL v136; // [rsp+388h] [rbp+288h]
  HLOCAL v137; // [rsp+390h] [rbp+290h]
  HLOCAL v138; // [rsp+398h] [rbp+298h]
  HLOCAL v139; // [rsp+3A0h] [rbp+2A0h]
  ULONG ServiceSidLength[4]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _OWORD v141[4]; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v142; // [rsp+430h] [rbp+330h]
  __int64 Base; // [rsp+440h] [rbp+340h] BYREF
  void *v144[2]; // [rsp+448h] [rbp+348h] BYREF
  _BYTE ServiceSid[80]; // [rsp+460h] [rbp+360h] BYREF

  v122 = a3;
  v120 = this;
  v124 = a4;
  v8 = a4;
  memset_0(v141, 0, 0x48u);
  memset_0(v132, 0, 0xF0u);
  v9 = 0;
  ServiceName = 0;
  ServiceSidLength[0] = 0;
  p_Base = 0;
  *(_OWORD *)v144 = 0;
  v123 = 0;
  v11 = 0;
  v117 = 0;
  v113 = 0;
  hMem = 0;
  SecurityDescriptor = 0;
  v130 = 0;
  Sid = 0;
  v127 = 0;
  Base = 0;
  v115 = 0;
  v116 = 0;
  v118 = 0;
  v121 = 0;
  LODWORD(v119) = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_SS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      66,
      (unsigned int)WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
      *((_QWORD *)a2 + 2),
      *((_QWORD *)a2 + 3));
  if ( *((_WORD *)a2 + 24) == 6 || *((_WORD *)a2 + 24) == 17 )
  {
    FwRule = ResolvePorts((char *)a2 + 56, &v113, 1);
    if ( FwRule < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v14 = 67;
LABEL_10:
        WPP_SF_d(*(_QWORD *)(v13 + 16), v14, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids, (unsigned int)FwRule);
        goto LABEL_11;
      }
      goto LABEL_11;
    }
    if ( v113 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 68, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
      FwAuditLogEmptyResolution(v16, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 4);
      v17 = 8;
LABEL_39:
      FwMetaDataAddEnforcementState(v8, v17);
      goto LABEL_11;
    }
    v11 = 1;
    FwRule = ResolvePorts((char *)a2 + 80, &v113, 1);
    if ( FwRule < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v14 = 69;
        goto LABEL_10;
      }
LABEL_11:
      if ( (a6 & 0x40) == 0 )
        goto LABEL_13;
      goto LABEL_12;
    }
    if ( v113 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 70, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
      FwAuditLogEmptyResolution(v18, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 5);
      v17 = 9;
      goto LABEL_39;
    }
  }
  FwRule = ResolveInterfaces(
             (int)a2 + 248,
             *((_DWORD *)a2 + 66),
             (unsigned int)&v115,
             (unsigned int)&v116,
             (__int64)&v113);
  if ( FwRule < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_54;
    v20 = 71;
    goto LABEL_53;
  }
  if ( v113 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 72, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
    FwAuditLogEmptyResolution(v21, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 1);
    FwMetaDataAddEnforcementState(v8, 10);
    goto LABEL_54;
  }
  p_Base = v115;
  if ( v115 )
  {
    v22 = v116;
  }
  else
  {
    p_Base = (unsigned __int64 *)&Base;
    v22 = 1;
    v115 = (unsigned __int64 *)&Base;
    LODWORD(v116) = 1;
  }
  v114 = v22;
  FwRule = ResolveNetworkNames((char *)a2 + 400, &v121, &v119, &v113);
  if ( FwRule < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        73,
        WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
        (unsigned int)FwRule);
LABEL_67:
    v9 = v11;
    v118 = v121;
    goto LABEL_11;
  }
  if ( v113 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 74, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
    FwMetaDataAddEnforcementState(v8, 24);
    goto LABEL_67;
  }
  v23 = (unsigned __int64 *)v121;
  v118 = v121;
  if ( v121 )
  {
    v24 = (unsigned int)v119;
  }
  else
  {
    v23 = (unsigned __int64 *)&Base;
    v24 = 1;
    v118 = &Base;
  }
  if ( v22 == 1 )
  {
    v25 = (CDfwEngWriter *)&Base;
    if ( p_Base == (unsigned __int64 *)&Base )
    {
      v22 = v24;
      v115 = v23;
      p_Base = v23;
      v118 = 0;
LABEL_82:
      v114 = v22;
      goto LABEL_83;
    }
  }
  if ( (_DWORD)v24 != 1 || (v25 = (CDfwEngWriter *)&Base, v23 != (unsigned __int64 *)&Base) )
  {
    FwIfIndexesIntersect(v22, p_Base, v24, v23, (__int64)&v116);
    v22 = v116;
    goto LABEL_82;
  }
LABEL_83:
  if ( !v22 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 75, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
    FwMetaDataAddEnforcementState(v8, 24);
    goto LABEL_88;
  }
  if ( *((_WORD *)a2 + 24) == 1 )
  {
    if ( *((_DWORD *)a2 + 14) )
    {
      FwRule = CDfwEngWriter::ConvertICMPTypeCode(v25, &v117, (struct _tag_FW_RULE *)((char *)a2 + 56));
      if ( FwRule < 0 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_88;
        v27 = 76;
LABEL_95:
        WPP_SF_d(*(_QWORD *)(v26 + 16), v27, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids, (unsigned int)FwRule);
LABEL_88:
        v9 = v11;
        goto LABEL_11;
      }
    }
  }
  if ( *((_WORD *)a2 + 24) == 58 )
  {
    if ( *((_DWORD *)a2 + 14) )
    {
      FwRule = CDfwEngWriter::ConvertICMPTypeCode(v25, &v117, (struct _tag_FW_RULE *)((char *)a2 + 56));
      if ( FwRule < 0 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_88;
        v27 = 77;
        goto LABEL_95;
      }
    }
  }
  v28 = (unsigned __int16 *)*((_QWORD *)a2 + 34);
  if ( v28 )
  {
    FwRule = CDfwEngWriter::HelperConvertAppNameToDevicePath(this, v28, &v123);
    if ( FwRule < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_108;
      v30 = 78;
      goto LABEL_107;
    }
    if ( !v123 )
    {
      v31 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 79, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
      FwAuditLogEmptyResolution(v31, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 0);
      v32 = 11;
      goto LABEL_114;
    }
    v134 = v123;
  }
  v33 = (const WCHAR *)*((_QWORD *)a2 + 35);
  HIDWORD(v116) = 1;
  v144[1] = 0;
  v144[0] = 0;
  if ( v33 )
  {
    if ( !lstrcmpiW(v33, L"*") )
    {
      HIDWORD(v116) = 2;
      for ( i = 0; i < 2; ++i )
      {
        FwRule = FwSidCreate(*((unsigned int *)&SIDMap + i), 0, &v144[i]);
        if ( FwRule < 0 )
        {
          v29 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v30 = 80;
            goto LABEL_107;
          }
          goto LABEL_108;
        }
      }
      goto LABEL_139;
    }
    v35 = (WCHAR *)*((_QWORD *)a2 + 35);
    HIDWORD(v116) = 1;
    ServiceName.Buffer = v35;
    if ( v35 )
    {
      v36 = 260;
      do
      {
        if ( !*v35 )
          break;
        ++v35;
        --v36;
      }
      while ( v36 );
      FwRule = v36 == 0 ? 0x80070057 : 0;
      if ( v36 )
      {
        ServiceSidLength[0] = 68;
        ServiceName.Length = v36 != 0 ? 2 * (260 - v36) : 0;
        ServiceName.MaximumLength = ServiceName.Length;
        v37 = RtlCreateServiceSid(&ServiceName, ServiceSid, ServiceSidLength);
        FwRule = FwNtStatusToHResult(v37);
        if ( FwRule >= 0 )
        {
          v144[0] = ServiceSid;
          goto LABEL_139;
        }
        v29 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_108;
        v30 = 82;
LABEL_107:
        WPP_SF_d(*(_QWORD *)(v29 + 16), v30, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids, (unsigned int)FwRule);
LABEL_108:
        v9 = v11;
        goto LABEL_11;
      }
    }
    else
    {
      FwRule = -2147024809;
    }
    v29 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_108;
    v30 = 81;
    goto LABEL_107;
  }
LABEL_139:
  v38 = (const WCHAR *)*((_QWORD *)a2 + 37);
  if ( v38 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v38, 1u, &hMem, 0) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 83, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
      v32 = 12;
      goto LABEL_114;
    }
    v139 = hMem;
  }
  v39 = (const WCHAR *)*((_QWORD *)a2 + 38);
  if ( v39 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v39, 1u, &SecurityDescriptor, 0) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 84, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
      v32 = 13;
      goto LABEL_114;
    }
    v138 = SecurityDescriptor;
  }
  v40 = (const WCHAR *)*((_QWORD *)a2 + 46);
  if ( v40 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v40, 1u, &v130, 0) )
    {
      v41 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
        goto LABEL_159;
      v42 = 85;
LABEL_158:
      WPP_SF_(*(_QWORD *)(v41 + 16), v42, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
LABEL_159:
      v32 = 20;
LABEL_114:
      FwMetaDataAddEnforcementState(v8, v32);
      goto LABEL_108;
    }
    v137 = v130;
  }
  else
  {
    v43 = (const WCHAR *)*((_QWORD *)a2 + 48);
    if ( v43 && !*((_QWORD *)a2 + 35) )
    {
      if ( !ConvertStringSidToSidW(v43, &Sid) )
      {
        v41 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
          goto LABEL_159;
        v42 = 86;
        goto LABEL_158;
      }
      v136 = Sid;
    }
  }
  v133 &= ~0x4000u;
  v44 = (const WCHAR *)*((_QWORD *)a2 + 47);
  if ( v44 )
  {
    if ( lstrcmpiW(v44, L"*") )
    {
      v45 = (const WCHAR *)*((_QWORD *)a2 + 47);
    }
    else
    {
      v133 |= 0x4000u;
      v45 = L"S-1-0-0";
    }
    if ( !ConvertStringSidToSidW(v45, &v127) )
    {
      v41 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
        goto LABEL_159;
      v42 = 87;
      goto LABEL_158;
    }
    v135 = v127;
  }
  if ( (a6 & 0x40) == 0 )
  {
LABEL_184:
    v50 = 3;
    v51 = v125;
    v52 = a2;
    v53 = 3;
    do
    {
      v54 = *((_OWORD *)v52 + 1);
      *v51 = *(_OWORD *)v52;
      v55 = *((_OWORD *)v52 + 2);
      v51[1] = v54;
      v56 = *((_OWORD *)v52 + 3);
      v51[2] = v55;
      v57 = *((_OWORD *)v52 + 4);
      v51[3] = v56;
      v58 = *((_OWORD *)v52 + 5);
      v51[4] = v57;
      v59 = *((_OWORD *)v52 + 6);
      v51[5] = v58;
      v60 = *((_OWORD *)v52 + 7);
      v52 = (struct _tag_FW_RULE *)((char *)v52 + 128);
      v51[6] = v59;
      v51[7] = v60;
      v51 += 8;
      --v53;
    }
    while ( v53 );
    v61 = *((_OWORD *)v52 + 1);
    *v51 = *(_OWORD *)v52;
    v62 = *((_OWORD *)v52 + 2);
    v51[1] = v61;
    v63 = *((_OWORD *)v52 + 3);
    v51[2] = v62;
    v64 = *((_OWORD *)v52 + 4);
    v51[3] = v63;
    v65 = *((_OWORD *)v52 + 5);
    v51[4] = v64;
    v66 = *((_OWORD *)v52 + 6);
    v67 = *((_QWORD *)v52 + 14);
    v51[5] = v65;
    v51[6] = v66;
    *((_QWORD *)v51 + 14) = v67;
    if ( (a6 & 1) != 0 )
    {
LABEL_203:
      v90 = v114;
    }
    else
    {
      if ( (*((_WORD *)a2 + 146) & 0x400) == 0 )
      {
        for ( j = 0; ; ++j )
        {
          if ( j >= 3 )
          {
            v8 = v124;
            goto LABEL_203;
          }
          if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(j) & a5) != 0 )
          {
            v69 = a2;
            v70 = v125;
            v71 = 3;
            do
            {
              v72 = v70[1];
              *(_OWORD *)v69 = *v70;
              v73 = v70[2];
              *((_OWORD *)v69 + 1) = v72;
              v74 = v70[3];
              *((_OWORD *)v69 + 2) = v73;
              v75 = v70[4];
              *((_OWORD *)v69 + 3) = v74;
              v76 = v70[5];
              *((_OWORD *)v69 + 4) = v75;
              v77 = v70[6];
              *((_OWORD *)v69 + 5) = v76;
              v78 = v70[7];
              v70 += 8;
              *((_OWORD *)v69 + 6) = v77;
              *((_OWORD *)v69 + 7) = v78;
              v69 = (struct _tag_FW_RULE *)((char *)v69 + 128);
              --v71;
            }
            while ( v71 );
            v79 = v70[1];
            *(_OWORD *)v69 = *v70;
            v80 = v70[2];
            *((_OWORD *)v69 + 1) = v79;
            v81 = v70[3];
            *((_OWORD *)v69 + 2) = v80;
            v82 = v70[4];
            *((_OWORD *)v69 + 3) = v81;
            v83 = v70[5];
            *((_OWORD *)v69 + 4) = v82;
            v84 = v70[6];
            v85 = *((_QWORD *)v70 + 14);
            *((_OWORD *)v69 + 5) = v83;
            *((_OWORD *)v69 + 6) = v84;
            *((_QWORD *)v69 + 14) = v85;
            ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(j);
            v87 = v124;
            v88 = v122;
            v89 = v120;
            *((_DWORD *)a2 + 10) = a5 & ProfileTypeFromProfileIndex;
            FwRule = CDfwEngWriter::HelperGenerateFwRule(
                       v89,
                       a2,
                       v88,
                       v87,
                       (struct FW_PLUMBER_FILTER *)v132,
                       v144,
                       v117,
                       v115,
                       v114);
            if ( FwRule < 0 )
              break;
          }
        }
        v19 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v20 = 89;
          goto LABEL_53;
        }
        goto LABEL_54;
      }
      v90 = v114;
      v91 = v122;
      v92 = v120;
      *((_DWORD *)a2 + 10) = a5;
      FwRule = CDfwEngWriter::HelperGenerateFwRule(
                 v92,
                 a2,
                 v91,
                 v8,
                 (struct FW_PLUMBER_FILTER *)v132,
                 v144,
                 v117,
                 v115,
                 v90);
      if ( FwRule < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_54;
        v20 = 90;
LABEL_53:
        WPP_SF_d(*(_QWORD *)(v19 + 16), v20, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids, (unsigned int)FwRule);
LABEL_54:
        p_Base = v115;
        v9 = v11;
        goto LABEL_11;
      }
    }
    if ( (a6 & 2) != 0 )
    {
      if ( (a6 & 1) == 0 )
      {
LABEL_209:
        v93 = v120;
        v94 = *((unsigned int *)v120 + 76);
        if ( !(_DWORD)v94 || (_DWORD)v94 == 11 )
        {
          if ( (a6 & 0x20) != 0 )
            v133 |= 0x10000u;
        }
        else
        {
          if ( (unsigned int)v94 >= 0xF )
            MicrosoftTelemetryAssertTriggeredArgs("mpssvc", v94, (unsigned int)(v94 + 5));
          (*(void (__fastcall **)(CDfwEngWriter *, _QWORD))(*(_QWORD *)v93 + 88LL))(
            v93,
            (unsigned int)(*((_DWORD *)v93 + 76) + 5));
        }
        goto LABEL_217;
      }
    }
    else if ( (a6 & 1) == 0 )
    {
      if ( (a6 & 0x20) == 0 )
        goto LABEL_54;
      goto LABEL_209;
    }
    v93 = v120;
LABEL_217:
    v95 = a2;
    v96 = v125;
    do
    {
      v97 = v96[1];
      *(_OWORD *)v95 = *v96;
      v98 = v96[2];
      *((_OWORD *)v95 + 1) = v97;
      v99 = v96[3];
      *((_OWORD *)v95 + 2) = v98;
      v100 = v96[4];
      *((_OWORD *)v95 + 3) = v99;
      v101 = v96[5];
      *((_OWORD *)v95 + 4) = v100;
      v102 = v96[6];
      *((_OWORD *)v95 + 5) = v101;
      v103 = v96[7];
      v96 += 8;
      *((_OWORD *)v95 + 6) = v102;
      *((_OWORD *)v95 + 7) = v103;
      v95 = (struct _tag_FW_RULE *)((char *)v95 + 128);
      --v50;
    }
    while ( v50 );
    p_Base = v115;
    v104 = v96[1];
    v105 = v122;
    *(_OWORD *)v95 = *v96;
    v106 = v96[2];
    *((_OWORD *)v95 + 1) = v104;
    v107 = v96[3];
    *((_OWORD *)v95 + 2) = v106;
    v108 = v96[4];
    *((_OWORD *)v95 + 3) = v107;
    v109 = v96[5];
    *((_OWORD *)v95 + 4) = v108;
    v110 = v96[6];
    v111 = *((_QWORD *)v96 + 14);
    *((_OWORD *)v95 + 5) = v109;
    *((_OWORD *)v95 + 6) = v110;
    *((_QWORD *)v95 + 14) = v111;
    v112 = v117;
    *((_DWORD *)a2 + 10) = 0x7FFFFFFF;
    FwRule = CDfwEngWriter::HelperGenerateFwRule(
               v93,
               a2,
               v105,
               v8,
               (struct FW_PLUMBER_FILTER *)v132,
               v144,
               v112,
               p_Base,
               v90);
    if ( FwRule >= 0 )
      goto LABEL_108;
    v29 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_108;
    v30 = 91;
    goto LABEL_107;
  }
  FwRule = ResolveNotLocalAddresses((struct _tag_FW_RULE *)((char *)a2 + 104));
  if ( FwRule >= 0 )
  {
    v46 = *(_OWORD *)((char *)a2 + 104);
    v133 |= 0x20000u;
    v47 = *(_OWORD *)((char *)a2 + 120);
    v141[0] = v46;
    v48 = *(_OWORD *)((char *)a2 + 136);
    v141[1] = v47;
    v49 = *(_OWORD *)((char *)a2 + 152);
    v141[2] = v48;
    v142 = *((_QWORD *)a2 + 21);
    v141[3] = v49;
    goto LABEL_184;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      88,
      WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
      (unsigned int)FwRule);
  v9 = v11;
LABEL_12:
  FwPolioEmptyWFAddresses(v141);
LABEL_13:
  FwFree(v117);
  FwFree(v123);
  if ( v118 != &Base )
    FwFree(v118);
  if ( p_Base != (unsigned __int64 *)&Base )
    FwFree(p_Base);
  if ( HIDWORD(v116) == 2 )
  {
    FwSidDestroy(v144[0]);
    FwSidDestroy(v144[1]);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v130 )
    LocalFree(v130);
  if ( Sid )
  {
    LocalFree(Sid);
    Sid = 0;
  }
  if ( v127 )
  {
    LocalFree(v127);
    v127 = 0;
  }
  if ( v11 == 1 )
    FwFree(*((_QWORD *)a2 + 9));
  if ( v9 == 1 )
    FwFree(*((_QWORD *)a2 + 12));
  return (unsigned int)FwRule;
}

```

## disassembly

```asm
0x18002b8b0  push    rbp
0x18002b8b2  push    rbx
0x18002b8b3  push    rsi
0x18002b8b4  push    rdi
0x18002b8b5  push    r12
0x18002b8b7  push    r13
0x18002b8b9  push    r14
0x18002b8bb  push    r15
0x18002b8bd  lea     rbp, [rsp-3C8h]
0x18002b8c5  sub     rsp, 4C8h
0x18002b8cc  mov     rax, cs:__security_cookie
0x18002b8d3  xor     rax, rsp
0x18002b8d6  mov     [rbp+400h+var_50], rax
0x18002b8dd  mov     rsi, rdx
0x18002b8e0  mov     [rbp+400h+var_470], r8
0x18002b8e4  xor     edx, edx; Val
0x18002b8e6  mov     [rbp+400h+var_480], rcx
0x18002b8ea  mov     r12, rcx
0x18002b8ed  mov     [rbp+400h+var_460], r9
0x18002b8f1  lea     rcx, [rbp+400h+var_110]; void *
0x18002b8f8  mov     r13, r9
0x18002b8fb  lea     r8d, [rdx+48h]; Size
0x18002b8ff  call    memset_0
0x18002b904  xor     edx, edx; Val
0x18002b906  lea     rcx, [rbp+400h+var_210]; void *
0x18002b90d  mov     r8d, 0F0h; Size
0x18002b913  call    memset_0
0x18002b918  xor     ebx, ebx
0x18002b91a  xorps   xmm0, xmm0
0x18002b91d  xorps   xmm1, xmm1
0x18002b920  mov     dword ptr [rsp+500h+var_4A0+4], ebx
0x18002b924  movups  xmmword ptr [rbp+400h+ServiceName.Length], xmm0
0x18002b92b  mov     [rbp+400h+ServiceSidLength], ebx
0x18002b931  mov     r15d, ebx
0x18002b934  movups  xmmword ptr [rbp+400h+var_B8], xmm1
0x18002b93b  mov     [rbp+400h+var_468], rbx
0x18002b93f  mov     r14d, ebx
0x18002b942  mov     [rsp+500h+var_498], rbx
0x18002b947  mov     [rsp+500h+var_4B0], ebx
0x18002b94b  mov     [rbp+400h+hMem], rbx
0x18002b952  mov     [rbp+400h+SecurityDescriptor], rbx
0x18002b959  mov     [rbp+400h+var_230], rbx
0x18002b960  mov     [rbp+400h+Sid], rbx
0x18002b967  mov     [rbp+400h+var_248], rbx
0x18002b96e  mov     [rbp+400h+Base], rbx
0x18002b975  mov     [rsp+500h+var_4A8], rbx
0x18002b97a  mov     dword ptr [rsp+500h+var_4A0], ebx
0x18002b97e  mov     [rsp+500h+var_490], rbx
0x18002b983  mov     [rbp+400h+var_478], rbx
0x18002b987  mov     dword ptr [rsp+500h+var_488], ebx
0x18002b98b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b992  lea     rax, WPP_GLOBAL_Control
0x18002b999  cmp     rcx, rax
0x18002b99c  jz      short loc_18002B9C4
0x18002b99e  test    byte ptr [rcx+1Ch], 4
0x18002b9a2  jz      short loc_18002B9C4
0x18002b9a4  mov     rax, [rsi+18h]
0x18002b9a8  lea     edx, [rbx+42h]
0x18002b9ab  mov     r9, [rsi+10h]
0x18002b9af  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x18002b9b6  mov     rcx, [rcx+10h]
0x18002b9ba  mov     [rsp+500h+var_4E0], rax
0x18002b9bf  call    WPP_SF_SS
0x18002b9c4  cmp     word ptr [rsi+30h], 6
0x18002b9c9  jz      short loc_18002B9D6
0x18002b9cb  cmp     word ptr [rsi+30h], 11h
0x18002b9d0  jnz     loc_18002BCA4
0x18002b9d6  lea     rcx, [rsi+38h]
0x18002b9da  mov     r8d, 1
0x18002b9e0  lea     rdx, [rsp+500h+var_4B0]
0x18002b9e5  call    ResolvePorts
0x18002b9ea  mov     edi, eax
0x18002b9ec  test    eax, eax
0x18002b9ee  jns     loc_18002BBA9
0x18002b9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9fb  lea     rax, WPP_GLOBAL_Control
0x18002ba02  cmp     rcx, rax
0x18002ba05  jz      short loc_18002BA25
0x18002ba07  test    byte ptr [rcx+1Ch], 1
0x18002ba0b  jz      short loc_18002BA25
0x18002ba0d  mov     edx, 43h ; 'C'
0x18002ba12  mov     rcx, [rcx+10h]
0x18002ba16  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x18002ba1d  mov     r9d, edi
0x18002ba20  call    WPP_SF_d
0x18002ba25  xor     r12d, r12d
0x18002ba28  test    byte ptr [rbp+400h+arg_28], 40h
0x18002ba2f  jz      short loc_18002BA44
0x18002ba31  lea     rcx, [rbp+400h+var_110]
0x18002ba38  call    cs:__imp_FwPolioEmptyWFAddresses
0x18002ba3f  nop     dword ptr [rax+rax+00h]
0x18002ba44  mov     rcx, [rsp+500h+var_498]
0x18002ba49  call    cs:__imp_FwFree
0x18002ba50  nop     dword ptr [rax+rax+00h]
0x18002ba55  mov     rcx, [rbp+400h+var_468]
0x18002ba59  call    cs:__imp_FwFree
0x18002ba60  nop     dword ptr [rax+rax+00h]
0x18002ba65  mov     rax, [rsp+500h+var_490]
0x18002ba6a  lea     rcx, [rbp+400h+Base]
0x18002ba71  cmp     rax, rcx
0x18002ba74  jz      short loc_18002BA85
0x18002ba76  mov     rcx, rax
0x18002ba79  call    cs:__imp_FwFree
0x18002ba80  nop     dword ptr [rax+rax+00h]
0x18002ba85  lea     rax, [rbp+400h+Base]
0x18002ba8c  cmp     r15, rax
0x18002ba8f  jz      short loc_18002BAA0
0x18002ba91  mov     rcx, r15
0x18002ba94  call    cs:__imp_FwFree
0x18002ba9b  nop     dword ptr [rax+rax+00h]
0x18002baa0  cmp     dword ptr [rsp+500h+var_4A0+4], 2
0x18002baa5  jnz     short loc_18002BACD
0x18002baa7  mov     rcx, [rbp+400h+var_B8]
0x18002baae  call    cs:__imp_FwSidDestroy
0x18002bab5  nop     dword ptr [rax+rax+00h]
0x18002baba  mov     rcx, [rbp+400h+var_B8+8]
0x18002bac1  call    cs:__imp_FwSidDestroy
0x18002bac8  nop     dword ptr [rax+rax+00h]
0x18002bacd  mov     rcx, [rbp+400h+hMem]; hMem
0x18002bad4  test    rcx, rcx
0x18002bad7  jz      short loc_18002BAE5
0x18002bad9  call    cs:__imp_LocalFree
0x18002bae0  nop     dword ptr [rax+rax+00h]
0x18002bae5  mov     rcx, [rbp+400h+SecurityDescriptor]; hMem
0x18002baec  test    rcx, rcx
0x18002baef  jz      short loc_18002BAFD
0x18002baf1  call    cs:__imp_LocalFree
0x18002baf8  nop     dword ptr [rax+rax+00h]
0x18002bafd  mov     rcx, [rbp+400h+var_230]; hMem
0x18002bb04  test    rcx, rcx
0x18002bb07  jz      short loc_18002BB15
0x18002bb09  call    cs:__imp_LocalFree
0x18002bb10  nop     dword ptr [rax+rax+00h]
0x18002bb15  mov     rcx, [rbp+400h+Sid]; hMem
0x18002bb1c  test    rcx, rcx
0x18002bb1f  jz      short loc_18002BB34
0x18002bb21  call    cs:__imp_LocalFree
0x18002bb28  nop     dword ptr [rax+rax+00h]
0x18002bb2d  mov     [rbp+400h+Sid], r12
0x18002bb34  mov     rcx, [rbp+400h+var_248]; hMem
0x18002bb3b  test    rcx, rcx
0x18002bb3e  jz      short loc_18002BB53
0x18002bb40  call    cs:__imp_LocalFree
0x18002bb47  nop     dword ptr [rax+rax+00h]
0x18002bb4c  mov     [rbp+400h+var_248], r12
0x18002bb53  mov     r15d, 1
0x18002bb59  cmp     r14d, r15d
0x18002bb5c  jnz     short loc_18002BB6E
0x18002bb5e  mov     rcx, [rsi+48h]
0x18002bb62  call    cs:__imp_FwFree
0x18002bb69  nop     dword ptr [rax+rax+00h]
0x18002bb6e  cmp     ebx, r15d
0x18002bb71  jnz     short loc_18002BB83
0x18002bb73  mov     rcx, [rsi+60h]
0x18002bb77  call    cs:__imp_FwFree
0x18002bb7e  nop     dword ptr [rax+rax+00h]
0x18002bb83  mov     eax, edi
0x18002bb85  mov     rcx, [rbp+400h+var_50]
0x18002bb8c  xor     rcx, rsp; StackCookie
0x18002bb8f  call    __security_check_cookie
0x18002bb94  add     rsp, 4C8h
0x18002bb9b  pop     r15
0x18002bb9d  pop     r14
0x18002bb9f  pop     r13
0x18002bba1  pop     r12
0x18002bba3  pop     rdi
0x18002bba4  pop     rsi
0x18002bba5  pop     rbx
0x18002bba6  pop     rbp
0x18002bba7  retn
0x18002bba9  cmp     [rsp+500h+var_4B0], ebx
0x18002bbad  jz      short loc_18002BC09
0x18002bbaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbb6  lea     rax, WPP_GLOBAL_Control
0x18002bbbd  cmp     rcx, rax
0x18002bbc0  jz      short loc_18002BBDD
0x18002bbc2  test    byte ptr [rcx+1Ch], 4
0x18002bbc6  jz      short loc_18002BBDD
0x18002bbc8  mov     rcx, [rcx+10h]
0x18002bbcc  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x18002bbd3  mov     edx, 44h ; 'D'
0x18002bbd8  call    WPP_SF_
0x18002bbdd  mov     r8, [rsi+18h]
0x18002bbe1  mov     r9d, 4
0x18002bbe7  mov     rdx, [rsi+10h]
0x18002bbeb  call    FwAuditLogEmptyResolution
0x18002bbf0  mov     edx, 8
0x18002bbf5  mov     rcx, r13
0x18002bbf8  call    cs:__imp_FwMetaDataAddEnforcementState
0x18002bbff  nop     dword ptr [rax+rax+00h]
0x18002bc04  jmp     loc_18002BA25
0x18002bc09  mov     eax, 1
0x18002bc0e  lea     rcx, [rsi+50h]
0x18002bc12  mov     r8d, eax
0x18002bc15  lea     rdx, [rsp+500h+var_4B0]
0x18002bc1a  mov     r14d, eax
0x18002bc1d  call    ResolvePorts
0x18002bc22  mov     edi, eax
0x18002bc24  test    eax, eax
0x18002bc26  jns     short loc_18002BC53
0x18002bc28  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc2f  lea     rax, WPP_GLOBAL_Control
0x18002bc36  cmp     rcx, rax
0x18002bc39  jz      loc_18002BA25
0x18002bc3f  test    [rcx+1Ch], r14b
0x18002bc43  jz      loc_18002BA25
0x18002bc49  mov     edx, 45h ; 'E'
0x18002bc4e  jmp     loc_18002BA12
0x18002bc53  cmp     [rsp+500h+var_4B0], ebx
0x18002bc57  jz      short loc_18002BCA4
0x18002bc59  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc60  lea     rax, WPP_GLOBAL_Control
0x18002bc67  cmp     rcx, rax
0x18002bc6a  jz      short loc_18002BC87
0x18002bc6c  test    byte ptr [rcx+1Ch], 4
0x18002bc70  jz      short loc_18002BC87
0x18002bc72  mov     rcx, [rcx+10h]
0x18002bc76  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x18002bc7d  mov     edx, 46h ; 'F'
0x18002bc82  call    WPP_SF_
0x18002bc87  mov     r8, [rsi+18h]
0x18002bc8b  mov     r9d, 5
0x18002bc91  mov     rdx, [rsi+10h]
0x18002bc95  call    FwAuditLogEmptyResolution
0x18002bc9a  mov     edx, 9
0x18002bc9f  jmp     loc_18002BBF5
0x18002bca4  mov     edx, [rsi+108h]
0x18002bcaa  lea     rax, [rsp+500h+var_4B0]
0x18002bcaf  lea     rcx, [rsi+0F8h]
0x18002bcb6  mov     [rsp+500h+var_4E0], rax
0x18002bcbb  lea     r9, [rsp+500h+var_4A0]
0x18002bcc0  lea     r8, [rsp+500h+var_4A8]
0x18002bcc5  call    ResolveInterfaces
0x18002bcca  mov     edi, eax
0x18002bccc  test    eax, eax
0x18002bcce  jns     short loc_18002BD0E
0x18002bcd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bcd7  lea     rax, WPP_GLOBAL_Control
0x18002bcde  cmp     rcx, rax
0x18002bce1  jz      short loc_18002BD01
0x18002bce3  test    byte ptr [rcx+1Ch], 1
0x18002bce7  jz      short loc_18002BD01
0x18002bce9  mov     edx, 47h ; 'G'
0x18002bcee  mov     rcx, [rcx+10h]
0x18002bcf2  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x18002bcf9  mov     r9d, edi
0x18002bcfc  call    WPP_SF_d
0x18002bd01  mov     r15, [rsp+500h+var_4A8]
0x18002bd06  mov     ebx, r14d
0x18002bd09  jmp     loc_18002BA25
0x18002bd0e  cmp     [rsp+500h+var_4B0], ebx
0x18002bd12  jz      short loc_18002BD6B
0x18002bd14  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd1b  lea     rax, WPP_GLOBAL_Control
0x18002bd22  cmp     rcx, rax
0x18002bd25  jz      short loc_18002BD42
0x18002bd27  test    byte ptr [rcx+1Ch], 4
0x18002bd2b  jz      short loc_18002BD42
0x18002bd2d  mov     rcx, [rcx+10h]
0x18002bd31  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x18002bd38  mov     edx, 48h ; 'H'
0x18002bd3d  call    WPP_SF_
0x18002bd42  mov     r8, [rsi+18h]
0x18002bd46  mov     r9d, 1
0x18002bd4c  mov     rdx, [rsi+10h]
0x18002bd50  call    FwAuditLogEmptyResolution
0x18002bd55  mov     edx, 0Ah
0x18002bd5a  mov     rcx, r13
0x18002bd5d  call    cs:__imp_FwMetaDataAddEnforcementState
0x18002bd64  nop     dword ptr [rax+rax+00h]
0x18002bd69  jmp     short loc_18002BD01
0x18002bd6b  mov     r15, [rsp+500h+var_4A8]
0x18002bd70  mov     [rsp+500h+var_4A8], r15
0x18002bd75  test    r15, r15
0x18002bd78  jnz     short loc_18002BD91
0x18002bd7a  lea     r15, [rbp+400h+Base]
0x18002bd81  mov     ebx, 1
0x18002bd86  mov     [rsp+500h+var_4A8], r15
0x18002bd8b  mov     dword ptr [rsp+500h+var_4A0], ebx
0x18002bd8f  jmp     short loc_18002BD95
0x18002bd91  mov     ebx, dword ptr [rsp+500h+var_4A0]
0x18002bd95  lea     rcx, [rsi+190h]
0x18002bd9c  mov     [rsp+500h+var_4AC], ebx
0x18002bda0  lea     r9, [rsp+500h+var_4B0]
0x18002bda5  lea     r8, [rsp+500h+var_488]
0x18002bdaa  lea     rdx, [rbp+400h+var_478]
0x18002bdae  call    ResolveNetworkNames
0x18002bdb3  xor     r9d, r9d
0x18002bdb6  mov     edi, eax
0x18002bdb8  test    eax, eax
0x18002bdba  jns     short loc_18002BDFD
0x18002bdbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bdc3  lea     rax, WPP_GLOBAL_Control
0x18002bdca  cmp     rcx, rax
0x18002bdcd  jz      short loc_18002BDEC
0x18002bdcf  test    byte ptr [rcx+1Ch], 1
0x18002bdd3  jz      short loc_18002BDEC
0x18002bdd5  mov     rcx, [rcx+10h]
0x18002bdd9  lea     edx, [r9+49h]
0x18002bddd  mov     r9d, edi
  ... truncated ...
```
