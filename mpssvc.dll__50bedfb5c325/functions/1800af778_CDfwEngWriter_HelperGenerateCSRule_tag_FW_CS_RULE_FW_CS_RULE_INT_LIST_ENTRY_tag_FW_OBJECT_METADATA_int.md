# CDfwEngWriter::HelperGenerateCSRule(_tag_FW_CS_RULE *,_FW_CS_RULE_INT_ *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *,int)

- ea: `0x1800af778`
- end: `0x1800b0532`
- name: `?HelperGenerateCSRule@CDfwEngWriter@@AEAAJPEAU_tag_FW_CS_RULE@@PEAU_FW_CS_RULE_INT_@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@H@Z`
- size: `3514`
- prototype: `__int64 __fastcall(CDfwEngWriter *__hidden this, struct _tag_FW_CS_RULE *, struct _FW_CS_RULE_INT_ *, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x1800ae7c0`

## callees

- `0x18000a710`
- `0x18000b030`
- `0x18000e430`
- `0x1800192e0`
- `0x18002cf08`
- `0x18003defc`
- `0x18003f1f0`
- `0x18003f928`
- `0x18004cf10`
- `0x18004d54c`
- `0x1800607bc`
- `0x18006c0cc`
- `0x1800729c0`
- `0x180073488`
- `0x1800af778`
- `0x1800b0e48`
- `0x1800b2190`
- `0x1800c5d6c`

## import_xrefs

