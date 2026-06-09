# Smb2CreateSuccessCompletion

- ea: `0x140005820`
- end: `0x140006cbf`
- name: `Smb2CreateSuccessCompletion`
- size: `5279`
- prototype: `__int64 __fastcall(_QWORD *pContext, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140007020`
- `0x140024760`

## callees

- `0x140004640`
- `0x140004b30`
- `0x140004d30`
- `0x140004f20`
- `0x140005820`
- `0x140006cd0`
- `0x140007bd0`
- `0x14000ab50`
- `0x14000ad90`
- `0x14000bd50`
- `0x140015100`
- `0x140015780`
- `0x140027880`
- `0x140028950`
- `0x1400297fc`
- `0x140029840`
- `0x14002a040`
- `0x14002a648`
- `0x14002a6a8`
- `0x140035464`
- `0x1400355c8`
- `0x140035c40`
- `0x140037120`
- `0x1400375c0`
- `0x140055780`
- `0x140056350`
- `0x140056930`
- `0x140056e90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140005960`
- `ntoskrnl!ExAllocatePool2` at `0x140005960`
- `ntoskrnl!ExReleasePushLockEx` at `0x140006954`
- `ntoskrnl!ExReleasePushLockEx` at `0x140038867`
- `ntoskrnl!ExReleasePushLockEx` at `0x140006954`
- `ntoskrnl!ExReleasePushLockEx` at `0x140038867`
- `ntoskrnl!RtlHashUnicodeString` at `0x140005f1c`
- `ntoskrnl!RtlHashUnicodeString` at `0x140006766`
- `ntoskrnl!RtlHashUnicodeString` at `0x140005f1c`
- `ntoskrnl!RtlHashUnicodeString` at `0x140006766`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006913`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006913`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140006018`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140006834`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140006896`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140006018`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140006834`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140006896`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140005efc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400067fa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003884e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140005efc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400067fa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003884e`
- `rdbss!RxNameCacheCheckEntry` at `0x140006850`
- `rdbss!RxNameCacheCheckEntry` at `0x140006850`
- `rdbss!RxNameCacheExpireEntry` at `0x14000664a`
- `rdbss!RxNameCacheExpireEntry` at `0x1400068fc`
- `rdbss!RxNameCacheExpireEntry` at `0x14000664a`
- `rdbss!RxNameCacheExpireEntry` at `0x1400068fc`
- `rdbss!RxNameCacheActivateEntry` at `0x140006881`
- `rdbss!RxNameCacheActivateEntry` at `0x140006881`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140005f8f`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140006664`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140006817`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140005f8f`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140006664`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140006817`
- `rdbss!RxCrackPathName` at `0x14000634c`
- `rdbss!RxCrackPathName` at `0x140006737`
- `rdbss!RxCrackPathName` at `0x1400067e5`
- `rdbss!RxCrackPathName` at `0x14000634c`
- `rdbss!RxCrackPathName` at `0x140006737`
- `rdbss!RxCrackPathName` at `0x1400067e5`
- `rdbss!RxRegisterSrvOpenWithBufferingManager` at `0x14000612f`
- `rdbss!RxRegisterSrvOpenWithBufferingManager` at `0x14000612f`
- `rdbss!RxRegisterFcbWithBufferingManager` at `0x140005d8b`
- `rdbss!RxRegisterFcbWithBufferingManager` at `0x140005d8b`
- `rdbss!RxFinishFcbInitialization` at `0x140005c54`
- `rdbss!RxFinishFcbInitialization` at `0x140006225`
- `rdbss!RxFinishFcbInitialization` at `0x140006559`
- `rdbss!RxFinishFcbInitialization` at `0x140006ca1`
- `rdbss!RxFinishFcbInitialization` at `0x140005c54`
- `rdbss!RxFinishFcbInitialization` at `0x140006225`
- `rdbss!RxFinishFcbInitialization` at `0x140006559`
- `rdbss!RxFinishFcbInitialization` at `0x140006ca1`
- `rdbss!RxIndicateChangeOfOplockStateForTarget` at `0x140006a41`
- `rdbss!RxIndicateChangeOfOplockStateForTarget` at `0x14003863e`
- `rdbss!RxIndicateChangeOfOplockStateForTarget` at `0x140006a41`
- `rdbss!RxIndicateChangeOfOplockStateForTarget` at `0x14003863e`
- `rdbss!RxCreateNetFobx` at `0x14000592d`
- `rdbss!RxCreateNetFobx` at `0x14000592d`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14000603f`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14000628f`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14000603f`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14000628f`
- `mrxsmb!MRxSmbIsStreamFile` at `0x140005ee7`
- `mrxsmb!MRxSmbIsStreamFile` at `0x140005ee7`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140006465`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000651e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400065d5`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400386dd`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140006465`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000651e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400065d5`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400386dd`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x1400058df`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x1400058df`

## pseudocode

```c
__int64 __fastcall Smb2CreateSuccessCompletion(_QWORD *pContext, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r13
  __int64 v6; // r14
  PMRX_FOBX v8; // rdi
  __int64 v9; // r15
  __int64 v10; // rax
  char v11; // r12
  char v12; // al
  __int64 v13; // r8
  __int64 v14; // rcx
  PMRX_FOBX NetFobx; // rax
  WCHAR *Pool2; // rax
  unsigned int v17; // r13d
  bool v18; // di
  __int64 v19; // rax
  int v20; // ecx
  _DWORD *v21; // rdx
  int v22; // r12d
  int v23; // ecx
  __int64 v24; // r10
  unsigned int v25; // eax
  ULONG v26; // ecx
  __int64 v27; // r9
  int v28; // eax
  __int64 v29; // rdi
  int v30; // r11d
  int v31; // edx
  int v32; // r10d
  __int64 v33; // r8
  unsigned int v34; // ecx
  int v35; // edx
  int v36; // r12d
  __int64 v37; // r8
  int v38; // eax
  ULONG v39; // eax
  __int64 *v40; // rax
  ULONG v41; // r11d
  __int64 v42; // rdi
  ULONG v43; // r12d
  int v44; // r10d
  int v45; // r9d
  int v46; // r8d
  int v47; // ecx
  int v48; // r9d
  __int64 v49; // r8
  unsigned int v50; // edx
  int v51; // ecx
  char v52; // al
  __int64 v53; // r12
  __int64 v54; // r8
  int v55; // edi
  __int64 v56; // rcx
  __int64 v57; // r12
  __int64 v58; // rdi
  __int64 v59; // rcx
  __int64 v61; // r9
  bool v62; // zf
  __int64 v63; // rax
  struct _NAME_CACHE_CONTROL_ *v64; // rdi
  __int64 v65; // r15
  struct _NAME_CACHE *i; // rax
  __int64 v67; // rax
  __int64 v68; // rcx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // rcx
  int FileInformationFromDirCache; // eax
  __int64 *v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rax
  _DWORD *v76; // r15
  __int64 v77; // r12
  __int64 v78; // rdi
  int v79; // edx
  int v80; // r8d
  int v81; // eax
  unsigned int v82; // r12d
  __int64 v83; // rax
  __int64 v84; // r8
  PDEVICE_OBJECT v85; // rcx
  __int64 v86; // r9
  __int64 v87; // rdx
  __int16 v88; // cx
  __int64 v89; // rax
  __int16 v90; // cx
  __int64 v91; // rax
  __int64 v92; // rdi
  struct _NAME_CACHE_CONTROL_ *v93; // r15
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v95; // rdi
  struct _LIST_ENTRY *Flink; // r12
  __int64 v97; // rax
  __int64 v98; // rcx
  int v99; // eax
  __int16 v100; // cx
  __int64 v101; // r9
  unsigned int v102; // edi
  __int64 v103; // rcx
  __int64 v104; // rdi
  __int64 ConfigurationBlock; // rax
  unsigned __int64 v106; // rcx
  __int64 v107; // r10
  int ShadowSrvOpen; // eax
  int Src; // [rsp+28h] [rbp-E8h]
  size_t Size; // [rsp+30h] [rbp-E0h]
  int v111; // [rsp+90h] [rbp-80h]
  bool v112; // [rsp+94h] [rbp-7Ch]
  char v113; // [rsp+95h] [rbp-7Bh]
  unsigned int v114; // [rsp+98h] [rbp-78h]
  ULONG v115; // [rsp+98h] [rbp-78h]
  ULONG HashValue[2]; // [rsp+A0h] [rbp-70h] BYREF
  unsigned int v117; // [rsp+A8h] [rbp-68h]
  int v118; // [rsp+ACh] [rbp-64h]
  int v119; // [rsp+B0h] [rbp-60h] BYREF
  __int128 v120; // [rsp+B8h] [rbp-58h] BYREF
  UNICODE_STRING String1; // [rsp+C8h] [rbp-48h] BYREF
  __int128 v122; // [rsp+D8h] [rbp-38h] BYREF
  UNICODE_STRING String; // [rsp+E8h] [rbp-28h] BYREF
  __int128 v124; // [rsp+F8h] [rbp-18h] BYREF
  _BYTE InitPacket[80]; // [rsp+110h] [rbp+0h] BYREF
  _QWORD v126[18]; // [rsp+160h] [rbp+50h] BYREF
  _QWORD v127[18]; // [rsp+1F0h] [rbp+E0h] BYREF
  __int128 v128; // [rsp+280h] [rbp+170h] BYREF
  __int128 v129; // [rsp+290h] [rbp+180h]
  __int128 v130; // [rsp+2A0h] [rbp+190h]
  __int64 v131; // [rsp+2B0h] [rbp+1A0h]
  _OWORD v132[2]; // [rsp+2B8h] [rbp+1A8h] BYREF
  __int64 v133; // [rsp+2D8h] [rbp+1C8h]

  v4 = pContext[9];
  v6 = pContext[7];
  v8 = (PMRX_FOBX)pContext[8];
  *(_QWORD *)&v122 = a2;
  v9 = *(_QWORD *)(v6 + 136);
  *(_QWORD *)&String1.Length = *(_QWORD *)(v4 + 48);
  v10 = pContext[81];
  *(_QWORD *)&String.Length = a4;
  *(_QWORD *)&v120 = v4;
  v11 = *(_BYTE *)(v10 + 77);
  memset(InitPacket, 0, 0x4Cu);
  v128 = 0;
  v131 = 0;
  v129 = 0;
  v119 = 0;
  v130 = 0;
  v112 = (_QWORD)v122 == 0;
  v12 = SmbCeCheckServerEntryDialect(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 120) + 32LL) + 32LL), 3, 0, 0);
  v13 = *(_QWORD *)&String1.Length;
  v113 = v12;
  *(_OWORD *)(*(_QWORD *)&String1.Length + 28LL) = *(_OWORD *)(a3 + 64);
  *(_QWORD *)(v4 + 104) = *(_QWORD *)(a3 + 64);
  *(_QWORD *)(v4 + 112) = 0;
  v14 = (__int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_iii(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
      pContext,
      *(_QWORD *)(v13 + 28),
      *(_QWORD *)(v13 + 36));
  }
  if ( !v8 )
  {
    NetFobx = RxCreateNetFobx((PRX_CONTEXT)pContext, (PMRX_SRV_OPEN)v4);
    pContext[8] = NetFobx;
    v8 = NetFobx;
    if ( !NetFobx )
    {
      v17 = -1073741670;
      v85 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return v17;
      }
      v86 = v120;
      v87 = 20;
      goto LABEL_244;
    }
  }
  if ( !v8->UnicodeQueryTemplate.Buffer )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(256, 56, 1834182982);
    if ( Pool2 )
    {
      v14 = 58400;
      *Pool2 = -7136;
      v8->UnicodeQueryTemplate.Buffer = Pool2;
      goto LABEL_7;
    }
    v17 = -1073741670;
    v85 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return v17;
    }
    v86 = pContext[8];
    v87 = 21;
