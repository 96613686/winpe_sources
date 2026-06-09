# SmbCeParseSmbHeader

- ea: `0x140007820`
- end: `0x140008833`
- name: `SmbCeParseSmbHeader`
- size: `4115`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `4`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140005fe0`
- `0x140006080`
- `0x140006230`
- `0x140006af0`

## callees

- `0x140007820`
- `0x14000af80`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e694`
- `0x14000ebd8`
- `0x140012014`
- `0x140012f20`
- `0x140016560`
- `0x1400166c0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140007d50`
- `ntoskrnl!EtwWriteTransfer` at `0x140007d50`
- `ntoskrnl!RtlCompareMemory` at `0x140007b82`
- `ntoskrnl!RtlCompareMemory` at `0x140008224`
- `ntoskrnl!RtlCompareMemory` at `0x14000831d`
- `ntoskrnl!RtlCompareMemory` at `0x140008342`
- `ntoskrnl!RtlCompareMemory` at `0x140008362`
- `ntoskrnl!RtlCompareMemory` at `0x14000838b`
- `ntoskrnl!RtlCompareMemory` at `0x140007b82`
- `ntoskrnl!RtlCompareMemory` at `0x140008224`
- `ntoskrnl!RtlCompareMemory` at `0x14000831d`
- `ntoskrnl!RtlCompareMemory` at `0x140008342`
- `ntoskrnl!RtlCompareMemory` at `0x140008362`
- `ntoskrnl!RtlCompareMemory` at `0x14000838b`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140007bab`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140007ef0`

## pseudocode