- `fwbase!FwMetaDataAddEnforcementState` at `0x1800af9c2`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800afa92`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800afe82`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800aff55`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800b051c`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800af9c2`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800afa92`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800afe82`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800aff55`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800b051c`
- `fwbase!FwSortAddresses` at `0x1800afb72`
- `fwbase!FwSortAddresses` at `0x1800afb8b`
- `fwbase!FwSortAddresses` at `0x1800afc64`
- `fwbase!FwSortAddresses` at `0x1800afb72`
- `fwbase!FwSortAddresses` at `0x1800afb8b`
- `fwbase!FwSortAddresses` at `0x1800afc64`
- `fwbase!IsAddressesEmpty` at `0x1800afad1`
- `fwbase!IsAddressesEmpty` at `0x1800afae7`
- `fwbase!IsAddressesEmpty` at `0x1800afad1`
- `fwbase!IsAddressesEmpty` at `0x1800afae7`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800affeb`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800affeb`
- `fwbase!FwFree` at `0x1800af8b1`
- `fwbase!FwFree` at `0x1800af8ca`
- `fwbase!FwFree` at `0x1800af8e2`
- `fwbase!FwFree` at `0x1800af8b1`
- `fwbase!FwFree` at `0x1800af8ca`
- `fwbase!FwFree` at `0x1800af8e2`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800af8f8`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800af90e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800af91e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800af92e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800af941`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800afc48`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800afd25`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800af8f8`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800af90e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800af91e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800af92e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800af941`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800afc48`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800afd25`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800afba2`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800afbe3`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800afc7b`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800afcc0`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800afba2`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800afbe3`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800afc7b`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800afcc0`

## pseudocode

```c
__int64 __fastcall CDfwEngWriter::HelperGenerateCSRule(
        CDfwEngWriter *this,
        struct _tag_FW_CS_RULE *a2,
        struct _FW_CS_RULE_INT_ *a3,
        struct _LIST_ENTRY *a4,
        struct _tag_FW_OBJECT_METADATA *a5,
        int a6)
{
  unsigned __int64 *v6; // r12
  int v9; // r13d
  int v10; // ebx
  int v11; // eax
  int v12; // edi
  int v13; // r14d
  int v14; // r12d
  __int64 *v15; // rcx
  int v17; // eax
  int v18; // r15d
  int v19; // eax
  __int64 v20; // rcx
  int v21; // r12d
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int16 v26; // ax
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  CDfwEngWriter *v32; // rcx
  unsigned int v33; // r15d
  __int64 v34; // r12
  unsigned int i; // r15d
  int v36; // ebx
  int v37; // r9d
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  int CSMirrorIntersect; // eax
  __int64 v43; // rcx
  __int64 v44; // rdx
  CDfwEngWriter *v45; // r9
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // r12
  int v49; // ecx
  int v50; // ecx
  struct _LIST_ENTRY *v51; // r8
  __int64 j; // rbx
  struct _LIST_ENTRY *v53; // r8
  __int64 k; // rbx
  struct _LIST_ENTRY *v55; // r8
  __int64 v56; // rbx
  __int64 v57; // r15
  struct _LIST_ENTRY *v58; // r8
  __int64 *v59; // [rsp+48h] [rbp-B8h]
  int v60; // [rsp+50h] [rbp-B0h] BYREF
  int v61; // [rsp+54h] [rbp-ACh]
  __int64 *v62; // [rsp+58h] [rbp-A8h] BYREF
  CDfwEngWriter *v63; // [rsp+60h] [rbp-A0h]
  unsigned int v64; // [rsp+68h] [rbp-98h]
  int v65; // [rsp+6Ch] [rbp-94h]
  struct _tag_FW_OBJECT_METADATA *v66; // [rsp+70h] [rbp-90h]
  int v67[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _LIST_ENTRY *v68; // [rsp+80h] [rbp-80h]
  int v69; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v70[80]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v71[80]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v72[80]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v73[80]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v74; // [rsp+1D0h] [rbp+D0h]
  int v75; // [rsp+1D8h] [rbp+D8h]
  __int64 v76; // [rsp+1E0h] [rbp+E0h] BYREF

  v6 = (unsigned __int64 *)a5;
  v63 = this;
  v68 = a4;
  v69 = 0;
  v59 = 0;
  v9 = 0;
  v62 = 0;
  v10 = 0;
  v76 = 0;
  v60 = 0;
  v66 = a5;
  v74 = 0;
  v75 = 0;
  memset_0(v73, 0, 0x48u);
  memset_0(v70, 0, 0x48u);
  memset_0(v71, 0, 0x48u);
  memset_0(v72, 0, 0x48u);
  *(_QWORD *)v67 = 0;
  v11 = ResolveAddresses((struct _tag_FW_CS_RULE *)((char *)a2 + 48), 0, 1, 0);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        131,
        WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
        (unsigned int)v11);
    v13 = 0;
LABEL_6:
    v14 = 0;
    goto LABEL_7;
  }
  v17 = ResolveAddresses((struct _tag_FW_CS_RULE *)((char *)a2 + 120), 0, 1, 0);
  v12 = v17;
  if ( v17 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        133,
        WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
        (unsigned int)v17);
    v13 = 1;
    goto LABEL_6;
  }
  if ( !(unsigned int)IsCSRuleTunnelMode(a2) && (*((_BYTE *)a2 + 340) & 2) == 0 )
  {
    v18 = IsAddressesEmpty((char *)a2 + 48);
    v19 = IsAddressesEmpty((char *)a2 + 120);
    v21 = v19;
    if ( !v18 || !v19 )
    {
      v22 = ResolveLocalAddresses(v20, &v69, v73);
      v12 = v22;
      if ( v22 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_36;
        v24 = 135;
        goto LABEL_35;
      }
      if ( v69 )
      {
        v6 = (unsigned __int64 *)v66;
        v25 = 19;
LABEL_25:
        FwMetaDataAddEnforcementState(v6, v25);
LABEL_26:
        v13 = 1;
LABEL_185:
        FwMetaDataAddEnforcementState(v6, 1);
        v14 = 1;
        goto LABEL_7;
      }
      FwSortAddresses(v73);
      if ( !v18 )
      {
        FwSortAddresses((char *)a2 + 48);
        v22 = FwPolioCopyWFAddressesContents(v73, v70);
        v12 = v22;
        if ( v22 < 0 )
        {
          v23 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_36;
          v24 = 136;
          goto LABEL_35;
        }
        v22 = FwPolioCopyWFAddressesContents((char *)a2 + 48, v71);
        v12 = v22;
        if ( v22 < 0 )
        {
          v23 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_36;
          v24 = 137;
          goto LABEL_35;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_ConSec_Rule_IPV6_Parsing_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_ConSec_Rule_IPV6_Parsing_Fix>::GetImpl'::`2'::impl) )
          FWAddressAndIPAddressIntersect(v71, v70);
        else
          FWAddressAndIPAddressIntersect_Old(v71, v70);
        FwPolioEmptyWFAddresses(v70);
      }
      if ( !v21 )
      {
        FwSortAddresses((char *)a2 + 120);
        v22 = FwPolioCopyWFAddressesContents(v73, v70);
        v12 = v22;
        if ( v22 < 0 )
        {
          v23 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_36;
          v24 = 138;
          goto LABEL_35;
        }
        v22 = FwPolioCopyWFAddressesContents((char *)a2 + 120, v72);
        v12 = v22;
        if ( v22 < 0 )
        {
          v23 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_36;
          v24 = 139;
          goto LABEL_35;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_ConSec_Rule_IPV6_Parsing_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_ConSec_Rule_IPV6_Parsing_Fix>::GetImpl'::`2'::impl) )
          FWAddressAndIPAddressIntersect(v72, v70);
        else
          FWAddressAndIPAddressIntersect_Old(v72, v70);
        FwPolioEmptyWFAddresses(v70);
      }
    }
    v6 = (unsigned __int64 *)v66;
  }
  v26 = *((_WORD *)a2 + 152);
  if ( v26 == 6 || v26 == 17 )
  {
    v22 = ResolvePorts((char *)a2 + 256, &v69, 1);
    v12 = v22;
    if ( v22 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_36;
      v24 = 140;
LABEL_35:
      WPP_SF_d(*(_QWORD *)(v23 + 16), v24, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids, (unsigned int)v22);
      goto LABEL_36;
    }
    if ( v69 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 141, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
      FwAuditLogEmptyResolution(v27, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 8);
      v25 = 8;
      goto LABEL_25;
    }
    v9 = 1;
    v28 = ResolvePorts((char *)a2 + 280, &v69, 1);
    v12 = v28;
    if ( v28 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          142,
          WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
          (unsigned int)v28);
      v14 = 1;
      v13 = 1;
      goto LABEL_7;
    }
    if ( v69 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 143, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
      FwAuditLogEmptyResolution(v29, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 9);
      FwMetaDataAddEnforcementState(v6, 9);
      v13 = 1;
      goto LABEL_185;
    }
  }
  v30 = ResolveInterfaces((int)a2 + 192, *((_DWORD *)a2 + 52), (unsigned int)&v62, (unsigned int)&v60, (__int64)&v69);
  v12 = v30;
  if ( v30 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        144,
        WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
        (unsigned int)v30);
    v14 = 1;
    v10 = v9;
    v15 = v62;
    v13 = 1;
    goto LABEL_8;
  }
  if ( v69 )
  {
    v31 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 145, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
    FwAuditLogEmptyResolution(v31, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 1);
    FwMetaDataAddEnforcementState(v6, 10);
    v10 = v9;
    v59 = v62;
    goto LABEL_26;
  }
  v32 = (CDfwEngWriter *)v62;
  v61 = 0;
  v59 = v62;
  if ( v62 )
  {
    v64 = v60;
  }
  else
  {
    v64 = 1;
    v59 = &v76;
  }
  if ( *((_DWORD *)a2 + 10) != 0x7FFFFFFF || a6 )
  {
    if ( a6 != 1 )
    {
      v34 = 0;
      for ( i = 0; i < 3; ++i )
      {
        v36 = *((_DWORD *)a2 + 10);
        if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(i) & v36) != 0 )
        {
          *((_DWORD *)&v74 + v34) = i;
          v34 = (unsigned int)(v34 + 1);
        }
      }
      v60 = v34;
      v6 = (unsigned __int64 *)v66;
      v33 = v60;
      goto LABEL_111;
    }
    LODWORD(v74) = 3;
  }
  else
  {
    LODWORD(v74) = 4;
  }
  v33 = 1;
  v60 = 1;