LABEL_244:
    WPP_SF_qD(v85->AttachedDevice, v87, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids, v86, -1073741670);
    return v17;
  }
LABEL_7:
  v17 = 0;
  v18 = 0;
  if ( (*(_DWORD *)(v9 + 8) & 2) == 0 )
  {
    v14 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids, pContext);
    }
  }
  pContext[75] = *(unsigned int *)(a3 + 4);
  v19 = pContext[84];
  if ( v19 )
    v18 = (*(_DWORD *)(v19 + 12) & 0x40000000) != 0;
  switch ( v11 )
  {
    case 0:
      v20 = *(_DWORD *)(a3 + 56);
      v21 = (_DWORD *)(a3 + 56);
      v118 = v20 & 0x10;
      v22 = -(v118 != 0);
      v23 = v20 & 0x400;
      if ( v113 )
      {
        if ( v23 )
          v117 = 2;
        else
          v117 = 4 - ((*(_BYTE *)(a3 + 3) & 1) != 0);
      }
      else if ( v23 )
      {
        v117 = 2;
      }
      else if ( (*((_DWORD *)pContext + 135) & 0x200000) != 0 )
      {
        v117 = 4;
      }
      else
      {
        HashValue[0] = 40;
        v133 = 0;
        memset(v132, 0, sizeof(v132));
        FileInformationFromDirCache = Smb2QueryFileInformationFromDirCache(
                                        (_DWORD)pContext,
                                        (_DWORD)v21,
                                        1,
                                        4,
                                        (__int64)v132,
                                        (__int64)HashValue);
        v21 = (_DWORD *)(a3 + 56);
        v117 = 1;
        if ( FileInformationFromDirCache >= 0 )
          v117 = 4 - ((v133 & 0x400) != 0);
      }
      v24 = *(_QWORD *)&String1.Length;
      if ( (((*(_BYTE *)(v6 + 355) & 0x3C) - 12) & 0xFFFFFFFB) == 0 && (*v21 & 0x400) != 0 )
        *(_DWORD *)(*(_QWORD *)&String1.Length + 8LL) |= 0x10000000u;
      v25 = *(unsigned __int8 *)(a3 + 2);
      if ( (_BYTE)v25 != 0xFF )
      {
        v26 = *(_DWORD *)(v9 + 60);
        v27 = *(unsigned __int8 *)(a3 + 2);
        *(_DWORD *)(v24 + 24) = v25;
        *(_DWORD *)(v24 + 360) = 0;
        v114 = v25;
        v28 = *(_DWORD *)(v6 + 196);
        HashValue[0] = v26;
        if ( !(*(_DWORD *)(v6 + 192) + v28) || (_QWORD)v122 && (v26 < 8 || (unsigned __int8)v27 >= 8u) )
        {
          *(_DWORD *)InitPacket = v117;
          *(_QWORD *)&InitPacket[16] = &v119;
          *(_QWORD *)&InitPacket[24] = a3 + 8;
          *(_QWORD *)&InitPacket[32] = a3 + 16;
          *(_QWORD *)&InitPacket[40] = a3 + 24;
          *(_QWORD *)&InitPacket[48] = a3 + 32;
          v119 = 1;
          *(_QWORD *)&InitPacket[8] = v21;
          if ( v18 )
          {
            v73 = &MaxFileSize;
            *(_QWORD *)&InitPacket[56] = &MaxFileSize;
          }
          else
          {
            *(_QWORD *)&InitPacket[56] = a3 + 40;
            v73 = (__int64 *)(a3 + 48);
          }
          *(_QWORD *)&InitPacket[72] = v73;
          *(_QWORD *)&InitPacket[64] = v73;
          RxFinishFcbInitialization((PMRX_FCB)v6, (RX_FILE_TYPE)(v22 + 60450), (PFCB_INIT_PACKET)InitPacket);
          v27 = v114;
        }
        v29 = pContext[9];
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
            v29,
            v27,
            0);
          v27 = v114;
        }
        v30 = 0;
        v31 = 0;
        if ( !(_BYTE)v27 )
        {
          v32 = 3;
LABEL_31:
          v33 = *(_QWORD *)(v29 + 32);
          v34 = v31 & 0xF7FFFFFF;
          if ( (*(_DWORD *)(v33 + 232) & 0x200) == 0 )
            v34 = v31;
          v35 = *((_DWORD *)pContext + 128);
          if ( (v35 & 1) == 0 && (v35 & 2) != 0 )
          {
            v34 &= 0xF5FFFFFF;
            v32 = 3;
          }
          if ( (v35 & 4) != 0 && (v35 & 2) == 0 )
          {
            v34 &= ~0x8000000u;
            v32 |= 2u;
          }
          v36 = v118;
          if ( (v35 & 0x23) == 0 || v118 )
            v32 |= 0x200u;
          if ( *(_WORD *)v33 == 0xEC21 )
            *(_DWORD *)(v29 + 72) |= 0x80u;
          v37 = v120;
          *((_DWORD *)pContext + 184) = v30;
          *((_DWORD *)pContext + 185) = v34;
          *(_DWORD *)(v29 + 72) |= v32;
          if ( (*(_DWORD *)(v37 + 72) & 0x200) == 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 )
            {
              v102 = HashValue[0];
            }
            else
            {
              v102 = HashValue[0];
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_DDqq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  24,
                  WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
                  v27,
                  HashValue[0],
                  v6,
                  v37);
                LODWORD(v27) = v114;
                v37 = v120;
              }
            }
            if ( (unsigned int)v27 >= v102 )
              *(_DWORD *)(v9 + 60) = v27;
          }
          goto LABEL_69;
        }
        v32 = 0;
        if ( (_DWORD)v27 != 1 )
        {
          if ( (_DWORD)v27 != 8 )
          {
            if ( (_DWORD)v27 != 9 )
            {
LABEL_29:
              if ( (_BYTE)v27 == 1 )
                v32 = 2;
              goto LABEL_31;
            }
            v31 = 4196352;
            v30 = 16;
          }
          v30 |= 6u;
          v31 |= 0x8200000u;
        }
        v30 |= 9u;
        v31 |= 0x2100000u;
        goto LABEL_29;
      }
      v39 = 0;
      v41 = *(_DWORD *)(v9 + 64);
      HashValue[0] = v41;
      v115 = 0;
      if ( !*(_QWORD *)&String.Length )
      {
LABEL_45:
        *(_DWORD *)(v24 + 360) = v39;
        *(_DWORD *)(v24 + 24) = *(unsigned __int8 *)(a3 + 2);
        if ( !(*(_DWORD *)(v6 + 192) + *(_DWORD *)(v6 + 196)) || (v41 & 3) != 3 && (v41 & 4) == 0 )
        {
          *(_DWORD *)InitPacket = v117;
          *(_QWORD *)&InitPacket[16] = &v119;
          *(_QWORD *)&InitPacket[24] = a3 + 8;
          *(_QWORD *)&InitPacket[32] = a3 + 16;
          *(_QWORD *)&InitPacket[40] = a3 + 24;
          *(_QWORD *)&InitPacket[48] = a3 + 32;
          v119 = 1;
          *(_QWORD *)&InitPacket[8] = v21;
          if ( v18 )
          {
            v40 = &MaxFileSize;
            *(_QWORD *)&InitPacket[56] = &MaxFileSize;
          }
          else
          {
            *(_QWORD *)&InitPacket[56] = a3 + 40;
            v40 = (__int64 *)(a3 + 48);
          }
          *(_QWORD *)&InitPacket[72] = v40;
          *(_QWORD *)&InitPacket[64] = v40;
          RxFinishFcbInitialization((PMRX_FCB)v6, (RX_FILE_TYPE)(v22 + 60450), (PFCB_INIT_PACKET)InitPacket);
          v41 = HashValue[0];
        }
        v42 = pContext[9];
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v43 = v115;
        }
        else
        {
          v43 = v115;
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
            v42,
            255,
            v115);
          v41 = HashValue[0];
        }
        v44 = 0;
        v45 = (v43 & 1) != 0 ? 0x2100000 : 0;
        v46 = (v43 & 1) != 0 ? 9 : 0;
        if ( (v43 & 4) != 0 )
        {
          v46 |= 6u;
          v45 |= 0x8200000u;
        }
        v47 = v45 | 0x400800;
        if ( (v43 & 2) == 0 )
          v47 = v45;
        v48 = v46 | 0x20;
        if ( (v43 & 2) == 0 )
          v48 = v46;
        v49 = *(_QWORD *)(v42 + 32);
        v50 = v47 & 0xF7FFFFFF;
        if ( (*(_DWORD *)(v49 + 232) & 0x200) == 0 )
          v50 = v47;
        v51 = *((_DWORD *)pContext + 128);
        if ( (v51 & 1) == 0 && (v51 & 2) != 0 )
        {
          v50 &= 0xF5FFFFFF;
          v44 = 3;
        }
        if ( (v51 & 4) != 0 && (v51 & 2) == 0 )
        {
          v50 &= ~0x8000000u;
          v44 |= 2u;
        }
        if ( *(_WORD *)v49 == 0xEC21 )
          *(_DWORD *)(v42 + 72) |= 0x80u;
        v37 = v120;
        *((_DWORD *)pContext + 184) = v48;
        *((_DWORD *)pContext + 185) = v50;
        *(_DWORD *)(v42 + 72) |= v44;
        if ( (*(_DWORD *)(v37 + 72) & 0x200) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_DDqq(
              WPP_GLOBAL_Control->AttachedDevice,
              23,
              WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
              v43,
              v41,
              v6,
              v37);
            v37 = v120;
          }
          *(_DWORD *)(v9 + 60) = 255;
          *(_DWORD *)(v9 + 64) = v43;
        }
        v36 = v118;
