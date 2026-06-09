# PolicyManager::GetManagedPolicyInternal(ushort const *,NgcPolicy::NgcPolicy *,PolicyManager::PolicyType *)

- ea: `0x180020320`
- end: `0x1800213be`
- name: `?GetManagedPolicyInternal@PolicyManager@@YAJPEBGPEAVNgcPolicy@2@PEAW4PolicyType@1@@Z`
- size: `4254`
- prototype: `__int64 __fastcall(PolicyManager *__hidden this, const unsigned __int16 *, struct NgcPolicy *, enum PolicyManager::PolicyType *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x1800201f8`

## callees

- `0x180006780`
- `0x180008108`
- `0x18000edb0`
- `0x1800158e0`
- `0x18001ee80`
- `0x180020014`
- `0x180020320`
- `0x180023714`
- `0x180023e1c`
- `0x180024014`
- `0x18002cb1c`
- `0x18002cbf8`
- `0x18002dff0`
- `0x18002e02c`
- `0x18002f150`
- `0x18002f7db`
- `0x18003ddb8`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800207bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002090c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020a2e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020b5c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020edc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021068`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021163`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021370`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800207bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002090c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020a2e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020b5c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020edc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021068`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021163`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021370`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800203c8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800203ef`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020968`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020f41`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800211d6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180021299`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800203c8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800203ef`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020968`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020f41`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800211d6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180021299`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PolicyManager::GetManagedPolicyInternal(
        PolicyManager *this,
        const unsigned __int16 *a2,
        struct NgcPolicy *a3,
        enum PolicyManager::PolicyType *a4)
{
  unsigned __int64 v4; // rdi
  bool v5; // zf
  int v6; // eax
  void **v7; // rcx
  PolicyManager *v8; // rdx
  GUID *v9; // r9
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rcx
  _OWORD *v15; // rax
  int DefaultPolicy; // ebx
  unsigned int v17; // r12d
  unsigned __int64 v18; // rdx
  void *v19; // rcx
  void *v20; // rbx
  unsigned __int8 v21; // r13
  _WORD *v22; // r14
  __int64 v23; // r15
  size_t v24; // rdi
  _OWORD *p_EventDescriptor; // rdi
  char v26; // si
  size_t v27; // rcx
  void *v28; // rax
  _QWORD *v29; // rsi
  size_t v30; // rdi
  unsigned __int64 v31; // rdx
  void *v32; // rcx
  unsigned __int64 v33; // rdx
  void *Ptr; // rcx
  unsigned __int64 v35; // rdx
  void *v36; // rcx
  PolicyManager *v37; // rcx
  void **v38; // rdx
  _OWORD *v39; // rax
  struct NgcPolicy *v40; // r9
  unsigned int v42; // [rsp+30h] [rbp-D0h] BYREF
  int JoinInfo; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v44; // [rsp+38h] [rbp-C8h] BYREF
  int v45; // [rsp+3Ch] [rbp-C4h] BYREF
  bool v46[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  PolicyManager *v48; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v49; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v50[44]; // [rsp+68h] [rbp-98h]
  int v51; // [rsp+98h] [rbp-68h] BYREF
  int v52; // [rsp+9Ch] [rbp-64h] BYREF
  int v53; // [rsp+A0h] [rbp-60h] BYREF
  int v54; // [rsp+A4h] [rbp-5Ch] BYREF
  int v55; // [rsp+A8h] [rbp-58h] BYREF
  int v56; // [rsp+ACh] [rbp-54h] BYREF
  int v57; // [rsp+B0h] [rbp-50h] BYREF
  int v58; // [rsp+B4h] [rbp-4Ch] BYREF
  int v59; // [rsp+B8h] [rbp-48h] BYREF
  int v60; // [rsp+BCh] [rbp-44h] BYREF
  int v61; // [rsp+C0h] [rbp-40h] BYREF
  int v62; // [rsp+C4h] [rbp-3Ch] BYREF
  int v63; // [rsp+C8h] [rbp-38h] BYREF
  int v64; // [rsp+CCh] [rbp-34h] BYREF
  int v65; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v66[6]; // [rsp+D8h] [rbp-28h] BYREF
  __int16 v67; // [rsp+108h] [rbp+8h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v69; // [rsp+120h] [rbp+20h]
  unsigned __int64 v70; // [rsp+128h] [rbp+28h]
  int v71; // [rsp+130h] [rbp+30h] BYREF
  char v72; // [rsp+134h] [rbp+34h]
  GUID ActivityId; // [rsp+138h] [rbp+38h] BYREF
  GUID v74; // [rsp+148h] [rbp+48h] BYREF
  void *v75[2]; // [rsp+158h] [rbp+58h] BYREF
  __int128 v76; // [rsp+168h] [rbp+68h]
  struct _EVENT_DATA_DESCRIPTOR v77; // [rsp+178h] [rbp+78h] BYREF
  char *v78; // [rsp+188h] [rbp+88h]
  unsigned __int64 v79; // [rsp+190h] [rbp+90h]
  unsigned int *v80; // [rsp+198h] [rbp+98h]
  __int64 v81; // [rsp+1A0h] [rbp+A0h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+1B0h] [rbp+B0h] BYREF
  int *v83; // [rsp+1C0h] [rbp+C0h]
  int v84; // [rsp+1C8h] [rbp+C8h]
  int v85; // [rsp+1CCh] [rbp+CCh]
  unsigned int *v86; // [rsp+1D0h] [rbp+D0h]
  __int64 v87; // [rsp+1D8h] [rbp+D8h]
  void **p_Block; // [rsp+1E0h] [rbp+E0h]
  __int64 v89; // [rsp+1E8h] [rbp+E8h]
  PolicyManager *v90; // [rsp+1F0h] [rbp+F0h]
  int v91; // [rsp+1F8h] [rbp+F8h]
  int v92; // [rsp+1FCh] [rbp+FCh]
  void **v93; // [rsp+200h] [rbp+100h]
  int v94; // [rsp+208h] [rbp+108h]
  int v95; // [rsp+20Ch] [rbp+10Ch]
  int *v96; // [rsp+210h] [rbp+110h]
  __int64 v97; // [rsp+218h] [rbp+118h]
  int *v98; // [rsp+220h] [rbp+120h]
  __int64 v99; // [rsp+228h] [rbp+128h]
  int *v100; // [rsp+230h] [rbp+130h]
  __int64 v101; // [rsp+238h] [rbp+138h]
  int *v102; // [rsp+240h] [rbp+140h]
  __int64 v103; // [rsp+248h] [rbp+148h]
  int *v104; // [rsp+250h] [rbp+150h]
  __int64 v105; // [rsp+258h] [rbp+158h]
  int *v106; // [rsp+260h] [rbp+160h]
  __int64 v107; // [rsp+268h] [rbp+168h]
  int *v108; // [rsp+270h] [rbp+170h]
  __int64 v109; // [rsp+278h] [rbp+178h]
  int *v110; // [rsp+280h] [rbp+180h]
  __int64 v111; // [rsp+288h] [rbp+188h]
  int *v112; // [rsp+290h] [rbp+190h]
  __int64 v113; // [rsp+298h] [rbp+198h]
  int *v114; // [rsp+2A0h] [rbp+1A0h]
  __int64 v115; // [rsp+2A8h] [rbp+1A8h]
  int *v116; // [rsp+2B0h] [rbp+1B0h]
  __int64 v117; // [rsp+2B8h] [rbp+1B8h]
  int *v118; // [rsp+2C0h] [rbp+1C0h]
  __int64 v119; // [rsp+2C8h] [rbp+1C8h]
  int *v120; // [rsp+2D0h] [rbp+1D0h]
  __int64 v121; // [rsp+2D8h] [rbp+1D8h]
  int *v122; // [rsp+2E0h] [rbp+1E0h]
  __int64 v123; // [rsp+2E8h] [rbp+1E8h]
  int *v124; // [rsp+2F0h] [rbp+1F0h]
  __int64 v125; // [rsp+2F8h] [rbp+1F8h]

  v48 = this;
  *(_QWORD *)v46 = a2;
  v42 = 0;
  JoinInfo = 0;
  *(_OWORD *)v75 = 0;
  *(_QWORD *)&v76 = 0;
  *((_QWORD *)&v76 + 1) = 7;
  LOWORD(v75[0]) = 0;
  v45 = 0;
  v71 = 0;
  v72 = 0;
  if ( (unsigned int)dword_18006E000 > 5
    && (this = (PolicyManager *)qword_18006E018, (qword_18006E010 & 0x400000000000LL) != 0)
    && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
  {
    EventActivityIdControl(3u, &ActivityId);
    v74 = ActivityId;
    EventActivityIdControl(4u, &v74);
    v72 = 1;
  }
  else
  {
    ActivityId = 0;
  }
  v71 = 1;
  v4 = -1;
  if ( (unsigned int)dword_18006E000 > 5 )
  {
    this = (PolicyManager *)qword_18006E018;
    if ( (qword_18006E010 & 0x400000000000LL) != 0 && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
    {
      v51 = *(_DWORD *)(*(_QWORD *)v46 + 56LL);
      v52 = *(_DWORD *)(*(_QWORD *)v46 + 52LL);
      v53 = *(_DWORD *)(*(_QWORD *)v46 + 48LL);
      v54 = *(_DWORD *)(*(_QWORD *)v46 + 44LL);
      v55 = *(_DWORD *)(*(_QWORD *)v46 + 40LL);
      v56 = *(_DWORD *)(*(_QWORD *)v46 + 36LL);
      v57 = *(_DWORD *)(*(_QWORD *)v46 + 32LL);
      v58 = *(_DWORD *)(*(_QWORD *)v46 + 28LL);
      v59 = *(_DWORD *)(*(_QWORD *)v46 + 24LL);
      v60 = *(_DWORD *)(*(_QWORD *)v46 + 20LL);
      v61 = *(_DWORD *)(*(_QWORD *)v46 + 12LL);
      v62 = *(_DWORD *)(*(_QWORD *)v46 + 8LL);
      v63 = *(_DWORD *)(*(_QWORD *)v46 + 4LL);
      if ( !(unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
        || !(unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
        || !(unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
        || !(unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
        || !(unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
        || !(unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
        || (v5 = (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent() == 0,
            v6 = 1,
            v5) )
      {
        v6 = 0;
      }
      v64 = v6;
      v65 = v45;
      v7 = v75;
      if ( *((_QWORD *)&v76 + 1) > 7u )
        v7 = (void **)v75[0];
      v8 = v48;
      LODWORD(Block) = v48 != 0;
      v44 = JoinInfo;
      if ( v72 && (v74.Data1 || *(_DWORD *)&v74.Data2 || *(_DWORD *)v74.Data4 || *(_DWORD *)&v74.Data4[4]) )
        v9 = &v74;
      else
        v9 = 0;
      v124 = &v51;
      v125 = 4;
      v122 = &v52;
      v123 = 4;
      v120 = &v53;
      v121 = 4;
      v118 = &v54;
      v119 = 4;
      v116 = &v55;
      v117 = 4;
      v114 = &v56;
      v115 = 4;
      v112 = &v57;
      v113 = 4;
      v110 = &v58;
      v111 = 4;
      v108 = &v59;
      v109 = 4;
      v106 = &v60;
      v107 = 4;
      v104 = &v61;
      v105 = 4;
      v102 = &v62;
      v103 = 4;
      v100 = &v63;
      v101 = 4;
      v98 = &v64;
      v99 = 4;
      v96 = &v65;
      v97 = 4;
      if ( v7 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *((_WORD *)v7 + v10) );
        v11 = 2 * v10 + 2;
      }
      else
      {
        v7 = (void **)&LocaleName;
        v11 = 2;
      }
      v93 = v7;
      v94 = v11;
      v95 = 0;
      if ( v48 )
      {
        v12 = -1;
        do
          ++v12;
        while ( *((_WORD *)v48 + v12) );
        v13 = 2 * v12 + 2;
      }
      else
      {
        v8 = (PolicyManager *)&LocaleName;
        v13 = 2;
      }
      v90 = v8;
      v91 = v13;
      v92 = 0;
      p_Block = &Block;
      v89 = 4;
      v86 = &v44;
      v87 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 261;
      EventDescriptor.Keyword = 0x400000000000LL;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      UserData.Reserved = 2;
      v83 = &dword_18006181C;
      v84 = 364;
      v85 = 1;
      v42 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, v9, 0x15u, &UserData);
    }
  }
  v66[0] = &v71;
  v66[1] = &JoinInfo;
  v66[2] = &v48;
  v66[3] = v75;
  v66[4] = &v45;
  v66[5] = v46;
  v67 = 256;
  LOBYTE(v49) = 0;
  DWORD1(v49) = 1;
  *((_QWORD *)&v49 + 1) = 1;
  v50[0] = 0;
  *(_QWORD *)&v50[4] = 0x7F00000008LL;
  *(_OWORD *)&v50[12] = 0;
  *(_DWORD *)&v50[28] = 2;
  *(_QWORD *)&v50[32] = 1;
  *(_DWORD *)&v50[40] = 0;
  JoinInfo = PolicyManager::ReadGroupPolicy(this, a2, &v49);
  if ( JoinInfo >= 0 )
  {
    if ( (unsigned int)dword_18006E000 > 4 )
    {
      v42 = JoinInfo;
      v80 = &v42;
      v81 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 0;
      v77.Ptr = (ULONGLONG)off_18006E008;
      v77.Size = *(unsigned __int16 *)off_18006E008;
      v77.Reserved = 2;
      v78 = byte_1800617EB;
      v79 = 0x100000025LL;
      v44 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v77);
    }
    v45 = 1;
    v15 = *(_OWORD **)v46;
    **(_OWORD **)v46 = v49;
    v15[1] = *(_OWORD *)v50;
    v15[2] = *(_OWORD *)&v50[16];
    *(_OWORD *)((char *)v15 + 44) = *(_OWORD *)&v50[28];
    DefaultPolicy = JoinInfo;
LABEL_41:
    wil::details::ScopeExitFnGuard__lambda_dd3f83e45279d804243b81ffa37ccc19___::operator()(v66);
    if ( v71 != 1 )
      goto LABEL_49;
    if ( v72 )
      EventActivityIdControl(4u, &v74);
    v71 = 2;
    if ( (unsigned int)dword_18006E000 <= 5
      || (qword_18006E010 & 0x400000000000LL) == 0
      || (qword_18006E018 & 0x400000000000LL) != qword_18006E018 )
    {
      goto LABEL_49;
    }
    EventDescriptor.Keyword = 0x400000000000LL;
    v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_48:
    *(_DWORD *)&EventDescriptor.Level = 517;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    v77.Ptr = (ULONGLONG)off_18006E008;
    v77.Size = *(unsigned __int16 *)off_18006E008;
    v77.Reserved = 2;
    v78 = (char *)&dword_18005E36C;
    v79 = 0x100000020LL;
    v42 = v17;
    EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &v77);
LABEL_49:
    v71 = 3;
    if ( *((_QWORD *)&v76 + 1) > 7u )
    {
      v18 = 2LL * *((_QWORD *)&v76 + 1) + 2;
      if ( v18 < 0x1000 )
      {
        operator delete(v75[0], v18);
      }
      else
      {
        v19 = (void *)*((_QWORD *)v75[0] - 1);
        if ( (unsigned __int64)((char *)v75[0] - (char *)v19 - 8) > 0x1F )
          __fastfail(5u);
        operator delete(v19, 2LL * *((_QWORD *)&v76 + 1) + 41);
      }
    }
    return (unsigned int)DefaultPolicy;
  }
  Block = 0;
  JoinInfo = DsrGetJoinInfo(v14, &Block);
  if ( JoinInfo < 0 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v42 = JoinInfo;
      v80 = &v42;
      v81 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      v77.Ptr = (ULONGLONG)off_18006E008;
      v77.Size = *(unsigned __int16 *)off_18006E008;
      v77.Reserved = 2;
      v78 = byte_1800617C5;
      v79 = 0x10000001ALL;
      v44 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v77);
    }
    DefaultPolicy = JoinInfo;
    if ( Block )
      DsrFreeJoinInfo(Block);
    goto LABEL_41;
  }
  v20 = Block;
  if ( Block && *(_DWORD *)Block == 1 )
  {
    v21 = 1;
    v22 = (_WORD *)*((_QWORD *)Block + 4);
    if ( v22 )
    {
      EventDescriptor = 0;
      do
        ++v4;
      while ( v22[v4] );
      v23 = 0x7FFFFFFFFFFFFFFELL;
      if ( v4 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( v4 <= 7 )
      {
        v69 = v4;
        v70 = 7;
        v24 = 2 * v4;
        memcpy_0(&EventDescriptor, v22, v24);
        *(USHORT *)((char *)&EventDescriptor.Id + v24) = 0;
        p_EventDescriptor = &EventDescriptor;
        v26 = 1;
        goto LABEL_82;
      }
      if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v23 = v4 | 7;
        if ( (v4 | 7) < 0xA )
          v23 = 10;
        if ( (unsigned __int64)(v23 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          goto LABEL_151;
        v27 = 2 * (v23 + 1);
        if ( !v27 )
        {
          v29 = 0;
          goto LABEL_79;
        }
      }
      else
      {
        v27 = -2;
      }
      if ( v27 >= 0x1000 )
      {
        if ( v27 + 39 >= v27 )
        {
          v28 = operator new(v27 + 39);
          if ( !v28 )
            goto LABEL_100;
          v29 = (_QWORD *)(((unsigned __int64)v28 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v29 - 1) = v28;
          goto LABEL_79;
        }
LABEL_151:
        std::_Throw_bad_array_new_length();
      }
      v29 = operator new(v27);
LABEL_79:
      *(_QWORD *)&EventDescriptor.Id = v29;
      v69 = v4;
      v70 = v23;
      v30 = 2 * v4;
      memcpy_0(v29, v22, v30);
      *(_WORD *)((char *)v29 + v30) = 0;
      p_EventDescriptor = &EventDescriptor;
      v26 = 1;
      goto LABEL_82;
    }
  }
  else
  {
    v21 = 0;
  }
  v77 = 0;
  v78 = 0;
  v79 = 7;
  LOWORD(v77.Ptr) = 0;
  p_EventDescriptor = &v77;
  v26 = 2;
LABEL_82:
  if ( *((_QWORD *)&v76 + 1) > 7u )
  {
    v31 = 2LL * *((_QWORD *)&v76 + 1) + 2;
    if ( v31 < 0x1000 )
    {
      v32 = v75[0];
    }
    else
    {
      v32 = (void *)*((_QWORD *)v75[0] - 1);
      if ( (unsigned __int64)((char *)v75[0] - (char *)v32 - 8) > 0x1F )
        goto LABEL_100;
      v31 = 2LL * *((_QWORD *)&v76 + 1) + 41;
    }
    operator delete(v32, v31);
  }
  *(_OWORD *)v75 = *p_EventDescriptor;
  v76 = p_EventDescriptor[1];
  *((_QWORD *)p_EventDescriptor + 2) = 0;
  *((_QWORD *)p_EventDescriptor + 3) = 7;
  *(_WORD *)p_EventDescriptor = 0;
  if ( (v26 & 2) != 0 )
  {
    v26 &= ~2u;
    if ( v79 > 7 )
    {
      v33 = 2 * v79 + 2;
      if ( v33 < 0x1000 )
      {
        Ptr = (void *)v77.Ptr;
      }
      else
      {
        Ptr = *(void **)(v77.Ptr - 8);
        if ( v77.Ptr - (unsigned __int64)Ptr - 8 > 0x1F )
          goto LABEL_100;
        v33 = 2 * v79 + 41;
      }
      operator delete(Ptr, v33);
    }
  }
  if ( (v26 & 1) != 0 && v70 > 7 )
  {
    v35 = 2 * v70 + 2;
    if ( v35 < 0x1000 )
    {
      v36 = *(void **)&EventDescriptor.Id;
      goto LABEL_102;
    }
    v36 = *(void **)(*(_QWORD *)&EventDescriptor.Id - 8LL);
    if ( (unsigned __int64)(*(_QWORD *)&EventDescriptor.Id - (_QWORD)v36 - 8LL) <= 0x1F )
    {
      v35 = 2 * v70 + 41;
LABEL_102:
      operator delete(v36, v35);
      goto LABEL_103;
    }
LABEL_100:
    __fastfail(5u);
  }
LABEL_103:
  if ( v20 )
    DsrFreeJoinInfo(v20);
  v37 = v48;
  if ( v48 )
  {
    if ( (_QWORD)v76 )
    {
      v38 = v75;
      if ( *((_QWORD *)&v76 + 1) > 7u )
        v38 = (void **)v75[0];
      JoinInfo = PolicyManager::ReadPassportCspPolicy(v48, v38, &v49);
      if ( JoinInfo >= 0 )
      {
        if ( (unsigned int)dword_18006E000 > 4 )
        {
          v42 = JoinInfo;
          v80 = &v42;
          v81 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 4;
          EventDescriptor.Keyword = 0;
          v77.Ptr = (ULONGLONG)off_18006E008;
          v77.Size = *(unsigned __int16 *)off_18006E008;
          v77.Reserved = 2;
          v78 = (char *)&dword_180061794;
          v79 = 0x100000025LL;
          v44 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v77);
        }
        v45 = 2;
LABEL_113:
        v39 = *(_OWORD **)v46;
        **(_OWORD **)v46 = v49;
        v39[1] = *(_OWORD *)v50;
        v39[2] = *(_OWORD *)&v50[16];
        *(_OWORD *)((char *)v39 + 44) = *(_OWORD *)&v50[28];
        DefaultPolicy = JoinInfo;
        wil::details::ScopeExitFnGuard__lambda_dd3f83e45279d804243b81ffa37ccc19___::operator()(v66);
        if ( v71 != 1 )
          goto LABEL_49;
        if ( v72 )
          EventActivityIdControl(4u, &v74);
        v71 = 2;
        if ( (unsigned int)dword_18006E000 <= 5
          || (qword_18006E010 & 0x400000000000LL) == 0
          || (qword_18006E018 & 0x400000000000LL) != qword_18006E018 )
        {
          goto LABEL_49;
        }
        EventDescriptor.Keyword = 0x400000000000LL;
        v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        goto LABEL_48;
      }
    }
    else
    {
      JoinInfo = PolicyManager::BuildMergedPassportCspPolicy(v48, &v49);
      if ( JoinInfo >= 0 )
      {
        if ( (unsigned int)dword_18006E000 > 4 )
        {
          v42 = JoinInfo;
          v80 = &v42;
          v81 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 4;
          EventDescriptor.Keyword = 0;
          v77.Ptr = (ULONGLONG)off_18006E008;
          v77.Size = *(unsigned __int16 *)off_18006E008;
          v77.Reserved = 2;
          v78 = byte_18006175D;
          v79 = 0x10000002BLL;
          v44 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v77);
        }
        v45 = 3;
        goto LABEL_113;
      }
    }
    v37 = v48;
  }
  JoinInfo = PolicyManager::ReadDeviceLockPolicy(v37);
  if ( JoinInfo >= 0 )
  {
    if ( (unsigned int)dword_18006E000 > 4 )
    {
      v42 = JoinInfo;
      v80 = &v42;
      v81 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 0;
      v77.Ptr = (ULONGLONG)off_18006E008;
      v77.Size = *(unsigned __int16 *)off_18006E008;
      v77.Reserved = 2;
      v78 = &byte_180061727;
      v79 = 0x10000002ALL;
      v44 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v77);
    }
    v45 = 4;
    goto LABEL_113;
  }
  v45 = 5;
  DefaultPolicy = PolicyManager::GetDefaultPolicy(v48, (const unsigned __int16 *)v21, v46[0], v40);
  JoinInfo = DefaultPolicy;
  if ( DefaultPolicy < 0 )
  {
    wil::details::ScopeExitFnGuard__lambda_dd3f83e45279d804243b81ffa37ccc19___::operator()(v66);
    if ( v71 != 1 )
      goto LABEL_49;
    if ( v72 )
      EventActivityIdControl(4u, &v74);
    v71 = 2;
    if ( (unsigned int)dword_18006E000 <= 5
      || (qword_18006E010 & 0x400000000000LL) == 0
      || (qword_18006E018 & 0x400000000000LL) != qword_18006E018 )
    {
      goto LABEL_49;
    }
    EventDescriptor.Keyword = 0x400000000000LL;
    v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    goto LABEL_48;
  }
  if ( (unsigned int)dword_18006E000 > 4 )
  {
    v42 = JoinInfo;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18006E000,
      (unsigned int)&word_1800616EE,
      0,
      0,
      (__int64)&v42);
  }
  DefaultPolicy = JoinInfo;
  wil::details::ScopeExitFnGuard__lambda_dd3f83e45279d804243b81ffa37ccc19___::operator()(v66);
  if ( v71 == 1 )
  {
    if ( v72 )
      EventActivityIdControl(4u, &v74);
    v71 = 2;
    if ( (unsigned int)dword_18006E000 > 5
      && (qword_18006E010 & 0x400000000000LL) != 0
      && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
    {
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 517;
      EventDescriptor.Keyword = 0x400000000000LL;
      v77.Ptr = (ULONGLONG)off_18006E008;
      v77.Size = *(unsigned __int16 *)off_18006E008;
      v77.Reserved = 2;
      v78 = (char *)&dword_18005E36C;
      v79 = 0x100000020LL;
      v42 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &v77);
    }
  }
  v71 = 3;
  std::wstring::~wstring(v75);
  return (unsigned int)DefaultPolicy;
}

```

## disassembly

```asm
0x180020320  mov     [rsp-8+arg_10], rbx
0x180020325  push    rbp
0x180020326  push    rsi
0x180020327  push    rdi
0x180020328  push    r12
0x18002032a  push    r13
0x18002032c  push    r14
0x18002032e  push    r15
0x180020330  lea     rbp, [rsp-210h]
0x180020338  sub     rsp, 310h
0x18002033f  mov     rax, cs:__security_cookie
0x180020346  xor     rax, rsp
0x180020349  mov     [rbp+240h+var_40], rax
0x180020350  mov     [rsp+340h+var_2F0], rcx
0x180020355  mov     qword ptr [rsp+340h+var_300], rdx
0x18002035a  xor     r15d, r15d
0x18002035d  mov     [rsp+340h+var_310], r15d
0x180020362  mov     [rsp+340h+var_30C], r15d
0x180020367  xorps   xmm0, xmm0
0x18002036a  movups  xmmword ptr [rbp+240h+var_1E8], xmm0
0x18002036e  mov     qword ptr [rbp+240h+var_1D8], r15
0x180020372  mov     qword ptr [rbp+240h+var_1D8+8], 7
0x18002037a  mov     word ptr [rbp+240h+var_1E8], r15w
0x18002037f  mov     [rsp+340h+var_304], r15d
0x180020384  mov     [rbp+240h+var_210], r15d
0x180020388  mov     [rbp+240h+var_20C], r15b
0x18002038c  mov     eax, cs:dword_18006E000
0x180020392  mov     rsi, 400000000000h
0x18002039c  cmp     eax, 5
0x18002039f  jbe     short loc_1800203FB
0x1800203a1  mov     rcx, cs:qword_18006E018
0x1800203a8  mov     rax, cs:qword_18006E010
0x1800203af  test    rsi, rax
0x1800203b2  jz      short loc_1800203FB
0x1800203b4  mov     rax, rcx
0x1800203b7  and     rax, rsi
0x1800203ba  cmp     rax, rcx
0x1800203bd  jnz     short loc_1800203FB
0x1800203bf  lea     rdx, [rbp+240h+ActivityId]; ActivityId
0x1800203c3  mov     ecx, 3; ControlCode
0x1800203c8  call    cs:__imp_EventActivityIdControl
0x1800203ce  mov     eax, [rbp+240h+ActivityId.Data1]
0x1800203d1  mov     [rbp+240h+var_1F8.Data1], eax
0x1800203d4  mov     eax, dword ptr [rbp+240h+ActivityId.Data2]
0x1800203d7  mov     dword ptr [rbp+240h+var_1F8.Data2], eax
0x1800203da  mov     eax, dword ptr [rbp+240h+ActivityId.Data4]
0x1800203dd  mov     dword ptr [rbp+240h+var_1F8.Data4], eax
0x1800203e0  mov     eax, dword ptr [rbp+240h+ActivityId.Data4+4]
0x1800203e3  mov     dword ptr [rbp+240h+var_1F8.Data4+4], eax
0x1800203e6  lea     rdx, [rbp+240h+var_1F8]; ActivityId
0x1800203ea  mov     ecx, 4; ControlCode
0x1800203ef  call    cs:__imp_EventActivityIdControl
0x1800203f5  mov     [rbp+240h+var_20C], 1
0x1800203f9  jmp     short loc_1800203FF
0x1800203fb  movups  xmmword ptr [rbp+240h+ActivityId.Data1], xmm0
0x1800203ff  mov     [rbp+240h+var_210], 1
0x180020406  mov     eax, cs:dword_18006E000
0x18002040c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180020413  lea     r12, _TraceLoggingMetadataEnd
0x18002041a  lea     r14, _TraceLoggingMetadata
0x180020421  cmp     eax, 5
0x180020424  jbe     loc_1800207C2
0x18002042a  mov     rcx, cs:qword_18006E018
0x180020431  mov     rax, cs:qword_18006E010
0x180020438  test    rsi, rax
0x18002043b  jz      loc_1800207C2
0x180020441  mov     rax, rcx
0x180020444  and     rax, rsi
0x180020447  cmp     rax, rcx
0x18002044a  jnz     loc_1800207C2
0x180020450  mov     rcx, qword ptr [rsp+340h+var_300]
0x180020455  mov     eax, [rcx+38h]
0x180020458  mov     [rbp+240h+var_2A8], eax
0x18002045b  mov     eax, [rcx+34h]
0x18002045e  mov     [rbp+240h+var_2A4], eax
0x180020461  mov     eax, [rcx+30h]
0x180020464  mov     [rbp+240h+var_2A0], eax
0x180020467  mov     eax, [rcx+2Ch]
0x18002046a  mov     [rbp+240h+var_29C], eax
0x18002046d  mov     eax, [rcx+28h]
0x180020470  mov     [rbp+240h+var_298], eax
0x180020473  mov     eax, [rcx+24h]
0x180020476  mov     [rbp+240h+var_294], eax
0x180020479  mov     eax, [rcx+20h]
0x18002047c  mov     [rbp+240h+var_290], eax
0x18002047f  mov     eax, [rcx+1Ch]
0x180020482  mov     [rbp+240h+var_28C], eax
0x180020485  mov     eax, [rcx+18h]
0x180020488  mov     [rbp+240h+var_288], eax
0x18002048b  mov     eax, [rcx+14h]
0x18002048e  mov     [rbp+240h+var_284], eax
0x180020491  mov     eax, [rcx+0Ch]
0x180020494  mov     [rbp+240h+var_280], eax
0x180020497  mov     eax, [rcx+8]
0x18002049a  mov     [rbp+240h+var_27C], eax
0x18002049d  mov     eax, [rcx+4]
0x1800204a0  mov     [rbp+240h+var_278], eax
0x1800204a3  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x1800204a8  test    al, al
0x1800204aa  jz      short loc_1800204E7
0x1800204ac  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x1800204b1  test    al, al
0x1800204b3  jz      short loc_1800204E7
0x1800204b5  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x1800204ba  test    al, al
0x1800204bc  jz      short loc_1800204E7
0x1800204be  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x1800204c3  test    al, al
0x1800204c5  jz      short loc_1800204E7
0x1800204c7  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x1800204cc  test    al, al
0x1800204ce  jz      short loc_1800204E7
0x1800204d0  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x1800204d5  test    al, al
0x1800204d7  jz      short loc_1800204E7
0x1800204d9  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x1800204de  test    al, al
0x1800204e0  mov     eax, 1
0x1800204e5  jnz     short loc_1800204EA
0x1800204e7  mov     eax, r15d
0x1800204ea  mov     [rbp+240h+var_274], eax
0x1800204ed  mov     eax, [rsp+340h+var_304]
0x1800204f1  mov     [rbp+240h+var_270], eax
0x1800204f4  lea     rcx, [rbp+240h+var_1E8]
0x1800204f8  cmp     qword ptr [rbp+240h+var_1D8+8], 7
0x1800204fd  cmova   rcx, [rbp+240h+var_1E8]
0x180020502  mov     rdx, [rsp+340h+var_2F0]
0x180020507  mov     eax, r15d
0x18002050a  test    rdx, rdx
0x18002050d  setnz   al
0x180020510  mov     dword ptr [rsp+340h+Block], eax
0x180020514  mov     eax, [rsp+340h+var_30C]
0x180020518  mov     [rsp+340h+var_308], eax
0x18002051c  cmp     [rbp+240h+var_20C], 0
0x180020520  jz      short loc_180020540
0x180020522  cmp     [rbp+240h+var_1F8.Data1], 0
0x180020526  jnz     short loc_18002053A
0x180020528  cmp     dword ptr [rbp+240h+var_1F8.Data2], 0
0x18002052c  jnz     short loc_18002053A
0x18002052e  cmp     dword ptr [rbp+240h+var_1F8.Data4], 0
0x180020532  jnz     short loc_18002053A
0x180020534  cmp     dword ptr [rbp+240h+var_1F8.Data4+4], 0
0x180020538  jz      short loc_180020540
0x18002053a  lea     r9, [rbp+240h+var_1F8]
0x18002053e  jmp     short loc_180020543
0x180020540  mov     r9, r15; RelatedActivityId
0x180020543  lea     rax, [rbp+240h+var_2A8]
0x180020547  mov     [rbp+240h+var_50], rax
0x18002054e  mov     [rbp+240h+var_48], 4
0x180020559  lea     rax, [rbp+240h+var_2A4]
0x18002055d  mov     [rbp+240h+var_60], rax
0x180020564  mov     [rbp+240h+var_58], 4
0x18002056f  lea     rax, [rbp+240h+var_2A0]
0x180020573  mov     [rbp+240h+var_70], rax
0x18002057a  mov     [rbp+240h+var_68], 4
0x180020585  lea     rax, [rbp+240h+var_29C]
0x180020589  mov     [rbp+240h+var_80], rax
0x180020590  mov     [rbp+240h+var_78], 4
0x18002059b  lea     rax, [rbp+240h+var_298]
0x18002059f  mov     [rbp+240h+var_90], rax
0x1800205a6  mov     [rbp+240h+var_88], 4
0x1800205b1  lea     rax, [rbp+240h+var_294]
0x1800205b5  mov     [rbp+240h+var_A0], rax
0x1800205bc  mov     [rbp+240h+var_98], 4
0x1800205c7  lea     rax, [rbp+240h+var_290]
0x1800205cb  mov     [rbp+240h+var_B0], rax
0x1800205d2  mov     [rbp+240h+var_A8], 4
0x1800205dd  lea     rax, [rbp+240h+var_28C]
0x1800205e1  mov     [rbp+240h+var_C0], rax
0x1800205e8  mov     [rbp+240h+var_B8], 4
0x1800205f3  lea     rax, [rbp+240h+var_288]
0x1800205f7  mov     [rbp+240h+var_D0], rax
0x1800205fe  mov     [rbp+240h+var_C8], 4
0x180020609  lea     rax, [rbp+240h+var_284]
0x18002060d  mov     [rbp+240h+var_E0], rax
0x180020614  mov     [rbp+240h+var_D8], 4
0x18002061f  lea     rax, [rbp+240h+var_280]
0x180020623  mov     [rbp+240h+var_F0], rax
0x18002062a  mov     [rbp+240h+var_E8], 4
0x180020635  lea     rax, [rbp+240h+var_27C]
0x180020639  mov     [rbp+240h+var_100], rax
0x180020640  mov     [rbp+240h+var_F8], 4
0x18002064b  lea     rax, [rbp+240h+var_278]
0x18002064f  mov     [rbp+240h+var_110], rax
0x180020656  mov     [rbp+240h+var_108], 4
0x180020661  lea     rax, [rbp+240h+var_274]
0x180020665  mov     [rbp+240h+var_120], rax
0x18002066c  mov     [rbp+240h+var_118], 4
0x180020677  lea     rax, [rbp+240h+var_270]
0x18002067b  mov     [rbp+240h+var_130], rax
0x180020682  mov     [rbp+240h+var_128], 4
0x18002068d  test    rcx, rcx
0x180020690  jz      short loc_1800206A9
0x180020692  mov     rax, rdi
0x180020695  lea     rax, [rax+1]
0x180020699  cmp     word ptr [rcx+rax*2], 0
0x18002069e  jnz     short loc_180020695
0x1800206a0  lea     eax, ds:2[rax*2]
0x1800206a7  jmp     short loc_1800206B5
0x1800206a9  lea     rcx, LocaleName
0x1800206b0  mov     eax, 2
0x1800206b5  mov     [rbp+240h+var_140], rcx
0x1800206bc  mov     [rbp+240h+var_138], eax
0x1800206c2  mov     [rbp+240h+var_134], r15d
0x1800206c9  test    rdx, rdx
0x1800206cc  jz      short loc_1800206E5
0x1800206ce  mov     rax, rdi
0x1800206d1  lea     rax, [rax+1]
0x1800206d5  cmp     word ptr [rdx+rax*2], 0
0x1800206da  jnz     short loc_1800206D1
0x1800206dc  lea     eax, ds:2[rax*2]
0x1800206e3  jmp     short loc_1800206F1
0x1800206e5  lea     rdx, LocaleName
0x1800206ec  mov     eax, 2
0x1800206f1  mov     [rbp+240h+var_150], rdx
0x1800206f8  mov     [rbp+240h+var_148], eax
0x1800206fe  mov     [rbp+240h+var_144], r15d
0x180020705  lea     rax, [rsp+340h+Block]
0x18002070a  mov     [rbp+240h+var_160], rax
0x180020711  mov     [rbp+240h+var_158], 4
0x18002071c  lea     rax, [rsp+340h+var_308]
0x180020721  mov     [rbp+240h+var_170], rax
0x180020728  mov     [rbp+240h+var_168], 4
0x180020733  mov     dword ptr [rbp+240h+EventDescriptor.Id], 0B000000h
0x18002073a  movzx   eax, cs:word_180061812
0x180020741  mov     dword ptr [rbp+240h+EventDescriptor.Level], eax
0x180020744  mov     [rbp+240h+EventDescriptor.Keyword], rsi
0x180020748  mov     rax, cs:off_18006E008
0x18002074f  mov     [rbp+240h+var_190.Ptr], rax
0x180020756  movzx   eax, word ptr [rax]
0x180020759  mov     [rbp+240h+var_190.Size], eax
0x18002075f  mov     dword ptr [rbp+240h+var_190.0Ch], 2
0x180020769  lea     rax, dword_18006181C
0x180020770  mov     [rbp+240h+var_180], rax
0x180020777  mov     [rbp+240h+var_178], 16Ch
0x180020781  mov     [rbp+240h+var_174], 1
0x18002078b  mov     rax, r12
0x18002078e  sub     eax, r14d
0x180020791  mov     [rsp+340h+var_310], eax
0x180020795  mov     eax, [rsp+340h+var_310]
0x180020799  lea     rax, [rbp+240h+var_190]
0x1800207a0  mov     [rsp+340h+UserData], rax; UserData
0x1800207a5  mov     [rsp+340h+UserDataCount], 15h; UserDataCount
0x1800207ad  lea     r8, [rbp+240h+ActivityId]; ActivityId
0x1800207b1  lea     rdx, [rbp+240h+EventDescriptor]; EventDescriptor
0x1800207b5  mov     rcx, cs:RegHandle; RegHandle
0x1800207bc  call    cs:__imp_EventWriteTransfer
0x1800207c2  lea     rax, [rbp+240h+var_210]
0x1800207c6  mov     [rbp+240h+var_268], rax
0x1800207ca  lea     rax, [rsp+340h+var_30C]
0x1800207cf  mov     [rbp+240h+var_260], rax
0x1800207d3  lea     rax, [rsp+340h+var_2F0]
0x1800207d8  mov     [rbp+240h+var_258], rax
0x1800207dc  lea     rax, [rbp+240h+var_1E8]
0x1800207e0  mov     [rbp+240h+var_250], rax
0x1800207e4  lea     rax, [rsp+340h+var_304]
0x1800207e9  mov     [rbp+240h+var_248], rax
0x1800207ed  lea     rax, [rsp+340h+var_300]
0x1800207f2  mov     [rbp+240h+var_240], rax
0x1800207f6  mov     [rbp+240h+var_238], 100h
0x1800207fc  mov     byte ptr [rsp+340h+var_2E8], 0
0x180020801  mov     dword ptr [rsp+340h+var_2E8+4], 1
0x180020809  mov     qword ptr [rsp+340h+var_2E8+8], 1
0x180020812  mov     byte ptr [rsp+340h+var_2D8], 0
0x180020817  mov     dword ptr [rsp+340h+var_2D8+4], 8
0x18002081f  mov     dword ptr [rsp+340h+var_2D8+8], 7Fh
0x180020827  xorps   xmm0, xmm0
0x18002082a  movdqu  [rsp+340h+var_2D8+0Ch], xmm0
0x180020830  mov     dword ptr [rbp+240h+var_2BC], 2
0x180020837  mov     qword ptr [rbp+240h+var_2BC+4], 1
0x18002083f  mov     dword ptr [rbp+240h+var_2BC+0Ch], r15d
0x180020843  lea     r8, [rsp+340h+var_2E8]
0x180020848  call    PolicyManager__ReadGroupPolicy
0x18002084d  mov     [rsp+340h+var_30C], eax
0x180020851  test    eax, eax
0x180020853  js      loc_180020A8E
0x180020859  mov     eax, cs:dword_18006E000
0x18002085f  cmp     eax, 4
0x180020862  jbe     loc_180020912
0x180020868  mov     eax, [rsp+340h+var_30C]
0x18002086c  mov     [rsp+340h+var_310], eax
0x180020870  lea     rax, [rsp+340h+var_310]
0x180020875  mov     [rbp+240h+var_1A8], rax
0x18002087c  mov     [rbp+240h+var_1A0], 4
0x180020887  mov     dword ptr [rbp+240h+EventDescriptor.Id], 0B000000h
0x18002088e  movzx   eax, cs:word_1800617E1
0x180020895  mov     dword ptr [rbp+240h+EventDescriptor.Level], eax
0x180020898  mov     [rbp+240h+EventDescriptor.Keyword], r15
0x18002089c  mov     rax, cs:off_18006E008
0x1800208a3  mov     [rbp+240h+var_1C8.Ptr], rax
0x1800208a7  movzx   eax, word ptr [rax]
0x1800208aa  mov     [rbp+240h+var_1C8.Size], eax
0x1800208b0  mov     dword ptr [rbp+240h+var_1C8.0Ch], 2
0x1800208ba  lea     rax, byte_1800617EB
0x1800208c1  mov     [rbp+240h+var_1B8], rax
0x1800208c8  mov     dword ptr [rbp+240h+var_1B0], 25h ; '%'
0x1800208d2  mov     dword ptr [rbp+240h+var_1B0+4], 1
0x1800208dc  mov     rax, r12
0x1800208df  sub     eax, r14d
0x1800208e2  mov     [rsp+340h+var_308], eax
  ... truncated ...
```
