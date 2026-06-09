# CDfwEngWriter::GenerateFwRule(_tag_FW_RULE *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *,ulong,ulong)

- ea: `0x1800281d0`
- end: `0x18002919b`
- name: `?GenerateFwRule@CDfwEngWriter@@EEAAJPEAU_tag_FW_RULE@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@KK@Z`
- size: `4043`
- prototype: `__int64 __usercall@<rax>(CDfwEngWriter *__hidden this@<rcx>, struct _tag_FW_RULE *@<rdx>, struct _LIST_ENTRY *@<r8>, struct _tag_FW_OBJECT_METADATA *@<r9>, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000af3c`
- `0x18000b080`
- `0x1800126e0`
- `0x180017110`
- `0x1800281d0`
- `0x180029260`
- `0x18002973c`
- `0x18002a4e0`
- `0x18003ee6c`
- `0x180041e8c`
- `0x18004600c`
- `0x1800670c0`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800aaad0`
- `0x1800abcc0`
- `0x1800e6010`

## import_xrefs

- `ntdll!RtlCreateServiceSid` at `0x180028a44`
- `ntdll!RtlCreateServiceSid` at `0x180028a44`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002894c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180028c6f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002894c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180028c6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028405`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002841e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028405`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002841e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028ade`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028b46`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028bae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028ade`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028b46`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028bae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180028c1c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180028c98`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180028c1c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180028c98`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800284c3`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180028622`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800286f9`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800287b7`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002890f`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800284c3`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180028622`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800286f9`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800287b7`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002890f`
- `fwbase!FwNtStatusToHResult` at `0x180028a4c`
- `fwbase!FwNtStatusToHResult` at `0x180028a4c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180028e50`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180028ef9`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180028e50`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180028ef9`
- `fwbase!FwSidDestroy` at `0x1800283b0`
- `fwbase!FwSidDestroy` at `0x1800283bd`
- `fwbase!FwSidDestroy` at `0x1800283b0`
- `fwbase!FwSidDestroy` at `0x1800283bd`
- `fwbase!FwSidCreate` at `0x180028983`
- `fwbase!FwSidCreate` at `0x180028983`
- `fwbase!FwFree` at `0x180028363`
- `fwbase!FwFree` at `0x18002836d`
- `fwbase!FwFree` at `0x180028387`
- `fwbase!FwFree` at `0x18002839c`
- `fwbase!FwFree` at `0x18002843a`
- `fwbase!FwFree` at `0x180028449`
- `fwbase!FwFree` at `0x180028363`
- `fwbase!FwFree` at `0x18002836d`
- `fwbase!FwFree` at `0x180028387`
- `fwbase!FwFree` at `0x18002839c`
- `fwbase!FwFree` at `0x18002843a`
- `fwbase!FwFree` at `0x180028449`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180028358`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180028358`

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
      (unsigned int)WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
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
        WPP_SF_d(*(_QWORD *)(v13 + 16), v14, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids, (unsigned int)FwRule);
        goto LABEL_11;
      }
      goto LABEL_11;
    }
    if ( v113 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 68, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
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
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 70, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
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
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 72, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
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
        WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
        (unsigned int)FwRule);
