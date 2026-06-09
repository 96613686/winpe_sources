# SmbCseSubmitBufferContext

- ea: `0x14000b4b0`
- end: `0x14000c01c`
- name: `SmbCseSubmitBufferContext`
- size: `2924`
- prototype: ``
- caller_count: `4`
- callee_count: `33`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400099d0`
- `0x14000c880`
- `0x140048f20`
- `0x1400831e0`

## callees

- `0x140003480`
- `0x140006660`
- `0x140006bb0`
- `0x140009360`
- `0x140009fc0`
- `0x14000b4b0`
- `0x14000c030`
- `0x14000c6a0`
- `0x14000c990`
- `0x14000cfa0`
- `0x14000d910`
- `0x14000df60`
- `0x14000fbe0`
- `0x1400147b0`
- `0x1400148f0`
- `0x1400149d0`
- `0x14001b2a0`
- `0x14001bc70`
- `0x14001c050`
- `0x14001c9d0`
- `0x1400215b0`
- `0x1400272dc`
- `0x140028960`
- `0x140038068`
- `0x1400383d0`
- `0x14003e14c`
- `0x14004843c`
- `0x1400488e8`
- `0x140048954`
- `0x140056974`
- `0x140059ea0`
- `0x14005a200`
- `0x14008d220`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000b6aa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000b775`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005c9c9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005ca3c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000b6aa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000b775`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005c9c9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005ca3c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b6d8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b799`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c9e5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005ca58`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b6d8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b799`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c9e5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005ca58`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000bc6f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000bc6f`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005c86d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005c86d`
- `rdbss!RxCeTrackTransportOpEx` at `0x14000b977`
- `rdbss!RxCeTrackTransportOpEx` at `0x14005c672`
- `rdbss!RxCeTrackTransportOpEx` at `0x14000b977`
- `rdbss!RxCeTrackTransportOpEx` at `0x14005c672`
- `rdbss!RxCeUntrackTransportOpEx` at `0x14000bd6a`
- `rdbss!RxCeUntrackTransportOpEx` at `0x14005c6da`
- `rdbss!RxCeUntrackTransportOpEx` at `0x14000bd6a`
- `rdbss!RxCeUntrackTransportOpEx` at `0x14005c6da`
- `rdbss!RxPerProcessCountersEnabled` at `0x14000ba7a`
- `rdbss!RxPerProcessCountersEnabled` at `0x14000ba7a`

## pseudocode

```c
__int64 __fastcall SmbCseSubmitBufferContext(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // r13
  __int64 v4; // rsi
  __int64 v5; // r15
  __int64 v6; // r12
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  int v11; // r14d
  __int64 v12; // rcx
  PVOID v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rsi
  int v16; // eax
  _QWORD *v17; // rdi
  __int64 v18; // r14
  unsigned int v19; // esi
  __int64 PaddingMdl; // rcx
  __int64 *v21; // rdx
  __int64 *v22; // r8
  _QWORD *v23; // rcx
  _DWORD *v25; // rsi
  __int64 v26; // rsi
  __int64 v27; // rax
  __int64 v28; // r14
  __int64 v29; // rcx
  int v30; // eax
  PVOID v31; // rax
  __int64 Timer_high; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  int v35; // eax
  PDEVICE_OBJECT v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rdx
  unsigned int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r8
  unsigned int v42; // r14d
  __int64 v43; // rcx
  __int64 v44; // rdx
  _QWORD *v45; // rax
  __int64 v46; // rax
  int v47; // edi
  unsigned __int64 v48; // r9
  unsigned int v49; // ecx
  __int64 v50; // rax
  unsigned __int64 v51; // rax
  __int64 v52; // r13
  __int64 v53; // rax
  __int64 v54; // rbx
  int v55; // ecx
  __int64 v56; // rdx
  __int64 v57; // rax
  __int64 v58; // rdi
  PVOID v59; // r15
  KSPIN_LOCK *v60; // r13
  __int64 v61; // rdx
  unsigned int v62; // eax
  __int64 v63; // rsi
  KIRQL v64; // al
  KIRQL v65; // di
  unsigned int LockArray_high; // eax
  __int64 v67; // rcx
  __int64 v68; // rax
  int v69; // eax
  KSPIN_LOCK *v70; // r12
  KSPIN_LOCK *v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // r12
  void *Priority; // [rsp+28h] [rbp-A1h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-89h] BYREF
  __int64 v76; // [rsp+58h] [rbp-71h]
  __int64 v77; // [rsp+60h] [rbp-69h]
  __int64 v78; // [rsp+68h] [rbp-61h]
  _QWORD v79[22]; // [rsp+70h] [rbp-59h] BYREF
  unsigned __int64 v80; // [rsp+130h] [rbp+67h] BYREF
  int v81; // [rsp+138h] [rbp+6Fh]
  PVOID pContext; // [rsp+140h] [rbp+77h]
  __int64 v83; // [rsp+148h] [rbp+7Fh]

  v1 = *(_QWORD *)(a1 + 56);
  v3 = a1;
  v4 = *(_QWORD *)(v1 + 96);
  v5 = *(_QWORD *)(v1 + 56);
  v83 = *(_QWORD *)(v1 + 72);
  v6 = *(_QWORD *)(v4 + 392);
  v77 = v4;
  v78 = v5;
  pContext = *(PVOID *)(v6 + 512);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v76 = *(_QWORD *)(v1 + 80);
  memset(v79, 0, 0x68u);
  v10 = *(_DWORD *)(v4 + 12);
  v11 = 0;
  if ( v10 && v10 != 3 )
  {
    v11 = *(_DWORD *)(v4 + 272);
    if ( v11 >= 0 )
    {
      __int2c();
      return (unsigned int)v11;
    }
    v81 = *(_DWORD *)(v4 + 276);
    goto LABEL_24;
  }
  if ( (*(_DWORD *)(v1 + 68) & 0x100) != 0 )
  {
    v47 = 16;
    v81 = 16;
    v11 = -1073741536;
    goto LABEL_163;
  }
  v12 = *(_QWORD *)(a1 + 96);
  *(_DWORD *)(a1 + 4) |= 0x200u;
  *(_DWORD *)(a1 + 872) = 0;
  v81 = 0;
  if ( (*(_BYTE *)(v12 + 10) & 5) != 0 )
    v13 = *(PVOID *)(v12 + 24);
  else
    v13 = MmMapLockedPagesSpecifyCache((PMDL)v12, 0, MmCached, 0, 0, 0x40000010u);
  if ( !v13 )
  {
    v11 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqqL(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_ca2d5009ac97347054a9c333c3e72a58_Traceguids,
        *(_QWORD *)(v1 + 48),
        v1,
        a1,
        -1073741670);
    }
    goto LABEL_97;
  }
  if ( v5 )
    SmbCeAcquireCompoundingKeyLock(v5, v7, v8, v9);
  else
    SmbCeAcquireExchangeLock(*(_QWORD *)(a1 + 56));
  v15 = (_QWORD *)(a1 + 760);
  if ( !*(_QWORD *)(a1 + 760) && *(_DWORD *)(a1 + 776) )
  {
    *(_DWORD *)(a1 + 4) |= 0x800u;
    LODWORD(v80) = 0;
    *(_BYTE *)(a1 + 84) = 1;
    if ( v5 )
      SmbCeReleaseCompoundingKeyLock(v5);
    else
      SmbCeReleaseExchangeLock(*(PVOID *)(a1 + 56));
    v35 = *(_DWORD *)(a1 + 4);
    if ( (v35 & 0x2000) != 0 )
    {
      if ( *(_DWORD *)(v6 + 320) == 2 )
      {
        if ( *(_QWORD *)(a1 + 528) != a1 + 528 )
          __int2c();
        *(_QWORD *)(a1 + 360) = *(_QWORD *)(v6 + 104) & 0xFFFFFFFFFFFFFFF8uLL | 5;
        RxCeTrackTransportOpEx(a1 + 344, 1, *(_QWORD *)(v6 + 104), a1);
        LOBYTE(v38) = 25;
        RDR_PERF_ENTER(a1 + 880, v38);
        Priority = &SmbCeMemoryRegisterCompleteInd;
        v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64))(SmbdFastDispatch + 16))(
                *(_QWORD *)(v6 + 104),
                *(_QWORD *)(a1 + 768),
                *(unsigned int *)(a1 + 776),
                a1 + 760,
                a1);
        v11 = v39;
        if ( v39 != 259 )
          RxCeUntrackTransportOpEx(a1 + 344, v39);
      }
      else if ( *(_DWORD *)(v6 + 320) == 3 )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v6 + 128) + 52LL) & 1) != 0 )
        {
          *v15 = -1;
        }
        else
        {
          LOBYTE(v34) = 1;
          v11 = VmbusRegisterBuffer(v6, *(_QWORD *)(a1 + 768), *(_DWORD *)(a1 + 776), v34, a1 + 760);
        }
      }
      else
      {
        v11 = -1073741595;
      }
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (Timer_high & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v40 = 22;
LABEL_175:
          LODWORD(Priority) = v11;
          WPP_SF_qdD(v36->AttachedDevice, v40, v33, a1, *(_DWORD *)(a1 + 776));
        }
      }
    }
    else
    {
      v11 = -1073741811;
      if ( (v35 & 0x4000) == 0 )
        goto LABEL_186;
      if ( *(_DWORD *)(v6 + 320) == 2 )
      {
        if ( *(_QWORD *)(a1 + 528) != a1 + 528 )
          __int2c();
        *(_QWORD *)(a1 + 360) = *(_QWORD *)(v6 + 104) & 0xFFFFFFFFFFFFFFF8uLL | 5;
        RxCeTrackTransportOpEx(a1 + 344, 1, *(_QWORD *)(v6 + 104), a1);
        LOBYTE(v61) = 26;
        RDR_PERF_ENTER(a1 + 880, v61);
        Priority = &SmbCeMemoryRegisterCompleteInd;
        v62 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64))(SmbdFastDispatch + 8))(
                *(_QWORD *)(v6 + 104),
                *(_QWORD *)(a1 + 768),
                *(unsigned int *)(a1 + 776),
                a1 + 760,
                a1);
        v11 = v62;
        if ( v62 != 259 )
          RxCeUntrackTransportOpEx(a1 + 344, v62);
      }
      else if ( *(_DWORD *)(v6 + 320) == 3 )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v6 + 128) + 52LL) & 1) != 0 )
        {
          *v15 = -1;
          v11 = 0;
        }
        else
        {
          v11 = VmbusRegisterBuffer(v6, *(_QWORD *)(a1 + 768), *(_DWORD *)(a1 + 776), 0, a1 + 760);
        }
      }
      else
      {
        v11 = -1073741595;
      }
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v40 = 23;
        goto LABEL_175;
      }
    }
    if ( v11 >= 0 )
    {
      if ( v11 == 259 )
        return (unsigned int)v11;
      if ( v5 )
        SmbCeAcquireCompoundingKeyLock(v5, Timer_high, v33, v34);
      else
        SmbCeAcquireExchangeLock(*(_QWORD *)(a1 + 56));
      *(_DWORD *)(a1 + 4) &= ~0x800u;
      LOBYTE(v37) = 27;
      *(_BYTE *)(a1 + 84) = 0;
      *(_BYTE *)(a1 + 87) = 1;
      RDR_PERF_ENTER(a1 + 880, v37);
      v14 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 96LL) + 392LL);
      if ( *(_DWORD *)(v14 + 320) == 2 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int64 *))(SmbdFastDispatch + 48))(*v15, 0, &v80);
      }
      else if ( *(_DWORD *)(v14 + 320) == 3 )
      {
        if ( *v15 == -1 )
          v55 = 8
              * ((*(unsigned int *)(*(_QWORD *)(a1 + 768) + 40LL)
                + 4095LL
                + (unsigned __int64)(*(_DWORD *)(*(_QWORD *)(a1 + 768) + 44LL) & 0xFFF)) >> 12)
              + 8;
        else
          v55 = 16;
        LODWORD(v80) = v55;
      }
      if ( *(unsigned __int16 *)(a1 + 784) < (unsigned int)v80 )
      {
        v11 = -1073741507;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_ca2d5009ac97347054a9c333c3e72a58_Traceguids, a1, v1);
        }
        if ( v5 )
          SmbCeReleaseCompoundingKeyLock(v5);
        else
          SmbCeReleaseExchangeLock(*(PVOID *)(a1 + 56));
        v47 = 0;
        goto LABEL_163;
      }
      goto LABEL_9;
    }