LABEL_69:
        *(_DWORD *)(v9 + 56) = *(_DWORD *)(a3 + 56);
        v52 = *(_BYTE *)(a3 + 2);
        if ( v52 == -1 )
        {
          RxRegisterFcbWithBufferingManager(v6);
        }
        else if ( (v52 == 1 || (unsigned __int8)(v52 - 8) <= 1u) && !v36 )
        {
          RxRegisterSrvOpenWithBufferingManager(v37);
        }
        v53 = *(_QWORD *)&String.Length;
        v54 = *(_QWORD *)&String1.Length;
        if ( *(_QWORD *)&String.Length && (**(_BYTE **)&String.Length & 0x60) != 0 )
          *(_DWORD *)(*(_QWORD *)&String1.Length + 8LL) |= 4u;
        v55 = *(_DWORD *)(v54 + 4);
        *(_QWORD *)HashValue = 0;
        Smb2CompleteSrvOpenInitialization(v120, v112, 0);
        if ( v53 && (*(_BYTE *)v53 & 0x40) != 0 && (*(_DWORD *)(v53 + 48) & 2) != 0 )
        {
          if ( *(_BYTE *)(MRxSmbGetConfigurationBlock(v56) + 238) != 1 )
            *(_DWORD *)(v120 + 72) |= 0x1000u;
          v103 = *(_QWORD *)&String1.Length;
          *(_DWORD *)(*(_QWORD *)&String1.Length + 8LL) |= 0x20u;
          v104 = 10000LL * *(unsigned int *)(v53 + 52);
          *(_QWORD *)(v103 + 256) = v104;
          ConfigurationBlock = MRxSmbGetConfigurationBlock(v103);
          v57 = v120;
          v106 = v104 * *(unsigned int *)(ConfigurationBlock + 244);
          v58 = v122;
          *(_QWORD *)(*(_QWORD *)&String1.Length + 256LL) = v106 >> 3;
          if ( pContext[5] )
            Smb2RegisterResilientHandle(*(_QWORD *)(*(_QWORD *)(v58 + 72) + 24LL), v57);
        }
        else
        {
          if ( (_QWORD)v122
            && (*(_BYTE *)(v122 + 2408) & 0x20) != 0
            && (!v118 || *((_DWORD *)pContext + 134) != 1 || (pContext[64] & 0x20F005E) != 0) )
          {
            v57 = v120;
            if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x400000) != 0 )
            {
              v107 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v120 + 32) + 120LL) + 88LL);
              McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
                **(_WORD **)(v120 + 80) >> 1,
                (unsigned int)HandlePersistenceNotGranted,
                *(_QWORD *)(v120 + 80),
                *(_DWORD *)&String1.Length,
                *(_QWORD *)(*(_QWORD *)&String1.Length + 28LL),
                *(_QWORD *)(*(_QWORD *)&String1.Length + 36LL),
                *(_QWORD *)&String1.Length + 264LL,
                v55,
                *(_WORD *)(*(_QWORD *)&String1.Length + 4LL),
                0,
                0,
                *(_WORD *)v107 >> 1,
                *(_QWORD *)(v107 + 8),
                **(_WORD **)(v120 + 80) >> 1,
                *(_QWORD *)(*(_QWORD *)(v120 + 80) + 8LL),
                0,
                0);
              v58 = v122;
              goto LABEL_76;
            }
          }
          else
          {
            v57 = v120;
          }
          v58 = v122;
        }
