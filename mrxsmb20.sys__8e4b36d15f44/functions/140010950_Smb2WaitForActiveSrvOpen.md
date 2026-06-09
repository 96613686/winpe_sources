# Smb2WaitForActiveSrvOpen

- ea: `0x140010950`
- end: `0x140010fb1`
- name: `Smb2WaitForActiveSrvOpen`
- size: `1633`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1400087c0`
- `0x14000bd50`
- `0x140010950`
- `0x140010fc0`
- `0x140011d00`
- `0x140019b70`
- `0x140033f10`
- `0x1400342b8`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010af2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010cc5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010af2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010cc5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010a3a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010d11`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010a3a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010d11`
- `rdbss!RxDispatchToWorkerThread` at `0x14003a565`
- `rdbss!RxDispatchToWorkerThread` at `0x14003a565`
- `mrxsmb!SmbCseReferenceCompoundingKey` at `0x140010ca9`
- `mrxsmb!SmbCseReferenceCompoundingKey` at `0x140010ca9`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140010fa0`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140010fa0`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x140010cff`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x140010cff`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x140010d44`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x140010d44`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140010d6c`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140010d6c`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140010bf5`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140010e1b`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140010bf5`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140010e1b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140010e04`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140010e04`
- `mrxsmb!SmbCeSuspendExchangeLite` at `0x14003a2e1`
- `mrxsmb!SmbCeSuspendExchangeLite` at `0x14003a588`
- `mrxsmb!SmbCeSuspendExchangeLite` at `0x14003a2e1`
- `mrxsmb!SmbCeSuspendExchangeLite` at `0x14003a588`
- `mrxsmb!SmbCeSwitchConnectionObjectTransport` at `0x140010bd4`
- `mrxsmb!SmbCeSwitchConnectionObjectTransport` at `0x140010bd4`

## pseudocode