LABEL_186:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_ca2d5009ac97347054a9c333c3e72a58_Traceguids,
        *(_QWORD *)(a1 + 56),
        a1,
        v11);
    }
    if ( v5 )
    {
      SmbCeAcquireCompoundingKeyLock(v5, Timer_high, v33, v34);
      *(_DWORD *)(a1 + 4) &= ~0x800u;
      *(_BYTE *)(a1 + 84) = 0;
      SmbCeReleaseCompoundingKeyLock(v5);
      goto LABEL_24;
    }
    SmbCeAcquireExchangeLock(*(_QWORD *)(a1 + 56));
    *(_DWORD *)(a1 + 4) &= ~0x800u;
    *(_BYTE *)(a1 + 84) = 0;
    goto LABEL_193;
  }
LABEL_9:
  if ( !v5 || (v16 = *(_DWORD *)(a1 + 4), (v16 & 0x40) != 0) )
  {
    LOBYTE(v80) = 0;
    if ( v5 )
    {
      v52 = *(_QWORD *)(v5 + 48);
      if ( v52 == v5 + 48 )
        v3 = 0;
      else
        v3 = v52 - 64;
      v1 = *(_QWORD *)(v3 + 56);
    }
    if ( (*(_DWORD *)(v3 + 4) & 1) != 0 )
      goto LABEL_34;
    if ( byte_14007D25F )
    {
      LOBYTE(v14) = 28;
      RDR_PERF_ENTER_EX(a1 + 880, v14);
    }
    v25 = pContext;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)pContext + 32, &LockHandle);
    v11 = SmbCseAssociateMidWithBufferContextLite(v25, v3);
    if ( *(_DWORD *)(v6 + 320) == 2 )
    {
      LODWORD(v79[2]) = v25[20];
      LOBYTE(v80) = 1;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_ca2d5009ac97347054a9c333c3e72a58_Traceguids,
        v3,
        *(_QWORD *)(v1 + 72),
        v11);
    }
    if ( !v11 )
    {
LABEL_34:
      if ( byte_14007D25F )
      {
        LOBYTE(v14) = 29;
        RDR_PERF_ENTER_EX(a1 + 880, v14);
      }
      v26 = v83;
      v27 = *(_QWORD *)(v83 + 56);
      if ( v27 && (*(unsigned int (__fastcall **)(__int64))(v27 + 872))(v3) )
      {
        if ( v5 )
          SmbCeReleaseCompoundingKeyLock(v5);
        else
          SmbCeReleaseExchangeLock(*(PVOID *)(a1 + 56));
        v63 = *(_QWORD *)(v26 + 24);
        VctSetEndpointState(v6, 1, 0);
        v64 = SmbCeAcquireSpinLock(v63);
        v11 = -1073741300;
        v80 = 0x14C000020CLL;
        v65 = v64;
        SmbCeIndicateDisconnectToBindingObjectsLite(v6, 0x14C000020CLL);
        *(_DWORD *)(v63 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v63 + 1920), v65);
        v47 = 0;
        goto LABEL_163;
      }
      v28 = v3;
      v29 = 0;
      v83 = 0;
      do
      {
        v30 = *(_DWORD *)(v28 + 4);
        *(_BYTE *)(v28 + 86) = 1;
        if ( (v30 & 4) != 0 )
        {
          *(_BYTE *)(v28 + 85) = 1;
        }
        else
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)pContext + 32, &LockHandle);
          v31 = pContext;
          _InterlockedIncrement((volatile signed __int32 *)pContext + 22);
          SmbCseDissociateMidFromBufferContextLite(v31);
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          v29 = v83;
        }
        v41 = *(_QWORD *)(v28 + 56);
        if ( v41 != v29 )
        {
          if ( (*(_DWORD *)(v41 + 68) & 0x40) != 0 )
          {
            *(_QWORD *)(v41 + 208) = 0x7FFFFFFFFFFFFFFFLL;
          }
          else
          {
            v48 = *(_QWORD *)(v41 + 208);
            v49 = *(_DWORD *)(*(_QWORD *)(v41 + 72) + 768LL);
            v50 = (unsigned int)dword_14007D08C;
            if ( v49 )
              v50 = v49;
            v51 = MEMORY[0xFFFFF78000000008] + 10000000 * v50;
            if ( v48 == 0x7FFFFFFFFFFFFFFFLL || v51 > v48 )
              *(_QWORD *)(v41 + 208) = v51;
          }
          v83 = *(_QWORD *)(v28 + 56);
        }
        if ( !v5 )
        {
          SmbCeReleaseExchangeLock(*(PVOID *)(a1 + 56));
          v42 = *(_DWORD *)(v3 + 728);
          goto LABEL_77;
        }
        v56 = *(_QWORD *)(v28 + 64);
        v28 = 0;
        v29 = v83;
        if ( v56 != v5 + 48 )
          v28 = v56 - 64;
      }
      while ( v28 );
      SmbCeReleaseCompoundingKeyLock(v5);
      v42 = *(_DWORD *)(v5 + 76);