LABEL_76:
        v59 = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 120) + 32LL) + 32LL) + 716LL);
        if ( (v59 & 0x80u) != 0LL )
        {
          v89 = MRxSmbGetConfigurationBlock(v59);
          if ( !v118 && !*(_BYTE *)(v89 + 230) )
          {
            ShadowSrvOpen = Smb2CreateShadowSrvOpen(pContext);
            if ( ShadowSrvOpen < 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_qqD(
                WPP_GLOBAL_Control->AttachedDevice,
                25,
                WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
                pContext,
                v57,
                ShadowSrvOpen);
            }
          }
        }
        if ( !v58 )
          return v17;
        if ( (unsigned __int8)Smb2ShouldUpdateFileIdentityCache(pContext, v9) )
          Smb2UpdateFileIdentityCacheEntryEx(
            pContext,
            *(_QWORD *)(*(_QWORD *)(pContext[7] + 120LL) + 40LL) + 192LL,
            v9 + 24,
            v117,
            v9 + 24);
        v62 = *(_DWORD *)(a3 + 4) == 2;
        *(_QWORD *)&v130 = *(_QWORD *)(a3 + 40);
        *((_QWORD *)&v129 + 1) = *(_QWORD *)(a3 + 32);
        *(_QWORD *)&v128 = *(_QWORD *)(a3 + 8);
        *((_QWORD *)&v130 + 1) = *(_QWORD *)(a3 + 48);
        LODWORD(v131) = *(_DWORD *)(a3 + 56);
        *((_QWORD *)&v128 + 1) = *(_QWORD *)(a3 + 16);
        *(_QWORD *)&v129 = *(_QWORD *)(a3 + 24);
        if ( v62 && v118 )
        {
          LOBYTE(v61) = 1;
          Smb2InvalidateFileNotFoundCacheEx(pContext, *(_QWORD *)(*(_QWORD *)(v6 + 120) + 40LL) + 560LL, 0, v61);
        }
        else
        {
          v63 = *(_QWORD *)(v6 + 120);
          String = 0;
          v64 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v63 + 40) + 560LL);
          memset(v126, 0, 0x88u);
          v65 = pContext[7];
          MRxSmbIsStreamFile(v65 + 360, &String);
          ExAcquirePushLockExclusiveEx(&Smb2FileNotFoundCacheLock, 0);
          HashValue[0] = 0;
          RtlHashUnicodeString(&String, 1u, 0, HashValue);
          memset(v126, 0, 0x88u);
          LODWORD(v126[0]) = 8973226;
          v126[13] = &v126[12];
          v126[12] = &v126[12];
          v126[9] = &v126[8];
          v126[8] = &v126[8];
          LODWORD(v126[14]) = HashValue[0];
          for ( i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v64, &String, 0, v126);
                i;
                i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v64, &String, 0, v126) )
          {
            RxNameCacheExpireEntry(v64, i);
          }
          v67 = v126[12];
          if ( (_QWORD *)v126[12] != &v126[12] )
          {
            if ( *(_QWORD **)(v126[12] + 8LL) != &v126[12] )
              goto LABEL_152;
            v68 = v126[13];
            if ( *(_QWORD **)v126[13] != &v126[12] )
              goto LABEL_152;
            *(_QWORD *)v126[13] = v126[12];
            *(_QWORD *)(v67 + 8) = v68;
            v126[13] = &v126[12];
            v126[12] = &v126[12];
          }
          if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x200) != 0 )
          {
            LOWORD(Src) = *(_WORD *)(v65 + 360) >> 1;
            McTemplateK0pphzr2q_EtwWriteTransfer(
              (unsigned __int16)Src,
              (unsigned int)SmbInvalidateFNFCache,
              (_DWORD)pContext + 412,
              (_DWORD)pContext,
              pContext[7],
              Src,
              *(_QWORD *)(v65 + 368));
          }
          ExReleasePushLockExclusiveEx(&Smb2FileNotFoundCacheLock, 0);
        }
        v69 = pContext[7];
        v70 = *(_QWORD *)(v69 + 120);
        v71 = *(_QWORD *)(v70 + 32);
        if ( (*(_DWORD *)(v71 + 96) & 0x80u) != 0
          || (*(_BYTE *)(*(_QWORD *)(v71 + 32) + 764LL) & 2) == 0
          || (*(_DWORD *)(*(_QWORD *)(v69 + 136) + 8LL) & 1) != 0
          || *(_BYTE *)(v70 + 77)
          || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(pContext[9] + 40LL) + 40LL) + 424LL) + 184LL) & 0x800000) != 0 )
        {
          MRxSmbGetInstanceConfigurationBlock(pContext[10]);
          return v17;
        }
        if ( !*(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(pContext[10]) + 12) )
          return v17;
        LODWORD(Size) = 56;
        Smb2UpdateFileInfoCacheEntry(
          (int)pContext,
          *(_QWORD *)(*(_QWORD *)(v6 + 120) + 40LL) + 376,
          1,
          34,
          0,
          &v128,
          Size);
        if ( *(_DWORD *)(a3 + 4) == 2 )
        {
LABEL_179:
          v91 = *(_QWORD *)(v6 + 120);
          String = 0;
          v92 = *(_QWORD *)(v91 + 40);
          v122 = 0;
          memset(v127, 0, 0x88u);
          RxCrackPathName(pContext[7] + 360LL, &String, &v122, 0);
          if ( !(_WORD)v122 )
            goto LABEL_134;
          HashValue[0] = 0;
          v93 = (struct _NAME_CACHE_CONTROL_ *)(v92 + 1112);
          RtlHashUnicodeString(&String, 1u, 0, HashValue);
          memset(v127, 0, 0x88u);
          LODWORD(v127[0]) = 8973226;
          v127[13] = &v127[12];
          v127[12] = &v127[12];
          v127[9] = &v127[8];
          v127[8] = &v127[8];
          LODWORD(v127[14]) = HashValue[0];
          while ( 1 )
          {
            v124 = 0;
            RxCrackPathName(&String, 0, &v124, 0);
            ExAcquirePushLockExclusiveEx(&Smb2DirCacheLock, 0);
            while ( 1 )
            {
              Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v93, &v124, 0, v127);
              v95 = Entry;
              if ( !Entry )
              {
                ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
                goto LABEL_189;
              }
              if ( RxNameCacheCheckEntry(Entry, 0) == RX_NC_SUCCESS )
                break;
              RxNameCacheExpireEntry(v93, v95);
            }
            Flink = v95->Link.Flink;
            if ( Flink )
              Smb2ReferenceDirCacheObject(v95->Link.Flink);
            RxNameCacheActivateEntry(v93, v95, 0, 0);
            ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
            if ( !Flink )
              break;
            v99 = (int)Flink[2].Flink;
            if ( !v99 || v99 == 3 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_ZqZ(
                  WPP_GLOBAL_Control->AttachedDevice,
                  25,
                  v84,
                  (unsigned int)&v122,
                  (char)Flink,
                  (__int64)&String);
              }
              ExAcquirePushLockExclusiveEx(&Flink[6].Blink, 0);
              _InterlockedIncrement((volatile signed __int32 *)&Flink[4].Flink + 1);
              ExReleasePushLockEx(&Flink[6].Blink, 0);
            }
            Smb2DereferenceDirCacheObject(Flink);
          }
