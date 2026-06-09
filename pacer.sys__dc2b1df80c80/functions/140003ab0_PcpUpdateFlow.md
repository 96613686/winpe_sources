# PcpUpdateFlow

- ea: `0x140003ab0`
- end: `0x1400046b5`
- name: `PcpUpdateFlow`
- size: `3077`
- prototype: `__int64 __fastcall(KAFFINITY, __int64, ULONG, int, char *Src, char, int, _DWORD *, _WORD *, _WORD *)`
- caller_count: `5`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000adf8`
- `0x14000c460`
- `0x14000c5c0`
- `0x140020d30`
- `0x140020ec4`

## callees

- `0x1400023d0`
- `0x140002484`
- `0x1400026c4`
- `0x140002d48`
- `0x140003770`
- `0x140003ab0`
- `0x1400046bc`
- `0x140004c58`
- `0x140004fe0`
- `0x1400051cc`
- `0x140008290`
- `0x140009b80`
- `0x14000a910`
- `0x14000b250`
- `0x14000b2e8`
- `0x14000b584`
- `0x14000bc84`
- `0x140011154`
- `0x140011a34`
- `0x140011a8c`
- `0x1400120f8`
- `0x14001233c`
- `0x140012410`
- `0x140013300`
- `0x140013600`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004094`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400045ec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004652`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004094`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400045ec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004652`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400041be`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400041be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e12`
- `ntoskrnl!ExAllocatePool2` at `0x140003ddd`
- `ntoskrnl!ExAllocatePool2` at `0x140003ddd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003da6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003da6`
- `NDIS!NdisReleaseRWLock` at `0x140004256`
- `NDIS!NdisReleaseRWLock` at `0x1400044e6`
- `NDIS!NdisReleaseRWLock` at `0x1400045dc`
- `NDIS!NdisReleaseRWLock` at `0x140004256`
- `NDIS!NdisReleaseRWLock` at `0x1400044e6`
- `NDIS!NdisReleaseRWLock` at `0x1400045dc`
- `NDIS!NdisAcquireRWLockWrite` at `0x140004234`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400043ad`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400045ba`
- `NDIS!NdisAcquireRWLockWrite` at `0x140004234`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400043ad`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400045ba`

## pseudocode

```c
__int64 __fastcall PcpUpdateFlow(
        KAFFINITY a1,
        __int64 a2,
        ULONG a3,
        int a4,
        char *Src,
        char a6,
        int a7,
        _DWORD *a8,
        _WORD *a9,
        _WORD *a10)
{
  __int64 v11; // r14
  int v12; // edi
  int v13; // r8d
  int v14; // ebx
  __int64 v15; // r9
  int v16; // esi
  int updated; // esi
  unsigned int *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  unsigned int *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  _OWORD *v26; // r8
  ULONG v27; // ecx
  __int64 Pool2; // rsi
  void *v29; // rcx
  int v30; // edx
  _OWORD *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rbx
  unsigned int v34; // esi
  int v35; // eax
  _DWORD *v36; // rcx
  int v37; // eax
  int v38; // eax
  bool v39; // zf
  int v40; // eax
  int *v41; // rcx
  int v42; // eax
  int v43; // eax
  int v44; // eax
  unsigned int v45; // eax
  __int64 v46; // rdx
  int v47; // r15d
  __int64 v48; // rbx
  int v49; // ecx
  char v50; // r15
  PVOID *p_Reserved; // rbx
  __int64 v53; // rax
  PVOID *v54; // r8
  __int64 v55; // rax
  int v56; // eax
  unsigned int v57; // esi
  unsigned int v58; // esi
  unsigned int v59; // esi
  unsigned int v60; // esi
  ULONG CurrentProcessorNumber; // eax
  __int64 v62; // r8
  __int64 v63; // rdx
  ULONG v64; // esi
  __int64 CurrentTime; // rax
  int *v66; // rbx
  int v67; // ecx
  __int64 v68; // rdx
  unsigned __int8 v69; // dl
  int v70; // ecx
  int v71; // r13d
  int v72; // ecx
  char v73; // dl
  __int64 v74; // rax
  unsigned __int64 v75; // rdx
  unsigned int v76; // eax
  char v77; // di
  _QWORD *ProcessorHistory; // rax
  __int64 v79; // [rsp+20h] [rbp-E0h]
  char v80; // [rsp+51h] [rbp-AFh]
  int v81; // [rsp+54h] [rbp-ACh] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp-A8h] BYREF
  ULONG Size; // [rsp+5Ch] [rbp-A4h]
  int Size_4; // [rsp+60h] [rbp-A0h]
  int v85; // [rsp+64h] [rbp-9Ch]
  int v86[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v87; // [rsp+70h] [rbp-90h]
  __int64 v88; // [rsp+78h] [rbp-88h]
  unsigned int v89; // [rsp+80h] [rbp-80h]
  int v90; // [rsp+84h] [rbp-7Ch]
  int v91; // [rsp+88h] [rbp-78h]
  int v92; // [rsp+8Ch] [rbp-74h]
  int v93; // [rsp+90h] [rbp-70h]
  int v94; // [rsp+94h] [rbp-6Ch] BYREF
  _OWORD v95[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v96; // [rsp+B8h] [rbp-48h]
  _QWORD v97[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v98; // [rsp+100h] [rbp+0h] BYREF
  PNET_BUFFER_LIST NetBufferList; // [rsp+108h] [rbp+8h] BYREF
  PNET_BUFFER_LIST v100; // [rsp+110h] [rbp+10h] BYREF
  __int64 v101; // [rsp+118h] [rbp+18h]
  __int64 v102; // [rsp+120h] [rbp+20h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+128h] [rbp+28h] BYREF
  __int128 v104; // [rsp+140h] [rbp+40h]
  __int128 v105; // [rsp+150h] [rbp+50h]
  _QWORD v106[16]; // [rsp+160h] [rbp+60h] BYREF

  v98 = a2;
  Size = a3;
  v85 = a4;
  v101 = (__int64)a9;
  v102 = (__int64)a10;
  memset(v97, 0, sizeof(v97));
  v96 = 0;
  NetBufferList = 0;
  v100 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v90 = 0;
  v11 = 0;
  memset(v95, 0, sizeof(v95));
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(v106, 0, 0x50u);
  v94 = 0;
  *a9 = -1;
  *a10 = -1;
  v12 = 0;
  v104 = 0;
  v105 = 0;
  if ( a8 )
    *a8 = 0;
  v13 = v85;
  v14 = *((_DWORD *)PcgFlowTypeToFeatureFlagsMapping + v85);
  v81 = v14;
  if ( v85 == 2 )
  {
    v15 = *((_QWORD *)Src + 9);
    v16 = *((_DWORD *)Src + 16);
    *(_QWORD *)v86 = *(_QWORD *)Src;
    v87 = *((_QWORD *)Src + 1);
    v88 = *((_QWORD *)Src + 2);
    v89 = *((_DWORD *)Src + 6);
    v91 = -1;
    v92 = -1;
    goto LABEL_19;
  }
  if ( v85 == 1 )
  {
    if ( *(_WORD *)Src > 0x1FEu )
    {
      updated = -1073741811;
LABEL_97:
      *(_WORD *)v101 = -1;
      *(_WORD *)v102 = -1;
      return (unsigned int)updated;
    }
    v16 = *((_DWORD *)Src + 147);
    v11 = PcpLineFindByInstanceName(Src + 2);
    if ( !v11 )
    {
      updated = -1073741275;
      goto LABEL_97;
    }
    v13 = v85;
    v18 = (unsigned int *)(Src + 524);
    LODWORD(v15) = (_DWORD)Src + 592;
  }
  else
  {
    v15 = *((_QWORD *)Src + 9);
    v18 = (unsigned int *)Src;
    v16 = *((_DWORD *)Src + 16);
  }
  v19 = *v18;
  *(_QWORD *)v86 = -1;
  if ( (_DWORD)v19 != -1 )
    *(_QWORD *)v86 = v19;
  v20 = v18[1];
  v87 = -1;
  if ( (_DWORD)v20 != -1 )
    v87 = v20;
  v21 = v18[2];
  v88 = -1;
  if ( (_DWORD)v21 != -1 )
    v88 = v21;
  v89 = v18[5];
  v91 = v18[7];
  v92 = v18[6];
LABEL_19:
  if ( a6 != 1 )
  {
    v22 = *(_QWORD *)(a1 + 600);
    if ( v13 == 2 )
    {
      v95[0] = *(_OWORD *)v22;
      *(_QWORD *)&v95[1] = *(_QWORD *)(v22 + 16);
      DWORD2(v95[1]) = *(_DWORD *)(v22 + 24);
      v96 = -1;
    }
    else
    {
      v23 = (unsigned int *)(v22 + 524);
      if ( v13 != 1 )
        v23 = *(unsigned int **)(a1 + 600);
      *(_QWORD *)&v95[0] = -1;
      if ( *v23 != -1 )
        *(_QWORD *)&v95[0] = *v23;
      v24 = v23[1];
      *((_QWORD *)&v95[0] + 1) = -1;
      if ( (_DWORD)v24 != -1 )
        *((_QWORD *)&v95[0] + 1) = v24;
      v25 = v23[2];
      *(_QWORD *)&v95[1] = -1;
      if ( (_DWORD)v25 != -1 )
        *(_QWORD *)&v95[1] = v25;
      DWORD2(v95[1]) = v23[5];
      LODWORD(v96) = v23[7];
      HIDWORD(v96) = v23[6];
    }
  }
  v26 = v95;
  if ( a6 )
    LODWORD(v26) = 0;
  updated = PcpValidateFlowParameters((int)&v81, (int)v86, (int)v26, v15, v16, v106, a7, v101, v102);
  if ( updated < 0 )
    goto LABEL_94;
  v80 = 0;
  if ( a6 == 1 && (*(_DWORD *)(a1 + 616) & 2) != 0 )
  {
    updated = PcpFilterIncrementIntercept();
    if ( updated < 0 )
      goto LABEL_94;
    v80 = 1;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 96), &LockHandle);
  while ( *(_DWORD *)(a1 + 104) )
    ;
  if ( !a6 )
  {
    v27 = Size;
    if ( *(_DWORD *)(a1 + 608) >= Size )
      goto LABEL_48;
    Pool2 = ExAllocatePool2(64, Size, 1818649424);
    if ( !Pool2 )
    {
      updated = -1073741670;
LABEL_91:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      goto LABEL_92;
    }
    v29 = *(void **)(a1 + 600);
    if ( v29 != (void *)(a1 + 624) )
      ExFreePoolWithTag(v29, 0);
    *(_QWORD *)(a1 + 600) = Pool2;
  }
  v27 = Size;
LABEL_48:
  if ( v98 )
    *(_QWORD *)(a1 + 592) = v98;
  v30 = v85;
  v31 = *(_OWORD **)(a1 + 600);
  *(_DWORD *)(a1 + 608) = v27;
  *(_DWORD *)(a1 + 48) = v14;
  if ( v30 == 2 )
  {
    memmove(v31, Src, v27);
    v32 = *(_QWORD *)(a1 + 600);
    v33 = v87;
    v34 = v89;
    v35 = v90;
    *(_QWORD *)v32 = *(_QWORD *)v86;
    *(_QWORD *)(v32 + 16) = v88;
    *(_QWORD *)(v32 + 8) = v33;
    *(_DWORD *)(v32 + 24) = v34;
    *(_DWORD *)(v32 + 28) = v35;
LABEL_67:
    v45 = *((_DWORD *)Src + 16);
    if ( v45 )
    {
      memmove((void *)(*(_QWORD *)(a1 + 600) + 80LL), *((const void **)Src + 9), v45);
      *(_QWORD *)(*(_QWORD *)(a1 + 600) + 72LL) = *(_QWORD *)(a1 + 600) + 80LL;
    }
    goto LABEL_69;
  }
  if ( v30 != 1 )
  {
    v33 = v87;
    v39 = *(_QWORD *)v86 == -1;
    v34 = v89;
    *v31 = *(_OWORD *)Src;
    v31[1] = *((_OWORD *)Src + 1);
    v31[2] = *((_OWORD *)Src + 2);
    v31[3] = *((_OWORD *)Src + 3);
    v31[4] = *((_OWORD *)Src + 4);
    v41 = *(int **)(a1 + 600);
    v42 = -1;
    if ( !v39 )
      v42 = v86[0];
    *v41 = v42;
    v43 = -1;
    if ( v33 != -1 )
      v43 = v33;
    v41[5] = v34;
    v39 = v88 == -1;
    v41[1] = v43;
    v44 = -1;
    if ( !v39 )
      v44 = v88;
    v41[2] = v44;
    v41[7] = v91;
    v41[6] = v92;
    goto LABEL_67;
  }
  memmove(v31, Src, v27);
  v36 = *(_DWORD **)(a1 + 600);
  v37 = -1;
  v33 = v87;
  if ( *(_QWORD *)v86 != -1 )
    v37 = v86[0];
  v34 = v89;
  v36[131] = v37;
  v38 = -1;
  if ( v33 != -1 )
    v38 = v33;
  v36[136] = v34;
  v39 = v88 == -1;
  v36[132] = v38;
  v40 = -1;
  if ( !v39 )
    v40 = v88;
  v36[133] = v40;
  v36[138] = v91;
  v36[137] = v92;
LABEL_69:
  v46 = *(_QWORD *)v86;
  v97[2] = v88;
  LODWORD(v97[4]) = v91;
  v97[0] = *(_QWORD *)v86;
  v97[1] = v33;
  if ( !v106[8] || (v47 = *(_DWORD *)(v106[8] + 8LL), v47 == -1) )
    v47 = *(_DWORD *)(a1 + 456);
  LODWORD(v97[7]) = v47;
  if ( v47 && !v11 )
  {
    if ( v106[9] )
      v48 = *(_QWORD *)(v106[9] + 8LL);
    else
      v48 = *(_QWORD *)(a1 + 88);
    if ( !v48 )
    {
      updated = -1073741811;
      goto LABEL_91;
    }
    v11 = PcpLineFindByLuid(v48);
    if ( !v11 )
    {
      updated = -1073741275;
      goto LABEL_91;
    }
    v46 = *(_QWORD *)v86;
    *(_QWORD *)(a1 + 88) = v48;
  }
  if ( !v106[5] )
    goto LABEL_99;
  v49 = *(_DWORD *)(v106[5] + 8LL);
  if ( v47 == -1 )
    v47 = *(_DWORD *)(a1 + 456);
  if ( !v47 )
  {
    if ( v46 == -1 && v49 )
    {
      updated = -1073610623;
      goto LABEL_91;
    }
LABEL_99:
    v50 = 1;
    goto LABEL_100;
  }
  v50 = 1;
  if ( (unsigned int)(v49 - 1) > 1 )
  {
    updated = -1073610621;
    goto LABEL_91;
  }
LABEL_100:
  p_Reserved = &WPP_MAIN_CB.Reserved;
  if ( !v11 || (v53 = *(_QWORD *)(v11 + 256), LODWORD(v54) = v53 + 168, !v53) )
    v54 = &WPP_MAIN_CB.Reserved;
  PcpMrkSetMarkingValues(a1, v34, (_DWORD)v54, (unsigned int)v106, (__int64)&v97[6]);
  if ( v11 )
  {
    v55 = *(_QWORD *)(v11 + 256);
    if ( v55 )
      p_Reserved = (PVOID *)(v55 + 168);
  }
  if ( v106[5] )
  {
    v56 = *(_DWORD *)(v106[5] + 8LL);
LABEL_119:
    HIDWORD(v97[4]) = v56;
    goto LABEL_121;
  }
  if ( (*(_DWORD *)(a1 + 48) & 0x1000) != 0 )
  {
    v57 = v34 - 2;
    if ( v57 )
    {
      v58 = v57 - 1;
      if ( v58 )
      {
        v59 = v58 - 3;
        if ( !v59 )
          goto LABEL_121;
        v60 = v59 - 4;
        if ( v60 )
        {
          if ( v60 != 3 )
          {
            HIDWORD(v97[4]) = 0;
            goto LABEL_121;
          }
          v56 = *((_DWORD *)p_Reserved + 5);
        }
        else
        {
          v56 = *((_DWORD *)p_Reserved + 4);
        }
      }
      else
      {
        v56 = *((_DWORD *)p_Reserved + 3);
      }
    }
    else
    {
      v56 = *((_DWORD *)p_Reserved + 2);
    }
    goto LABEL_119;
  }
  HIDWORD(v97[4]) = 1;
LABEL_121:
  if ( v106[6] )
    v97[5] = *(_QWORD *)(v106[6] + 8LL);
  else
    v97[5] = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  LOBYTE(v62) = 1;
  LOBYTE(v63) = 1;
  Size = CurrentProcessorNumber;
  v64 = CurrentProcessorNumber;
  CurrentTime = QosTimerGetCurrentTime(CurrentProcessorNumber, v63, v62);
  v66 = (int *)(a1 + 136);
  *((_QWORD *)&v95[1] + 1) = 0x7FFFFFFFFFFFFFFFLL;
  v67 = *(_DWORD *)(a1 + 456);
  v96 = 0;
  LODWORD(v95[0]) = v67;
  memset((char *)v95 + 4, 0, 20);
  if ( v67 && (unsigned __int8)QosTbcAdjustBytesSent(a1 + 136, CurrentTime) )
  {
    PcpLineSignalExternalEvent(v11, v64);
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v11 + 16), &LockState, 0);
    QosLineQueryQueueFeedback(v11 + 24, v68, v95);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v11 + 16), &LockState);
    QosTbcAdjustSendWindow(a1 + 136, v95);
  }
  updated = 0;
  v69 = BYTE4(v97[7]) | 1;
  HIDWORD(v97[7]) |= 1u;
  v81 = v97[7];
  if ( LODWORD(v97[7]) == -1
    || ((v70 = *(_DWORD *)(a1 + 456), v71 = LODWORD(v97[7]) - v70, v93 = v70, LODWORD(v97[7]) - v70 != LODWORD(v97[7]))
      ? (Size_4 = (v71 != -v70) - 1)
      : (Size_4 = 1),
        !v71) )
  {
    v72 = *(_DWORD *)(a1 + 552);
    v81 = 0;
    if ( ((v69 ^ (unsigned __int8)v72) & 2) != 0 )
      *(_DWORD *)(a1 + 552) = v72 ^ (v69 ^ (unsigned __int8)v72) & 2;
    if ( LOBYTE(v97[6]) == *(_BYTE *)(a1 + 216)
      && *(_WORD *)((char *)&v97[6] + 1) == *(_WORD *)(a1 + 217)
      && *(_WORD *)((char *)&v97[6] + 3) == *(_WORD *)(a1 + 219)
      && BYTE5(v97[6]) == *(_BYTE *)(a1 + 221) )
    {
      v81 = *v66;
    }
    else
    {
      ++*v66;
      v50 = 0;
    }
    QosMrkFlowUpdate(a1 + 136, v97);
    QosTbcFlowUpdate(
      a1 + 136,
      Size,
      (unsigned int)v97,
      (unsigned __int64)&v81 & -(__int64)(v50 != 0),
      v79,
      (__int64)&v94,
      (__int64)&NetBufferList,
      (__int64)&v100);
    HIDWORD(v97[7]) &= ~1u;
    v71 = DWORD2(v104);
    Size_4 = HIDWORD(v104);
    v81 = DWORD1(v104);
    v93 = v104;
  }
  else
  {
    updated = 259;
  }
  if ( a6 )
    v12 = 1;
  LODWORD(v98) = v12;
  if ( updated != 259 )
  {
    if ( v11 )
    {
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v11 + 16), &LockState, 0);
      QosLineUpdateStats(v11 + 24, &v98);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v11 + 16), &LockState);
    }
    goto LABEL_175;
  }
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v11 + 16), &LockState, 0);
  v73 = 0;
  if ( ((BYTE8(v105) ^ (unsigned __int8)(*(_DWORD *)(v11 + 232) >> 1)) & 1) != 0 )
  {
    v73 = 1;
    *(_DWORD *)(v11 + 232) ^= ((unsigned __int8)*(_DWORD *)(v11 + 232) ^ (unsigned __int8)(2 * BYTE8(v105))) & 2;
  }
  if ( (unsigned __int64)(v105 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    *(_QWORD *)(v11 + 120) = v105;
    v73 = 1;
  }
  if ( v71 )
  {
    updated = QosLineUpdateTotalWeight((int)v11 + 24, v71, Size_4, v93, v81);
    if ( updated >= 0 )
    {
LABEL_153:
      QosLineComputeControlInterval(v11 + 24);
      QosLineComputeBufferSizes();
      v74 = *(_QWORD *)(v11 + 120);
      if ( !v74 || v74 == *(_QWORD *)(v11 + 32) )
        v75 = 0;
      else
        v75 = v74 * (unsigned __int64)*(unsigned int *)(v11 + 140) / 0xF4240;
      *(_QWORD *)(v11 + 216) = v75;
    }
  }
  else
  {
    updated = 0;
    if ( v73 )
      goto LABEL_153;
  }
  *(_DWORD *)(v11 + 48) += v12;
  if ( v12 <= 0 )
  {
    ++*(_DWORD *)(v11 + 96);
  }
  else
  {
    v76 = *(_DWORD *)(v11 + 104);
    if ( v76 <= *(_DWORD *)(v11 + 48) )
      v76 = *(_DWORD *)(v11 + 48);
    ++*(_DWORD *)(v11 + 84);
    *(_DWORD *)(v11 + 104) = v76;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v11 + 16), &LockState);
  v81 = 0;
  if ( updated >= 0 )
  {
    if ( ((BYTE4(v97[7]) ^ *(_BYTE *)(a1 + 552)) & 2) != 0 )
      *(_DWORD *)(a1 + 552) ^= (BYTE4(v97[7]) ^ (unsigned __int8)*(_DWORD *)(a1 + 552)) & 2;
    if ( LOBYTE(v97[6]) == *(_BYTE *)(a1 + 216)
      && *(_WORD *)((char *)&v97[6] + 1) == *(_WORD *)(a1 + 217)
      && *(_WORD *)((char *)&v97[6] + 3) == *(_WORD *)(a1 + 219)
      && BYTE5(v97[6]) == *(_BYTE *)(a1 + 221) )
    {
      v77 = 1;
      v81 = *v66;
    }
    else
    {
      ++*v66;
      v77 = 0;
    }
    QosMrkFlowUpdate(a1 + 136, v97);
    QosTbcFlowUpdate(
      a1 + 136,
      Size,
      (unsigned int)v97,
      (unsigned __int64)&v81 & -(__int64)(v77 != 0),
      v79,
      (__int64)&v94,
      (__int64)&NetBufferList,
      (__int64)&v100);
  }