LABEL_77:
      if ( *(_DWORD *)(v6 + 320) != 2 )
      {
        v7 = MEMORY[0xFFFFF78000000008];
        v57 = MEMORY[0xFFFFF78000000008];
        *(_QWORD *)(v3 + 840) = MEMORY[0xFFFFF78000000008];
        if ( (unsigned __int64)(v57 - *(_QWORD *)(v6 + 256)) > 0x1E8480 || *(_BYTE *)(v6 + 265) )
        {
          VctUpdateConnectionPerformance(v6);
          *(_BYTE *)(v6 + 265) = 0;
        }
      }
      if ( (*(_DWORD *)(v3 + 4) & 0x10000) != 0 && (unsigned int)Smb2IsTrafficCompressionActive(v1) )
      {
        v8 = *(_QWORD *)(*(_QWORD *)(v1 + 88) + 424LL);
        LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
        LOBYTE(v80) = 1;
        v7 = *(unsigned int *)(a1 + 872);
        LODWORD(v7) = v7 | 0x1000000;
        v67 = *(_QWORD *)(v8 + 1480) + 192LL * (LockArray_high % *(_DWORD *)(v8 + 1488));
        *(_DWORD *)(a1 + 872) = v7;
        v79[3] = v67 + 128;
        v79[5] = v67 + 136;
        v79[4] = v67 + 144;
        if ( *(_BYTE *)(v6 + 596) )
          HIDWORD(v79[2]) |= 1u;
        v68 = *(_QWORD *)(*(_QWORD *)(v3 + 56) + 48LL);
        if ( v68 && (*(_DWORD *)(v68 + 120) & 0x1000) != 0 && v42 >= dword_14007D0AC )
        {
          LODWORD(v7) = v7 | 0x80000000;
          *(_DWORD *)(a1 + 872) = v7;
        }
      }
      if ( (*(_DWORD *)(v3 + 4) & 0x8000) == 0 )
        goto LABEL_80;
      v79[1] = *(_QWORD *)(v76 + 440);
      if ( *(_DWORD *)(v6 + 320) != 4 || !*(_BYTE *)(v6 + 604) )
        *(_DWORD *)(a1 + 872) |= 0x40000000u;
      v46 = *(_QWORD *)(*(_QWORD *)(v3 + 56) + 48LL);
      if ( v46 && (*(_DWORD *)(v46 + 120) & 0x1000) != 0 && v42 >= dword_14007D0A8 )
        *(_DWORD *)(a1 + 872) |= 0x80000000;
      v79[0] = *(_QWORD *)(v77 + 528);
      if ( v79[0] )
      {
        LOBYTE(v80) = 1;
LABEL_80:
        if ( (unsigned __int8)RxPerProcessCountersEnabled() )
        {
          if ( v5 )
            v1 = *(_QWORD *)(v5 + 8LL * (unsigned int)(*(_DWORD *)(v5 + 168) - 1) + 176);
          v43 = *(_QWORD *)(v1 + 48);
          if ( v43 && *(int *)(v43 + 120) >= 0 )
          {
            if ( *(_DWORD *)(v6 + 368) )
              _InterlockedAdd(
                (volatile signed __int32 *)(v43 + 192),
                _InterlockedExchange((volatile __int32 *)(v6 + 368), 0));
            _InterlockedAdd((volatile signed __int32 *)(v43 + 192), v42);
          }
          else
          {
            _InterlockedAdd((volatile signed __int32 *)(v6 + 368), v42);
          }
        }
        v44 = v42;
        _InterlockedAdd64(
          (volatile signed __int64 *)MRxSmbLegacyPerfCtrs + 32 * (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) + 6,
          v42);
        if ( *(_DWORD *)(v6 + 320) == 2 && *(_QWORD *)(a1 + 344) != a1 + 344 )
          __int2c();
        if ( byte_14007D25F )
        {
          LOBYTE(v44) = 30;
          RDR_PERF_ENTER_EX(a1 + 880, v44);
        }
        v45 = v79;
        if ( !(_BYTE)v80 )
          v45 = 0;
        v11 = VctSend((PRXCE_VC)v6, *(_DWORD *)(a1 + 872), *(PMDL *)(a1 + 96), v42, v45, (int)Priority, v3);
        goto LABEL_24;
      }
      v11 = -1073741300;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          WPP_ca2d5009ac97347054a9c333c3e72a58_Traceguids,
          v1,
          -1073741300);
        v47 = 0;
        goto LABEL_163;
      }