LABEL_189:
          v97 = v127[12];
          if ( (_QWORD *)v127[12] == &v127[12] )
            goto LABEL_134;
          if ( *(_QWORD **)(v127[12] + 8LL) == &v127[12] )
          {
            v98 = v127[13];
            if ( *(_QWORD **)v127[13] == &v127[12] )
            {
              *(_QWORD *)v127[13] = v127[12];
              *(_QWORD *)(v97 + 8) = v98;
              goto LABEL_134;
            }
          }
LABEL_152:
          __fastfail(3u);
        }
        v74 = pContext[7];
        v75 = pContext[9];
        HashValue[0] = 0;
        v76 = 0;
        v77 = *(_QWORD *)(v74 + 136);
        *(_QWORD *)&String.Length = *(_QWORD *)(*(_QWORD *)(v75 + 40) + 40LL);
        *(_QWORD *)&v122 = v74 + 360;
        v78 = *(_QWORD *)(*(_QWORD *)&String.Length + 424LL);
        v120 = 0;
        String1 = 0;
        v124 = 0;
        RxCrackPathName(v74 + 360, &v120, &String1, &v124);
        if ( String1.Length )
        {
          v81 = *(_DWORD *)(v77 + 8);
          v82 = -1073741802;
          if ( (v81 & 1) != 0 )
            goto LABEL_128;
          v83 = Smb2FindOrCreateDirCacheObject(pContext, v78 + 1112, &v120, 0, 0, 0);
          v76 = (_DWORD *)v83;
          if ( !v83 || *(_DWORD *)(v83 + 32) )
            goto LABEL_128;
          ExAcquirePushLockSharedEx(v83 + 104, 0);
          v82 = QueryFileInfoFromDirectoryCache(v76, &String1, 0, 0, (__int64)HashValue);
          ExReleasePushLockEx(v76 + 26, 0);
          if ( v82 != -1073741275 && v82 != -1073741533 )
          {
            if ( v82 == -1073741789 )
              v82 = (_WORD)v124 != 0 ? 0xC0000016 : 0;
LABEL_128:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_DqZ(WPP_GLOBAL_Control->AttachedDevice, v79, v80, v82, (char)v76, v122);
            }
            if ( v76 )
              Smb2DereferenceDirCacheObject(v76);
            if ( v82 != -1073741772 )
            {
              Smb2UpdateSingleFileInDirInfoCache(pContext, *(_QWORD *)(*(_QWORD *)(v6 + 120) + 40LL) + 1112LL, &v128);
LABEL_134:
              if ( *(_DWORD *)(a3 + 4) == 2 )
              {
                LOBYTE(v84) = 1;
                Smb2InvalidateFileAbeStatusCacheEntry(pContext, *(_QWORD *)(*(_QWORD *)(v6 + 120) + 40LL) + 1296LL, v84);
              }
              Smb2InsertFileAbeStatusCacheEntry(pContext, *(_QWORD *)(*(_QWORD *)(v6 + 120) + 40LL) + 1296LL);
              return v17;
            }
            goto LABEL_179;
          }
          if ( !v76[17] )
          {
            _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)&String.Length + 560LL));
            v82 = -1073741772;
            goto LABEL_128;
          }
        }
        v82 = -1073741802;
        goto LABEL_128;
      }
      if ( (**(_BYTE **)&String.Length & 0x10) != 0 )
        v111 = *(_DWORD *)(*(_QWORD *)&String.Length + 40LL);
      else
        v111 = -1;
      if ( (*(_DWORD *)(*(_QWORD *)&String.Length + 44LL) & 2) != 0 )
        goto LABEL_163;
      if ( v111 != -1 )
      {
        if ( (*(_DWORD *)(v6 + 156) & 0x10) == 0 )
        {
          v115 = *(_DWORD *)(*(_QWORD *)&String.Length + 36LL);
LABEL_112:
          v38 = v111;
          goto LABEL_43;
        }
        v88 = *(_WORD *)(v9 + 68);
        if ( (unsigned __int16)(v88 - v111) <= 0x7FFFu && v88 != (_WORD)v111 )
        {
LABEL_163:
          v39 = v41;
          v115 = v41;
          goto LABEL_45;
        }
      }
      v115 = *(_DWORD *)(*(_QWORD *)&String.Length + 36LL);
      if ( (*(_DWORD *)(v6 + 156) & 0x10) != 0 && v41 )
      {
        if ( v41 == v115 )
        {
          if ( v111 == -1 )
            goto LABEL_44;
          v90 = *(_WORD *)(v9 + 68);
          if ( (unsigned __int16)(v111 - v90) > 0x7FFFu )
            goto LABEL_112;
          v38 = v111;
          if ( (_WORD)v111 == v90 )
            goto LABEL_43;
LABEL_208:
          *(_BYTE *)(v9 + 80) = 1;
          RxIndicateChangeOfOplockStateForTarget(
            *(_QWORD *)(*(_QWORD *)(v6 + 120) + 32LL),
            v6,
            0,
            32 * (unsigned int)(unsigned __int16)v38);
          v41 = HashValue[0];
          v21 = (_DWORD *)(a3 + 56);
          v24 = *(_QWORD *)&String1.Length;
          goto LABEL_112;
        }
        if ( v41 == (v41 & v115) )
        {
          if ( v111 == -1 )
            goto LABEL_44;
          v100 = *(_WORD *)(v9 + 68);
          if ( (unsigned __int16)(v111 - v100 - 1) > 0x7FFFu )
            goto LABEL_112;
          v38 = v111;
          if ( (_WORD)v111 - 1 == v100 )
            goto LABEL_43;
          LOWORD(v38) = v111 - 1;
          goto LABEL_208;
        }
        *(_BYTE *)(v9 + 80) = 1;
        if ( v111 == -1 )
          v101 = 0;
        else
          v101 = 32 * (unsigned int)(unsigned __int16)v111;
        RxIndicateChangeOfOplockStateForTarget(*(_QWORD *)(*(_QWORD *)(v6 + 120) + 32LL), v6, 0, v101);
        v41 = HashValue[0];
        v21 = (_DWORD *)(a3 + 56);
        v24 = *(_QWORD *)&String1.Length;
      }
      v38 = v111;
      if ( v111 == -1 )
      {
LABEL_44:
        v39 = v115;
        goto LABEL_45;
      }