LABEL_111:
  CDfwEngWriter::RuleIPVersionExistence(
    v32,
    (struct _tag_FW_CS_RULE *)((char *)a2 + 48),
    (struct _tag_FW_CS_RULE *)((char *)a2 + 120),
    *((_WORD *)a2 + 152),
    v67);
  v37 = *((_DWORD *)a2 + 53);
  if ( !v37 && !*((_DWORD *)a2 + 58) )
  {
    v38 = *((_QWORD *)a2 + 27) - (_QWORD)g_IPV6_UNSPECIFIED_ADDRESS;
    if ( !v38 )
      v38 = *((_QWORD *)a2 + 28) - qword_180137780;
    if ( v38 )
      goto LABEL_119;
    v39 = *(_QWORD *)((char *)a2 + 236) - (_QWORD)g_IPV6_UNSPECIFIED_ADDRESS;
    if ( !v39 )
      v39 = *(_QWORD *)((char *)a2 + 244) - qword_180137780;
    if ( v39 )
LABEL_119:
      v67[0] = 0;
  }
  v40 = *((_QWORD *)a2 + 27) - (_QWORD)g_IPV6_UNSPECIFIED_ADDRESS;
  if ( !v40 )
    v40 = *((_QWORD *)a2 + 28) - qword_180137780;
  if ( !v40 )
  {
    v41 = *(_QWORD *)((char *)a2 + 236) - (_QWORD)g_IPV6_UNSPECIFIED_ADDRESS;
    if ( !v41 )
      v41 = *(_QWORD *)((char *)a2 + 244) - qword_180137780;
    if ( !v41 && (v37 || *((_DWORD *)a2 + 58)) )
      v67[1] = 0;
  }
  *(_QWORD *)a3 = a2;
  if ( (unsigned int)IsCSRuleTunnelMode(a2) == 1 )
  {
    CSMirrorIntersect = ConvertRangesToSubnets((char *)a2 + 48);
    v12 = CSMirrorIntersect;
    if ( CSMirrorIntersect < 0 )
    {
      v43 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_135;
      v44 = 146;
      goto LABEL_134;
    }
    v61 = 1;
    CSMirrorIntersect = ConvertRangesToSubnets((char *)a2 + 120);
    v12 = CSMirrorIntersect;
    if ( CSMirrorIntersect < 0 )
    {
      v43 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_135;
      v44 = 147;
LABEL_134:
      WPP_SF_d(
        *(_QWORD *)(v43 + 16),
        v44,
        WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
        (unsigned int)CSMirrorIntersect);
      goto LABEL_135;
    }
  }
  v45 = v63;
  if ( !*v6 )
    CDfwEngWriter::HelperGenerateUInt64FilterContextId(v63, v6);
  v46 = 0;
  *((_QWORD *)a3 + 5) = *v6;
  *((_QWORD *)a3 + 20) = v6 + 6;
  while ( 1 )
  {
    LODWORD(v62) = v46;
    v10 = v9;
    if ( (unsigned int)v46 >= v64 )
    {
      v13 = 1;
      v14 = 1;
      if ( v12 < 0 )
        goto LABEL_7;
      v6 = (unsigned __int64 *)v66;
      goto LABEL_185;
    }
    v47 = 0;
    *((_QWORD *)a3 + 18) = v59[v46];
LABEL_145:
    v65 = v47;
    if ( (unsigned int)v47 < v33 )
      break;
    v46 = (unsigned int)((_DWORD)v62 + 1);
  }
  v48 = 0;
  *((_DWORD *)a3 + 38) = *((_DWORD *)&v74 + v47);
  while ( 1 )
  {
    if ( (unsigned int)v48 >= 2 )
    {
      v33 = v60;
      v47 = (unsigned int)(v65 + 1);
      goto LABEL_145;
    }
    if ( !v67[v48] )
      goto LABEL_152;
    *((_DWORD *)a3 + 43) = -1;
    *((_DWORD *)a3 + 14) = 1;
    *((_DWORD *)a3 + 24) = 1;
    v49 = ((_DWORD)v48 != 0) + 1;
    *((_DWORD *)a3 + 15) = v49;
    *((_DWORD *)a3 + 25) = v49;
    v50 = *((_DWORD *)a2 + 72);
    if ( !*((_DWORD *)a2 + 66) )
    {
      *((_DWORD *)a3 + 34) = 0;
      if ( v50 )
      {
        for ( j = 0; (unsigned int)j < *((_DWORD *)a2 + 72); j = (unsigned int)(j + 1) )
        {
          v53 = v68;
          *((_WORD *)a3 + 70) = *(_WORD *)(*((_QWORD *)a2 + 37) + 4 * j);
          *((_WORD *)a3 + 71) = *(_WORD *)(*((_QWORD *)a2 + 37) + 4 * j + 2);
          CSMirrorIntersect = CDfwEngWriter::HelperGenerateCSMirrorIntersect(v45, a3, v53);
          v12 = CSMirrorIntersect;
          if ( CSMirrorIntersect < 0 )
          {
            v43 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v44 = 149;
              goto LABEL_134;
            }
            goto LABEL_135;
          }
          v45 = v63;
        }
      }
      else
      {
        v51 = v68;
        *((_DWORD *)a3 + 35) = 0;
        CSMirrorIntersect = CDfwEngWriter::HelperGenerateCSMirrorIntersect(v45, a3, v51);
        v12 = CSMirrorIntersect;
        if ( CSMirrorIntersect < 0 )
        {
          v43 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v44 = 148;
            goto LABEL_134;
          }
          goto LABEL_135;
        }
      }
      goto LABEL_152;
    }
    if ( !v50 )
    {
      *((_DWORD *)a3 + 35) = 0;
      for ( k = 0; (unsigned int)k < *((_DWORD *)a2 + 66); k = (unsigned int)(k + 1) )
      {
        v55 = v68;
        *((_WORD *)a3 + 68) = *(_WORD *)(*((_QWORD *)a2 + 34) + 4 * k);
        *((_WORD *)a3 + 69) = *(_WORD *)(*((_QWORD *)a2 + 34) + 4 * k + 2);
        CSMirrorIntersect = CDfwEngWriter::HelperGenerateCSMirrorIntersect(v45, a3, v55);
        v12 = CSMirrorIntersect;
        if ( CSMirrorIntersect < 0 )
        {
          v43 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v44 = 150;
            goto LABEL_134;
          }
          goto LABEL_135;
        }
        v45 = v63;
      }
      goto LABEL_152;
    }
    v56 = 0;