LABEL_97:
      v47 = 0;
      goto LABEL_163;
    }
    if ( v5 )
    {
      SmbCeReleaseCompoundingKeyLock(v5);
      goto LABEL_24;
    }
LABEL_193:
    SmbCeReleaseExchangeLock(*(PVOID *)(a1 + 56));
    goto LABEL_24;
  }
  v17 = (_QWORD *)(v5 + 48);
  if ( (_QWORD *)*v17 == v17 )
  {
    *(_DWORD *)(a1 + 4) = v16 | 0x80;
    goto LABEL_17;
  }
  v18 = *(_QWORD *)(v5 + 56);
  v19 = ((*(_DWORD *)(v18 + 664) + 7) & 0xFFFFFFF8) - *(_DWORD *)(v18 + 664);
  if ( !v19 )
  {
LABEL_17:
    v23 = *(_QWORD **)(v5 + 56);
    if ( (_QWORD *)*v23 != v17 )
      __fastfail(3u);
    *(_QWORD *)(a1 + 64) = v17;
    *(_QWORD *)(a1 + 72) = v23;
    *v23 = a1 + 64;
    *(_QWORD *)(v5 + 56) = a1 + 64;
    ++*(_DWORD *)(v5 + 64);
    *(_DWORD *)(a1 + 4) |= 0x40u;
    *(_BYTE *)(a1 + 84) = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_2ecbbf7dc68f37694aaad8a30b991413_Traceguids, a1);
    }
    v11 = 259;
    goto LABEL_23;
  }
  PaddingMdl = SmbMmAllocatePaddingMdl(v19);
  if ( PaddingMdl )
  {
    v21 = *(__int64 **)(v18 + 32);
    v22 = (__int64 *)*v21;
    if ( *v21 )
    {
      do
      {
        v21 = v22;
        v22 = (__int64 *)*v22;
      }
      while ( v22 );
    }
    *v21 = PaddingMdl;
    *(_DWORD *)(v18 + 664) += v19;
    goto LABEL_17;
  }
  v11 = -1073741670;