LABEL_43:
      *(_DWORD *)(v9 + 68) = v38;
      goto LABEL_44;
    case 1:
      *(_DWORD *)(pContext[81] + 104LL) = *(_DWORD *)(MRxSmbGetConfigurationBlock(v14) + 108);
      *((_DWORD *)pContext + 180) = 1;
      *(_QWORD *)((char *)pContext + 724) = 1;
      RxFinishFcbInitialization((PMRX_FCB)v6, (RX_FILE_TYPE)60450, 0);
      *(_QWORD *)HashValue = 0;
      break;
    case 3:
      RxFinishFcbInitialization((PMRX_FCB)v6, (RX_FILE_TYPE)60455, 0);
      pContext[92] = 0;
      *(_QWORD *)HashValue = 0;
      break;
    default:
      return v17;
  }
  Smb2CompleteSrvOpenInitialization(v120, v112, *(_QWORD *)HashValue);
  return v17;
}

```

## disassembly

```asm
0x140005820  push    rbp
0x140005822  push    rbx
0x140005823  push    rsi
0x140005824  push    rdi
0x140005825  push    r12
0x140005827  push    r13
0x140005829  push    r14
0x14000582b  push    r15
0x14000582d  lea     rbp, [rsp-1E8h]
0x140005835  sub     rsp, 2F8h
0x14000583c  mov     rax, cs:__security_cookie
0x140005843  xor     rax, rsp
0x140005846  mov     [rbp+220h+var_50], rax
0x14000584d  mov     r13, [rcx+48h]
0x140005851  mov     rsi, r8
0x140005854  mov     r14, [rcx+38h]
0x140005858  mov     rbx, rcx
0x14000585b  mov     rdi, [rcx+40h]
0x14000585f  mov     r8d, 4Ch ; 'L'; Size
0x140005865  mov     qword ptr [rbp+220h+var_258], rdx
0x140005869  xor     edx, edx; Val
0x14000586b  mov     rax, [r13+30h]
0x14000586f  mov     r15, [r14+88h]
0x140005876  mov     qword ptr [rbp+220h+String1.Length], rax
0x14000587a  mov     rax, [rcx+288h]
0x140005881  lea     rcx, [rbp+220h+InitPacket]; void *
0x140005885  mov     qword ptr [rbp+220h+String.Length], r9
0x140005889  mov     qword ptr [rbp+220h+var_278], r13
0x14000588d  movzx   r12d, byte ptr [rax+4Dh]
0x140005892  xor     eax, eax
0x140005894  mov     dword ptr [rbp+220h+InitPacket.pAttributes+4], eax
0x140005897  call    memset
0x14000589c  xor     eax, eax
0x14000589e  xorps   xmm0, xmm0
0x1400058a1  cmp     qword ptr [rbp+220h+var_258], rax
0x1400058a5  mov     edx, 3
0x1400058aa  movups  [rbp+220h+var_B0], xmm0
0x1400058b1  mov     [rbp+220h+var_80], rax
0x1400058b8  movups  [rbp+220h+var_A0], xmm0
0x1400058bf  mov     [rbp+220h+var_280], eax
0x1400058c2  movups  [rbp+220h+var_90], xmm0
0x1400058c9  mov     rax, [r14+78h]
0x1400058cd  setz    [rbp+220h+var_29C]
0x1400058d1  xor     r9d, r9d
0x1400058d4  xor     r8d, r8d
0x1400058d7  mov     rcx, [rax+20h]
0x1400058db  mov     rcx, [rcx+20h]
0x1400058df  call    cs:__imp_SmbCeCheckServerEntryDialect
0x1400058e6  nop     dword ptr [rax+rax+00h]
0x1400058eb  movups  xmm0, xmmword ptr [rsi+40h]
0x1400058ef  mov     r8, qword ptr [rbp+220h+String1.Length]
0x1400058f3  mov     [rbp+220h+var_29B], al
0x1400058f6  movups  xmmword ptr [r8+1Ch], xmm0
0x1400058fb  mov     rax, [rsi+40h]
0x1400058ff  mov     [r13+68h], rax
0x140005903  mov     qword ptr [r13+70h], 0
0x14000590b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005912  lea     rax, WPP_GLOBAL_Control
0x140005919  cmp     rcx, rax
0x14000591c  jnz     loc_140005AB7
0x140005922  test    rdi, rdi
0x140005925  jnz     short loc_140005949
0x140005927  mov     rdx, r13; MrxSrvOpen
0x14000592a  mov     rcx, rbx; RxContext
0x14000592d  call    cs:__imp_RxCreateNetFobx
0x140005934  nop     dword ptr [rax+rax+00h]
0x140005939  mov     [rbx+40h], rax
0x14000593d  mov     rdi, rax
0x140005940  test    rax, rax
0x140005943  jz      loc_1400064C0
0x140005949  cmp     qword ptr [rdi+38h], 0
0x14000594e  jnz     short loc_140005981
0x140005950  mov     edx, 38h ; '8'
0x140005955  mov     ecx, 100h
0x14000595a  mov     r8d, 6D536946h
0x140005960  call    cs:__imp_ExAllocatePool2
0x140005967  nop     dword ptr [rax+rax+00h]
0x14000596c  test    rax, rax
0x14000596f  jz      loc_14000667B
0x140005975  mov     ecx, 0E420h
0x14000597a  mov     [rax], cx
0x14000597d  mov     [rdi+38h], rax
0x140005981  mov     eax, [r15+8]
0x140005985  xor     r13d, r13d
0x140005988  xor     dil, dil
0x14000598b  test    al, 2
0x14000598d  jnz     short loc_1400059AD
0x14000598f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005996  lea     rdx, WPP_GLOBAL_Control
0x14000599d  cmp     rcx, rdx
0x1400059a0  jz      short loc_1400059AD
0x1400059a2  mov     eax, [rcx+2Ch]
0x1400059a5  test    al, 1
0x1400059a7  jnz     loc_1400069E5
0x1400059ad  mov     eax, [rsi+4]
0x1400059b0  mov     r8d, 1
0x1400059b6  mov     [rbx+258h], rax
0x1400059bd  mov     rax, [rbx+2A0h]
0x1400059c4  test    rax, rax
0x1400059c7  jz      short loc_1400059D8
0x1400059c9  test    dword ptr [rax+0Ch], 40000000h
0x1400059d0  movzx   edi, dil
0x1400059d4  cmovnz  edi, r8d
0x1400059d8  test    r12b, r12b
0x1400059db  jnz     loc_140006515
0x1400059e1  mov     ecx, [rsi+38h]
0x1400059e4  lea     rdx, [rsi+38h]
0x1400059e8  mov     eax, ecx
0x1400059ea  and     eax, 10h
0x1400059ed  mov     [rbp+220h+var_284], eax
0x1400059f0  neg     eax
0x1400059f2  sbb     r12d, r12d
0x1400059f5  and     ecx, 400h
0x1400059fb  cmp     [rbp+220h+var_29B], r13b
0x1400059ff  jz      loc_140006089
0x140005a05  test    ecx, ecx
0x140005a07  jnz     loc_140006A0C
0x140005a0d  movzx   eax, byte ptr [rsi+3]
0x140005a11  and     al, r8b
0x140005a14  neg     al
0x140005a16  sbb     eax, eax
0x140005a18  add     eax, 4
0x140005a1b  mov     [rbp+220h+var_288], eax
0x140005a1e  movzx   eax, byte ptr [r14+163h]
0x140005a26  mov     r10, qword ptr [rbp+220h+String1.Length]
0x140005a2a  and     eax, 3Ch
0x140005a2d  sub     eax, 0Ch
0x140005a30  test    eax, 0FFFFFFFBh
0x140005a35  jz      loc_140006434
0x140005a3b  movzx   eax, byte ptr [rsi+2]
0x140005a3f  cmp     al, 0FFh
0x140005a41  jz      loc_140006140
0x140005a47  mov     ecx, [r15+3Ch]
0x140005a4b  mov     r9d, eax
0x140005a4e  mov     [r10+18h], eax
0x140005a52  mov     [r10+168h], r13d
0x140005a59  mov     [rbp+220h+var_298], eax
0x140005a5c  mov     eax, [r14+0C4h]
0x140005a63  mov     [rbp+220h+HashValue], ecx
0x140005a66  add     eax, [r14+0C0h]
0x140005a6d  jz      loc_1400061C3
0x140005a73  cmp     qword ptr [rbp+220h+var_258], r13
0x140005a77  jnz     loc_1400061BA
0x140005a7d  mov     rdi, [rbx+48h]
0x140005a81  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a88  lea     rax, WPP_GLOBAL_Control
0x140005a8f  cmp     rcx, rax
0x140005a92  jz      short loc_140005AA1
0x140005a94  test    dword ptr [rcx+2Ch], 200h
0x140005a9b  jnz     loc_140006B63
0x140005aa1  xor     r11d, r11d
0x140005aa4  xor     edx, edx
0x140005aa6  test    r9b, r9b
0x140005aa9  jnz     loc_14000648E
0x140005aaf  mov     r10d, 3
0x140005ab5  jmp     short loc_140005B26
0x140005ab7  mov     eax, [rcx+2Ch]
0x140005aba  test    al, 20h
0x140005abc  jz      loc_140005922
0x140005ac2  cmp     byte ptr [rcx+29h], 2
0x140005ac6  jb      loc_140005922
0x140005acc  mov     rax, [r8+24h]
0x140005ad0  mov     edx, 13h
0x140005ad5  mov     rcx, [rcx+18h]
0x140005ad9  mov     r9, rbx
0x140005adc  mov     [rsp+330h+Src], rax
0x140005ae1  mov     rax, [r8+1Ch]
0x140005ae5  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140005aec  mov     [rsp+330h+var_310], rax
0x140005af1  call    WPP_SF_iii
0x140005af6  jmp     loc_140005922
0x140005afb  mov     edx, 400800h
0x140005b00  mov     r11d, 10h
0x140005b06  or      r11d, 6
0x140005b0a  or      edx, 8200000h
0x140005b10  or      r11d, 9
0x140005b14  or      edx, 2100000h
0x140005b1a  cmp     r9b, 1
0x140005b1e  jnz     short loc_140005B26
0x140005b20  mov     r10d, 2
0x140005b26  mov     r8, [rdi+20h]
0x140005b2a  mov     ecx, edx
0x140005b2c  btr     ecx, 1Bh
0x140005b30  test    dword ptr [r8+0E8h], 200h
0x140005b3b  cmovz   ecx, edx
0x140005b3e  mov     edx, [rbx+200h]
0x140005b44  mov     eax, edx
0x140005b46  and     eax, 2
0x140005b49  test    dl, 1
0x140005b4c  jz      loc_140006B98
0x140005b52  test    dl, 4
0x140005b55  jnz     loc_140006BB1
0x140005b5b  mov     r12d, [rbp+220h+var_284]
0x140005b5f  test    dl, 23h
0x140005b62  jnz     loc_140006507
0x140005b68  bts     r10d, 9
0x140005b6d  mov     eax, 0EC21h
0x140005b72  cmp     [r8], ax
0x140005b76  jnz     short loc_140005B7F
0x140005b78  or      dword ptr [rdi+48h], 80h
0x140005b7f  mov     r8, qword ptr [rbp+220h+var_278]
0x140005b83  mov     [rbx+2E0h], r11d
0x140005b8a  mov     [rbx+2E4h], ecx
0x140005b90  or      [rdi+48h], r10d
0x140005b94  test    dword ptr [r8+48h], 200h
0x140005b9c  jz      loc_14003865B
0x140005ba2  jmp     loc_140005D75
0x140005ba7  mov     eax, [r8+24h]
0x140005bab  mov     [rbp+220h+var_298], eax
0x140005bae  mov     eax, [r14+9Ch]
0x140005bb5  test    al, 10h
0x140005bb7  jnz     loc_1400065F0
0x140005bbd  mov     eax, [rbp+220h+var_2A0]
0x140005bc0  cmp     eax, 0FFFFFFFFh
0x140005bc3  jz      short loc_140005BC9
0x140005bc5  mov     [r15+44h], eax
0x140005bc9  mov     eax, [rbp+220h+var_298]
0x140005bcc  mov     [r10+168h], eax
0x140005bd3  movzx   eax, byte ptr [rsi+2]
0x140005bd7  mov     [r10+18h], eax
0x140005bdb  mov     eax, [r14+0C4h]
0x140005be2  add     eax, [r14+0C0h]
0x140005be9  jnz     loc_14000657F
0x140005bef  mov     eax, [rbp+220h+var_288]
0x140005bf2  mov     dword ptr [rbp+220h+InitPacket.pAttributes], eax
0x140005bf5  lea     rax, [rbp+220h+var_280]
0x140005bf9  mov     [rbp+220h+InitPacket.pCreationTime], rax
0x140005bfd  lea     rax, [rsi+8]
0x140005c01  mov     [rbp+220h+InitPacket.pLastAccessTime], rax
0x140005c05  lea     rax, [rsi+10h]
0x140005c09  mov     [rbp+220h+InitPacket.pLastWriteTime], rax
0x140005c0d  lea     rax, [rsi+18h]
0x140005c11  mov     [rbp+220h+InitPacket.pLastChangeTime], rax
0x140005c15  lea     rax, [rsi+20h]
0x140005c19  mov     [rbp+220h+InitPacket.pAllocationSize], rax
0x140005c1d  mov     [rbp+220h+var_280], 1
0x140005c24  mov     [rbp+220h+InitPacket.pNumLinks], rdx
0x140005c28  test    dil, dil
0x140005c2b  jnz     loc_140006AA0
0x140005c31  lea     rax, [rsi+28h]
0x140005c35  mov     [rbp+220h+InitPacket.pFileSize], rax
0x140005c39  lea     rax, [rsi+30h]
0x140005c3d  lea     edx, [r12+0EC22h]; FileType
0x140005c45  mov     [rbp+220h+var_1D8], rax
0x140005c49  lea     r8, [rbp+220h+InitPacket]; InitPacket
0x140005c4d  mov     [rbp+220h+InitPacket.pValidDataLength], rax
0x140005c51  mov     rcx, r14; Fcb
0x140005c54  call    cs:__imp_RxFinishFcbInitialization
0x140005c5b  nop     dword ptr [rax+rax+00h]
0x140005c60  mov     r11d, [rbp+220h+HashValue]
0x140005c64  mov     rdi, [rbx+48h]
0x140005c68  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c6f  lea     rax, WPP_GLOBAL_Control
0x140005c76  cmp     rcx, rax
0x140005c79  jz      short loc_140005C88
0x140005c7b  test    dword ptr [rcx+2Ch], 200h
0x140005c82  jnz     loc_140006AB0
0x140005c88  mov     r12d, [rbp+220h+var_298]
0x140005c8c  xor     r10d, r10d
0x140005c8f  mov     ecx, r12d
0x140005c92  and     ecx, 1
0x140005c95  mov     eax, ecx
0x140005c97  neg     eax
0x140005c99  sbb     r9d, r9d
0x140005c9c  and     r9d, 2100000h
0x140005ca3  neg     ecx
0x140005ca5  sbb     r8d, r8d
0x140005ca8  and     r8d, 9
0x140005cac  test    r12b, 4
0x140005cb0  jz      short loc_140005CBD
0x140005cb2  or      r8d, 6
0x140005cb6  or      r9d, 8200000h
0x140005cbd  mov     ecx, r9d
0x140005cc0  or      ecx, 400800h
0x140005cc6  bt      r12d, 1
0x140005ccb  cmovnb  ecx, r9d
0x140005ccf  mov     r9d, r8d
0x140005cd2  or      r9d, 20h
0x140005cd6  mov     edx, ecx
0x140005cd8  bt      r12d, 1
0x140005cdd  cmovnb  r9d, r8d
0x140005ce1  mov     r8, [rdi+20h]
0x140005ce5  btr     edx, 1Bh
0x140005ce9  test    dword ptr [r8+0E8h], 200h
0x140005cf4  cmovz   edx, ecx
0x140005cf7  mov     ecx, [rbx+200h]
0x140005cfd  mov     eax, ecx
0x140005cff  and     eax, 2
0x140005d02  test    cl, 1
0x140005d05  jz      loc_140006AEC
0x140005d0b  test    cl, 4
0x140005d0e  jnz     loc_140006B05
0x140005d14  mov     eax, 0EC21h
0x140005d19  cmp     [r8], ax
0x140005d1d  jnz     short loc_140005D26
0x140005d1f  or      dword ptr [rdi+48h], 80h
0x140005d26  mov     r8, qword ptr [rbp+220h+var_278]
0x140005d2a  mov     [rbx+2E0h], r9d
0x140005d31  mov     [rbx+2E4h], edx
0x140005d37  or      [rdi+48h], r10d
  ... truncated ...
```