LABEL_163:
    if ( (unsigned int)v56 < *((_DWORD *)a2 + 66) )
      break;
LABEL_152:
    v45 = v63;
    v48 = (unsigned int)(v48 + 1);
  }
  v57 = 0;
  *((_WORD *)a3 + 68) = *(_WORD *)(*((_QWORD *)a2 + 34) + 4 * v56);
  *((_WORD *)a3 + 69) = *(_WORD *)(*((_QWORD *)a2 + 34) + 4 * v56 + 2);
  while ( 1 )
  {
    if ( (unsigned int)v57 >= *((_DWORD *)a2 + 72) )
    {
      v56 = (unsigned int)(v56 + 1);
      goto LABEL_163;
    }
    v58 = v68;
    *((_WORD *)a3 + 70) = *(_WORD *)(*((_QWORD *)a2 + 37) + 4 * v57);
    *((_WORD *)a3 + 71) = *(_WORD *)(*((_QWORD *)a2 + 37) + 4 * v57 + 2);
    CSMirrorIntersect = CDfwEngWriter::HelperGenerateCSMirrorIntersect(v45, a3, v58);
    v12 = CSMirrorIntersect;
    if ( CSMirrorIntersect < 0 )
      break;
    v45 = v63;
    v57 = (unsigned int)(v57 + 1);
  }
  v43 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v44 = 151;
    goto LABEL_134;
  }