```c
__int64 __fastcall Smb2WaitForActiveSrvOpen(__int64 a1)
{
  int v1; // edi
  __int64 v2; // r12
  __int64 v4; // r14
  char v5; // al
  __int64 v6; // r15
  __int64 v7; // rsi
  char v8; // di
  int v9; // ebp
  int v10; // r9d
  PDEVICE_OBJECT *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  int v15; // r11d
  char v16; // dl
  char v17; // r9
  int v19; // r10d
  __int64 v20; // rdx
  __int64 v21; // rdi
  unsigned __int64 v22; // r9
  char v23; // kr00_1
  int v24; // r10d
  __int64 CompoundingKey; // rax
  __int16 v26; // ax
  __int64 v27; // rdi
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned int v31; // eax
  int v32; // eax
  int v33; // eax
  __int64 v34; // r9
  __int64 v35; // r10
  __int64 v36; // r9
  __int64 v37; // r9
  __int64 v38; // r8
  __int64 v39; // r9
  unsigned __int16 *v40; // r8
  __int64 v41; // r9
  int v42; // ecx
  unsigned __int16 *v43; // rax
  int v44; // ecx
  __int64 v45; // r8
  int *v46; // rax
  int *v47; // rax
  int *v48; // rbp
  int *v49; // r11
  int *v50; // rdx
  int *v51; // r8
  unsigned int v52; // [rsp+A0h] [rbp-68h]
  unsigned int v53; // [rsp+A4h] [rbp-64h]
  int v54; // [rsp+A8h] [rbp-60h]
  char v55; // [rsp+ACh] [rbp-5Ch]
  __int64 v56; // [rsp+B0h] [rbp-58h]
  char v57; // [rsp+110h] [rbp+8h]
  __int64 v58; // [rsp+110h] [rbp+8h]
  char v59; // [rsp+118h] [rbp+10h]
  char v60; // [rsp+118h] [rbp+10h]
  char v61; // [rsp+120h] [rbp+18h]
  int v62; // [rsp+128h] [rbp+20h]

  v1 = 0;
  v2 = 0;
  v4 = *(_QWORD *)(a1 + 48);
  v56 = *(_QWORD *)(a1 + 88);
  if ( (*(_DWORD *)(a1 + 68) & 0x1000) != 0 || (v5 = dbgDisableCompounding) != 0 )
    v5 = 1;
  if ( !v4 )
    goto LABEL_24;
  v6 = *(_QWORD *)(v4 + 72);
  if ( !v6 )
    goto LABEL_24;
  v7 = *(_QWORD *)(v6 + 48);
  if ( !v7 || (*(_DWORD *)(v7 + 8) & 1) != 0 )
    goto LABEL_24;
  v8 = *(_BYTE *)(v4 + 32);
  v54 = *(_DWORD *)(v7 + 8) & 8;
  v53 = *(_DWORD *)(v7 + 8) & 4;
  v57 = v8;
  v52 = *(_DWORD *)(v7 + 8) & 0x20;
  v9 = *(_DWORD *)(v7 + 8) & 0x40;
  if ( v8 == 2 )
    v5 = 1;
  v61 = v8 == 2;
  v55 = v5;
  ExAcquirePushLockExclusiveEx(v7 + 16, 0);
  v10 = *(_DWORD *)(v7 + 44);
  v11 = &WPP_GLOBAL_Control;
  v12 = v56;
  if ( !v10 )
    goto LABEL_11;
  v19 = *(_DWORD *)(v56 + 264);
  if ( v10 == v19 && *(_DWORD *)(v56 + 12) != 1 )
    goto LABEL_11;
  v33 = *(_DWORD *)(v7 + 4);
  v60 = v33;
  if ( v33 )
  {
    if ( v8 != 2 || v33 != 6 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qZddqqqqq(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        *(_QWORD *)(v56 + 416),
        v6,
        *(_QWORD *)(v6 + 80),
        v10,
        v19,
        a1,
        *(_QWORD *)(a1 + 48),
        *(_QWORD *)(v56 + 416),
        v56,
        *(_QWORD *)(*(_QWORD *)(v56 + 416) + 384LL));
      v12 = v56;
    }
    v13 = v53;
    v14 = v52;
    *(_DWORD *)(v7 + 4) = 7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qZddqqqqq(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        *(_QWORD *)(v56 + 416),
        v6,
        *(_QWORD *)(v6 + 80),
        v10,
        v19,
        a1,
        *(_QWORD *)(a1 + 48),
        *(_QWORD *)(v56 + 416),
        v56,
        *(_QWORD *)(*(_QWORD *)(v56 + 416) + 384LL));
      v12 = v56;
    }
    *(_DWORD *)(v7 + 4) = 1;
    Smb2DecrementActiveHandleCount(*(_QWORD *)(v12 + 416), v11);
    v13 = v53;
    v14 = v52;
    if ( **(_WORD **)(v6 + 32) == 0xEC21 && !v53 && !v52 )
    {
      *(_QWORD *)(v7 + 288) = 0;
      *(_QWORD *)(v7 + 280) = 0;
    }
    v12 = v56;
  }
  *(_QWORD *)(v7 + 248) = MEMORY[0xFFFFF78000000008];
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x400) != 0 )
  {
    v34 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 32) + 120LL) + 88LL);
    McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
      **(_WORD **)(v6 + 80) >> 1,
      (unsigned int)OpenHandleStateTransition,
      *(_QWORD *)(v6 + 80),
      v7,
      0,
      0,
      v7 + 264,
      v60,
      *(_WORD *)(v7 + 4),
      12,
      0,
      *(_WORD *)v34 >> 1,
      *(_QWORD *)(v34 + 8),
      **(_WORD **)(v6 + 80) >> 1,
      *(_QWORD *)(*(_QWORD *)(v6 + 80) + 8LL),
      0,
      0);
    v12 = v56;
LABEL_11:
    v13 = v53;
    v14 = v52;
  }
  v15 = *(_DWORD *)(v7 + 4);
  v62 = v15;
  if ( v15 == 1 )
  {
    if ( v8 != 2 )
      goto LABEL_14;
    goto LABEL_90;
  }
  if ( v15 )
  {
    v23 = v8;
    v22 = 0x140000000uLL;
    v1 = -1073741300;
    switch ( v15 )
    {
      case 3:
      case 4:
        v16 = v57;
        if ( !v57 )
        {
          *(_DWORD *)(v7 + 44) = 0;
          v1 = 0;
          *(_DWORD *)(a1 + 116) = 0;
          goto LABEL_20;
        }
        if ( !(_DWORD)v13 && !v54 )
          goto LABEL_20;
        LOBYTE(v22) = 1;
        v1 = SmbCeSuspendExchangeLite(a1, v7 + 56, Smb2CancelSuspendedExchangeOnSrvOpen, v22);
        goto LABEL_19;
      case 5:
      case 9:
        v16 = v57;
        goto LABEL_120;
      case 6:
        v16 = v57;
        if ( v57 != 2 )
          goto LABEL_120;
        v1 = 0;
        *(_DWORD *)(a1 + 116) = *(_DWORD *)(v7 + 44);
        goto LABEL_20;
      case 7:
        v8 = v57;
        if ( v57 != 2 )
        {
          v1 = -1073741628;
          goto LABEL_19;
        }
        v12 = v56;
        break;
      case 8:
        v16 = v57;
        v17 = *(_DWORD *)(v7 + 4);
        if ( !v57 )
        {
          *(_DWORD *)(v7 + 44) = 0;
          v1 = 0;
          *(_DWORD *)(a1 + 116) = 0;
        }
        goto LABEL_21;
      default:
        v16 = v23;
LABEL_120:
        v1 = -1073741628;
        goto LABEL_20;
    }
LABEL_90:
    if ( !(_DWORD)v14 && !v9 )
    {
      if ( !(_DWORD)v13
        || (v14 = *(_QWORD *)(v6 + 32), v32 = *(_DWORD *)(v14 + 164), (v32 & 0x10) == 0) && (v32 & 0x20) == 0
        || (*(_DWORD *)(v14 + 160) & 0x800) == 0 )
      {
LABEL_77:
        *(_DWORD *)(v7 + 4) = 9;
        v1 = -1073741628;
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x400) != 0 )
        {
          v36 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 32) + 120LL) + 88LL);
          McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
            **(_WORD **)(v6 + 80) >> 1,
            (unsigned int)OpenHandleStateTransition,
            *(_QWORD *)(v6 + 80),
            v7,
            0,
            0,
            v7 + 264,
            v15,
            9,
            196,
            0,
            *(_WORD *)v36 >> 1,
            *(_QWORD *)(v36 + 8),
            **(_WORD **)(v6 + 80) >> 1,
            *(_QWORD *)(*(_QWORD *)(v6 + 80) + 8LL),
            0,
            0);
        }
        goto LABEL_19;
      }
    }
LABEL_14:
    if ( !v8 )
      goto LABEL_15;
    if ( (_DWORD)v13 )
    {
      if ( !v54 )
        goto LABEL_15;
    }
    else if ( !v54 )
    {
      goto LABEL_77;
    }
    v14 = *(_QWORD *)(v6 + 32);
    v26 = *(_WORD *)(v14 + 360);
    if ( !v26 || v26 == 2 && **(_WORD **)(v14 + 368) == 92 )
    {
      if ( !(unsigned int)Smb2AttemptToUseCachedShareRootHandle(v12, v6) )
      {
        v27 = *(_QWORD *)(v56 + 416);
        v28 = *(_QWORD *)(v27 + 384);
        _InterlockedIncrement((volatile signed __int32 *)(v27 + 432));
        if ( *(_DWORD *)(v27 + 704) )
        {
          v31 = *(_DWORD *)(v28 + 772);
          v30 = 2;
          v29 = 10;
          if ( v31 )
            v29 = v31;
        }
        else
        {
          v29 = *(unsigned int *)(v28 + 776);
          if ( !(_DWORD)v29 )
            v29 = *(_DWORD *)(MRxSmbGetConfigurationBlock(v56) + 12) >> 1;
          v30 = 0;
        }
        SmbCeSetConnectionKeepalive(v27, v29, v30);
        v1 = 0;
        goto LABEL_19;
      }
      v15 = v62;
    }
LABEL_15:
    *(_DWORD *)(v7 + 44) = 0;
    if ( !v8 )
    {
      *(_DWORD *)(v7 + 4) = 3;
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x400) != 0 )
      {
        v37 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 32) + 120LL) + 88LL);
        McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
          **(_WORD **)(v6 + 80) >> 1,
          (unsigned int)OpenHandleStateTransition,
          *(_QWORD *)(v6 + 80),
          v7,
          0,
          0,
          v7 + 264,
          v15,
          3,
          0,
          0,
          *(_WORD *)v37 >> 1,
          *(_QWORD *)(v37 + 8),
          **(_WORD **)(v6 + 80) >> 1,
          *(_QWORD *)(*(_QWORD *)(v6 + 80) + 8LL),
          0,
          0);
      }
      v1 = 0;
      goto LABEL_19;
    }
    v24 = 4;
    if ( v15 != 1 )
      v24 = 8;
    *(_DWORD *)(v7 + 4) = v24;
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x400) != 0 )
    {
      v38 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 32) + 120LL) + 88LL);
      McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
        **(_WORD **)(v6 + 80) >> 1,
        (unsigned int)OpenHandleStateTransition,
        v38,
        v7,
        0,
        0,
        v7 + 264,
        v15,
        v24,
        0,
        0,
        *(_WORD *)v38 >> 1,
        *(_QWORD *)(v38 + 8),
        **(_WORD **)(v6 + 80) >> 1,
        *(_QWORD *)(*(_QWORD *)(v6 + 80) + 8LL),
        0,
        0);
    }
    *(_QWORD *)(v7 + 352) = v4;
    if ( v55 )
    {
      v1 = RxDispatchToWorkerThread(
             *(PRDBSS_DEVICE_OBJECT *)(v56 + 24),
             NormalWorkQueue,
             Smb2ReconnectSrvOpenAsyncWorker,
             (PVOID)v6);
      if ( v1 >= 0 )
      {
        LOBYTE(v39) = 1;
        v1 = SmbCeSuspendExchangeLite(a1, v7 + 56, Smb2CancelSuspendedExchangeOnSrvOpen, v39);
        if ( v1 >= 0 )
          goto LABEL_19;
      }
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x400) != 0 )
      {
        v40 = *(unsigned __int16 **)(v6 + 80);
        v41 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 32) + 120LL) + 88LL);
        v42 = *v40;
        LOWORD(v42) = (unsigned __int16)v42 >> 1;
        McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
          v42,
          (unsigned int)OpenHandleStateTransition,
          (_DWORD)v40,
          v7,
          0,
          0,
          v7 + 264,
          *(_WORD *)(v7 + 4),
          v62,
          v1,
          0,
          *(_WORD *)v41 >> 1,
          *(_QWORD *)(v41 + 8),
          v42,
          *((_QWORD *)v40 + 1),
          0,
          0);
      }
    }
    else
    {
      v2 = *(_QWORD *)(a1 + 56);
      if ( v2 )
      {
        v59 = 0;
        SmbCseReferenceCompoundingKey(*(_QWORD *)(a1 + 56), v14, v13);
LABEL_51:
        _InterlockedOr((volatile signed __int32 *)(v2 + 68), 0x100u);
        ExReleasePushLockExclusiveEx(v7 + 16, 0);
        v1 = Smb2ReconnectSrvOpenAsync((struct _MRX_SRV_OPEN_ *)v6, v2, v61);
        if ( v1 != 259 )
          Smb2CompleteSrvOpenReconnectionCallback(0);
        if ( v59 )
          SmbCseReleaseCompoundingKey(v2);
        ExAcquirePushLockExclusiveEx(v7 + 16, 0);
        if ( v1 == 259 )
        {
          v1 = 0;
          if ( (*(_DWORD *)(v7 + 4) & 0xFFFFFFFB) != 0 )
            v1 = -1073741300;
        }
        goto LABEL_19;
      }
      CompoundingKey = SmbCseAllocateCompoundingKey(96);
      v2 = CompoundingKey;
      if ( CompoundingKey )
      {
        v59 = 1;
        SmbCeAssociateExchangeWithCompoundingKeyEx(a1, CompoundingKey, 0xFFFF);
        goto LABEL_51;
      }
      v1 = -1073741670;
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x400) != 0 )
      {
        v43 = *(unsigned __int16 **)(v6 + 80);
        v44 = *v43;
        v45 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 32) + 120LL) + 88LL);
        LOWORD(v44) = (unsigned __int16)v44 >> 1;
        McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
          v44,
          (unsigned int)OpenHandleStateTransition,
          v45,
          v7,
          0,
          0,
          v7 + 264,
          *(_WORD *)(v7 + 4),
          v62,
          154,
          0,
          *(_WORD *)v45 >> 1,
          *(_QWORD *)(v45 + 8),
          v44,
          *((_QWORD *)v43 + 1),
          0,
          0);
      }
    }
    v17 = v62;
    v16 = v57;
    *(_DWORD *)(v7 + 4) = v62;
    goto LABEL_21;
  }
  if ( v8 == 2 )
  {
    v20 = 6;
    *(_DWORD *)(v7 + 4) = 6;
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x400) != 0 )
    {
      v35 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 32) + 120LL) + 88LL);
      McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
        **(_WORD **)(v6 + 80) >> 1,
        (unsigned int)OpenHandleStateTransition,
        *(_WORD *)v35 >> 1,
        v7,
        0,
        0,
        v7 + 264,
        0,
        6,
        40,
        0,
        *(_WORD *)v35 >> 1,
        *(_QWORD *)(v35 + 8),
        **(_WORD **)(v6 + 80) >> 1,
        *(_QWORD *)(*(_QWORD *)(v6 + 80) + 8LL),
        0,
        0);
      v12 = v56;
    }
    v21 = *(_QWORD *)(v12 + 416);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v21 + 432), 0xFFFFFFFF) == 1 )
    {
      if ( (*(_DWORD *)(*(_QWORD *)(v21 + 384) + 716LL) & 0x1000) == 0 )
        SmbCeSwitchConnectionObjectTransport(v21, v20, v13);
      if ( !*(_DWORD *)(v21 + 704) )
        SmbCeSetConnectionKeepalive(v21, 0, 0);
    }
  }
  v1 = 0;
  *(_DWORD *)(a1 + 116) = *(_DWORD *)(v7 + 44);
LABEL_19:
  v16 = v57;
LABEL_20:
  v17 = v62;
LABEL_21:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v46 = (int *)"Destructor";
    if ( v16 != 2 )
      v46 = &dword_14003ECEC;
    v58 = (__int64)v46;
    v47 = (int *)"Constructor";
    if ( v16 )
      v47 = &dword_14003ECEC;
    if ( !v9 || (v48 = (int *)"Resilient", v52) )
      v48 = &dword_14003ECEC;
    v49 = (int *)"Persistent";
    v50 = (int *)"Deferable";
    if ( !v52 )
      v49 = &dword_14003ECEC;
    v51 = (int *)"Durable";
    if ( !v53 )
      v51 = &dword_14003ECEC;
    if ( !v54 )
      v50 = &dword_14003ECEC;
    WPP_SF_qqdssssdLdLqssDZ(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v50,
      (_DWORD)v51,
      v4,
      v6,
      *(_DWORD *)(v7 + 44),
      (__int64)v50,
      (__int64)v51,
      (__int64)v49,
      (__int64)v48,
      v17,
      v17,
      *(_DWORD *)(v7 + 4),
      *(_DWORD *)(v7 + 4),
      a1,
      (__int64)v47,
      v58,
      v1,
      *(_QWORD *)(v6 + 80));
  }
  ExReleasePushLockExclusiveEx(v7 + 16, 0);
  if ( v1 != 259 )
LABEL_24:
    *(_DWORD *)(a1 + 40) = 1;
  if ( v2 )
    SmbCseDereferenceCompoundingKey(v2);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140010950  mov     rax, rsp
0x140010953  push    rdi
0x140010954  push    r12
0x140010956  sub     rsp, 0F8h
0x14001095d  mov     [rax-18h], rbx
0x140010961  xor     edi, edi
0x140010963  mov     [rax-38h], r14
0x140010967  xor     r12d, r12d
0x14001096a  mov     rax, [rcx+58h]
0x14001096e  mov     rbx, rcx
0x140010971  mov     r14, [rcx+30h]
0x140010975  mov     [rsp+108h+var_58], rax
0x14001097d  mov     eax, [rcx+44h]
0x140010980  bt      eax, 0Ch
0x140010984  jb      short loc_140010991
0x140010986  movzx   eax, cs:dbgDisableCompounding
0x14001098d  test    al, al
0x14001098f  jz      short loc_140010993
0x140010991  mov     al, 1
0x140010993  mov     [rsp+108h+var_20], rbp
0x14001099b  mov     edx, 1
0x1400109a0  mov     [rsp+108h+var_28], rsi
0x1400109a8  mov     [rsp+108h+var_40], r15
0x1400109b0  test    r14, r14
0x1400109b3  jz      loc_140010B13
0x1400109b9  mov     r15, [r14+48h]
0x1400109bd  test    r15, r15
0x1400109c0  jz      loc_140010B13
0x1400109c6  mov     rsi, [r15+30h]
0x1400109ca  test    rsi, rsi
0x1400109cd  jz      loc_140010B13
0x1400109d3  mov     ebp, [rsi+8]
0x1400109d6  test    dl, bpl
0x1400109d9  jnz     loc_140010B13
0x1400109df  movzx   edi, byte ptr [r14+20h]
0x1400109e4  mov     ecx, ebp
0x1400109e6  and     ecx, 8
0x1400109e9  movzx   eax, al
0x1400109ec  mov     [rsp+108h+var_60], ecx
0x1400109f3  mov     ecx, ebp
0x1400109f5  and     ecx, 4
0x1400109f8  mov     [rsp+108h+var_30], r13
0x140010a00  mov     [rsp+108h+var_64], ecx
0x140010a07  mov     ecx, ebp
0x140010a09  and     ecx, 20h
0x140010a0c  mov     byte ptr [rsp+108h+arg_0], dil
0x140010a14  mov     [rsp+108h+var_68], ecx
0x140010a1b  and     ebp, 40h
0x140010a1e  cmp     dil, 2
0x140010a22  lea     rcx, [rsi+10h]
0x140010a26  cmovz   eax, edx
0x140010a29  setz    byte ptr [rsp+108h+arg_10]
0x140010a31  xor     edx, edx
0x140010a33  mov     [rsp+108h+var_5C], eax
0x140010a3a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140010a41  nop     dword ptr [rax+rax+00h]
0x140010a46  mov     r9d, [rsi+2Ch]
0x140010a4a  lea     rdx, WPP_GLOBAL_Control
0x140010a51  mov     rcx, [rsp+108h+var_58]
0x140010a59  test    r9d, r9d
0x140010a5c  jnz     loc_140010B71
0x140010a62  mov     r8d, [rsp+108h+var_64]
0x140010a6a  mov     edx, [rsp+108h+var_68]
0x140010a71  mov     r11d, [rsi+4]
0x140010a75  mov     [rsp+108h+arg_18], r11d
0x140010a7d  cmp     r11d, 1
0x140010a81  jnz     loc_140010B55
0x140010a87  cmp     dil, 2
0x140010a8b  jz      loc_140010F0F
0x140010a91  test    dil, dil
0x140010a94  jnz     loc_140010E46
0x140010a9a  mov     [rsi+2Ch], r12d
0x140010a9e  test    dil, dil
0x140010aa1  jnz     loc_140010C51
0x140010aa7  mov     edi, 3
0x140010aac  mov     [rsi+4], edi
0x140010aaf  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 4
0x140010ab6  jnz     loc_14003A442
0x140010abc  xor     edi, edi
0x140010abe  movzx   edx, byte ptr [rsp+108h+arg_0]
0x140010ac6  mov     r9d, [rsp+108h+arg_18]
0x140010ace  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ad5  lea     rax, WPP_GLOBAL_Control
0x140010adc  cmp     rcx, rax
0x140010adf  jz      short loc_140010AEC
0x140010ae1  mov     eax, [rcx+2Ch]
0x140010ae4  test    al, 40h
0x140010ae6  jnz     loc_14003A6CF
0x140010aec  xor     edx, edx
0x140010aee  lea     rcx, [rsi+10h]
0x140010af2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010af9  nop     dword ptr [rax+rax+00h]
0x140010afe  mov     r13, [rsp+108h+var_30]
0x140010b06  cmp     edi, 103h
0x140010b0c  jz      short loc_140010B16
0x140010b0e  mov     edx, 1
0x140010b13  mov     [rbx+28h], edx
0x140010b16  mov     r15, [rsp+108h+var_40]
0x140010b1e  mov     r14, [rsp+108h+var_38]
0x140010b26  mov     rsi, [rsp+108h+var_28]
0x140010b2e  mov     rbp, [rsp+108h+var_20]
0x140010b36  mov     rbx, [rsp+108h+var_18]
0x140010b3e  test    r12, r12
0x140010b41  jnz     loc_140010F9D
0x140010b47  mov     eax, edi
0x140010b49  add     rsp, 0F8h
0x140010b50  pop     r12
0x140010b52  pop     rdi
0x140010b53  retn
0x140010b55  test    r11d, r11d
0x140010b58  jnz     loc_140010C06
0x140010b5e  cmp     dil, 2
0x140010b62  jz      short loc_140010B90
0x140010b64  mov     eax, [rsi+2Ch]
0x140010b67  xor     edi, edi
0x140010b69  mov     [rbx+74h], eax
0x140010b6c  jmp     loc_140010ABE
0x140010b71  mov     r10d, [rcx+108h]
0x140010b78  cmp     r9d, r10d
0x140010b7b  jnz     loc_14003A0A4
0x140010b81  cmp     dword ptr [rcx+0Ch], 1
0x140010b85  jnz     loc_140010A62
0x140010b8b  jmp     loc_14003A0A4
0x140010b90  mov     edx, 6
0x140010b95  mov     [rsi+4], edx
0x140010b98  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 4
0x140010b9f  jnz     loc_14003A2FE
0x140010ba5  mov     rdi, [rcx+1A0h]
0x140010bac  mov     eax, 0FFFFFFFFh
0x140010bb1  lock xadd [rdi+1B0h], eax
0x140010bb9  cmp     eax, 1
0x140010bbc  jnz     short loc_140010B64
0x140010bbe  mov     rax, [rdi+180h]
0x140010bc5  test    dword ptr [rax+2CCh], 1000h
0x140010bcf  jnz     short loc_140010BE0
0x140010bd1  mov     rcx, rdi
0x140010bd4  call    cs:__imp_SmbCeSwitchConnectionObjectTransport
0x140010bdb  nop     dword ptr [rax+rax+00h]
0x140010be0  cmp     [rdi+2C0h], r12d
0x140010be7  jnz     loc_140010B64
0x140010bed  xor     r8d, r8d
0x140010bf0  xor     edx, edx
0x140010bf2  mov     rcx, rdi
0x140010bf5  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140010bfc  nop     dword ptr [rax+rax+00h]
0x140010c01  jmp     loc_140010B64
0x140010c06  lea     eax, [r11-3]; switch 7 cases
0x140010c0a  cmp     eax, 6
0x140010c0d  ja      def_140010C2C; jumptable 0000000140010C2C default case
0x140010c13  lea     r9, cs:140000000h
0x140010c1a  cdqe
0x140010c1c  mov     edi, 0C000020Ch
0x140010c21  mov     ecx, ds:(jpt_140010C2C - 140000000h)[r9+rax*4]
0x140010c29  add     rcx, r9
0x140010c2c  jmp     rcx; switch jump
0x140010c32  movzx   edx, byte ptr [rsp+108h+arg_0]; jumptable 0000000140010C2C cases 3,4
0x140010c3a  test    dl, dl
0x140010c3c  jnz     loc_140010EBF
0x140010c42  mov     [rsi+2Ch], r12d
0x140010c46  xor     edi, edi
0x140010c48  mov     [rbx+74h], r12d
0x140010c4c  jmp     loc_140010AC6
0x140010c51  cmp     r11d, 1
0x140010c55  lea     rdi, [rsi+108h]
0x140010c5c  mov     eax, 8
0x140010c61  mov     r10d, 4
0x140010c67  cmovnz  r10d, eax
0x140010c6b  mov     [rsi+4], r10d
0x140010c6f  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 4
0x140010c76  jnz     loc_14003A4C9
0x140010c7c  mov     [rsi+160h], r14
0x140010c83  cmp     byte ptr [rsp+108h+var_5C], r12b
0x140010c8b  jnz     loc_14003A54A
0x140010c91  mov     r12, [rbx+38h]
0x140010c95  test    r12, r12
0x140010c98  jz      loc_140010D3F
0x140010c9e  mov     rcx, r12
0x140010ca1  mov     byte ptr [rsp+108h+arg_8], 0
0x140010ca9  call    cs:__imp_SmbCseReferenceCompoundingKey
0x140010cb0  nop     dword ptr [rax+rax+00h]
0x140010cb5  lock or dword ptr [r12+44h], 100h
0x140010cbf  xor     edx, edx
0x140010cc1  lea     rcx, [rsi+10h]
0x140010cc5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010ccc  nop     dword ptr [rax+rax+00h]
0x140010cd1  movzx   r8d, byte ptr [rsp+108h+arg_10]
0x140010cda  mov     rdx, r12
0x140010cdd  mov     rcx, r15
0x140010ce0  call    Smb2ReconnectSrvOpenAsync
0x140010ce5  mov     edi, eax
0x140010ce7  cmp     eax, 103h
0x140010cec  jnz     loc_140010F74
0x140010cf2  cmp     byte ptr [rsp+108h+arg_8], 0
0x140010cfa  jz      short loc_140010D0B
0x140010cfc  mov     rcx, r12
0x140010cff  call    cs:__imp_SmbCseReleaseCompoundingKey
0x140010d06  nop     dword ptr [rax+rax+00h]
0x140010d0b  xor     edx, edx
0x140010d0d  lea     rcx, [rsi+10h]
0x140010d11  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140010d18  nop     dword ptr [rax+rax+00h]
0x140010d1d  cmp     edi, 103h
0x140010d23  jnz     loc_140010ABE
0x140010d29  xor     edi, edi
0x140010d2b  mov     eax, 0C000020Ch
0x140010d30  test    dword ptr [rsi+4], 0FFFFFFFBh
0x140010d37  cmovnz  edi, eax
0x140010d3a  jmp     loc_140010ABE
0x140010d3f  mov     ecx, 60h ; '`'
0x140010d44  call    cs:__imp_SmbCseAllocateCompoundingKey
0x140010d4b  nop     dword ptr [rax+rax+00h]
0x140010d50  mov     r12, rax
0x140010d53  test    rax, rax
0x140010d56  jz      short loc_140010D7D
0x140010d58  mov     r8d, 0FFFFh
0x140010d5e  mov     byte ptr [rsp+108h+arg_8], 1
0x140010d66  mov     rdx, rax
0x140010d69  mov     rcx, rbx
0x140010d6c  call    cs:__imp_SmbCeAssociateExchangeWithCompoundingKeyEx
0x140010d73  nop     dword ptr [rax+rax+00h]
0x140010d78  jmp     loc_140010CB5
0x140010d7d  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 4
0x140010d84  mov     edi, 0C000009Ah
0x140010d89  jnz     loc_14003A62B
0x140010d8f  mov     r9d, [rsp+108h+arg_18]
0x140010d97  movzx   edx, byte ptr [rsp+108h+arg_0]
0x140010d9f  mov     [rsi+4], r9d
0x140010da3  jmp     loc_140010ACE
0x140010da8  test    eax, eax
0x140010daa  jz      loc_140010A9A
0x140010db0  mov     rdx, [r15+20h]
0x140010db4  movzx   eax, word ptr [rdx+168h]
0x140010dbb  test    ax, ax
0x140010dbe  jnz     loc_140010F47
0x140010dc4  mov     rdx, r15
0x140010dc7  call    Smb2AttemptToUseCachedShareRootHandle
0x140010dcc  test    eax, eax
0x140010dce  jnz     loc_140010F67
0x140010dd4  mov     rcx, [rsp+108h+var_58]
0x140010ddc  mov     rdi, [rcx+1A0h]
0x140010de3  mov     rdx, [rdi+180h]
0x140010dea  lock inc dword ptr [rdi+1B0h]
0x140010df1  cmp     [rdi+2C0h], r12d
0x140010df8  jnz     short loc_140010E2E
0x140010dfa  mov     edx, [rdx+308h]
0x140010e00  test    edx, edx
0x140010e02  jnz     short loc_140010E15
0x140010e04  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140010e0b  nop     dword ptr [rax+rax+00h]
0x140010e10  mov     edx, [rax+0Ch]
0x140010e13  shr     edx, 1
0x140010e15  xor     r8d, r8d
0x140010e18  mov     rcx, rdi
0x140010e1b  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140010e22  nop     dword ptr [rax+rax+00h]
0x140010e27  xor     edi, edi
0x140010e29  jmp     loc_140010ABE
0x140010e2e  mov     eax, [rdx+304h]
0x140010e34  mov     r8d, 2
0x140010e3a  test    eax, eax
0x140010e3c  mov     edx, 0Ah
0x140010e41  cmovnz  edx, eax
0x140010e44  jmp     short loc_140010E18
0x140010e46  mov     eax, [rsp+108h+var_60]
0x140010e4d  test    r8d, r8d
0x140010e50  jnz     loc_140010DA8
0x140010e56  test    eax, eax
0x140010e58  jnz     loc_140010DB0
0x140010e5e  mov     dword ptr [rsi+4], 9
0x140010e65  mov     edi, 0C00000C4h
0x140010e6a  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 4
0x140010e71  jz      loc_140010ABE
0x140010e77  jmp     loc_14003A3B6
0x140010e7c  movzx   edi, byte ptr [rsp+108h+arg_0]; jumptable 0000000140010C2C case 7
0x140010e84  cmp     dil, 2
0x140010e88  jz      loc_14003A394
0x140010e8e  mov     edi, 0C00000C4h
0x140010e93  jmp     loc_140010ABE
0x140010e98  movzx   edx, byte ptr [rsp+108h+arg_0]; jumptable 0000000140010C2C case 8
0x140010ea0  mov     r9d, [rsp+108h+arg_18]
0x140010ea8  test    dl, dl
0x140010eaa  jnz     loc_140010ACE
0x140010eb0  mov     [rsi+2Ch], r12d
0x140010eb4  xor     edi, edi
0x140010eb6  mov     [rbx+74h], r12d
0x140010eba  jmp     loc_140010ACE
0x140010ebf  test    r8d, r8d
0x140010ec2  jnz     loc_14003A2D0
0x140010ec8  cmp     [rsp+108h+var_60], r12d
0x140010ed0  jz      loc_140010AC6
0x140010ed6  jmp     loc_14003A2D0
0x140010edb  movzx   edx, byte ptr [rsp+108h+arg_0]; jumptable 0000000140010C2C case 6
0x140010ee3  cmp     dl, 2
0x140010ee6  jnz     loc_14003A2F4
0x140010eec  mov     eax, [rsi+2Ch]
0x140010eef  xor     edi, edi
0x140010ef1  mov     [rbx+74h], eax
0x140010ef4  jmp     loc_140010AC6
0x140010ef9  movzx   edx, dil; jumptable 0000000140010C2C default case
0x140010efd  jmp     loc_14003A2F4
  ... truncated ...
```