LABEL_175:
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( updated < 0 )
  {
LABEL_92:
    if ( v80 )
      PcpFilterDecrementIntercept(1);
    goto LABEL_94;
  }
  if ( a6 == 1 )
  {
    PcpCreateFlowInstanceName(a1);
    RtlAcquireWriteLock(&WPP_MAIN_CB.Dpc.SystemArgument1, &LockHandle);
    ProcessorHistory = (_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory;
    if ( *(struct _DEVICE_OBJECT **)WPP_MAIN_CB.Dpc.ProcessorHistory != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DpcListEntry )
      __fastfail(3u);
    *(_QWORD *)a1 = &WPP_MAIN_CB.Dpc.DpcListEntry;
    *(_QWORD *)(a1 + 8) = ProcessorHistory;
    *ProcessorHistory = a1;
    WPP_MAIN_CB.Dpc.ProcessorHistory = a1;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v85 == 1 )
      PcpTcNotify(v11, -83820282, (const void *)(v11 + 48), 4u);
  }
  if ( NetBufferList )
    PcpSchedulerBatchAndSendOrDropNblChain(NetBufferList);
  if ( v100 )
    PcpSchedulerBatchAndSendOrDropNblChain(v100);
LABEL_94:
  if ( v11 )
    PcpLineDereference((PVOID)v11);
  if ( updated < 0 )
    goto LABEL_97;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140003ab0  mov     [rsp-8+arg_8], rbx