LABEL_135:
  v10 = v9;
LABEL_36:
  v14 = 1;
  v13 = 1;
LABEL_7:
  v15 = v59;
LABEL_8:
  if ( v15 != &v76 )
    FwFree(v15);
  if ( v9 == 1 )
    FwFree(*((_QWORD *)a2 + 34));
  if ( v10 == 1 )
    FwFree(*((_QWORD *)a2 + 37));
  if ( v13 == 1 )
    FwPolioEmptyWFAddresses((char *)a2 + 48);
  if ( v14 == 1 )
    FwPolioEmptyWFAddresses((char *)a2 + 120);
  FwPolioEmptyWFAddresses(v71);
  FwPolioEmptyWFAddresses(v72);
  FwPolioEmptyWFAddresses(v73);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800af778  push    rbp
0x1800af77a  push    rbx
0x1800af77b  push    rsi
0x1800af77c  push    rdi
0x1800af77d  push    r12
0x1800af77f  push    r13
0x1800af781  push    r14
0x1800af783  push    r15
0x1800af785  lea     rbp, [rsp-0F8h]
0x1800af78d  sub     rsp, 1F8h
0x1800af794  mov     rax, cs:__security_cookie
0x1800af79b  xor     rax, rsp
0x1800af79e  mov     [rbp+130h+var_48], rax
0x1800af7a5  mov     r12, [rbp+130h+arg_20]
0x1800af7ac  xor     eax, eax
0x1800af7ae  mov     [rsp+230h+var_1D0], rcx
0x1800af7b3  mov     r14, r8
0x1800af7b6  xor     ecx, ecx
0x1800af7b8  mov     [rbp+130h+var_1B0], r9
0x1800af7bc  mov     rsi, rdx
0x1800af7bf  mov     [rbp+130h+var_1A8], ecx
0x1800af7c2  mov     [rsp+230h+var_1E8], rcx
0x1800af7c7  mov     r13d, ecx
0x1800af7ca  mov     [rsp+230h+var_1D8], rcx
0x1800af7cf  mov     ebx, ecx
0x1800af7d1  lea     edi, [rcx+48h]
0x1800af7d4  mov     [rbp+130h+var_50], rcx
0x1800af7db  mov     [rsp+230h+var_1E0], ecx
0x1800af7df  mov     r8d, edi; Size
0x1800af7e2  mov     [rsp+230h+var_1EC], ecx
0x1800af7e6  xor     edx, edx; Val
0x1800af7e8  lea     rcx, [rbp+130h+var_B0]; void *
0x1800af7ef  mov     [rsp+230h+var_1C0], r12
0x1800af7f4  mov     [rbp+130h+var_60], rax
0x1800af7fb  mov     [rbp+130h+var_58], eax
0x1800af801  call    memset_0
0x1800af806  mov     r8d, edi; Size
0x1800af809  lea     rcx, [rbp+130h+var_1A0]; void *
0x1800af80d  xor     edx, edx; Val
0x1800af80f  call    memset_0
0x1800af814  mov     r8d, edi; Size
0x1800af817  lea     rcx, [rbp+130h+var_150]; void *
0x1800af81b  xor     edx, edx; Val
0x1800af81d  call    memset_0
0x1800af822  mov     r8d, edi; Size
0x1800af825  lea     rcx, [rbp+130h+var_100]; void *
0x1800af829  xor     edx, edx; Val
0x1800af82b  call    memset_0
0x1800af830  xor     eax, eax
0x1800af832  lea     ecx, [rdi-47h]
0x1800af835  mov     [rsp+230h+var_200], rax; __int64
0x1800af83a  lea     r8, [rbp+130h+var_1A8]
0x1800af83e  mov     dword ptr [rsp+230h+var_208], ecx; char
0x1800af842  mov     r9d, ecx
0x1800af845  lea     rcx, [rsi+30h]; struct _tag_FW_ADDRESSES *
0x1800af849  mov     qword ptr [rsp+230h+var_1B8], rax
0x1800af84e  mov     edx, 7FFFFFFFh
0x1800af853  mov     [rsp+230h+var_210], rax; __int64
0x1800af858  call    ResolveAddresses
0x1800af85d  xor     ecx, ecx
0x1800af85f  mov     edi, eax
0x1800af861  test    eax, eax
0x1800af863  jns     loc_1800AF973
0x1800af869  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af870  lea     rdx, WPP_GLOBAL_Control
0x1800af877  cmp     rcx, rdx
0x1800af87a  jz      short loc_1800AF89A
0x1800af87c  test    byte ptr [rcx+1Ch], 1
0x1800af880  jz      short loc_1800AF89A
0x1800af882  mov     rcx, [rcx+10h]
0x1800af886  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800af88d  mov     edx, 83h
0x1800af892  mov     r9d, eax
0x1800af895  call    WPP_SF_d
0x1800af89a  mov     r14d, ebx
0x1800af89d  mov     r12d, ebx
0x1800af8a0  mov     rcx, [rsp+230h+var_1E8]
0x1800af8a5  lea     rax, [rbp+130h+var_50]
0x1800af8ac  cmp     rcx, rax
0x1800af8af  jz      short loc_1800AF8BD
0x1800af8b1  call    cs:__imp_FwFree
0x1800af8b8  nop     dword ptr [rax+rax+00h]
0x1800af8bd  cmp     r13d, 1
0x1800af8c1  jnz     short loc_1800AF8D6
0x1800af8c3  mov     rcx, [rsi+110h]
0x1800af8ca  call    cs:__imp_FwFree
0x1800af8d1  nop     dword ptr [rax+rax+00h]
0x1800af8d6  cmp     ebx, 1
0x1800af8d9  jnz     short loc_1800AF8EE
0x1800af8db  mov     rcx, [rsi+128h]
0x1800af8e2  call    cs:__imp_FwFree
0x1800af8e9  nop     dword ptr [rax+rax+00h]
0x1800af8ee  cmp     r14d, 1
0x1800af8f2  jnz     short loc_1800AF904
0x1800af8f4  lea     rcx, [rsi+30h]
0x1800af8f8  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800af8ff  nop     dword ptr [rax+rax+00h]
0x1800af904  cmp     r12d, 1
0x1800af908  jnz     short loc_1800AF91A
0x1800af90a  lea     rcx, [rsi+78h]
0x1800af90e  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800af915  nop     dword ptr [rax+rax+00h]
0x1800af91a  lea     rcx, [rbp+130h+var_150]
0x1800af91e  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800af925  nop     dword ptr [rax+rax+00h]
0x1800af92a  lea     rcx, [rbp+130h+var_100]
0x1800af92e  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800af935  nop     dword ptr [rax+rax+00h]
0x1800af93a  lea     rcx, [rbp+130h+var_B0]
0x1800af941  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800af948  nop     dword ptr [rax+rax+00h]
0x1800af94d  mov     eax, edi
0x1800af94f  mov     rcx, [rbp+130h+var_48]
0x1800af956  xor     rcx, rsp; StackCookie
0x1800af959  call    __security_check_cookie
0x1800af95e  add     rsp, 1F8h
0x1800af965  pop     r15
0x1800af967  pop     r14
0x1800af969  pop     r13
0x1800af96b  pop     r12
0x1800af96d  pop     rdi
0x1800af96e  pop     rsi
0x1800af96f  pop     rbx
0x1800af970  pop     rbp
0x1800af971  retn
0x1800af973  cmp     [rbp+130h+var_1A8], ecx
0x1800af976  jz      short loc_1800AF9D6
0x1800af978  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af97f  lea     rdx, WPP_GLOBAL_Control
0x1800af986  cmp     rcx, rdx
0x1800af989  jz      short loc_1800AF9A6
0x1800af98b  test    byte ptr [rcx+1Ch], 4
0x1800af98f  jz      short loc_1800AF9A6
0x1800af991  mov     rcx, [rcx+10h]
0x1800af995  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800af99c  mov     edx, 84h
0x1800af9a1  call    WPP_SF_
0x1800af9a6  mov     r8, [rsi+18h]
0x1800af9aa  mov     r15d, 6
0x1800af9b0  mov     rdx, [rsi+10h]
0x1800af9b4  mov     r9d, r15d
0x1800af9b7  call    FwAuditLogEmptyResolution
0x1800af9bc  mov     edx, r15d
0x1800af9bf  mov     rcx, r12
0x1800af9c2  call    cs:__imp_FwMetaDataAddEnforcementState
0x1800af9c9  nop     dword ptr [rax+rax+00h]
0x1800af9ce  mov     r14d, ebx
0x1800af9d1  jmp     loc_1800B0514
0x1800af9d6  mov     edx, 1
0x1800af9db  mov     [rsp+230h+var_200], rcx; __int64
0x1800af9e0  mov     dword ptr [rsp+230h+var_208], edx; char
0x1800af9e4  lea     r8, [rbp+130h+var_1A8]
0x1800af9e8  mov     [rsp+230h+var_210], rcx; __int64
0x1800af9ed  mov     r9d, edx
0x1800af9f0  mov     [rsp+230h+var_1F0], edx
0x1800af9f4  lea     rcx, [rsi+78h]; struct _tag_FW_ADDRESSES *
0x1800af9f8  mov     edx, 7FFFFFFFh
0x1800af9fd  call    ResolveAddresses
0x1800afa02  mov     edi, eax
0x1800afa04  test    eax, eax
0x1800afa06  jns     short loc_1800AFA43
0x1800afa08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afa0f  lea     rdx, WPP_GLOBAL_Control
0x1800afa16  cmp     rcx, rdx
0x1800afa19  jz      short loc_1800AFA39
0x1800afa1b  test    byte ptr [rcx+1Ch], 1
0x1800afa1f  jz      short loc_1800AFA39
0x1800afa21  mov     rcx, [rcx+10h]
0x1800afa25  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800afa2c  mov     edx, 85h
0x1800afa31  mov     r9d, eax
0x1800afa34  call    WPP_SF_d
0x1800afa39  mov     r14d, [rsp+230h+var_1F0]
0x1800afa3e  jmp     loc_1800AF89D
0x1800afa43  cmp     [rbp+130h+var_1A8], ebx
0x1800afa46  jz      short loc_1800AFAA8
0x1800afa48  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afa4f  lea     rdx, WPP_GLOBAL_Control
0x1800afa56  cmp     rcx, rdx
0x1800afa59  jz      short loc_1800AFA76
0x1800afa5b  test    byte ptr [rcx+1Ch], 4
0x1800afa5f  jz      short loc_1800AFA76
0x1800afa61  mov     rcx, [rcx+10h]
0x1800afa65  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800afa6c  mov     edx, 86h
0x1800afa71  call    WPP_SF_
0x1800afa76  mov     r14d, 7
0x1800afa7c  mov     r8, [rsi+18h]
0x1800afa80  mov     r9d, r14d
0x1800afa83  mov     rdx, [rsi+10h]
0x1800afa87  call    FwAuditLogEmptyResolution
0x1800afa8c  mov     edx, r14d
0x1800afa8f  mov     rcx, r12
0x1800afa92  call    cs:__imp_FwMetaDataAddEnforcementState
0x1800afa99  nop     dword ptr [rax+rax+00h]
0x1800afa9e  mov     r14d, [rsp+230h+var_1F0]
0x1800afaa3  jmp     loc_1800B0514
0x1800afaa8  mov     rcx, rsi
0x1800afaab  mov     [rsp+230h+var_1EC], 1
0x1800afab3  call    IsCSRuleTunnelMode
0x1800afab8  test    eax, eax
0x1800afaba  jnz     loc_1800AFD36
0x1800afac0  test    byte ptr [rsi+154h], 2
0x1800afac7  jnz     loc_1800AFD36
0x1800afacd  lea     rcx, [rsi+30h]
0x1800afad1  call    cs:__imp_IsAddressesEmpty
0x1800afad8  nop     dword ptr [rax+rax+00h]
0x1800afadd  lea     rdi, [rsi+78h]
0x1800afae1  mov     r15d, eax
0x1800afae4  mov     rcx, rdi
0x1800afae7  call    cs:__imp_IsAddressesEmpty
0x1800afaee  nop     dword ptr [rax+rax+00h]
0x1800afaf3  mov     r12d, eax
0x1800afaf6  test    r15d, r15d
0x1800afaf9  jz      short loc_1800AFB03
0x1800afafb  test    eax, eax
0x1800afafd  jnz     loc_1800AFD31
0x1800afb03  lea     r8, [rbp+130h+var_B0]
0x1800afb0a  lea     rdx, [rbp+130h+var_1A8]
0x1800afb0e  call    ResolveLocalAddresses
0x1800afb13  mov     edi, eax
0x1800afb15  test    eax, eax
0x1800afb17  jns     short loc_1800AFB57
0x1800afb19  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afb20  lea     rdx, WPP_GLOBAL_Control
0x1800afb27  cmp     rcx, rdx
0x1800afb2a  jz      short loc_1800AFB4A
0x1800afb2c  test    byte ptr [rcx+1Ch], 1
0x1800afb30  jz      short loc_1800AFB4A
0x1800afb32  mov     edx, 87h
0x1800afb37  mov     rcx, [rcx+10h]
0x1800afb3b  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800afb42  mov     r9d, eax
0x1800afb45  call    WPP_SF_d
0x1800afb4a  mov     r12d, [rsp+230h+var_1EC]
0x1800afb4f  mov     r14d, r12d
0x1800afb52  jmp     loc_1800AF8A0
0x1800afb57  cmp     [rbp+130h+var_1A8], ebx
0x1800afb5a  jz      short loc_1800AFB6B
0x1800afb5c  mov     r12, [rsp+230h+var_1C0]
0x1800afb61  mov     edx, 13h
0x1800afb66  jmp     loc_1800AFA8F
0x1800afb6b  lea     rcx, [rbp+130h+var_B0]
0x1800afb72  call    cs:__imp_FwSortAddresses
0x1800afb79  nop     dword ptr [rax+rax+00h]
0x1800afb7e  test    r15d, r15d
0x1800afb81  jnz     loc_1800AFC54
0x1800afb87  lea     rcx, [rsi+30h]
0x1800afb8b  call    cs:__imp_FwSortAddresses
0x1800afb92  nop     dword ptr [rax+rax+00h]
0x1800afb97  lea     rdx, [rbp+130h+var_1A0]
0x1800afb9b  lea     rcx, [rbp+130h+var_B0]
0x1800afba2  call    cs:__imp_FwPolioCopyWFAddressesContents
0x1800afba9  nop     dword ptr [rax+rax+00h]
0x1800afbae  mov     edi, eax
0x1800afbb0  test    eax, eax
0x1800afbb2  jns     short loc_1800AFBDB
0x1800afbb4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afbbb  lea     rdx, WPP_GLOBAL_Control
0x1800afbc2  cmp     rcx, rdx
0x1800afbc5  jz      short loc_1800AFB4A
0x1800afbc7  test    byte ptr [rcx+1Ch], 1
0x1800afbcb  jz      loc_1800AFB4A
0x1800afbd1  mov     edx, 88h
0x1800afbd6  jmp     loc_1800AFB37
0x1800afbdb  lea     rdx, [rbp+130h+var_150]
0x1800afbdf  lea     rcx, [rsi+30h]
0x1800afbe3  call    cs:__imp_FwPolioCopyWFAddressesContents
0x1800afbea  nop     dword ptr [rax+rax+00h]
0x1800afbef  mov     edi, eax
0x1800afbf1  test    eax, eax
0x1800afbf3  jns     short loc_1800AFC20
0x1800afbf5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afbfc  lea     rdx, WPP_GLOBAL_Control
0x1800afc03  cmp     rcx, rdx
0x1800afc06  jz      loc_1800AFB4A
0x1800afc0c  test    byte ptr [rcx+1Ch], 1
0x1800afc10  jz      loc_1800AFB4A
0x1800afc16  mov     edx, 89h
0x1800afc1b  jmp     loc_1800AFB37
0x1800afc20  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IPSec_ConSec_Rule_IPV6_Parsing_Fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_ConSec_Rule_IPV6_Parsing_Fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_ConSec_Rule_IPV6_Parsing_Fix> `wil::Feature<__WilFeatureTraits_Feature_IPSec_ConSec_Rule_IPV6_Parsing_Fix>::GetImpl(void)'::`2'::impl
0x1800afc27  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_ConSec_Rule_IPV6_Parsing_Fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_ConSec_Rule_IPV6_Parsing_Fix>::__private_IsEnabled(void)
0x1800afc2c  lea     rdx, [rbp+130h+var_1A0]
0x1800afc30  lea     rcx, [rbp+130h+var_150]
0x1800afc34  test    al, al
0x1800afc36  jz      short loc_1800AFC3F
0x1800afc38  call    FWAddressAndIPAddressIntersect
0x1800afc3d  jmp     short loc_1800AFC44
0x1800afc3f  call    FWAddressAndIPAddressIntersect_Old
0x1800afc44  lea     rcx, [rbp+130h+var_1A0]
0x1800afc48  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800afc4f  nop     dword ptr [rax+rax+00h]
0x1800afc54  lea     rdi, [rsi+78h]
0x1800afc58  test    r12d, r12d
0x1800afc5b  jnz     loc_1800AFD31
0x1800afc61  mov     rcx, rdi
0x1800afc64  call    cs:__imp_FwSortAddresses
0x1800afc6b  nop     dword ptr [rax+rax+00h]
0x1800afc70  lea     rdx, [rbp+130h+var_1A0]
0x1800afc74  lea     rcx, [rbp+130h+var_B0]
  ... truncated ...
```
