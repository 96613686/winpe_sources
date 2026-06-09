# CDfwEngWriter::HelperGenerateCSRule(_tag_FW_CS_RULE *,_FW_CS_RULE_INT_ *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *,int)

- ea: `0x1800a9748`
- end: `0x1800aa46c`
- name: `?HelperGenerateCSRule@CDfwEngWriter@@AEAAJPEAU_tag_FW_CS_RULE@@PEAU_FW_CS_RULE_INT_@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@H@Z`
- size: `3364`
- prototype: `__int64 __fastcall(CDfwEngWriter *__hidden this, struct _tag_FW_CS_RULE *, struct _FW_CS_RULE_INT_ *, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1800a8b10`

## callees

- `0x18000af3c`
- `0x18000b800`
- `0x180017110`
- `0x18002973c`
- `0x18002a4e0`
- `0x18003db10`
- `0x18003ed90`
- `0x18003ee6c`
- `0x180049f28`
- `0x18004a53c`
- `0x18005bc94`
- `0x180069240`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800a9748`
- `0x1800bf0c0`

## import_xrefs

- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a98c9`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a9a3d`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a9d9e`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a9e6d`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800aa461`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a98c9`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a9a3d`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a9d9e`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a9e6d`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800aa461`
- `fwbase!FwSortAddresses` at `0x1800a9aea`
- `fwbase!FwSortAddresses` at `0x1800a9afd`
- `fwbase!FwSortAddresses` at `0x1800a9bab`
- `fwbase!FwSortAddresses` at `0x1800a9aea`
- `fwbase!FwSortAddresses` at `0x1800a9afd`
- `fwbase!FwSortAddresses` at `0x1800a9bab`
- `fwbase!IsAddressesEmpty` at `0x1800a9a71`
- `fwbase!IsAddressesEmpty` at `0x1800a9a7d`
- `fwbase!IsAddressesEmpty` at `0x1800a9a71`
- `fwbase!IsAddressesEmpty` at `0x1800a9a7d`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800a9efd`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800a9efd`
- `fwbase!FwFree` at `0x1800a9958`
- `fwbase!FwFree` at `0x1800a996b`
- `fwbase!FwFree` at `0x1800a997d`
- `fwbase!FwFree` at `0x1800a9958`
- `fwbase!FwFree` at `0x1800a996b`
- `fwbase!FwFree` at `0x1800a997d`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800a9b0e`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800a9b4d`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800a9bbc`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800a9bfa`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800a9b0e`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800a9b4d`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800a9bbc`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x1800a9bfa`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a998c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a999d`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a99a7`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a99b1`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a99be`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a9b95`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a9c42`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a998c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a999d`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a99a7`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a99b1`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a99be`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a9b95`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a9c42`

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
  int v8; // r13d
  int v9; // r12d
  int v10; // ebx
  int v11; // esi
  struct _tag_FW_ADDRESSES *v12; // r13
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 *v16; // rcx
  char *v17; // r15
  unsigned __int64 *v19; // r14
  int v20; // r15d
  int v21; // eax
  __int64 v22; // rcx
  int v23; // r13d
  __int64 v24; // rdx
  __int16 v25; // ax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  CDfwEngWriter *v31; // rcx
  unsigned int v32; // r15d
  int v33; // ebx
  int v34; // ebx
  int v35; // r9d
  int v36; // eax
  int CSMirrorIntersect; // eax
  __int64 v38; // rcx
  __int64 v39; // rdx
  unsigned __int64 *v40; // rdx
  CDfwEngWriter *v41; // r9
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // r13
  int v46; // ecx
  __int64 v47; // rax
  struct _LIST_ENTRY *v48; // r8
  __int64 v49; // rbx
  struct _LIST_ENTRY *v50; // r8
  __int64 v51; // rbx
  struct _LIST_ENTRY *v52; // r8
  __int64 v53; // r15
  struct _LIST_ENTRY *v54; // r8
  __int64 *v55; // [rsp+48h] [rbp-B8h]
  unsigned int v56; // [rsp+50h] [rbp-B0h]
  unsigned int v57; // [rsp+54h] [rbp-ACh] BYREF
  int v58; // [rsp+58h] [rbp-A8h]
  CDfwEngWriter *v59; // [rsp+60h] [rbp-A0h]
  unsigned __int64 *v60; // [rsp+68h] [rbp-98h]
  __int64 *v61; // [rsp+70h] [rbp-90h] BYREF
  int v62; // [rsp+78h] [rbp-88h]
  int v63; // [rsp+7Ch] [rbp-84h]
  int v64[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _LIST_ENTRY *v65; // [rsp+88h] [rbp-78h]
  _DWORD v66[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v67[80]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v68[80]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v69[80]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v70[80]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v71; // [rsp+1E0h] [rbp+E0h]
  int v72; // [rsp+1E8h] [rbp+E8h]
  __int64 v73; // [rsp+1F0h] [rbp+F0h] BYREF

  v59 = this;
  v60 = (unsigned __int64 *)a5;
  v66[0] = 0;
  v55 = 0;
  v8 = 0;
  v61 = 0;
  v9 = 0;
  v73 = 0;
  v57 = 0;
  v10 = 0;
  v63 = 0;
  v65 = a4;
  v71 = 0;
  v72 = 0;
  memset_0(v70, 0, 0x48u);
  memset_0(v69, 0, 0x48u);
  memset_0(v67, 0, 0x48u);
  memset_0(v68, 0, 0x48u);
  *(_QWORD *)v64 = 0;
  v11 = ResolveAddresses((struct _tag_FW_CS_RULE *)((char *)a2 + 48), 0, 1, 0);
  if ( v11 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        131,
        WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
        (unsigned int)v11);
    goto LABEL_11;
  }
  v12 = (struct _tag_FW_CS_RULE *)((char *)a2 + 120);
  v13 = ResolveAddresses((struct _tag_FW_CS_RULE *)((char *)a2 + 120), 0, 1, 0);
  v11 = v13;
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_10;
    v15 = 133;
    goto LABEL_9;
  }
  v63 = 1;
  if ( !(unsigned int)IsCSRuleTunnelMode(a2) && (*((_BYTE *)a2 + 340) & 2) == 0 )
  {
    v20 = IsAddressesEmpty((char *)a2 + 48);
    v21 = IsAddressesEmpty((char *)a2 + 120);
    v23 = v21;
    if ( v20 && v21 )
      goto LABEL_56;
    v13 = ResolveLocalAddresses(v22, v66, v70);
    v11 = v13;
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_10;
      v15 = 135;
      goto LABEL_9;
    }
    if ( v66[0] )
    {
      v24 = 19;
LABEL_25:
      v19 = v60;
      FwMetaDataAddEnforcementState(v60, v24);
LABEL_167:
      v8 = 1;
LABEL_168:
      FwMetaDataAddEnforcementState(v19, 1);
      goto LABEL_11;
    }
    FwSortAddresses(v70);
    if ( !v20 )
    {
      FwSortAddresses((char *)a2 + 48);
      v13 = FwPolioCopyWFAddressesContents(v70, v69);
      v11 = v13;
      if ( v13 < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_10;
        v15 = 136;
        goto LABEL_9;
      }
      v13 = FwPolioCopyWFAddressesContents((char *)a2 + 48, v67);
      v11 = v13;
      if ( v13 < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_10;
        v15 = 137;
        goto LABEL_9;
      }
      FWAddressAndIPAddressIntersect(v67, v69);
      FwPolioEmptyWFAddresses(v69);
    }
    if ( v23 )
    {
LABEL_56:
      v12 = (struct _tag_FW_CS_RULE *)((char *)a2 + 120);
    }
    else
    {
      v12 = (struct _tag_FW_CS_RULE *)((char *)a2 + 120);
      FwSortAddresses((char *)a2 + 120);
      v13 = FwPolioCopyWFAddressesContents(v70, v69);
      v11 = v13;
      if ( v13 < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_10;
        v15 = 138;
        goto LABEL_9;
      }
      v13 = FwPolioCopyWFAddressesContents((char *)a2 + 120, v68);
      v11 = v13;
      if ( v13 < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_10;
        v15 = 139;
        goto LABEL_9;
      }
      FWAddressAndIPAddressIntersect(v68, v69);
      FwPolioEmptyWFAddresses(v69);
    }
  }
  v25 = *((_WORD *)a2 + 152);
  if ( v25 == 6 || v25 == 17 )
  {
    v13 = ResolvePorts((char *)a2 + 256, v66, 1);
    v11 = v13;
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_10;
      v15 = 140;
LABEL_9:
      WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids, (unsigned int)v13);
      goto LABEL_10;
    }
    if ( v66[0] )
    {
      v26 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 141, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
      FwAuditLogEmptyResolution(v26, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 8);
      v24 = 8;
      goto LABEL_25;
    }
    v9 = 1;
    v27 = ResolvePorts((char *)a2 + 280, v66, 1);
    v11 = v27;
    if ( v27 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          142,
          WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
          (unsigned int)v27);
      v8 = 1;
      goto LABEL_11;
    }
    if ( v66[0] )
    {
      v28 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 143, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
      FwAuditLogEmptyResolution(v28, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 9);
      v19 = v60;
      FwMetaDataAddEnforcementState(v60, 9);
      v8 = 1;
      goto LABEL_168;
    }
  }
  v29 = ResolveInterfaces((int)a2 + 192, *((_DWORD *)a2 + 52), (unsigned int)&v61, (unsigned int)&v57, (__int64)v66);
  v11 = v29;
  if ( v29 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        144,
        WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
        (unsigned int)v29);
    v16 = v61;
    v10 = v9;
    v8 = 1;
    goto LABEL_12;
  }
  if ( v66[0] )
  {
    v30 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 145, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
    FwAuditLogEmptyResolution(v30, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3), 1);
    v19 = v60;
    FwMetaDataAddEnforcementState(v60, 10);
    v10 = v9;
    v55 = v61;
    goto LABEL_167;
  }
  v31 = (CDfwEngWriter *)v61;
  v32 = 0;
  v58 = 0;
  v55 = v61;
  if ( !v61 )
  {
    v57 = 1;
    v55 = &v73;
  }
  if ( *((_DWORD *)a2 + 10) != 0x7FFFFFFF || a6 )
  {
    if ( a6 != 1 )
    {
      v56 = 0;
      do
      {
        v34 = *((_DWORD *)a2 + 10);
        if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(v32) & v34) != 0 )
        {
          *((_DWORD *)&v71 + v56) = v32;
          v33 = ++v56;
        }
        else
        {
          v33 = v56;
        }
        ++v32;
      }
      while ( v32 < 3 );
      goto LABEL_101;
    }
    LODWORD(v71) = 3;
  }
  else
  {
    LODWORD(v71) = 4;
  }
  v33 = 1;
  v56 = 1;
LABEL_101:
  CDfwEngWriter::RuleIPVersionExistence(
    v31,
    (struct _tag_FW_CS_RULE *)((char *)a2 + 48),
    v12,
    *((_WORD *)a2 + 152),
    v64);
  v35 = *((_DWORD *)a2 + 53);
  if ( !v35
    && !*((_DWORD *)a2 + 58)
    && (*((unsigned __int8 near **)a2 + 27) != g_IPV6_UNSPECIFIED_ADDRESS
     || *((_QWORD *)a2 + 28) != qword_1801315C0
     || *(unsigned __int8 near **)((char *)a2 + 236) != g_IPV6_UNSPECIFIED_ADDRESS
     || *(_QWORD *)((char *)a2 + 244) != qword_1801315C0) )
  {
    v64[0] = 0;
  }
  if ( *((unsigned __int8 near **)a2 + 27) == g_IPV6_UNSPECIFIED_ADDRESS
    && *((_QWORD *)a2 + 28) == qword_1801315C0
    && *(unsigned __int8 near **)((char *)a2 + 236) == g_IPV6_UNSPECIFIED_ADDRESS
    && *(_QWORD *)((char *)a2 + 244) == qword_1801315C0
    && (v35 || *((_DWORD *)a2 + 58)) )
  {
    v64[1] = 0;
  }
  *(_QWORD *)a3 = a2;
  if ( (unsigned int)IsCSRuleTunnelMode(a2) == 1 )
  {
    v17 = (char *)a2 + 48;
    v36 = ConvertRangesToSubnets((char *)a2 + 48);
    v11 = v36;
    if ( v36 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          146,
          WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
          (unsigned int)v36);
      v16 = v55;
      v10 = v9;
      v8 = 1;
      goto LABEL_13;
    }
    v58 = 1;
    CSMirrorIntersect = ConvertRangesToSubnets(v12);
    v11 = CSMirrorIntersect;
    if ( CSMirrorIntersect < 0 )
    {
      v38 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v39 = 147;
LABEL_125:
        WPP_SF_d(
          *(_QWORD *)(v38 + 16),
          v39,
          WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
          (unsigned int)CSMirrorIntersect);
      }
      goto LABEL_126;
    }
  }
  v40 = v60;
  v41 = v59;
  if ( !*v60 )
    CDfwEngWriter::HelperGenerateUInt64FilterContextId(v59, v60);
  *((_QWORD *)a3 + 5) = *v40;
  *((_QWORD *)a3 + 20) = v40 + 6;
  v42 = 0;
  LODWORD(v61) = 0;
  if ( !v57 )
  {
LABEL_165:
    v10 = v9;
    if ( v11 < 0 )
      goto LABEL_10;
    v19 = v60;
    goto LABEL_167;
  }
  while ( 1 )
  {
    v43 = v55[v42];
    v44 = 0;
    *((_QWORD *)a3 + 18) = v43;
    v62 = 0;
    if ( v33 )
      break;
LABEL_154:
    v42 = (unsigned int)((_DWORD)v61 + 1);
    LODWORD(v61) = v42;
    if ( (unsigned int)v42 >= v57 )
      goto LABEL_165;
    v41 = v59;
  }
LABEL_131:
  v45 = 0;
  *((_DWORD *)a3 + 38) = *((_DWORD *)&v71 + v44);
  while ( 1 )
  {
    if ( !v64[v45] )
      goto LABEL_152;
    *((_DWORD *)a3 + 43) = -1;
    *((_DWORD *)a3 + 14) = 1;
    *((_DWORD *)a3 + 24) = 1;
    v46 = ((_DWORD)v45 != 0) + 1;
    *((_DWORD *)a3 + 15) = v46;
    *((_DWORD *)a3 + 25) = v46;
    v47 = *((unsigned int *)a2 + 66);
    if ( !(_DWORD)v47 )
    {
      if ( *((_DWORD *)a2 + 72) )
      {
        v49 = 0;
        *((_DWORD *)a3 + 34) = 0;
        if ( *((_DWORD *)a2 + 72) )
        {
          while ( 1 )
          {
            v50 = v65;
            *((_WORD *)a3 + 70) = *(_WORD *)(*((_QWORD *)a2 + 37) + 4 * v49);
            *((_WORD *)a3 + 71) = *(_WORD *)(*((_QWORD *)a2 + 37) + 4 * v49 + 2);
            CSMirrorIntersect = CDfwEngWriter::HelperGenerateCSMirrorIntersect(v41, a3, v50);
            v11 = CSMirrorIntersect;
            if ( CSMirrorIntersect < 0 )
              break;
            v41 = v59;
            v49 = (unsigned int)(v49 + 1);
            if ( (unsigned int)v49 >= *((_DWORD *)a2 + 72) )
              goto LABEL_152;
          }
          v38 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v39 = 149;
            goto LABEL_125;
          }
          goto LABEL_126;
        }
      }
      else
      {
        v48 = v65;
        *((_QWORD *)a3 + 17) = v47;
        CSMirrorIntersect = CDfwEngWriter::HelperGenerateCSMirrorIntersect(v41, a3, v48);
        v11 = CSMirrorIntersect;
        if ( CSMirrorIntersect < 0 )
        {
          v38 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v39 = 148;
            goto LABEL_125;
          }
          goto LABEL_126;
        }
      }
      goto LABEL_152;
    }
    v51 = 0;
    if ( *((_DWORD *)a2 + 72) )
      break;
    *((_DWORD *)a3 + 35) = 0;
    if ( *((_DWORD *)a2 + 66) )
    {
      while ( 1 )
      {
        v52 = v65;
        *((_WORD *)a3 + 68) = *(_WORD *)(*((_QWORD *)a2 + 34) + 4 * v51);
        *((_WORD *)a3 + 69) = *(_WORD *)(*((_QWORD *)a2 + 34) + 4 * v51 + 2);
        CSMirrorIntersect = CDfwEngWriter::HelperGenerateCSMirrorIntersect(v41, a3, v52);
        v11 = CSMirrorIntersect;
        if ( CSMirrorIntersect < 0 )
          break;
        v41 = v59;
        v51 = (unsigned int)(v51 + 1);
        if ( (unsigned int)v51 >= *((_DWORD *)a2 + 66) )
          goto LABEL_152;
      }
      v38 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v39 = 150;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
LABEL_152:
    v41 = v59;
    v45 = (unsigned int)(v45 + 1);
    if ( (unsigned int)v45 >= 2 )
    {
      v33 = v56;
      v44 = (unsigned int)(v62 + 1);
      v62 = v44;
      if ( (unsigned int)v44 < v56 )
        goto LABEL_131;
      goto LABEL_154;
    }
  }
  while ( 1 )
  {
    v53 = 0;
    *((_WORD *)a3 + 68) = *(_WORD *)(*((_QWORD *)a2 + 34) + 4 * v51);
    *((_WORD *)a3 + 69) = *(_WORD *)(*((_QWORD *)a2 + 34) + 4 * v51 + 2);
    if ( *((_DWORD *)a2 + 72) )
      break;
LABEL_151:
    v41 = v59;
    v51 = (unsigned int)(v51 + 1);
    if ( (unsigned int)v51 >= *((_DWORD *)a2 + 66) )
      goto LABEL_152;
  }
  while ( 1 )
  {
    v54 = v65;
    *((_WORD *)a3 + 70) = *(_WORD *)(*((_QWORD *)a2 + 37) + 4 * v53);
    *((_WORD *)a3 + 71) = *(_WORD *)(*((_QWORD *)a2 + 37) + 4 * v53 + 2);
    CSMirrorIntersect = CDfwEngWriter::HelperGenerateCSMirrorIntersect(v41, a3, v54);
    v11 = CSMirrorIntersect;
    if ( CSMirrorIntersect < 0 )
      break;
    v41 = v59;
    v53 = (unsigned int)(v53 + 1);
    if ( (unsigned int)v53 >= *((_DWORD *)a2 + 72) )
      goto LABEL_151;
  }
  v38 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v39 = 151;
    goto LABEL_125;
  }
LABEL_126:
  v10 = v9;
LABEL_10:
  v8 = 1;
LABEL_11:
  v16 = v55;
LABEL_12:
  v17 = (char *)a2 + 48;
LABEL_13:
  if ( v16 != &v73 )
    FwFree(v16);
  if ( v9 == 1 )
    FwFree(*((_QWORD *)a2 + 34));
  if ( v10 == 1 )
    FwFree(*((_QWORD *)a2 + 37));
  if ( v8 == 1 )
    FwPolioEmptyWFAddresses(v17);
  if ( v63 == 1 )
    FwPolioEmptyWFAddresses((char *)a2 + 120);
  FwPolioEmptyWFAddresses(v67);
  FwPolioEmptyWFAddresses(v68);
  FwPolioEmptyWFAddresses(v70);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800a9748  push    rbp
0x1800a974a  push    rbx
0x1800a974b  push    rsi
0x1800a974c  push    rdi
0x1800a974d  push    r12
0x1800a974f  push    r13
0x1800a9751  push    r14
0x1800a9753  push    r15
0x1800a9755  lea     rbp, [rsp-108h]
0x1800a975d  sub     rsp, 208h
0x1800a9764  mov     rax, cs:__security_cookie
0x1800a976b  xor     rax, rsp
0x1800a976e  mov     [rbp+140h+var_48], rax
0x1800a9775  mov     rax, [rbp+140h+arg_20]
0x1800a977c  mov     r14, r8
0x1800a977f  mov     [rsp+240h+var_1E0], rcx
0x1800a9784  mov     rdi, rdx
0x1800a9787  xor     ecx, ecx
0x1800a9789  mov     [rsp+240h+var_1D8], rax
0x1800a978e  xor     eax, eax
0x1800a9790  mov     [rbp+140h+var_1B0], ecx
0x1800a9793  mov     [rsp+240h+var_1F8], rcx
0x1800a9798  mov     r13d, ecx
0x1800a979b  mov     [rsp+240h+var_1D0], rcx
0x1800a97a0  mov     r12d, ecx
0x1800a97a3  lea     esi, [rcx+48h]
0x1800a97a6  mov     [rbp+140h+var_50], rcx
0x1800a97ad  mov     [rsp+240h+var_1EC], ecx
0x1800a97b1  mov     ebx, ecx
0x1800a97b3  mov     [rsp+240h+var_1C4], ecx
0x1800a97b7  mov     r8d, esi; Size
0x1800a97ba  xor     edx, edx; Val
0x1800a97bc  mov     [rbp+140h+var_1B8], r9
0x1800a97c0  lea     rcx, [rbp+140h+var_B0]; void *
0x1800a97c7  mov     [rbp+140h+var_60], rax
0x1800a97ce  mov     [rbp+140h+var_58], eax
0x1800a97d4  call    memset_0
0x1800a97d9  mov     r8d, esi; Size
0x1800a97dc  lea     rcx, [rbp+140h+var_100]; void *
0x1800a97e0  xor     edx, edx; Val
0x1800a97e2  call    memset_0
0x1800a97e7  mov     r8d, esi; Size
0x1800a97ea  lea     rcx, [rbp+140h+var_1A0]; void *
0x1800a97ee  xor     edx, edx; Val
0x1800a97f0  call    memset_0
0x1800a97f5  mov     r8d, esi; Size
0x1800a97f8  lea     rcx, [rbp+140h+var_150]; void *
0x1800a97fc  xor     edx, edx; Val
0x1800a97fe  call    memset_0
0x1800a9803  xor     eax, eax
0x1800a9805  lea     ecx, [rsi-47h]
0x1800a9808  mov     [rsp+240h+var_210], rax; __int64
0x1800a980d  lea     r8, [rbp+140h+var_1B0]
0x1800a9811  mov     dword ptr [rsp+240h+var_218], ecx; char
0x1800a9815  mov     r9d, ecx
0x1800a9818  lea     rcx, [rdi+30h]; struct _tag_FW_ADDRESSES *
0x1800a981c  mov     qword ptr [rbp+140h+var_1C0], rax
0x1800a9820  mov     edx, 7FFFFFFFh
0x1800a9825  mov     [rsp+240h+var_220], rax; __int64
0x1800a982a  call    ResolveAddresses
0x1800a982f  mov     esi, eax
0x1800a9831  xor     eax, eax
0x1800a9833  test    esi, esi
0x1800a9835  jns     short loc_1800A9875
0x1800a9837  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a983e  lea     rdx, WPP_GLOBAL_Control
0x1800a9845  cmp     rcx, rdx
0x1800a9848  jz      loc_1800A9943
0x1800a984e  test    byte ptr [rcx+1Ch], 1
0x1800a9852  jz      loc_1800A9943
0x1800a9858  mov     rcx, [rcx+10h]
0x1800a985c  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a9863  mov     edx, 83h
0x1800a9868  mov     r9d, esi
0x1800a986b  call    WPP_SF_d
0x1800a9870  jmp     loc_1800A9943
0x1800a9875  cmp     [rbp+140h+var_1B0], eax
0x1800a9878  jz      short loc_1800A98D4
0x1800a987a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9881  lea     rdx, WPP_GLOBAL_Control
0x1800a9888  cmp     rcx, rdx
0x1800a988b  jz      short loc_1800A98A8
0x1800a988d  test    byte ptr [rcx+1Ch], 4
0x1800a9891  jz      short loc_1800A98A8
0x1800a9893  mov     rcx, [rcx+10h]
0x1800a9897  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a989e  mov     edx, 84h
0x1800a98a3  call    WPP_SF_
0x1800a98a8  mov     r8, [rdi+18h]
0x1800a98ac  mov     r15d, 6
0x1800a98b2  mov     rdx, [rdi+10h]
0x1800a98b6  mov     r9d, r15d
0x1800a98b9  call    FwAuditLogEmptyResolution
0x1800a98be  mov     r14, [rsp+240h+var_1D8]
0x1800a98c3  mov     edx, r15d
0x1800a98c6  mov     rcx, r14
0x1800a98c9  call    cs:__imp_FwMetaDataAddEnforcementState
0x1800a98cf  jmp     loc_1800AA459
0x1800a98d4  mov     ecx, 1
0x1800a98d9  mov     [rsp+240h+var_210], rax; __int64
0x1800a98de  mov     dword ptr [rsp+240h+var_218], ecx; char
0x1800a98e2  lea     r13, [rdi+78h]
0x1800a98e6  mov     [rsp+240h+var_200], ecx
0x1800a98ea  lea     r8, [rbp+140h+var_1B0]
0x1800a98ee  mov     r9d, ecx
0x1800a98f1  mov     [rsp+240h+var_220], rax; __int64
0x1800a98f6  mov     rcx, r13; struct _tag_FW_ADDRESSES *
0x1800a98f9  mov     edx, 7FFFFFFFh
0x1800a98fe  call    ResolveAddresses
0x1800a9903  mov     esi, eax
0x1800a9905  test    eax, eax
0x1800a9907  jns     loc_1800A99E9
0x1800a990d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9914  lea     rdx, WPP_GLOBAL_Control
0x1800a991b  cmp     rcx, rdx
0x1800a991e  jz      short loc_1800A993E
0x1800a9920  test    byte ptr [rcx+1Ch], 1
0x1800a9924  jz      short loc_1800A993E
0x1800a9926  mov     edx, 85h
0x1800a992b  mov     rcx, [rcx+10h]
0x1800a992f  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a9936  mov     r9d, eax
0x1800a9939  call    WPP_SF_d
0x1800a993e  mov     r13d, [rsp+240h+var_200]
0x1800a9943  mov     rcx, [rsp+240h+var_1F8]
0x1800a9948  lea     r15, [rdi+30h]
0x1800a994c  lea     rax, [rbp+140h+var_50]
0x1800a9953  cmp     rcx, rax
0x1800a9956  jz      short loc_1800A995E
0x1800a9958  call    cs:__imp_FwFree
0x1800a995e  cmp     r12d, 1
0x1800a9962  jnz     short loc_1800A9971
0x1800a9964  mov     rcx, [rdi+110h]
0x1800a996b  call    cs:__imp_FwFree
0x1800a9971  cmp     ebx, 1
0x1800a9974  jnz     short loc_1800A9983
0x1800a9976  mov     rcx, [rdi+128h]
0x1800a997d  call    cs:__imp_FwFree
0x1800a9983  cmp     r13d, 1
0x1800a9987  jnz     short loc_1800A9992
0x1800a9989  mov     rcx, r15
0x1800a998c  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800a9992  cmp     [rsp+240h+var_1C4], 1
0x1800a9997  jnz     short loc_1800A99A3
0x1800a9999  lea     rcx, [rdi+78h]
0x1800a999d  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800a99a3  lea     rcx, [rbp+140h+var_1A0]
0x1800a99a7  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800a99ad  lea     rcx, [rbp+140h+var_150]
0x1800a99b1  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800a99b7  lea     rcx, [rbp+140h+var_B0]
0x1800a99be  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800a99c4  mov     eax, esi
0x1800a99c6  mov     rcx, [rbp+140h+var_48]
0x1800a99cd  xor     rcx, rsp; StackCookie
0x1800a99d0  call    __security_check_cookie
0x1800a99d5  add     rsp, 208h
0x1800a99dc  pop     r15
0x1800a99de  pop     r14
0x1800a99e0  pop     r13
0x1800a99e2  pop     r12
0x1800a99e4  pop     rdi
0x1800a99e5  pop     rsi
0x1800a99e6  pop     rbx
0x1800a99e7  pop     rbp
0x1800a99e8  retn
0x1800a99e9  cmp     [rbp+140h+var_1B0], ebx
0x1800a99ec  jz      short loc_1800A9A48
0x1800a99ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a99f5  lea     rdx, WPP_GLOBAL_Control
0x1800a99fc  cmp     rcx, rdx
0x1800a99ff  jz      short loc_1800A9A1C
0x1800a9a01  test    byte ptr [rcx+1Ch], 4
0x1800a9a05  jz      short loc_1800A9A1C
0x1800a9a07  mov     rcx, [rcx+10h]
0x1800a9a0b  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a9a12  mov     edx, 86h
0x1800a9a17  call    WPP_SF_
0x1800a9a1c  mov     r14d, 7
0x1800a9a22  mov     r8, [rdi+18h]
0x1800a9a26  mov     r9d, r14d
0x1800a9a29  mov     rdx, [rdi+10h]
0x1800a9a2d  call    FwAuditLogEmptyResolution
0x1800a9a32  mov     edx, r14d
0x1800a9a35  mov     r14, [rsp+240h+var_1D8]
0x1800a9a3a  mov     rcx, r14
0x1800a9a3d  call    cs:__imp_FwMetaDataAddEnforcementState
0x1800a9a43  jmp     loc_1800AA454
0x1800a9a48  mov     rcx, rdi
0x1800a9a4b  mov     [rsp+240h+var_1C4], 1
0x1800a9a53  call    IsCSRuleTunnelMode
0x1800a9a58  test    eax, eax
0x1800a9a5a  jnz     loc_1800A9C4E
0x1800a9a60  test    byte ptr [rdi+154h], 2
0x1800a9a67  jnz     loc_1800A9C4E
0x1800a9a6d  lea     rcx, [rdi+30h]
0x1800a9a71  call    cs:__imp_IsAddressesEmpty
0x1800a9a77  mov     rcx, r13
0x1800a9a7a  mov     r15d, eax
0x1800a9a7d  call    cs:__imp_IsAddressesEmpty
0x1800a9a83  mov     r13d, eax
0x1800a9a86  test    r15d, r15d
0x1800a9a89  jz      short loc_1800A9A93
0x1800a9a8b  test    eax, eax
0x1800a9a8d  jnz     loc_1800A9C4A
0x1800a9a93  lea     r8, [rbp+140h+var_B0]
0x1800a9a9a  lea     rdx, [rbp+140h+var_1B0]
0x1800a9a9e  call    ResolveLocalAddresses
0x1800a9aa3  mov     esi, eax
0x1800a9aa5  test    eax, eax
0x1800a9aa7  jns     short loc_1800A9AD4
0x1800a9aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9ab0  lea     rdx, WPP_GLOBAL_Control
0x1800a9ab7  cmp     rcx, rdx
0x1800a9aba  jz      loc_1800A993E
0x1800a9ac0  test    byte ptr [rcx+1Ch], 1
0x1800a9ac4  jz      loc_1800A993E
0x1800a9aca  mov     edx, 87h
0x1800a9acf  jmp     loc_1800A992B
0x1800a9ad4  cmp     [rbp+140h+var_1B0], ebx
0x1800a9ad7  jz      short loc_1800A9AE3
0x1800a9ad9  mov     edx, 13h
0x1800a9ade  jmp     loc_1800A9A35
0x1800a9ae3  lea     rcx, [rbp+140h+var_B0]
0x1800a9aea  call    cs:__imp_FwSortAddresses
0x1800a9af0  test    r15d, r15d
0x1800a9af3  jnz     loc_1800A9B9B
0x1800a9af9  lea     rcx, [rdi+30h]
0x1800a9afd  call    cs:__imp_FwSortAddresses
0x1800a9b03  lea     rdx, [rbp+140h+var_100]
0x1800a9b07  lea     rcx, [rbp+140h+var_B0]
0x1800a9b0e  call    cs:__imp_FwPolioCopyWFAddressesContents
0x1800a9b14  mov     esi, eax
0x1800a9b16  test    eax, eax
0x1800a9b18  jns     short loc_1800A9B45
0x1800a9b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9b21  lea     rdx, WPP_GLOBAL_Control
0x1800a9b28  cmp     rcx, rdx
0x1800a9b2b  jz      loc_1800A993E
0x1800a9b31  test    byte ptr [rcx+1Ch], 1
0x1800a9b35  jz      loc_1800A993E
0x1800a9b3b  mov     edx, 88h
0x1800a9b40  jmp     loc_1800A992B
0x1800a9b45  lea     rdx, [rbp+140h+var_1A0]
0x1800a9b49  lea     rcx, [rdi+30h]
0x1800a9b4d  call    cs:__imp_FwPolioCopyWFAddressesContents
0x1800a9b53  mov     esi, eax
0x1800a9b55  test    eax, eax
0x1800a9b57  jns     short loc_1800A9B84
0x1800a9b59  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9b60  lea     rdx, WPP_GLOBAL_Control
0x1800a9b67  cmp     rcx, rdx
0x1800a9b6a  jz      loc_1800A993E
0x1800a9b70  test    byte ptr [rcx+1Ch], 1
0x1800a9b74  jz      loc_1800A993E
0x1800a9b7a  mov     edx, 89h
0x1800a9b7f  jmp     loc_1800A992B
0x1800a9b84  lea     rdx, [rbp+140h+var_100]
0x1800a9b88  lea     rcx, [rbp+140h+var_1A0]
0x1800a9b8c  call    FWAddressAndIPAddressIntersect
0x1800a9b91  lea     rcx, [rbp+140h+var_100]
0x1800a9b95  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800a9b9b  test    r13d, r13d
0x1800a9b9e  jnz     loc_1800A9C4A
0x1800a9ba4  lea     r13, [rdi+78h]
0x1800a9ba8  mov     rcx, r13
0x1800a9bab  call    cs:__imp_FwSortAddresses
0x1800a9bb1  lea     rdx, [rbp+140h+var_100]
0x1800a9bb5  lea     rcx, [rbp+140h+var_B0]
0x1800a9bbc  call    cs:__imp_FwPolioCopyWFAddressesContents
0x1800a9bc2  mov     esi, eax
0x1800a9bc4  test    eax, eax
0x1800a9bc6  jns     short loc_1800A9BF3
0x1800a9bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9bcf  lea     rdx, WPP_GLOBAL_Control
0x1800a9bd6  cmp     rcx, rdx
0x1800a9bd9  jz      loc_1800A993E
0x1800a9bdf  test    byte ptr [rcx+1Ch], 1
0x1800a9be3  jz      loc_1800A993E
0x1800a9be9  mov     edx, 8Ah
0x1800a9bee  jmp     loc_1800A992B
0x1800a9bf3  lea     rdx, [rbp+140h+var_150]
0x1800a9bf7  mov     rcx, r13
0x1800a9bfa  call    cs:__imp_FwPolioCopyWFAddressesContents
0x1800a9c00  mov     esi, eax
0x1800a9c02  test    eax, eax
0x1800a9c04  jns     short loc_1800A9C31
0x1800a9c06  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9c0d  lea     rdx, WPP_GLOBAL_Control
0x1800a9c14  cmp     rcx, rdx
0x1800a9c17  jz      loc_1800A993E
0x1800a9c1d  test    byte ptr [rcx+1Ch], 1
0x1800a9c21  jz      loc_1800A993E
0x1800a9c27  mov     edx, 8Bh
0x1800a9c2c  jmp     loc_1800A992B
0x1800a9c31  lea     rdx, [rbp+140h+var_100]
0x1800a9c35  lea     rcx, [rbp+140h+var_150]
0x1800a9c39  call    FWAddressAndIPAddressIntersect
0x1800a9c3e  lea     rcx, [rbp+140h+var_100]
0x1800a9c42  call    cs:__imp_FwPolioEmptyWFAddresses
  ... truncated ...
```