0x140003ab5  push    rbp
0x140003ab6  push    rsi
0x140003ab7  push    rdi
0x140003ab8  push    r12
0x140003aba  push    r13
0x140003abc  push    r14
0x140003abe  push    r15
0x140003ac0  lea     rbp, [rsp-0B0h]
0x140003ac8  sub     rsp, 1B0h
0x140003acf  mov     rdi, [rbp+0E0h+arg_40]
0x140003ad6  mov     r12, rcx
0x140003ad9  mov     rsi, [rbp+0E0h+arg_48]
0x140003ae0  lea     rcx, [rbp+0E0h+var_120]; void *
0x140003ae4  mov     r15, [rbp+0E0h+Src]
0x140003aeb  mov     rbx, [rbp+0E0h+arg_38]
0x140003af2  mov     [rbp+0E0h+var_E0], rdx
0x140003af6  xor     edx, edx; Val
0x140003af8  mov     dword ptr [rsp+1E0h+Size], r8d
0x140003afd  mov     [rsp+1E0h+var_17C], r9d
0x140003b02  mov     [rbp+0E0h+var_C8], rdi
0x140003b06  lea     r8d, [rdx+40h]; Size
0x140003b0a  mov     [rbp+0E0h+var_C0], rsi
0x140003b0e  call    memset
0x140003b13  xor     eax, eax
0x140003b15  lea     rcx, [rbp+0E0h+var_80]; void *
0x140003b19  xorps   xmm0, xmm0
0x140003b1c  mov     qword ptr [rbp+0E0h+LockHandle.OldIrql], rax
0x140003b20  xor     r13d, r13d
0x140003b23  mov     [rbp+0E0h+var_128], rax
0x140003b27  xor     edx, edx; Val
0x140003b29  mov     [rbp+0E0h+NetBufferList], r13
0x140003b2d  lea     r8d, [rax+50h]; Size
0x140003b31  mov     [rbp+0E0h+var_D0], r13
0x140003b35  movups  xmmword ptr [rbp+0E0h+LockHandle.LockQueue.Next], xmm0
0x140003b39  mov     [rbp+0E0h+var_15C], r13d
0x140003b3d  mov     r14d, r13d
0x140003b40  movups  [rbp+0E0h+var_148], xmm0
0x140003b44  mov     word ptr [rsp+1E0h+LockState.OldIrql], ax
0x140003b49  movups  [rbp+0E0h+var_138], xmm0
0x140003b4d  mov     [rsp+1E0h+LockState.Flags], al
0x140003b51  call    memset
0x140003b56  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140003b5a  mov     [rbp+0E0h+var_14C], r13d
0x140003b5e  mov     [rdi], dx
0x140003b61  xorps   xmm0, xmm0
0x140003b64  mov     [rsi], dx
0x140003b67  mov     edi, r13d
0x140003b6a  movups  [rbp+0E0h+var_A0], xmm0
0x140003b6e  movups  [rbp+0E0h+var_90], xmm0
0x140003b72  test    rbx, rbx
0x140003b75  jz      short loc_140003B7A
0x140003b77  mov     [rbx], r13d
0x140003b7a  movsxd  r8, [rsp+1E0h+var_17C]
0x140003b7f  lea     rax, PcgFlowTypeToFeatureFlagsMapping
0x140003b86  mov     r11d, 1
0x140003b8c  mov     ebx, [rax+r8*4]
0x140003b90  mov     [rsp+1E0h+var_18C], ebx
0x140003b94  cmp     r8d, 2
0x140003b98  jnz     short loc_140003BD4
0x140003b9a  mov     rax, [r15]
0x140003b9d  or      r13d, 0FFFFFFFFh
0x140003ba1  mov     r9, [r15+48h]
0x140003ba5  mov     esi, [r15+40h]
0x140003ba9  mov     qword ptr [rsp+1E0h+var_178], rax
0x140003bae  mov     rax, [r15+8]
0x140003bb2  mov     [rsp+1E0h+var_170], rax
0x140003bb7  mov     rax, [r15+10h]
0x140003bbb  mov     [rsp+1E0h+var_168], rax
0x140003bc0  mov     eax, [r15+18h]
0x140003bc4  mov     [rbp+0E0h+var_160], eax
0x140003bc7  mov     [rbp+0E0h+var_158], r13d
0x140003bcb  mov     [rbp+0E0h+var_154], r13d
0x140003bcf  jmp     loc_140003C88
0x140003bd4  cmp     r8d, r11d
0x140003bd7  jnz     short loc_140003C32
0x140003bd9  movzx   edx, word ptr [r15]
0x140003bdd  mov     eax, 1FEh
0x140003be2  cmp     dx, ax
0x140003be5  jbe     short loc_140003BF1
0x140003be7  mov     esi, 0C000000Dh
0x140003bec  jmp     loc_1400040C2
0x140003bf1  mov     esi, [r15+24Ch]
0x140003bf8  lea     rcx, [r15+2]; Buf1
0x140003bfc  call    PcpLineFindByInstanceName
0x140003c01  mov     r14, rax
0x140003c04  test    rax, rax
0x140003c07  jnz     short loc_140003C13
0x140003c09  mov     esi, 0C0000225h
0x140003c0e  jmp     loc_1400040C2
0x140003c13  mov     r8d, [rsp+1E0h+var_17C]
0x140003c18  lea     rcx, [r15+20Ch]
0x140003c1f  lea     r9, [r15+250h]
0x140003c26  mov     r11d, 1
0x140003c2c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140003c30  jmp     short loc_140003C3D
0x140003c32  mov     r9, [r15+48h]; int
0x140003c36  mov     rcx, r15
0x140003c39  mov     esi, [r15+40h]
0x140003c3d  mov     eax, [rcx]
0x140003c3f  or      r13d, 0FFFFFFFFh
0x140003c43  mov     qword ptr [rsp+1E0h+var_178], rdx
0x140003c48  cmp     eax, r13d
0x140003c4b  jz      short loc_140003C52
0x140003c4d  mov     qword ptr [rsp+1E0h+var_178], rax
0x140003c52  mov     eax, [rcx+4]
0x140003c55  mov     [rsp+1E0h+var_170], rdx
0x140003c5a  cmp     eax, r13d
0x140003c5d  jz      short loc_140003C64
0x140003c5f  mov     [rsp+1E0h+var_170], rax
0x140003c64  mov     eax, [rcx+8]
0x140003c67  mov     [rsp+1E0h+var_168], rdx
0x140003c6c  cmp     eax, r13d
0x140003c6f  jz      short loc_140003C76
0x140003c71  mov     [rsp+1E0h+var_168], rax
0x140003c76  mov     eax, [rcx+14h]
0x140003c79  mov     [rbp+0E0h+var_160], eax
0x140003c7c  mov     eax, [rcx+1Ch]
0x140003c7f  mov     [rbp+0E0h+var_158], eax
0x140003c82  mov     eax, [rcx+18h]
0x140003c85  mov     [rbp+0E0h+var_154], eax
0x140003c88  mov     r10b, [rbp+0E0h+arg_28]
0x140003c8f  cmp     r10b, r11b
0x140003c92  jz      loc_140003D20
0x140003c98  mov     rdx, [r12+258h]
0x140003ca0  cmp     r8d, 2
0x140003ca4  jnz     short loc_140003CCD
0x140003ca6  mov     rax, [rdx]
0x140003ca9  mov     qword ptr [rbp+0E0h+var_148], rax
0x140003cad  mov     rax, [rdx+8]
0x140003cb1  mov     qword ptr [rbp+0E0h+var_148+8], rax
0x140003cb5  mov     rax, [rdx+10h]
0x140003cb9  mov     qword ptr [rbp+0E0h+var_138], rax
0x140003cbd  mov     eax, [rdx+18h]
0x140003cc0  mov     dword ptr [rbp+0E0h+var_138+8], eax
0x140003cc3  mov     dword ptr [rbp+0E0h+var_128], r13d
0x140003cc7  mov     dword ptr [rbp+0E0h+var_128+4], r13d
0x140003ccb  jmp     short loc_140003D20
0x140003ccd  cmp     r8d, r11d
0x140003cd0  lea     rcx, [rdx+20Ch]
0x140003cd7  cmovnz  rcx, rdx
0x140003cdb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140003cdf  mov     qword ptr [rbp+0E0h+var_148], rdx
0x140003ce3  mov     eax, [rcx]
0x140003ce5  cmp     eax, r13d
0x140003ce8  jz      short loc_140003CEE
0x140003cea  mov     qword ptr [rbp+0E0h+var_148], rax
0x140003cee  mov     eax, [rcx+4]
0x140003cf1  mov     qword ptr [rbp+0E0h+var_148+8], rdx
0x140003cf5  cmp     eax, r13d
0x140003cf8  jz      short loc_140003CFE
0x140003cfa  mov     qword ptr [rbp+0E0h+var_148+8], rax
0x140003cfe  mov     eax, [rcx+8]
0x140003d01  mov     qword ptr [rbp+0E0h+var_138], rdx
0x140003d05  cmp     eax, r13d
0x140003d08  jz      short loc_140003D0E
0x140003d0a  mov     qword ptr [rbp+0E0h+var_138], rax
0x140003d0e  mov     eax, [rcx+14h]
0x140003d11  mov     dword ptr [rbp+0E0h+var_138+8], eax
0x140003d14  mov     eax, [rcx+1Ch]
0x140003d17  mov     dword ptr [rbp+0E0h+var_128], eax
0x140003d1a  mov     eax, [rcx+18h]
0x140003d1d  mov     dword ptr [rbp+0E0h+var_128+4], eax
0x140003d20  xor     eax, eax
0x140003d22  lea     r8, [rbp+0E0h+var_148]
0x140003d26  test    r10b, r10b
0x140003d29  lea     rdx, [rsp+1E0h+var_178]; int
0x140003d2e  lea     rcx, [rsp+1E0h+var_18C]; int
0x140003d33  cmovnz  r8, rax; int
0x140003d37  mov     rax, [rbp+0E0h+var_C0]
0x140003d3b  mov     [rsp+1E0h+var_1A0], rax; __int64
0x140003d40  mov     rax, [rbp+0E0h+var_C8]
0x140003d44  mov     [rsp+1E0h+var_1A8], rax; __int64
0x140003d49  mov     eax, [rbp+0E0h+arg_30]
0x140003d4f  mov     [rsp+1E0h+var_1B0], eax; int
0x140003d53  lea     rax, [rbp+0E0h+var_80]
0x140003d57  mov     [rsp+1E0h+var_1B8], rax; void *
0x140003d5c  mov     [rsp+1E0h+var_1C0], esi; int
0x140003d60  call    PcpValidateFlowParameters
0x140003d65  mov     esi, eax
0x140003d67  test    eax, eax
0x140003d69  js      loc_1400040B1
0x140003d6f  cmp     [rbp+0E0h+arg_28], 1
0x140003d76  mov     [rsp+1E0h+var_18F], dil
0x140003d7b  jnz     short loc_140003D9D
0x140003d7d  mov     eax, [r12+268h]
0x140003d85  test    al, 2
0x140003d87  jz      short loc_140003D9D
0x140003d89  call    PcpFilterIncrementIntercept
0x140003d8e  mov     esi, eax
0x140003d90  test    eax, eax
0x140003d92  js      loc_1400040B1
0x140003d98  mov     [rsp+1E0h+var_18F], 1
0x140003d9d  lea     rdx, [rbp+0E0h+LockHandle]; LockHandle
0x140003da1  lea     rcx, [r12+60h]; SpinLock
0x140003da6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003dad  nop     dword ptr [rax+rax+00h]
0x140003db2  mov     eax, [r12+68h]
0x140003db7  test    eax, eax
0x140003db9  jnz     short loc_140003DB2
0x140003dbb  cmp     [rbp+0E0h+arg_28], dil
0x140003dc2  jnz     short loc_140003E26
0x140003dc4  mov     ecx, dword ptr [rsp+1E0h+Size]
0x140003dc8  cmp     [r12+260h], ecx
0x140003dd0  jnb     short loc_140003E2A
0x140003dd2  mov     edx, ecx
0x140003dd4  mov     r8d, 6C666350h
0x140003dda  lea     ecx, [rax+40h]
0x140003ddd  call    cs:__imp_ExAllocatePool2
0x140003de4  nop     dword ptr [rax+rax+00h]
0x140003de9  mov     rsi, rax
0x140003dec  test    rax, rax
0x140003def  jnz     short loc_140003DFB
0x140003df1  mov     esi, 0C000009Ah
0x140003df6  jmp     loc_140004090
0x140003dfb  mov     rcx, [r12+258h]; P
0x140003e03  lea     rax, [r12+270h]
0x140003e0b  cmp     rcx, rax
0x140003e0e  jz      short loc_140003E1E
0x140003e10  xor     edx, edx; Tag
0x140003e12  call    cs:__imp_ExFreePoolWithTag
0x140003e19  nop     dword ptr [rax+rax+00h]
0x140003e1e  mov     [r12+258h], rsi
0x140003e26  mov     ecx, dword ptr [rsp+1E0h+Size]
0x140003e2a  mov     rax, [rbp+0E0h+var_E0]
0x140003e2e  test    rax, rax
0x140003e31  jz      short loc_140003E3B
0x140003e33  mov     [r12+250h], rax
0x140003e3b  mov     edx, [rsp+1E0h+var_17C]
0x140003e3f  mov     rax, [r12+258h]
0x140003e47  mov     [r12+260h], ecx
0x140003e4f  mov     [r12+30h], ebx
0x140003e54  cmp     edx, 2
0x140003e57  jnz     short loc_140003E9A
0x140003e59  mov     r8d, ecx; Size
0x140003e5c  mov     rdx, r15; Src
0x140003e5f  mov     rcx, rax; void *
0x140003e62  call    memmove
0x140003e67  mov     rcx, [r12+258h]
0x140003e6f  mov     rdx, qword ptr [rsp+1E0h+var_178]
0x140003e74  mov     rbx, [rsp+1E0h+var_170]
0x140003e79  mov     esi, [rbp+0E0h+var_160]
0x140003e7c  mov     eax, [rbp+0E0h+var_15C]
0x140003e7f  mov     [rcx], rdx
0x140003e82  mov     rdx, [rsp+1E0h+var_168]
0x140003e87  mov     [rcx+10h], rdx
0x140003e8b  mov     [rcx+8], rbx
0x140003e8f  mov     [rcx+18h], esi
0x140003e92  mov     [rcx+1Ch], eax
0x140003e95  jmp     loc_140003F8C
0x140003e9a  cmp     edx, 1
0x140003e9d  jnz     short loc_140003F13
0x140003e9f  mov     r8d, ecx; Size
0x140003ea2  mov     rdx, r15; Src
0x140003ea5  mov     rcx, rax; void *
0x140003ea8  call    memmove
0x140003ead  mov     rcx, [r12+258h]
0x140003eb5  or      r8, 0FFFFFFFFFFFFFFFFh
0x140003eb9  cmp     qword ptr [rsp+1E0h+var_178], r8
0x140003ebe  mov     eax, r13d
0x140003ec1  mov     rbx, [rsp+1E0h+var_170]
0x140003ec6  cmovnz  eax, [rsp+1E0h+var_178]
0x140003ecb  cmp     rbx, r8
0x140003ece  mov     esi, [rbp+0E0h+var_160]
0x140003ed1  mov     [rcx+20Ch], eax
0x140003ed7  mov     eax, r13d
0x140003eda  cmovnz  eax, ebx
0x140003edd  mov     [rcx+220h], esi
0x140003ee3  cmp     [rsp+1E0h+var_168], r8
0x140003ee8  mov     [rcx+210h], eax
0x140003eee  mov     eax, r13d
0x140003ef1  cmovnz  eax, dword ptr [rsp+1E0h+var_168]
0x140003ef6  mov     [rcx+214h], eax
0x140003efc  mov     eax, [rbp+0E0h+var_158]
0x140003eff  mov     [rcx+228h], eax
0x140003f05  mov     eax, [rbp+0E0h+var_154]
0x140003f08  mov     [rcx+224h], eax
0x140003f0e  jmp     loc_140003FBC
0x140003f13  movups  xmm0, xmmword ptr [r15]
0x140003f17  mov     rbx, [rsp+1E0h+var_170]
0x140003f1c  or      r8, 0FFFFFFFFFFFFFFFFh
0x140003f20  cmp     qword ptr [rsp+1E0h+var_178], r8
0x140003f25  mov     esi, [rbp+0E0h+var_160]
0x140003f28  movups  xmmword ptr [rax], xmm0
0x140003f2b  movups  xmm1, xmmword ptr [r15+10h]
0x140003f30  movups  xmmword ptr [rax+10h], xmm1
0x140003f34  movups  xmm0, xmmword ptr [r15+20h]
0x140003f39  movups  xmmword ptr [rax+20h], xmm0
0x140003f3d  movups  xmm1, xmmword ptr [r15+30h]
0x140003f42  movups  xmmword ptr [rax+30h], xmm1
0x140003f46  movups  xmm0, xmmword ptr [r15+40h]
0x140003f4b  movups  xmmword ptr [rax+40h], xmm0
0x140003f4f  mov     rcx, [r12+258h]
0x140003f57  mov     eax, r13d
0x140003f5a  cmovnz  eax, [rsp+1E0h+var_178]
0x140003f5f  cmp     rbx, r8
0x140003f62  mov     [rcx], eax
0x140003f64  mov     eax, r13d
0x140003f67  cmovnz  eax, ebx
0x140003f6a  mov     [rcx+14h], esi
  ... truncated ...
```