```c
__int64 __fastcall SmbCeParseSmbHeader(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned int LockArray_high; // esi
  __int64 v8; // r12
  unsigned int *v9; // r10
  __int64 v10; // rbx
  __int64 v11; // r13
  int SmbResponseNtStatus; // eax
  int v13; // r15d
  int v14; // r14d
  __int64 v15; // rdi
  __int64 v16; // rcx
  char v17; // al
  unsigned int *v18; // r9
  int v19; // ecx
  int v20; // ebx
  unsigned int v21; // r8d
  unsigned int v22; // edx
  unsigned int v23; // ecx
  unsigned int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r8
  _WORD *v28; // rdi
  SIZE_T v29; // rax
  __int64 v30; // r9
  __int64 v31; // rax
  __int16 v32; // ax
  unsigned int *v33; // r9
  _BYTE *v34; // r10
  char v35; // r11
  int v36; // esi
  int v37; // ebx
  unsigned int v38; // r15d
  char v39; // di
  int v40; // eax
  int v41; // ecx
  _BYTE *v42; // rdi
  _DWORD *v43; // rdx
  bool v44; // cc
  __int16 v45; // cx
  __int64 v46; // rax
  unsigned int v47; // eax
  unsigned int v48; // edx
  unsigned int v49; // ecx
  unsigned int v50; // edx
  unsigned int v51; // ecx
  unsigned int v52; // edi
  unsigned int v53; // ecx
  __int64 v54; // rax
  __int64 *v55; // rdi
  __int64 v56; // rsi
  char v57; // cl
  void *v58; // rdi
  __int64 v59; // rbx
  __int64 v60; // rbx
  _DWORD *v61; // rcx
  _BYTE *v62; // rdx
  int v63; // r15d
  unsigned int v64; // edi
  _BYTE *v65; // rbx
  int v66; // ecx
  int v67; // esi
  char v68; // r15
  unsigned int *v69; // r9
  _DWORD *v70; // rdi
  unsigned int v71; // ebx
  __int64 v72; // rdi
  int v73; // ebx
  __int32 v74; // eax
  __int64 v75; // rsi
  __int64 v76; // r8
  __int64 v77; // rdx
  int v78; // r9d
  __int64 result; // rax
  __int64 v80; // r9
  unsigned int *v81; // rcx
  __int64 v82; // rdx
  char v83; // [rsp+50h] [rbp-B0h]
  char v84; // [rsp+51h] [rbp-AFh]
  int v85; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v86; // [rsp+58h] [rbp-A8h]
  char v87; // [rsp+60h] [rbp-A0h] BYREF
  char v88; // [rsp+61h] [rbp-9Fh] BYREF
  char v89; // [rsp+62h] [rbp-9Eh] BYREF
  int v90; // [rsp+64h] [rbp-9Ch]
  unsigned int *v91; // [rsp+68h] [rbp-98h]
  int v92; // [rsp+70h] [rbp-90h]
  _BYTE *v93; // [rsp+78h] [rbp-88h]
  __int64 v94; // [rsp+80h] [rbp-80h]
  PVOID pContext; // [rsp+88h] [rbp-78h]
  __int64 v96; // [rsp+90h] [rbp-70h]
  void *Source1; // [rsp+98h] [rbp-68h]
  __int16 v98; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v99; // [rsp+A8h] [rbp-58h]
  void *v100; // [rsp+B0h] [rbp-50h] BYREF
  int v101; // [rsp+B8h] [rbp-48h] BYREF
  int *v102; // [rsp+C0h] [rbp-40h]
  __int64 v103; // [rsp+C8h] [rbp-38h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+D0h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-20h] BYREF
  __int16 *v106; // [rsp+F0h] [rbp-10h]
  int v107; // [rsp+F8h] [rbp-8h]
  int v108; // [rsp+FCh] [rbp-4h]
  __int16 *v109; // [rsp+100h] [rbp+0h]
  __int64 v110; // [rsp+108h] [rbp+8h]
  int *v111; // [rsp+110h] [rbp+10h]
  __int64 v112; // [rsp+118h] [rbp+18h]
  void **v113; // [rsp+120h] [rbp+20h]
  __int64 v114; // [rsp+128h] [rbp+28h]
  char *v115; // [rsp+130h] [rbp+30h]
  __int64 v116; // [rsp+138h] [rbp+38h]
  char *v117; // [rsp+140h] [rbp+40h]
  __int64 v118; // [rsp+148h] [rbp+48h]
  char *v119; // [rsp+150h] [rbp+50h]
  __int64 v120; // [rsp+158h] [rbp+58h]
  int *v121; // [rsp+160h] [rbp+60h]
  __int64 v122; // [rsp+168h] [rbp+68h]

  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v8 = *(_QWORD *)(a1 + 88);
  v9 = a7;
  v102 = a4;
  v103 = a3;
  v99 = a2;
  v94 = a1;
  v91 = a7;
  if ( v8 )
  {
    v10 = *(_QWORD *)(v8 + 96);
    v11 = *(_QWORD *)(v8 + 104);
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  v86 = v10;
  if ( a6 < 0x20 )
    goto LABEL_232;
  pContext = *(PVOID *)(a1 + 80);
  v96 = *(_QWORD *)(a1 + 24);
  SmbResponseNtStatus = GetSmbResponseNtStatus(a2, a1, 0);
  v92 = SmbResponseNtStatus;
  v13 = SmbResponseNtStatus;
  if ( SmbResponseNtStatus < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      36,
      WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids,
      (unsigned int)SmbResponseNtStatus);
    v9 = v91;
  }
  if ( v13 == -1073741628 )
  {
LABEL_232:
    *v9 = a6;
    return 3221225667LL;
  }
  v14 = 0;
  v90 = 0;
  v84 = 0;
  v15 = v99 + 32;
  v83 = *(_BYTE *)(v99 + 4);
  v93 = (_BYTE *)(v99 + 32);
  *v9 = 32;
  if ( v13 != -1073740964 )
    goto LABEL_19;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, v10);
  _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 12), 4, 0);
  v16 = v94;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v94 + 336)) <= 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, v94);
    v13 = -1069481983;
    v92 = -1069481983;
LABEL_19:
    v16 = v94;
  }
  v17 = v83;
  if ( v83 == 115 )
  {
    if ( v13 && *v91 + 2 <= a6 )
    {
      if ( !*(_BYTE *)v15 )
        v14 = v13;
      *(_DWORD *)(v16 + 248) = v14;
      if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(v16, (unsigned int)SessionSetupError, v96 + 412, v13, 194, 11);
      if ( v14 )
        goto LABEL_205;
    }
    v18 = v91;
    if ( *v91 + 9 > a6 )
      goto LABEL_204;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
      v18 = v91;
    }
    if ( *(_BYTE *)v15 == 3 )
    {
      v19 = *(unsigned __int16 *)(v15 + 7);
      v83 = *(_BYTE *)(v15 + 1);
      if ( v83 == -1 )
      {
        v20 = 0;
        v21 = v19 + 9;
        v14 = v13;
      }
      else
      {
        v22 = *(unsigned __int16 *)(v15 + 3);
        v23 = *v18 + v19 + 9;
        if ( v22 < v23 )
          v14 = -1073741629;
        v21 = *(unsigned __int16 *)(v15 + 3) - *v18;
        v20 = v22 < v23 ? 0x6E5 : 0;
      }
      if ( v14 >= 0 )
      {
        v24 = a6;
        LODWORD(v16) = v21 + *v18;
        if ( (unsigned int)v16 > a6 )
        {
          v28 = pContext;
          v14 = -1073741802;
        }
        else
        {
          *v18 = v16;
          v25 = v99;
          v26 = v21;
          v27 = v86;
          v93 = (_BYTE *)(v15 + v26);
          *(_WORD *)(v86 + 132) = *(_WORD *)(v99 + 28);
          if ( (*(_BYTE *)(v15 + 5) & 2) != 0 )
            *(_DWORD *)(v27 + 136) |= 2u;
          if ( (*(_BYTE *)(v15 + 5) & 1) != 0 )
            *(_DWORD *)(v27 + 136) |= 0x10u;
          v28 = pContext;
          if ( (*((_BYTE *)pContext + 672) & 0x18) == 0x10 )
          {
            v29 = RtlCompareMemory((const void *)(v25 + 14), InitialSecuritySignature, 8u);
            v30 = v94;
            v27 = v86;
            if ( v29 != 8 )
              *(_BYTE *)(v94 + 254) = 1;
          }
          else
          {
            v30 = v94;
          }
          LODWORD(v16) = MRxSmbLegacyPerfCtrs;
          _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)LockArray_high << 8)
                                                          + MRxSmbLegacyPerfCtrs
                                                          + 148));
          if ( (unsigned int)dword_14001F0D0 > 5 )
          {
            LODWORD(v16) = qword_14001F0E8;
            if ( (qword_14001F0E0 & 0x400000000000LL) != 0 && (qword_14001F0E8 & 0x400000000000LL) == qword_14001F0E8 )
            {
              v98 = v28[208];
              v109 = &v98;
              v101 = *(unsigned __int8 *)(v30 + 254);
              v111 = &v101;
              LODWORD(v100) = *(_DWORD *)(v27 + 136);
              v113 = &v100;
              v87 = *(_BYTE *)(v27 + 381);
              v115 = &v87;
              v88 = *(_BYTE *)(v27 + 380);
              v117 = &v88;
              v89 = *(_BYTE *)(v27 + 382);
              v119 = &v89;
              v31 = *((_QWORD *)v28 + 43);
              v110 = 2;
              v112 = 4;
              v114 = 4;
              v116 = 1;
              v118 = 1;
              v120 = 1;
              if ( v31 )
                v32 = *(_WORD *)(v31 + 320);
              else
                v32 = 255;
              LOWORD(v85) = v32;
              v122 = 2;
              v121 = &v85;
              *(_DWORD *)&EventDescriptor.Level = 5;
              UserData.Ptr = (ULONGLONG)EventInformation;
              EventDescriptor.Keyword = 0x400000000000LL;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              UserData.Size = *(unsigned __int16 *)EventInformation;
              v106 = &word_14001B4BE;
              UserData.Reserved = 2;
              v107 = 130;
              v108 = 1;
              LODWORD(Source1) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 9u, &UserData);
            }
          }
        }
LABEL_55:
        v17 = v83;
        goto LABEL_56;
      }
    }
    else
    {
      v14 = -1073741629;
      v20 = 1782;
    }
    v39 = 0;
    if ( !v20 )
      v39 = 11;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids,
        (unsigned int)v14);
    *(_DWORD *)(v94 + 248) = v14;
    _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)LockArray_high << 8)
                                                    + MRxSmbLegacyPerfCtrs
                                                    + 152));
    if ( !v20 )
      LOBYTE(v20) = 41;
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(MRxSmbLegacyPerfCtrs, (unsigned int)SessionSetupError, v96 + 412, v14, v20, v39);
    if ( v83 != 117 && v83 != 112 )
      goto LABEL_174;
    LODWORD(v16) = (_DWORD)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
    v28 = pContext;
    v24 = a6;
    v84 = 1;
    v90 = 1;
    goto LABEL_55;
  }
  v28 = pContext;
  v24 = a6;
LABEL_56:
  if ( v17 != 117 )
  {
    v67 = v96;
    v52 = a6;
    v65 = v93;
    goto LABEL_177;
  }
  if ( v14 < 0 )
    goto LABEL_205;
  v33 = v91;
  v34 = v93;
  if ( v13 && *v91 + 2 <= v24 )
  {
    v84 = 1;
    if ( !*v93 )
      v14 = v13;
    v90 = 1;
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
    {
      McTemplateK0qqq_EtwWriteTransfer(v16, (unsigned int)TreeConnectError, v96 + 412, v13, 66, 11);
      v33 = v91;
      v34 = v93;
    }
  }
  if ( v14 )
  {
LABEL_205:
    v68 = v83;
LABEL_206:
    v72 = v86;
    goto LABEL_207;
  }
  if ( *v33 + 9 > v24 )
  {
LABEL_204:
    v14 = -1073741802;
    goto LABEL_205;
  }
  v35 = v34[1];
  v36 = 0;
  v85 = 0;
  v37 = 0;
  Source1 = 0;
  v100 = 0;
  v38 = 0;
  v83 = v35;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
    v33 = v91;
    v34 = v93;
    v35 = v83;
  }
  switch ( *v34 )
  {
    case 0:
      v14 = v92;
      break;
    case 2:
      v38 = *(unsigned __int16 *)(v34 + 5);
      Source1 = v34 + 7;
      v36 = v38 + 7;
      v85 = v38 + 7;
      if ( v35 == -1 )
      {
        v14 = v92;
      }
      else
      {
        v50 = *(unsigned __int16 *)(v34 + 3);
        v51 = v36 + *v33;
        if ( v50 < v51 )
          v14 = -1073741629;
        v36 = *(unsigned __int16 *)(v34 + 3) - *v33;
        v85 = v36;
        v37 = v50 < v51 ? 0x813 : 0;
      }
      if ( *((int *)v28 + 104) >= 5 )
      {
        *(_QWORD *)(v8 + 120) = 2032127;
        *(_BYTE *)(v8 + 116) = 1;
        *(_WORD *)(v11 + 160) = 0;
      }
      if ( MRxSmbExtendedSignaturesRequired )
      {
        v37 = 2091;
        v14 = -1073741240;
        SmbCeTransportDisconnectIndicated(v28);
      }
      break;
    case 3:
    case 7:
      if ( *v34 == 7 )
      {
        v40 = *(_DWORD *)(v34 + 7);
        *(_DWORD *)(v8 + 120) = v40;
        v41 = *(_DWORD *)(v34 + 11);
        *(_DWORD *)(v8 + 124) = v41;
        if ( v40 == 511 )
          *(_DWORD *)(v8 + 120) = 2032127;
        if ( v41 == 511 )
          *(_DWORD *)(v8 + 124) = 2032127;
        v38 = *(unsigned __int16 *)(v34 + 15);
        v42 = v34 + 17;
        *(_WORD *)(v11 + 147) = 2316;
        *(_DWORD *)(v11 + 152) = 4096;
        *(_BYTE *)(v11 + 146) = 13;
        v36 = v38 + 17;
        *(_WORD *)(v11 + 144) = 2;
      }
      else
      {
        *(_QWORD *)(v8 + 120) = 2032127;
        v42 = v34 + 9;
        v38 = *(unsigned __int16 *)(v34 + 7);
        v36 = v38 + 9;
      }
      v43 = pContext;
      *(_BYTE *)(v8 + 116) = 1;
      Source1 = v42;
      v85 = v36;
      v44 = v43[104] < 5;
      v100 = v42 + 3;
      if ( !v44 )
      {
        v45 = *(_WORD *)(v34 + 5);
        *(_WORD *)(v11 + 160) = v45;
        if ( (v45 & 2) != 0 )
          *(_BYTE *)(v11 + 104) = 1;
        if ( (*(_DWORD *)(v94 + 72) & 0x10000) != 0 )
        {
          if ( (v45 & 0x20) != 0 )
          {
            v46 = v86;
            *(_OWORD *)(v86 + 188) = *(_OWORD *)(v86 + 316);
          }
          else
          {
            if ( MRxSmbExtendedSignaturesRequired )
            {
              v37 = 2006;
              v14 = -1073741240;
              SmbCeTransportDisconnectIndicated(v43);
              break;
            }
            v46 = v86;
          }
          *(_DWORD *)(v46 + 184) = 2;
        }
      }
      if ( v35 == -1 )
      {
        v14 = v92;
        v100 = v42 + 3;
        Source1 = v42;
      }
      else
      {
        v47 = *v33;
        v48 = *(unsigned __int16 *)(v34 + 3);
        v100 = v42 + 3;
        Source1 = v42;
        v49 = v47 + v36;
        if ( v48 < v47 + v36 )
          v14 = -1073741629;
        v36 = v48 - v47;
        v85 = v48 - v47;
        v37 = v48 < v49 ? 0x7EF : 0;
      }
      break;
    default:
      v37 = 2099;
      v14 = -1073741629;
      break;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, (unsigned int)v14);
  if ( v14 >= 0 )
  {
    v52 = a6;
    v53 = v36 + *v91;
    if ( v53 > a6 )
    {
      v65 = v93;
      v14 = -1073741802;
LABEL_176:
      v67 = v96;
      goto LABEL_177;
    }
    v54 = v99;
    v55 = &ServiceNameTable;
    *v91 = v53;
    *(_WORD *)(v8 + 112) |= 1u;
    *(_WORD *)(v8 + 114) = *(_WORD *)(v54 + 24);
    while ( 1 )
    {
      v56 = *((unsigned __int16 *)v55 + 1);
      if ( v38 >= (unsigned int)v56
        && RtlCompareMemory(Source1, (const void *)v55[1], *((unsigned __int16 *)v55 + 1)) == v56 )
      {
        break;
      }
      if ( *(_BYTE *)v55 == 2 )
      {
        if ( *(_BYTE *)(v11 + 105) != 4
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, v11);
        }
        v57 = 0;
        LODWORD(v56) = v38;
        if ( *(_BYTE *)(v11 + 105) != 4 )
          v57 = *(_BYTE *)(v11 + 105);
        *(_BYTE *)(v11 + 105) = v57;
        goto LABEL_147;
      }
      v55 += 2;
    }
    v57 = *(_BYTE *)(v11 + 105);
    if ( v57 == 4 )
      v57 = *(_BYTE *)v55;
    *(_BYTE *)(v11 + 105) = v57;
    if ( v57 != *(_BYTE *)v55
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, v11);
      v57 = *(_BYTE *)(v11 + 105);
    }
LABEL_147:
    if ( v57 )
    {
      v61 = pContext;
      *(_DWORD *)(v11 + 116) = *((_DWORD *)pContext + 121);
      *(_DWORD *)(v11 + 112) = v61[119];
LABEL_159:
      if ( (v61[105] & 0x10000) == 0 && v38 > (unsigned int)v56 )
      {
        v62 = (char *)Source1 + (unsigned int)v56;
        if ( *v62 )
        {
          v63 = v38 - v56;
          v64 = 1;
          if ( v63 != 1 )
          {
            do
            {
              if ( v64 == 7 )
                break;
              if ( !v62[v64] )
                break;
              ++v64;
            }
            while ( v64 != v63 );
          }
          memmove((void *)(v11 + 267), v62, v64);
          *(_BYTE *)(v11 + v64 + 267) = 0;
          *(_BYTE *)(v11 + 266) = v64;
        }
      }
      v65 = &v93[v85];
      v84 = 1;
      v90 = 0;
      goto LABEL_175;
    }
    v58 = v100;
    if ( v100 )
    {
      if ( (*((_DWORD *)pContext + 105) & 0x8000) != 0 )
      {
        v59 = (unsigned __int16)FileSystem_NTFS_UNICODE;
        if ( RtlCompareMemory(v100, Source2, (unsigned __int16)FileSystem_NTFS_UNICODE) != v59 )
        {
          v60 = (unsigned __int16)FileSystem_FAT_UNICODE;
          if ( RtlCompareMemory(v58, off_14001F140, (unsigned __int16)FileSystem_FAT_UNICODE) != v60 )
            goto LABEL_157;
          goto LABEL_156;
        }
        goto LABEL_154;
      }
      if ( RtlCompareMemory(v100, FileSystem_NTFS, 4u) == 4 )
      {
LABEL_154:
        *(_BYTE *)(v11 + 106) = 2;
        goto LABEL_157;
      }
      if ( RtlCompareMemory(v58, FileSystem_FAT, 3u) == 3 )
LABEL_156:
        *(_BYTE *)(v11 + 106) = 1;
    }
LABEL_157:
    v61 = pContext;
    *(_DWORD *)(v11 + 112) = *((_DWORD *)pContext + 118);
    *(_DWORD *)(v11 + 116) = v61[120];
    goto LABEL_159;
  }
  v66 = 0;
  v84 = 1;
  v90 = 1;
  if ( !v37 )
  {
    v66 = 11;
    LOBYTE(v37) = -72;
  }
  if ( (Microsoft_Windows_SMBClientEnableBits & 1) == 0 )
  {
LABEL_174:
    v65 = v93;
LABEL_175:
    v52 = a6;
    goto LABEL_176;
  }
  v67 = v96;
  McTemplateK0qqq_EtwWriteTransfer(v66, (unsigned int)TreeConnectError, v96 + 412, v14, v37, v66);
  v52 = a6;
  v65 = v93;
LABEL_177:
  v68 = v83;
  if ( v83 != 112 || v14 < 0 )
    goto LABEL_206;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
  v68 = -1;
  if ( v92 < 0 )
  {
    v14 = v92;
    v84 = 1;
    v90 = 9;
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(v92, (unsigned int)TreeConnectError, v67 + 412, v92, 254, 11);
  }
  else
  {
    v69 = v91;
    if ( *v91 + 7 <= v52 )
    {
      *(_WORD *)(v8 + 112) |= 1u;
      v70 = pContext;
      *(_WORD *)(v8 + 114) = *(_WORD *)(v65 + 3);
      if ( !v70[104] && *(_BYTE *)(v11 + 105) == 4 )
        *(_BYTE *)(v11 + 105) = 0;
      v71 = *(unsigned __int16 *)(v65 + 1);
      if ( v71 < 0x100 )
        v71 = 256;
      if ( !v70[117] )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, v71);
          v69 = v91;
        }
        v70[117] = v71;
      }
      if ( !*(_DWORD *)(v11 + 116) )
      {
        *(_DWORD *)(v11 + 112) = v71 - 48;
        *(_DWORD *)(v11 + 116) = v71 - 48;
      }
      *v69 += 7;
      v72 = v86;
      v90 = 0;
      v84 = 1;
      *(_WORD *)(v86 + 132) = *(_WORD *)(v99 + 28);
      goto LABEL_201;
    }
    v14 = -1073741802;
  }
  v72 = v86;
LABEL_201:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, (unsigned int)v14);
LABEL_207:
  v73 = v92;
  if ( v92 == -1073741309 || v92 == -1073741623 )
  {
    *(_WORD *)(v8 + 112) &= ~1u;
    _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 12), 1, 0);
    if ( v73 == -1073741309 )
      _InterlockedCompareExchange((volatile signed __int32 *)(v72 + 12), 1, 0);
    v74 = 1;
    goto LABEL_214;
  }
  if ( v84 )
  {
    v74 = v90;
LABEL_214:
    _InterlockedExchange((volatile __int32 *)(v8 + 12), v74);
  }
  v75 = v94;
  v76 = v99;
  if ( (*(_DWORD *)(v94 + 72) & 0x300) == 0 )
  {
    v77 = *(unsigned __int16 *)(v72 + 132);
    v78 = *(unsigned __int16 *)(v99 + 28);
    if ( ((_WORD)v78 != (_WORD)v77 || *(_WORD *)(v99 + 24) != *(_WORD *)(v8 + 114))
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_qqllll(
        WPP_GLOBAL_Control->AttachedDevice,
        v77,
        *(unsigned __int16 *)(v99 + 24),
        pContext,
        v94,
        v78,
        *(unsigned __int16 *)(v99 + 24),
        v77,
        *(unsigned __int16 *)(v8 + 114));
      v76 = v99;
    }
  }
  *(_DWORD *)(v75 + 40) = v73;
  if ( v14 == -1073741802 )
  {
    *v91 = 0;
    return 3221225494LL;
  }
  if ( v14 < 0 )
  {
    *v91 = a5;
    return (unsigned int)v14;
  }
  if ( v102 )
    *v102 = v73;
  v80 = v103;
  if ( v103 )
  {
    v81 = v91;
    v82 = *v91;
    *(_BYTE *)(v103 + 1) = v68;
    *(_WORD *)(v80 + 3) = *(_WORD *)v81;
    if ( (unsigned __int64)*v81 + 5 <= a5 )
    {
      result = (unsigned int)v14;
      *(_BYTE *)v80 = *(_BYTE *)(v82 + v76);
      return result;
    }
    *(_BYTE *)v80 = 0;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140007820  push    rbp
0x140007822  push    rbx
0x140007823  push    rsi
0x140007824  push    rdi
0x140007825  push    r12
0x140007827  push    r13
0x140007829  lea     rbp, [rsp-98h]
0x140007831  sub     rsp, 198h
0x140007838  mov     rax, cs:__security_cookie
0x14000783f  xor     rax, rsp
0x140007842  mov     [rbp+0C0h+var_50], rax
0x140007846  mov     esi, gs:1A4h
0x14000784e  mov     rax, rcx
0x140007851  mov     r12, [rcx+58h]
0x140007855  mov     r10, [rbp+0C0h+arg_30]
0x14000785c  mov     [rbp+0C0h+var_100], r9
0x140007860  mov     r9, rdx
0x140007863  mov     [rbp+0C0h+var_F8], r8
0x140007867  mov     [rbp+0C0h+var_118], rdx
0x14000786b  mov     [rbp+0C0h+var_140], rcx
0x14000786f  mov     [rsp+1C0h+var_158], r10
0x140007874  test    r12, r12
0x140007877  jz      short loc_140007885
0x140007879  mov     rbx, [r12+60h]
0x14000787e  mov     r13, [r12+68h]
0x140007883  jmp     short loc_14000788A
0x140007885  xor     ebx, ebx
0x140007887  xor     r13d, r13d
0x14000788a  mov     edi, [rbp+0C0h+arg_28]
0x140007890  mov     [rsp+1C0h+var_168], rbx
0x140007895  mov     [rsp+1C0h+var_38], r15
0x14000789d  cmp     edi, 20h ; ' '
0x1400078a0  jb      loc_140008806
0x1400078a6  mov     rcx, [rcx+50h]
0x1400078aa  xor     r8d, r8d
0x1400078ad  mov     [rbp+0C0h+pContext], rcx
0x1400078b1  mov     rdx, rax
0x1400078b4  mov     rcx, [rax+18h]
0x1400078b8  mov     [rbp+0C0h+var_130], rcx
0x1400078bc  mov     rcx, r9
0x1400078bf  call    GetSmbResponseNtStatus
0x1400078c4  mov     [rsp+1C0h+var_150], eax
0x1400078c8  mov     r15d, eax
0x1400078cb  lea     rdx, WPP_GLOBAL_Control
0x1400078d2  test    eax, eax
0x1400078d4  jns     short loc_14000790F
0x1400078d6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400078dd  cmp     rcx, rdx
0x1400078e0  jz      short loc_14000790F
0x1400078e2  test    dword ptr [rcx+2Ch], 400h
0x1400078e9  jz      short loc_140007908
0x1400078eb  mov     rcx, [rcx+18h]
0x1400078ef  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x1400078f6  mov     edx, 24h ; '$'
0x1400078fb  mov     r9d, eax
0x1400078fe  call    WPP_SF_d
0x140007903  mov     r10, [rsp+1C0h+var_158]
0x140007908  lea     rdx, WPP_GLOBAL_Control
0x14000790f  cmp     r15d, 0C00000C4h
0x140007916  jz      loc_140008806
0x14000791c  xor     eax, eax
0x14000791e  mov     [rsp+1C0h+var_30], r14
0x140007926  xor     r14d, r14d
0x140007929  mov     [rsp+1C0h+var_15C], eax
0x14000792d  mov     rax, [rbp+0C0h+var_118]
0x140007931  mov     r8d, 100h
0x140007937  mov     [rsp+1C0h+var_16F], r14b
0x14000793c  movzx   ecx, byte ptr [rax+4]
0x140007940  lea     rdi, [rax+20h]
0x140007944  mov     [rsp+1C0h+var_170], cl
0x140007948  mov     [rsp+1C0h+var_148], rdi
0x14000794d  mov     dword ptr [r10], 20h ; ' '
0x140007954  cmp     r15d, 0C000035Ch
0x14000795b  jnz     loc_1400079F2
0x140007961  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140007968  cmp     rcx, rdx
0x14000796b  jz      short loc_140007998
0x14000796d  test    [rcx+2Ch], r8d
0x140007971  jz      short loc_140007998
0x140007973  mov     rcx, [rcx+18h]
0x140007977  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x14000797e  mov     edx, 25h ; '%'
0x140007983  mov     r9, rbx
0x140007986  call    WPP_SF_q
0x14000798b  lea     rdx, WPP_GLOBAL_Control
0x140007992  mov     r8d, 100h
0x140007998  xor     eax, eax
0x14000799a  mov     ecx, 4
0x14000799f  lock cmpxchg [rbx+0Ch], ecx
0x1400079a4  mov     rcx, [rbp+0C0h+var_140]
0x1400079a8  mov     eax, 1
0x1400079ad  lock xadd [rcx+150h], eax
0x1400079b5  inc     eax
0x1400079b7  cmp     eax, 3
0x1400079ba  jg      short loc_1400079F6
0x1400079bc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400079c3  cmp     rcx, rdx
0x1400079c6  jz      short loc_1400079E7
0x1400079c8  test    [rcx+2Ch], r8d
0x1400079cc  jz      short loc_1400079E7
0x1400079ce  mov     r9, [rbp+0C0h+var_140]
0x1400079d2  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x1400079d9  mov     rcx, [rcx+18h]
0x1400079dd  mov     edx, 26h ; '&'
0x1400079e2  call    WPP_SF_q
0x1400079e7  mov     r15d, 0C0410001h
0x1400079ed  mov     [rsp+1C0h+var_150], r15d
0x1400079f2  mov     rcx, [rbp+0C0h+var_140]
0x1400079f6  movzx   eax, [rsp+1C0h+var_170]
0x1400079fb  mov     edx, 0Bh
0x140007a00  mov     ebx, 0C00000C3h
0x140007a05  cmp     al, 73h ; 's'
0x140007a07  jnz     loc_140007F9B
0x140007a0d  test    r15d, r15d
0x140007a10  jz      short loc_140007A6A
0x140007a12  mov     rax, [rsp+1C0h+var_158]
0x140007a17  mov     eax, [rax]
0x140007a19  add     eax, 2
0x140007a1c  cmp     eax, [rbp+0C0h+arg_28]
0x140007a22  ja      short loc_140007A6A
0x140007a24  cmp     [rdi], r14b
0x140007a27  cmovz   r14d, r15d
0x140007a2b  mov     [rcx+0F8h], r14d
0x140007a32  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 1
0x140007a39  jz      short loc_140007A61
0x140007a3b  mov     r8, [rbp+0C0h+var_130]
0x140007a3f  mov     r9d, r15d
0x140007a42  mov     dword ptr [rsp+1C0h+UserData], edx
0x140007a46  add     r8, 19Ch
0x140007a4d  lea     rdx, SessionSetupError
0x140007a54  mov     [rsp+1C0h+UserDataCount], 107006C2h
0x140007a5c  call    McTemplateK0qqq_EtwWriteTransfer
0x140007a61  test    r14d, r14d
0x140007a64  jnz     loc_140008688
0x140007a6a  mov     r9, [rsp+1C0h+var_158]
0x140007a6f  mov     eax, [r9]
0x140007a72  add     eax, 9
0x140007a75  cmp     eax, [rbp+0C0h+arg_28]
0x140007a7b  ja      loc_140008682
0x140007a81  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140007a88  lea     r10, WPP_GLOBAL_Control
0x140007a8f  cmp     rcx, r10
0x140007a92  jz      short loc_140007ABE
0x140007a94  test    dword ptr [rcx+2Ch], 400h
0x140007a9b  jz      short loc_140007ABE
0x140007a9d  mov     rcx, [rcx+18h]
0x140007aa1  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x140007aa8  mov     edx, 27h ; '''
0x140007aad  call    WPP_SF_
0x140007ab2  mov     r9, [rsp+1C0h+var_158]
0x140007ab7  lea     r10, WPP_GLOBAL_Control
0x140007abe  cmp     byte ptr [rdi], 3
0x140007ac1  jnz     loc_140007E9E
0x140007ac7  movzx   eax, byte ptr [rdi+1]
0x140007acb  movzx   ecx, word ptr [rdi+7]
0x140007acf  mov     [rsp+1C0h+var_170], al
0x140007ad3  cmp     al, 0FFh
0x140007ad5  jnz     short loc_140007AE2
0x140007ad7  xor     ebx, ebx
0x140007ad9  lea     r8d, [rcx+9]
0x140007add  mov     r14d, r15d
0x140007ae0  jmp     short loc_140007B04
0x140007ae2  movzx   edx, word ptr [rdi+3]
0x140007ae6  add     ecx, 9
0x140007ae9  mov     eax, [r9]
0x140007aec  mov     r8d, edx
0x140007aef  add     ecx, eax
0x140007af1  cmp     edx, ecx
0x140007af3  cmovb   r14d, ebx
0x140007af7  sub     r8d, eax
0x140007afa  cmp     edx, ecx
0x140007afc  sbb     ebx, ebx
0x140007afe  and     ebx, 6E5h
0x140007b04  test    r14d, r14d
0x140007b07  js      loc_140007EA6
0x140007b0d  mov     ecx, [r9]
0x140007b10  mov     ebx, [rbp+0C0h+arg_28]
0x140007b16  add     ecx, r8d
0x140007b19  cmp     ecx, ebx
0x140007b1b  ja      loc_140007E8F
0x140007b21  mov     [r9], ecx
0x140007b24  mov     rcx, [rbp+0C0h+var_118]
0x140007b28  mov     eax, r8d
0x140007b2b  mov     r8, [rsp+1C0h+var_168]
0x140007b30  add     rax, rdi
0x140007b33  mov     [rsp+1C0h+var_148], rax
0x140007b38  movzx   eax, word ptr [rcx+1Ch]
0x140007b3c  mov     [r8+84h], ax
0x140007b44  test    byte ptr [rdi+5], 2
0x140007b48  jz      short loc_140007B52
0x140007b4a  or      dword ptr [r8+88h], 2
0x140007b52  test    byte ptr [rdi+5], 1
0x140007b56  jz      short loc_140007B60
0x140007b58  or      dword ptr [r8+88h], 10h
0x140007b60  mov     rdi, [rbp+0C0h+pContext]
0x140007b64  movzx   eax, byte ptr [rdi+2A0h]
0x140007b6b  and     al, 18h
0x140007b6d  cmp     al, 10h
0x140007b6f  jnz     short loc_140007BA7
0x140007b71  add     rcx, 0Eh; Source1
0x140007b75  lea     rdx, InitialSecuritySignature; "BSRSPYL "
0x140007b7c  mov     r8d, 8; Length
0x140007b82  call    cs:__imp_RtlCompareMemory
0x140007b89  nop     dword ptr [rax+rax+00h]
0x140007b8e  mov     r9, [rbp+0C0h+var_140]
0x140007b92  mov     r8, [rsp+1C0h+var_168]
0x140007b97  cmp     rax, 8
0x140007b9b  jz      short loc_140007BAB
0x140007b9d  mov     byte ptr [r9+0FEh], 1
0x140007ba5  jmp     short loc_140007BAB
0x140007ba7  mov     r9, [rbp+0C0h+var_140]
0x140007bab  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x140007bb2  mov     edx, esi
0x140007bb4  shl     rdx, 8
0x140007bb8  mov     rcx, [rax]
0x140007bbb  lock inc dword ptr [rdx+rcx+94h]
0x140007bc3  mov     eax, cs:dword_14001F0D0
0x140007bc9  cmp     eax, 5
0x140007bcc  jbe     loc_140007D5C
0x140007bd2  mov     rcx, cs:qword_14001F0E8
0x140007bd9  mov     rdx, 400000000000h
0x140007be3  mov     rax, cs:qword_14001F0E0
0x140007bea  test    rdx, rax
0x140007bed  jz      loc_140007D5C
0x140007bf3  mov     rax, rcx
0x140007bf6  and     rax, rdx
0x140007bf9  cmp     rax, rcx
0x140007bfc  jnz     loc_140007D5C
0x140007c02  movzx   eax, word ptr [rdi+1A0h]
0x140007c09  mov     ecx, 2
0x140007c0e  mov     [rbp+0C0h+var_120], ax
0x140007c12  lea     rax, [rbp+0C0h+var_120]
0x140007c16  mov     [rbp+0C0h+var_C0], rax
0x140007c1a  movzx   eax, byte ptr [r9+0FEh]
0x140007c22  mov     [rbp+0C0h+var_108], eax
0x140007c25  lea     rax, [rbp+0C0h+var_108]
0x140007c29  mov     [rbp+0C0h+var_B0], rax
0x140007c2d  mov     eax, [r8+88h]
0x140007c34  mov     dword ptr [rbp+0C0h+var_110], eax
0x140007c37  lea     rax, [rbp+0C0h+var_110]
0x140007c3b  mov     [rbp+0C0h+var_A0], rax
0x140007c3f  movzx   eax, byte ptr [r8+17Dh]
0x140007c47  mov     [rsp+1C0h+var_160], al
0x140007c4b  lea     rax, [rsp+1C0h+var_160]
0x140007c50  mov     [rbp+0C0h+var_90], rax
0x140007c54  movzx   eax, byte ptr [r8+17Ch]
0x140007c5c  mov     [rsp+1C0h+var_15F], al
0x140007c60  lea     rax, [rsp+1C0h+var_15F]
0x140007c65  mov     [rbp+0C0h+var_80], rax
0x140007c69  movzx   eax, byte ptr [r8+17Eh]
0x140007c71  mov     [rsp+1C0h+var_15E], al
0x140007c75  lea     rax, [rsp+1C0h+var_15E]
0x140007c7a  mov     [rbp+0C0h+var_70], rax
0x140007c7e  mov     rax, [rdi+158h]
0x140007c85  mov     [rbp+0C0h+var_B8], rcx
0x140007c89  mov     [rbp+0C0h+var_A8], 4
0x140007c91  mov     [rbp+0C0h+var_98], 4
0x140007c99  mov     [rbp+0C0h+var_88], 1
0x140007ca1  mov     [rbp+0C0h+var_78], 1
0x140007ca9  mov     [rbp+0C0h+var_68], 1
0x140007cb1  test    rax, rax
0x140007cb4  jz      short loc_140007CBF
0x140007cb6  movzx   eax, word ptr [rax+140h]
0x140007cbd  jmp     short loc_140007CC4
0x140007cbf  mov     eax, 0FFh
0x140007cc4  mov     word ptr [rsp+1C0h+var_16C], ax
0x140007cc9  xor     r9d, r9d; RelatedActivityId
0x140007ccc  mov     [rbp+0C0h+var_58], rcx
0x140007cd0  lea     rax, [rsp+1C0h+var_16C]
0x140007cd5  mov     [rbp+0C0h+var_60], rax
0x140007cd9  xor     r8d, r8d; ActivityId
0x140007cdc  movzx   eax, cs:word_14001B4B4
0x140007ce3  mov     dword ptr [rbp+0C0h+EventDescriptor.Level], eax
0x140007ce6  mov     rax, cs:EventInformation
0x140007ced  mov     [rbp+0C0h+var_E0.Ptr], rax
0x140007cf1  mov     [rbp+0C0h+EventDescriptor.Keyword], rdx
0x140007cf5  lea     rdx, [rbp+0C0h+EventDescriptor]; EventDescriptor
0x140007cf9  mov     dword ptr [rbp+0C0h+EventDescriptor.Id], 0B000000h
0x140007d00  movzx   eax, word ptr [rax]
0x140007d03  mov     [rbp+0C0h+var_E0.Size], eax
0x140007d06  lea     rax, word_14001B4BE
0x140007d0d  mov     [rbp+0C0h+var_D0], rax
0x140007d11  lea     rax, _TraceLoggingMetadataEnd
0x140007d18  mov     dword ptr [rbp+0C0h+var_E0.0Ch], ecx
0x140007d1b  lea     rcx, _TraceLoggingMetadata
0x140007d22  sub     eax, ecx
0x140007d24  mov     [rbp+0C0h+var_C8], 82h
0x140007d2b  mov     [rbp+0C0h+var_C4], 1
0x140007d32  mov     dword ptr [rbp+0C0h+Source1], eax
0x140007d35  mov     eax, dword ptr [rbp+0C0h+Source1]
0x140007d38  mov     rcx, cs:RegHandle; RegHandle
0x140007d3f  lea     rax, [rbp+0C0h+var_E0]
0x140007d43  mov     [rsp+1C0h+UserData], rax; UserData
0x140007d48  mov     [rsp+1C0h+UserDataCount], 9; UserDataCount
0x140007d50  call    cs:__imp_EtwWriteTransfer
0x140007d57  nop     dword ptr [rax+rax+00h]
0x140007d5c  movzx   eax, [rsp+1C0h+var_170]
0x140007d61  mov     edx, 0Bh
0x140007d66  cmp     al, 75h ; 'u'
0x140007d68  jnz     loc_1400084BD
  ... truncated ...
```