LABEL_23:
  SmbCeReleaseCompoundingKeyLock(v5);
LABEL_24:
  if ( v11 >= 0 )
    return (unsigned int)v11;
  v47 = v81;
LABEL_163:
  if ( *(_BYTE *)(a1 + 1379) )
  {
    RDR_PERF_EXIT(a1 + 880);
    RDR_PERF_OUTPUT_ETW(a1 + 880);
    RDR_PERF_FREE(a1 + 880);
    v47 = v81;
  }
  if ( v5 )
    SmbCeAcquireCompoundingKeyLock(v5, v7, v8, v9);
  else
    SmbCeAcquireExchangeLock(*(_QWORD *)(a1 + 56));
  v69 = SmbCseInvalidateMemoryRegistrationAsync(a1);
  if ( v69 == 259 )
  {
    v80 = (unsigned int)v11;
    SmbCseUpdateBufferContextStatus(a1, (unsigned int)v11);
    v11 = 259;
  }
  else if ( v69 != -1073741816 )
  {
    *(_BYTE *)(a1 + 87) = 0;
  }
  if ( v5 )
    SmbCseUnchainCompoundedBufferContextsLite(v5);
  v70 = (KSPIN_LOCK *)pContext;
  if ( (*(_DWORD *)(v3 + 4) & 0x40) == 0 )
  {
    v71 = (KSPIN_LOCK *)((char *)pContext + 256);
    *(_WORD *)(v3 + 85) = 0;
    KeAcquireInStackQueuedSpinLock(v71, &LockHandle);
    SmbCseDissociateMidFromBufferContextLite(v70);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v80 = __PAIR64__(v47, v11);
    SmbCseUpdateBufferContextStatus(v3, __PAIR64__(v47, v11));
  }
  if ( v5 )
  {
    v53 = *(_QWORD *)(v5 + 48);
    v54 = v5 + 48;
    if ( v53 != v5 + 48 )
    {
      v58 = v53 - 64;
      if ( v53 != 64 )
      {
        v59 = pContext;
        v60 = v70 + 32;
        do
        {
          v72 = *(_QWORD *)(v58 + 64);
          *(_WORD *)(v58 + 85) = 0;
          v73 = 0;
          if ( v72 != v54 )
            v73 = v72 - 64;
          KeAcquireInStackQueuedSpinLock(v60, &LockHandle);
          SmbCseDissociateMidFromBufferContextLite(v59);
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          v80 = __PAIR64__(v81, v11);
          SmbCseUpdateBufferContextStatus(v58, __PAIR64__(v81, v11));
          if ( (unsigned __int8)SmbCepCheckExchangeForDeferredAbortOrIfFinalizable(*(_QWORD *)(v58 + 56)) )
            SmbCepCompleteExchangeLite(*(_QWORD *)(v58 + 56));
          v58 = v73;
        }
        while ( v73 );
        v5 = v78;
      }
    }
    SmbCeReleaseCompoundingKeyLock(v5);
  }
  else
  {
    SmbCeReleaseExchangeLock(*(PVOID *)(a1 + 56));
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000b4b0  push    rbp
0x14000b4b2  push    rbx
0x14000b4b3  push    rsi
0x14000b4b4  push    rdi
0x14000b4b5  push    r12
0x14000b4b7  push    r13
0x14000b4b9  push    r14
0x14000b4bb  push    r15
0x14000b4bd  lea     rbp, [rsp-1Fh]
0x14000b4c2  sub     rsp, 0E8h
0x14000b4c9  mov     rdi, [rcx+38h]
0x14000b4cd  xorps   xmm0, xmm0
0x14000b4d0  mov     rbx, rcx
0x14000b4d3  mov     r13, rcx
0x14000b4d6  xor     edx, edx; Val
0x14000b4d8  lea     rcx, [rbp+57h+var_B0]; void *
0x14000b4dc  mov     r8d, 68h ; 'h'; Size
0x14000b4e2  mov     rsi, [rdi+60h]
0x14000b4e6  mov     rax, [rdi+48h]
0x14000b4ea  mov     r15, [rdi+38h]
0x14000b4ee  mov     [rbp+57h+arg_18], rax
0x14000b4f2  mov     r12, [rsi+188h]
0x14000b4f9  mov     [rbp+57h+var_C0], rsi
0x14000b4fd  mov     [rbp+57h+var_B8], r15
0x14000b501  mov     rax, [r12+200h]
0x14000b509  mov     [rbp+57h+pContext], rax
0x14000b50d  xor     eax, eax
0x14000b50f  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000b513  movups  xmmword ptr [rsp+120h+LockHandle.LockQueue.Next], xmm0
0x14000b518  mov     rax, [rdi+50h]
0x14000b51c  mov     [rbp+57h+var_C8], rax
0x14000b520  call    memset
0x14000b525  mov     eax, [rsi+0Ch]
0x14000b528  xor     r14d, r14d
0x14000b52b  test    eax, eax
0x14000b52d  jnz     loc_14000BCEB
0x14000b533  mov     eax, [rdi+44h]
0x14000b536  bt      eax, 8
0x14000b53a  jb      loc_14000BD0C
0x14000b540  mov     rcx, [rbx+60h]; MemoryDescriptorList
0x14000b544  or      dword ptr [rbx+4], 200h
0x14000b54b  mov     [rbx+368h], r14d
0x14000b552  mov     [rbp+57h+arg_8], r14d
0x14000b556  test    byte ptr [rcx+0Ah], 5
0x14000b55a  jz      loc_14000BC57
0x14000b560  mov     rax, [rcx+18h]
0x14000b564  test    rax, rax
0x14000b567  jz      loc_14005C5F2
0x14000b56d  test    r15, r15
0x14000b570  jnz     loc_14000BD23
0x14000b576  mov     rcx, [rbx+38h]
0x14000b57a  call    SmbCeAcquireExchangeLock
0x14000b57f  lea     rsi, [rbx+2F8h]
0x14000b586  cmp     [rsi], r14
0x14000b589  jz      loc_14000B7C2
0x14000b58f  test    r15, r15
0x14000b592  jz      loc_14000B678
0x14000b598  mov     eax, [rbx+4]
0x14000b59b  test    al, 40h
0x14000b59d  jnz     loc_14000B678
0x14000b5a3  lea     rdi, [r15+30h]
0x14000b5a7  cmp     [rdi], rdi
0x14000b5aa  jz      short loc_14000B5F0
0x14000b5ac  mov     r14, [r15+38h]
0x14000b5b0  mov     eax, [r14+298h]
0x14000b5b7  lea     esi, [rax+7]
0x14000b5ba  and     esi, 0FFFFFFF8h
0x14000b5bd  sub     esi, eax
0x14000b5bf  jz      short loc_14000B5F7
0x14000b5c1  mov     ecx, esi
0x14000b5c3  call    SmbMmAllocatePaddingMdl
0x14000b5c8  mov     rcx, rax
0x14000b5cb  test    rax, rax
0x14000b5ce  jz      loc_14000BE0A
0x14000b5d4  mov     rdx, [r14+20h]
0x14000b5d8  mov     r8, [rdx]
0x14000b5db  test    r8, r8
0x14000b5de  jnz     loc_14000BE15
0x14000b5e4  mov     [rdx], rcx
0x14000b5e7  add     [r14+298h], esi
0x14000b5ee  jmp     short loc_14000B5F7
0x14000b5f0  bts     eax, 7
0x14000b5f4  mov     [rbx+4], eax
0x14000b5f7  mov     rcx, [rdi+8]
0x14000b5fb  cmp     [rcx], rdi
0x14000b5fe  jnz     loc_14000BC1D
0x14000b604  mov     [rbx+40h], rdi
0x14000b608  lea     rax, [rbx+40h]
0x14000b60c  mov     [rax+8], rcx
0x14000b610  mov     [rcx], rax
0x14000b613  mov     [rdi+8], rax
0x14000b617  inc     dword ptr [r15+40h]
0x14000b61b  or      dword ptr [rbx+4], 40h
0x14000b61f  mov     byte ptr [rbx+54h], 1
0x14000b623  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b62a  lea     rax, WPP_GLOBAL_Control
0x14000b631  cmp     rcx, rax
0x14000b634  jz      short loc_14000B647
0x14000b636  mov     eax, [rcx+2Ch]
0x14000b639  test    al, 20h
0x14000b63b  jz      short loc_14000B647
0x14000b63d  cmp     byte ptr [rcx+29h], 2
0x14000b641  jnb     loc_14000BE28
0x14000b647  mov     r14d, 103h
0x14000b64d  mov     rcx, r15
0x14000b650  call    SmbCeReleaseCompoundingKeyLock
0x14000b655  xor     esi, esi
0x14000b657  test    r14d, r14d
0x14000b65a  js      loc_14000BFC0
0x14000b660  mov     eax, r14d
0x14000b663  add     rsp, 0E8h
0x14000b66a  pop     r15
0x14000b66c  pop     r14
0x14000b66e  pop     r13
0x14000b670  pop     r12
0x14000b672  pop     rdi
0x14000b673  pop     rsi
0x14000b674  pop     rbx
0x14000b675  pop     rbp
0x14000b676  retn
0x14000b678  mov     byte ptr [rbp+57h+arg_0], 0
0x14000b67c  test    r15, r15
0x14000b67f  jnz     loc_14000BC97
0x14000b685  mov     eax, [r13+4]
0x14000b689  test    al, 1
0x14000b68b  jnz     short loc_14000B704
0x14000b68d  cmp     cs:byte_14007D25F, 0
0x14000b694  jnz     loc_14000B901
0x14000b69a  mov     rsi, [rbp+57h+pContext]
0x14000b69e  lea     rdx, [rsp+120h+LockHandle]; LockHandle
0x14000b6a3  lea     rcx, [rsi+100h]; SpinLock
0x14000b6aa  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000b6b1  nop     dword ptr [rax+rax+00h]
0x14000b6b6  mov     rdx, r13
0x14000b6b9  mov     rcx, rsi
0x14000b6bc  call    SmbCseAssociateMidWithBufferContextLite
0x14000b6c1  cmp     dword ptr [r12+140h], 2
0x14000b6ca  mov     r14d, eax
0x14000b6cd  jz      loc_14000BE45
0x14000b6d3  lea     rcx, [rsp+120h+LockHandle]; LockHandle
0x14000b6d8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000b6df  nop     dword ptr [rax+rax+00h]
0x14000b6e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6eb  lea     rax, WPP_GLOBAL_Control
0x14000b6f2  cmp     rcx, rax
0x14000b6f5  jnz     loc_14000BE54
0x14000b6fb  test    r14d, r14d
0x14000b6fe  jnz     loc_14000BE94
0x14000b704  cmp     cs:byte_14007D25F, 0
0x14000b70b  jnz     loc_14000B8EE
0x14000b711  mov     rsi, [rbp+57h+arg_18]
0x14000b715  mov     rax, [rsi+38h]
0x14000b719  test    rax, rax
0x14000b71c  jz      short loc_14000B735
0x14000b71e  mov     rax, [rax+368h]
0x14000b725  mov     rcx, r13
0x14000b728  call    _guard_dispatch_icall
0x14000b72d  test    eax, eax
0x14000b72f  jnz     loc_14000BEAC
0x14000b735  xor     esi, esi
0x14000b737  mov     r14, r13
0x14000b73a  mov     ecx, esi
0x14000b73c  mov     rdx, 0FFFFF78000000008h
0x14000b746  mov     [rbp+57h+arg_18], rcx
0x14000b74a  mov     r10, 7FFFFFFFFFFFFFFFh
0x14000b754  mov     eax, [r14+4]
0x14000b758  mov     byte ptr [r14+56h], 1
0x14000b75d  test    al, 4
0x14000b75f  jnz     loc_14000BA0D
0x14000b765  mov     rcx, [rbp+57h+pContext]
0x14000b769  lea     rdx, [rsp+120h+LockHandle]; LockHandle
0x14000b76e  add     rcx, 100h; SpinLock
0x14000b775  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000b77c  nop     dword ptr [rax+rax+00h]
0x14000b781  mov     rax, [rbp+57h+pContext]
0x14000b785  lock inc dword ptr [rax+58h]
0x14000b789  mov     rdx, r14
0x14000b78c  mov     rcx, rax; pContext
0x14000b78f  call    SmbCseDissociateMidFromBufferContextLite
0x14000b794  lea     rcx, [rsp+120h+LockHandle]; LockHandle
0x14000b799  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000b7a0  nop     dword ptr [rax+rax+00h]
0x14000b7a5  mov     rcx, [rbp+57h+arg_18]
0x14000b7a9  mov     rdx, 0FFFFF78000000008h
0x14000b7b3  mov     r10, 7FFFFFFFFFFFFFFFh
0x14000b7bd  jmp     loc_14000BA12
0x14000b7c2  cmp     [rbx+308h], r14d
0x14000b7c9  jz      loc_14000B58F
0x14000b7cf  or      dword ptr [rbx+4], 800h
0x14000b7d6  mov     dword ptr [rbp+57h+arg_0], r14d
0x14000b7da  mov     byte ptr [rbx+54h], 1
0x14000b7de  test    r15, r15
0x14000b7e1  jz      loc_14000B914
0x14000b7e7  mov     rcx, r15
0x14000b7ea  call    SmbCeReleaseCompoundingKeyLock
0x14000b7ef  mov     eax, [rbx+4]
0x14000b7f2  bt      eax, 0Dh
0x14000b7f6  jb      loc_14000B930
0x14000b7fc  mov     r14d, 0C000000Dh
0x14000b802  bt      eax, 0Eh
0x14000b806  jnb     loc_14005C785
0x14000b80c  mov     ecx, [r12+140h]
0x14000b814  sub     ecx, 2
0x14000b817  jz      loc_14000BC80
0x14000b81d  cmp     ecx, 1
0x14000b820  jnz     loc_14000BD7B
0x14000b826  mov     rax, [r12+80h]
0x14000b82e  mov     ecx, [rax+34h]
0x14000b831  test    cl, 1
0x14000b834  jz      loc_14000BD86
0x14000b83a  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x14000b841  xor     r14d, r14d
0x14000b844  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b84b  lea     rax, WPP_GLOBAL_Control
0x14000b852  cmp     rcx, rax
0x14000b855  jnz     loc_14000BDAC
0x14000b85b  test    r14d, r14d
0x14000b85e  js      loc_14005C785
0x14000b864  cmp     r14d, 103h
0x14000b86b  jz      loc_14000B660
0x14000b871  test    r15, r15
0x14000b874  jz      loc_14000B922
0x14000b87a  mov     rcx, r15
0x14000b87d  call    SmbCeAcquireCompoundingKeyLock
0x14000b882  and     dword ptr [rbx+4], 0FFFFF7FFh
0x14000b889  lea     rcx, [rbx+370h]
0x14000b890  mov     dl, 1Bh
0x14000b892  mov     byte ptr [rbx+54h], 0
0x14000b896  mov     byte ptr [rbx+57h], 1
0x14000b89a  call    RDR_PERF_ENTER
0x14000b89f  mov     rax, [rbx+38h]
0x14000b8a3  mov     rcx, [rax+60h]
0x14000b8a7  mov     rdx, [rcx+188h]
0x14000b8ae  mov     ecx, [rdx+140h]
0x14000b8b4  sub     ecx, 2
0x14000b8b7  jnz     loc_14000BDCB
0x14000b8bd  mov     rax, cs:SmbdFastDispatch
0x14000b8c4  lea     r8, [rbp+57h+arg_0]
0x14000b8c8  mov     rcx, [rsi]
0x14000b8cb  xor     edx, edx
0x14000b8cd  mov     rax, [rax+30h]
0x14000b8d1  call    _guard_dispatch_icall
0x14000b8d6  movzx   eax, word ptr [rbx+310h]
0x14000b8dd  cmp     eax, dword ptr [rbp+57h+arg_0]
0x14000b8e0  jb      loc_14005C71A
0x14000b8e6  xor     r14d, r14d
0x14000b8e9  jmp     loc_14000B58F
0x14000b8ee  lea     rcx, [rbx+370h]
0x14000b8f5  mov     dl, 1Dh
0x14000b8f7  call    RDR_PERF_ENTER_EX
0x14000b8fc  jmp     loc_14000B711
0x14000b901  lea     rcx, [rbx+370h]
0x14000b908  mov     dl, 1Ch
0x14000b90a  call    RDR_PERF_ENTER_EX
0x14000b90f  jmp     loc_14000B69A
0x14000b914  mov     rcx, [rbx+38h]
0x14000b918  call    SmbCeReleaseExchangeLock
0x14000b91d  jmp     loc_14000B7EF
0x14000b922  mov     rcx, [rbx+38h]
0x14000b926  call    SmbCeAcquireExchangeLock
0x14000b92b  jmp     loc_14000B882
0x14000b930  mov     ecx, [r12+140h]
0x14000b938  sub     ecx, 2
0x14000b93b  jnz     loc_14000BC24
0x14000b941  lea     rax, [rbx+210h]
0x14000b948  cmp     [rax], rax
0x14000b94b  jz      short loc_14000B94F
0x14000b94d  int     2Ch; Windows NT - assertion failure
0x14000b94f  mov     rax, [r12+68h]
0x14000b954  lea     rcx, [rbx+158h]
0x14000b95b  and     rax, 0FFFFFFFFFFFFFFFDh
0x14000b95f  mov     r9, rbx
0x14000b962  or      rax, 5
0x14000b966  mov     edx, 1
0x14000b96b  mov     [rbx+168h], rax
0x14000b972  mov     r8, [r12+68h]
0x14000b977  call    cs:__imp_RxCeTrackTransportOpEx
0x14000b97e  nop     dword ptr [rax+rax+00h]
0x14000b983  lea     rcx, [rbx+370h]
0x14000b98a  mov     dl, 19h
0x14000b98c  call    RDR_PERF_ENTER
0x14000b991  mov     rax, cs:SmbdFastDispatch
0x14000b998  lea     rcx, SmbCeMemoryRegisterCompleteInd
0x14000b99f  mov     r8d, [rbx+308h]
0x14000b9a6  mov     r9, rsi
0x14000b9a9  mov     rdx, [rbx+300h]
0x14000b9b0  mov     qword ptr [rsp+120h+Priority], rcx
0x14000b9b5  mov     rax, [rax+10h]
0x14000b9b9  mov     rcx, [r12+68h]
0x14000b9be  mov     qword ptr [rsp+120h+BugCheckOnFailure], rbx
0x14000b9c3  call    _guard_dispatch_icall
0x14000b9c8  mov     r14d, eax
0x14000b9cb  cmp     eax, 103h
0x14000b9d0  jnz     loc_14000BD61
0x14000b9d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b9dd  lea     rax, WPP_GLOBAL_Control
0x14000b9e4  cmp     rcx, rax
0x14000b9e7  jz      loc_14000B85B
0x14000b9ed  mov     edx, [rcx+2Ch]
0x14000b9f0  test    dl, 10h
  ... truncated ...
```