LABEL_67:
    v9 = v11;
    v118 = v121;
    goto LABEL_11;
  }
  if ( v113 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 74, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
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
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 75, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
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
        WPP_SF_d(*(_QWORD *)(v26 + 16), v27, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids, (unsigned int)FwRule);
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
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 79, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
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
        WPP_SF_d(*(_QWORD *)(v29 + 16), v30, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids, (unsigned int)FwRule);
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
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 83, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
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
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 84, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
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
      WPP_SF_(*(_QWORD *)(v41 + 16), v42, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
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
        WPP_SF_d(*(_QWORD *)(v19 + 16), v20, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids, (unsigned int)FwRule);
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
      WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
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
0x1800281d0  push    rbp
0x1800281d2  push    rbx
0x1800281d3  push    rsi
0x1800281d4  push    rdi
0x1800281d5  push    r12
0x1800281d7  push    r13
0x1800281d9  push    r14
0x1800281db  push    r15
0x1800281dd  lea     rbp, [rsp-3C8h]
0x1800281e5  sub     rsp, 4C8h
0x1800281ec  mov     rax, cs:__security_cookie
0x1800281f3  xor     rax, rsp
0x1800281f6  mov     [rbp+400h+var_50], rax
0x1800281fd  mov     rsi, rdx
0x180028200  mov     [rbp+400h+var_470], r8
0x180028204  xor     edx, edx; Val
0x180028206  mov     [rbp+400h+var_480], rcx
0x18002820a  mov     r12, rcx
0x18002820d  mov     [rbp+400h+var_460], r9
0x180028211  lea     rcx, [rbp+400h+var_110]; void *
0x180028218  mov     r13, r9
0x18002821b  lea     r8d, [rdx+48h]; Size
0x18002821f  call    memset_0
0x180028224  xor     edx, edx; Val
0x180028226  lea     rcx, [rbp+400h+var_210]; void *
0x18002822d  mov     r8d, 0F0h; Size
0x180028233  call    memset_0
0x180028238  xor     ebx, ebx
0x18002823a  xorps   xmm0, xmm0
0x18002823d  xorps   xmm1, xmm1
0x180028240  mov     dword ptr [rsp+500h+var_4A0+4], ebx
0x180028244  movups  xmmword ptr [rbp+400h+ServiceName.Length], xmm0
0x18002824b  mov     [rbp+400h+ServiceSidLength], ebx
0x180028251  mov     r15d, ebx
0x180028254  movups  xmmword ptr [rbp+400h+var_B8], xmm1
0x18002825b  mov     [rbp+400h+var_468], rbx
0x18002825f  mov     r14d, ebx
0x180028262  mov     [rsp+500h+var_498], rbx
0x180028267  mov     [rsp+500h+var_4B0], ebx
0x18002826b  mov     [rbp+400h+hMem], rbx
0x180028272  mov     [rbp+400h+SecurityDescriptor], rbx
0x180028279  mov     [rbp+400h+var_230], rbx
0x180028280  mov     [rbp+400h+Sid], rbx
0x180028287  mov     [rbp+400h+var_248], rbx
0x18002828e  mov     [rbp+400h+Base], rbx
0x180028295  mov     [rsp+500h+var_4A8], rbx
0x18002829a  mov     dword ptr [rsp+500h+var_4A0], ebx
0x18002829e  mov     [rsp+500h+var_490], rbx
0x1800282a3  mov     [rbp+400h+var_478], rbx
0x1800282a7  mov     dword ptr [rsp+500h+var_488], ebx
0x1800282ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282b2  lea     rax, WPP_GLOBAL_Control
0x1800282b9  cmp     rcx, rax
0x1800282bc  jz      short loc_1800282E4
0x1800282be  test    byte ptr [rcx+1Ch], 4
0x1800282c2  jz      short loc_1800282E4
0x1800282c4  mov     rax, [rsi+18h]
0x1800282c8  lea     edx, [rbx+42h]
0x1800282cb  mov     r9, [rsi+10h]
0x1800282cf  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800282d6  mov     rcx, [rcx+10h]
0x1800282da  mov     [rsp+500h+var_4E0], rax
0x1800282df  call    WPP_SF_SS
0x1800282e4  cmp     word ptr [rsi+30h], 6
0x1800282e9  jz      short loc_1800282F6
0x1800282eb  cmp     word ptr [rsi+30h], 11h
0x1800282f0  jnz     loc_180028569
0x1800282f6  lea     rcx, [rsi+38h]
0x1800282fa  mov     r8d, 1
0x180028300  lea     rdx, [rsp+500h+var_4B0]
0x180028305  call    ResolvePorts
0x18002830a  mov     edi, eax
0x18002830c  test    eax, eax
0x18002830e  jns     loc_180028474
0x180028314  mov     rcx, cs:WPP_GLOBAL_Control
0x18002831b  lea     rax, WPP_GLOBAL_Control
0x180028322  cmp     rcx, rax
0x180028325  jz      short loc_180028345
0x180028327  test    byte ptr [rcx+1Ch], 1
0x18002832b  jz      short loc_180028345
0x18002832d  mov     edx, 43h ; 'C'
0x180028332  mov     rcx, [rcx+10h]
0x180028336  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x18002833d  mov     r9d, edi
0x180028340  call    WPP_SF_d
0x180028345  xor     r12d, r12d
0x180028348  test    byte ptr [rbp+400h+arg_28], 40h
0x18002834f  jz      short loc_18002835E
0x180028351  lea     rcx, [rbp+400h+var_110]
0x180028358  call    cs:__imp_FwPolioEmptyWFAddresses
0x18002835e  mov     rcx, [rsp+500h+var_498]
0x180028363  call    cs:__imp_FwFree
0x180028369  mov     rcx, [rbp+400h+var_468]
0x18002836d  call    cs:__imp_FwFree
0x180028373  mov     rax, [rsp+500h+var_490]
0x180028378  lea     rcx, [rbp+400h+Base]
0x18002837f  cmp     rax, rcx
0x180028382  jz      short loc_18002838D
0x180028384  mov     rcx, rax
0x180028387  call    cs:__imp_FwFree
0x18002838d  lea     rax, [rbp+400h+Base]
0x180028394  cmp     r15, rax
0x180028397  jz      short loc_1800283A2
0x180028399  mov     rcx, r15
0x18002839c  call    cs:__imp_FwFree
0x1800283a2  cmp     dword ptr [rsp+500h+var_4A0+4], 2
0x1800283a7  jnz     short loc_1800283C3
0x1800283a9  mov     rcx, [rbp+400h+var_B8]
0x1800283b0  call    cs:__imp_FwSidDestroy
0x1800283b6  mov     rcx, [rbp+400h+var_B8+8]
0x1800283bd  call    cs:__imp_FwSidDestroy
0x1800283c3  mov     rcx, [rbp+400h+hMem]; hMem
0x1800283ca  test    rcx, rcx
0x1800283cd  jz      short loc_1800283D5
0x1800283cf  call    cs:__imp_LocalFree
0x1800283d5  mov     rcx, [rbp+400h+SecurityDescriptor]; hMem
0x1800283dc  test    rcx, rcx
0x1800283df  jz      short loc_1800283E7
0x1800283e1  call    cs:__imp_LocalFree
0x1800283e7  mov     rcx, [rbp+400h+var_230]; hMem
0x1800283ee  test    rcx, rcx
0x1800283f1  jz      short loc_1800283F9
0x1800283f3  call    cs:__imp_LocalFree
0x1800283f9  mov     rcx, [rbp+400h+Sid]; hMem
0x180028400  test    rcx, rcx
0x180028403  jz      short loc_180028412
0x180028405  call    cs:__imp_LocalFree
0x18002840b  mov     [rbp+400h+Sid], r12
0x180028412  mov     rcx, [rbp+400h+var_248]; hMem
0x180028419  test    rcx, rcx
0x18002841c  jz      short loc_18002842B
0x18002841e  call    cs:__imp_LocalFree
0x180028424  mov     [rbp+400h+var_248], r12
0x18002842b  mov     r15d, 1
0x180028431  cmp     r14d, r15d
0x180028434  jnz     short loc_180028440
0x180028436  mov     rcx, [rsi+48h]
0x18002843a  call    cs:__imp_FwFree
0x180028440  cmp     ebx, r15d
0x180028443  jnz     short loc_18002844F
0x180028445  mov     rcx, [rsi+60h]
0x180028449  call    cs:__imp_FwFree
0x18002844f  mov     eax, edi
0x180028451  mov     rcx, [rbp+400h+var_50]
0x180028458  xor     rcx, rsp; StackCookie
0x18002845b  call    __security_check_cookie
0x180028460  add     rsp, 4C8h
0x180028467  pop     r15
0x180028469  pop     r14
0x18002846b  pop     r13
0x18002846d  pop     r12
0x18002846f  pop     rdi
0x180028470  pop     rsi
0x180028471  pop     rbx
0x180028472  pop     rbp
0x180028473  retn
0x180028474  cmp     [rsp+500h+var_4B0], ebx
0x180028478  jz      short loc_1800284CE
0x18002847a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028481  lea     rax, WPP_GLOBAL_Control
0x180028488  cmp     rcx, rax
0x18002848b  jz      short loc_1800284A8
0x18002848d  test    byte ptr [rcx+1Ch], 4
0x180028491  jz      short loc_1800284A8
0x180028493  mov     rcx, [rcx+10h]
0x180028497  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x18002849e  mov     edx, 44h ; 'D'
0x1800284a3  call    WPP_SF_
0x1800284a8  mov     r8, [rsi+18h]
0x1800284ac  mov     r9d, 4
0x1800284b2  mov     rdx, [rsi+10h]
0x1800284b6  call    FwAuditLogEmptyResolution
0x1800284bb  mov     edx, 8
0x1800284c0  mov     rcx, r13
0x1800284c3  call    cs:__imp_FwMetaDataAddEnforcementState
0x1800284c9  jmp     loc_180028345
0x1800284ce  mov     eax, 1
0x1800284d3  lea     rcx, [rsi+50h]
0x1800284d7  mov     r8d, eax
0x1800284da  lea     rdx, [rsp+500h+var_4B0]
0x1800284df  mov     r14d, eax
0x1800284e2  call    ResolvePorts
0x1800284e7  mov     edi, eax
0x1800284e9  test    eax, eax
0x1800284eb  jns     short loc_180028518
0x1800284ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284f4  lea     rax, WPP_GLOBAL_Control
0x1800284fb  cmp     rcx, rax
0x1800284fe  jz      loc_180028345
0x180028504  test    [rcx+1Ch], r14b
0x180028508  jz      loc_180028345
0x18002850e  mov     edx, 45h ; 'E'
0x180028513  jmp     loc_180028332
0x180028518  cmp     [rsp+500h+var_4B0], ebx
0x18002851c  jz      short loc_180028569
0x18002851e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028525  lea     rax, WPP_GLOBAL_Control
0x18002852c  cmp     rcx, rax
0x18002852f  jz      short loc_18002854C
0x180028531  test    byte ptr [rcx+1Ch], 4
0x180028535  jz      short loc_18002854C
0x180028537  mov     rcx, [rcx+10h]
0x18002853b  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x180028542  mov     edx, 46h ; 'F'
0x180028547  call    WPP_SF_
0x18002854c  mov     r8, [rsi+18h]
0x180028550  mov     r9d, 5
0x180028556  mov     rdx, [rsi+10h]
0x18002855a  call    FwAuditLogEmptyResolution
0x18002855f  mov     edx, 9
0x180028564  jmp     loc_1800284C0
0x180028569  mov     edx, [rsi+108h]
0x18002856f  lea     rax, [rsp+500h+var_4B0]
0x180028574  lea     rcx, [rsi+0F8h]
0x18002857b  mov     [rsp+500h+var_4E0], rax
0x180028580  lea     r9, [rsp+500h+var_4A0]
0x180028585  lea     r8, [rsp+500h+var_4A8]
0x18002858a  call    ResolveInterfaces
0x18002858f  mov     edi, eax
0x180028591  test    eax, eax
0x180028593  jns     short loc_1800285D3
0x180028595  mov     rcx, cs:WPP_GLOBAL_Control
0x18002859c  lea     rax, WPP_GLOBAL_Control
0x1800285a3  cmp     rcx, rax
0x1800285a6  jz      short loc_1800285C6
0x1800285a8  test    byte ptr [rcx+1Ch], 1
0x1800285ac  jz      short loc_1800285C6
0x1800285ae  mov     edx, 47h ; 'G'
0x1800285b3  mov     rcx, [rcx+10h]
0x1800285b7  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800285be  mov     r9d, edi
0x1800285c1  call    WPP_SF_d
0x1800285c6  mov     r15, [rsp+500h+var_4A8]
0x1800285cb  mov     ebx, r14d
0x1800285ce  jmp     loc_180028345
0x1800285d3  cmp     [rsp+500h+var_4B0], ebx
0x1800285d7  jz      short loc_18002862A
0x1800285d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285e0  lea     rax, WPP_GLOBAL_Control
0x1800285e7  cmp     rcx, rax
0x1800285ea  jz      short loc_180028607
0x1800285ec  test    byte ptr [rcx+1Ch], 4
0x1800285f0  jz      short loc_180028607
0x1800285f2  mov     rcx, [rcx+10h]
0x1800285f6  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800285fd  mov     edx, 48h ; 'H'
0x180028602  call    WPP_SF_
0x180028607  mov     r8, [rsi+18h]
0x18002860b  mov     r9d, 1
0x180028611  mov     rdx, [rsi+10h]
0x180028615  call    FwAuditLogEmptyResolution
0x18002861a  mov     edx, 0Ah
0x18002861f  mov     rcx, r13
0x180028622  call    cs:__imp_FwMetaDataAddEnforcementState
0x180028628  jmp     short loc_1800285C6
0x18002862a  mov     r15, [rsp+500h+var_4A8]
0x18002862f  mov     [rsp+500h+var_4A8], r15
0x180028634  test    r15, r15
0x180028637  jnz     short loc_180028650
0x180028639  lea     r15, [rbp+400h+Base]
0x180028640  mov     ebx, 1
0x180028645  mov     [rsp+500h+var_4A8], r15
0x18002864a  mov     dword ptr [rsp+500h+var_4A0], ebx
0x18002864e  jmp     short loc_180028654
0x180028650  mov     ebx, dword ptr [rsp+500h+var_4A0]
0x180028654  lea     rcx, [rsi+190h]
0x18002865b  mov     [rsp+500h+var_4AC], ebx
0x18002865f  lea     r9, [rsp+500h+var_4B0]
0x180028664  lea     r8, [rsp+500h+var_488]
0x180028669  lea     rdx, [rbp+400h+var_478]
0x18002866d  call    ResolveNetworkNames
0x180028672  xor     r9d, r9d
0x180028675  mov     edi, eax
0x180028677  test    eax, eax
0x180028679  jns     short loc_1800286BC
0x18002867b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028682  lea     rax, WPP_GLOBAL_Control
0x180028689  cmp     rcx, rax
0x18002868c  jz      short loc_1800286AB
0x18002868e  test    byte ptr [rcx+1Ch], 1
0x180028692  jz      short loc_1800286AB
0x180028694  mov     rcx, [rcx+10h]
0x180028698  lea     edx, [r9+49h]
0x18002869c  mov     r9d, edi
0x18002869f  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800286a6  call    WPP_SF_d
0x1800286ab  mov     rax, [rbp+400h+var_478]
0x1800286af  mov     ebx, r14d
0x1800286b2  mov     [rsp+500h+var_490], rax
0x1800286b7  jmp     loc_180028345
0x1800286bc  cmp     [rsp+500h+var_4B0], r9d
0x1800286c1  jz      short loc_180028701
0x1800286c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286ca  lea     rax, WPP_GLOBAL_Control
0x1800286d1  cmp     rcx, rax
0x1800286d4  jz      short loc_1800286F1
0x1800286d6  test    byte ptr [rcx+1Ch], 4
0x1800286da  jz      short loc_1800286F1
0x1800286dc  mov     rcx, [rcx+10h]
0x1800286e0  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
  ... truncated ...
```
