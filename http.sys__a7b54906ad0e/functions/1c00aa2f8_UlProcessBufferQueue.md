# UlProcessBufferQueue

- ea: `0x1c00aa2f8`
- end: `0x1c00aa7e6`
- name: `UlProcessBufferQueue`
- size: `1262`
- prototype: ``
- caller_count: `6`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1c0006870`
- `0x1c000cec0`
- `0x1c00b2fc0`
- `0x1c00ceb0c`
- `0x1c0117308`
- `0x1c0128fa4`

## callees

- `0x1c00060d4`
- `0x1c0006260`
- `0x1c0007860`
- `0x1c000fc68`
- `0x1c0015f24`
- `0x1c001b640`
- `0x1c008f21c`
- `0x1c008f3ec`
- `0x1c008f570`
- `0x1c008f680`
- `0x1c008f76c`
- `0x1c00903a4`
- `0x1c0090454`
- `0x1c00905f0`
- `0x1c0093c3c`
- `0x1c009a0f4`
- `0x1c009a180`
- `0x1c00aa2f8`
- `0x1c011750c`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x1c00e1015`
- `ntoskrnl!IoGetRequestorProcess` at `0x1c00e1015`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00e1063`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00e1063`
- `ntoskrnl!MmUnmapLockedPages` at `0x1c00e13ec`
- `ntoskrnl!MmUnmapLockedPages` at `0x1c00e13ec`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e0ef7`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e0fc2`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e1458`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e0ef7`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e0fc2`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e1458`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00e1024`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00e1024`

## pseudocode

```c
__int64 __fastcall UlProcessBufferQueue(__int64 a1, void *a2, int a3)
{
  unsigned int v4; // r13d
  IRP *v5; // r14
  int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rdx
  _QWORD *v9; // r8
  __int64 v10; // r9
  unsigned int v11; // edx
  __int64 **v12; // rbx
  __int64 *v13; // rax
  __int64 result; // rax
  unsigned int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // ebx
  _QWORD *v18; // r9
  _QWORD *v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rbx
  _QWORD *v22; // r11
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  PEPROCESS RequestorProcess; // rbx
  PEPROCESS CurrentProcess; // rax
  PMDL MdlAddress; // rcx
  char *MappedSystemVa; // rax
  __int64 v36; // r9
  __int64 v37; // rax
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // r10
  __int64 v41; // rbx
  unsigned int v42; // eax
  PMDL v43; // rcx
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // r14
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 **v45; // rax
  struct _LIST_ENTRY *v46; // rcx
  __int64 v47; // rcx
  unsigned int Size; // [rsp+60h] [rbp-88h]
  unsigned int Size_4; // [rsp+64h] [rbp-84h] BYREF
  unsigned int v50; // [rsp+68h] [rbp-80h]
  _QWORD *v51; // [rsp+70h] [rbp-78h]
  int v52; // [rsp+78h] [rbp-70h]
  _QWORD *v53; // [rsp+80h] [rbp-68h]
  void *v54; // [rsp+88h] [rbp-60h]
  __int64 v55; // [rsp+90h] [rbp-58h]
  __int64 *v56; // [rsp+98h] [rbp-50h]
  __int64 v57; // [rsp+A0h] [rbp-48h]
  __int64 v58; // [rsp+A8h] [rbp-40h]
  int v60; // [rsp+108h] [rbp+20h]

  v60 = 0;
  v54 = 0;
  v55 = 0;
  Size_4 = 0;
  v57 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 960LL);
  v4 = 0;
  v50 = 0;
  v5 = 0;
  v56 = 0;
  v6 = *(_DWORD *)(a1 + 2184) >> 8;
  LOBYTE(v6) = BYTE1(*(_DWORD *)(a1 + 2184)) & 1;
  v52 = v6;
  if ( (_BYTE)v6 )
  {
    v60 = -1;
  }
  else if ( a2 )
  {
    v60 = a3;
    v54 = a2;
  }
LABEL_4:
  v7 = v60;
  while ( 1 )
  {
    v8 = (_QWORD *)(a1 + 2144);
    v53 = (_QWORD *)(a1 + 2144);
    v9 = (_QWORD *)(a1 + 2128);
    v51 = (_QWORD *)(a1 + 2128);
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
    {
      WPP_SF_qLIIq(
        15,
        WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids,
        a1,
        *(unsigned int *)(a1 + 480),
        *v8,
        *v9,
        *(_QWORD *)(a1 + 2232));
      v8 = v53;
      v9 = v51;
    }
    else
    {
      v53 = (_QWORD *)(a1 + 2144);
      v51 = (_QWORD *)(a1 + 2128);
    }
    if ( *(_DWORD *)(a1 + 480) != 10 || *v8 != *v9 )
      break;
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
      WPP_SF_q(16, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1);
    v4 += *(_DWORD *)(a1 + 2152);
    v50 = v4;
    *(_DWORD *)(a1 + 2152) = 0;
    Size = 0;
LABEL_14:
    if ( !v7 )
    {
      if ( a2 || (_BYTE)v52 )
        goto LABEL_52;
      if ( v5 )
      {
        v28 = *(_QWORD *)(v55 + 32);
        *(_QWORD *)(v55 + 32) = 0;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v28 + 48), 0xFFFFFFFF) == 1 )
          UlpQueueFreeHttpRequest(v28);
        UlDestroyGrip(v5);
        if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
          WPP_SF_qqD(19, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v5, v5->IoStatus.Status);
        IofCompleteRequest(v5, 0);
        v5 = 0;
        v56 = 0;
      }
      v12 = (__int64 **)(a1 + 488);
      while ( 1 )
      {
        v13 = *v12;
        if ( *v12 == (__int64 *)v12 )
          break;
        v29 = *v13;
        if ( (__int64 **)v13[1] != v12 || *(__int64 **)(v29 + 8) != v13 )
          goto LABEL_140;
        *v12 = (__int64 *)v29;
        *(_QWORD *)(v29 + 8) = v12;
        *v13 = 0;
        v13[1] = 0;
        v5 = (IRP *)(v13 - 21);
        v56 = v13 - 21;
        v30 = v13[2];
        v55 = v30;
        if ( _InterlockedExchange64(v13 - 8, 0) )
        {
          if ( !v5->Cancel )
            break;
          v31 = *(_QWORD *)(v30 + 32);
          *(_QWORD *)(v30 + 32) = 0;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v31 + 48), 0xFFFFFFFF) == 1 )
            UlpQueueFreeHttpRequest(v31);
          UlDestroyGrip(v5);
          v5->IoStatus.Status = -1073741536;
          v5->IoStatus.Information = 0;
          if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
            WPP_SF_qqD(20, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v5, -1073741536);
          IofCompleteRequest(v5, 0);
        }
        v5 = 0;
        v56 = 0;
      }
      if ( !v5 )
        goto LABEL_21;
      if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
        WPP_SF_qq(21, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v5);
      v60 = *(_DWORD *)(v55 + 8) - LODWORD(v5->IoStatus.Information);
      RequestorProcess = IoGetRequestorProcess(v5);
      CurrentProcess = IoGetCurrentProcess();
      MdlAddress = v5->MdlAddress;
      if ( RequestorProcess == CurrentProcess )
      {
        MappedSystemVa = (char *)MdlAddress->StartVa + MdlAddress->ByteOffset;
      }
      else if ( (MdlAddress->MdlFlags & 5) != 0 )
      {
        MappedSystemVa = (char *)MdlAddress->MappedSystemVa;
      }
      else
      {
        MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000000u);
      }
      if ( !MappedSystemVa )
      {
        v5->IoStatus.Status = -1073741670;
        v5->IoStatus.Information = 0;
        goto LABEL_52;
      }
      v54 = &MappedSystemVa[v5->IoStatus.Information];
      v5->IoStatus.Status = 0;
      v7 = v60;
    }
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
    {
      v36 = *(_QWORD *)(a1 + 2232);
      if ( v36 )
        v37 = *(_QWORD *)(v36 + 128);
      else
        v37 = -1;
      WPP_SF_qqq(22, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v36, v37);
    }
    v15 = v7;
    v16 = Size;
    if ( Size <= v7 )
      v15 = Size;
    v17 = v15;
    if ( (unsigned __int64)v15 > *(_QWORD *)(a1 + 2136) )
      v17 = *(_DWORD *)(a1 + 2136);
    if ( v17 )
    {
      if ( !(_BYTE)v52 )
      {
        v58 = v17;
        memmove(v54, *(const void **)(a1 + 2240), v17);
        if ( v5 )
          v5->IoStatus.Information += v58;
        if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
        {
          WPP_SF_qD(23, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v17);
          if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
            WPP_SF_(24, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids);
        }
        v16 = Size;
      }
      *(_QWORD *)(a1 + 2240) += v17;
      v16 -= v17;
      Size = v16;
      *(_QWORD *)(a1 + 2136) -= v17;
      v18 = v53;
      *v53 += v17;
      v54 = (char *)v54 + v17;
      v60 -= v17;
      v4 += v17;
      v50 = v4;
    }
    else
    {
      if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
      {
        WPP_SF_q(25, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1);
        v16 = Size;
      }
      v18 = v53;
    }
    v19 = (_QWORD *)(a1 + 2136);
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
      WPP_SF_qLIIIIL(
        26,
        WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids,
        a1,
        *(unsigned int *)(a1 + 480),
        *v18,
        *v51,
        *v19,
        *(_QWORD *)(a1 + 2120),
        v16);
    if ( *(_DWORD *)(a1 + 480) == 10 && *v53 == *v51 )
    {
      if ( !(_BYTE)v52 && v5 && !v5->IoStatus.Information )
        v5->IoStatus.Status = -1073741807;
      v4 += *(_DWORD *)(a1 + 2152);
      v50 = v4;
      *(_DWORD *)(a1 + 2152) = 0;
      v7 = 0;
      v60 = 0;
      if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
        WPP_SF_qq(27, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v5);
    }
    else
    {
      if ( Size )
      {
        if ( *v19 )
          goto LABEL_4;
        if ( *v53 >= *v51 )
        {
          if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) == 0 )
            goto LABEL_52;
          v38 = 33;
LABEL_114:
          WPP_SF_q(v38, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1);
          goto LABEL_52;
        }
        v42 = ParseChunkLength(
                v57,
                (*(_DWORD *)(a1 + 2184) >> 7) & 1,
                *(_QWORD *)(a1 + 2240),
                Size,
                (__int64)&Size_4,
                a1 + 2136,
                0);
        if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
          WPP_SF_qlLq(32, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v42, Size_4, *v19);
        *(_QWORD *)(a1 + 2240) += Size_4;
        v4 += Size_4;
        v50 = v4;
        goto LABEL_4;
      }
      if ( *v53 == *v51 )
      {
        if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) == 0 )
          goto LABEL_52;
        v38 = 28;
        goto LABEL_114;
      }
      v20 = *(_QWORD *)(*(_QWORD *)(a1 + 2232) + 32LL);
      v21 = v20 - 32;
      if ( v20 == *(_QWORD *)(a1 + 24) + 472LL )
        v21 = 0;
      if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
      {
        if ( v21 )
          v39 = *(_DWORD *)(v21 + 120);
        else
          v39 = 0;
        WPP_SF_qqD(29, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v21, v39);
      }
      if ( !v21 || !*(_DWORD *)(v21 + 120) )
        goto LABEL_4;
      v22 = *(_QWORD **)(a1 + 2232);
      v51 = v22;
      *(_QWORD *)(a1 + 2232) = v21;
      v23 = v21 + 136;
      *(_QWORD *)(a1 + 2240) = v21 + 136;
      v24 = *(unsigned int *)(v21 + 112);
      if ( !*(_QWORD *)(a1 + 2136) )
      {
        v25 = ParseChunkLength(v57, (*(_DWORD *)(a1 + 2184) >> 7) & 1, v23, v24, (__int64)&Size_4, a1 + 2136, 0);
        if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
          WPP_SF_qlLq(30, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v25, Size_4, *(_QWORD *)(a1 + 2136));
        *(_QWORD *)(a1 + 2240) += Size_4;
        v4 += Size_4;
        v50 = v4;
        v22 = v51;
      }
      if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
      {
        v40 = *(_QWORD *)(a1 + 2232);
        if ( v40 )
          v41 = *(_QWORD *)(v40 + 128);
        else
          LOBYTE(v41) = -1;
        WPP_SF_qqIqIqqIqI(
          31,
          (unsigned int)WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids,
          a1,
          (_DWORD)v22,
          v22[16],
          v40,
          v41,
          *(_QWORD *)(a1 + 24),
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 488LL),
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 488LL) + 128LL),
          *(_QWORD *)(a1 + 2224),
          *(_QWORD *)(*(_QWORD *)(a1 + 2224) + 128LL));
      }
      v7 = v60;
      if ( v51 != *(_QWORD **)(a1 + 2224) )
        UlReleaseRequestBuffer(v57, v51, v23, v24);
    }
  }
  v10 = *(_QWORD *)(a1 + 2232);
  if ( v10 && *(_QWORD *)(a1 + 2144) != *(_QWORD *)(a1 + 2128) )
  {
    v11 = *(_DWORD *)(v10 + 112) - *(_DWORD *)(a1 + 2240) + v10 + 136;
    Size = v11;
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
    {
      WPP_SF_qD(18, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v11);
      v11 = Size;
    }
    if ( !v11 )
    {
      v26 = *(_QWORD *)(*(_QWORD *)(a1 + 2232) + 32LL);
      v27 = v26 - 32;
      if ( v26 == *(_QWORD *)(a1 + 24) + 472LL )
        v27 = 0;
      if ( !v27 || !*(_DWORD *)(v27 + 120) )
        goto LABEL_52;
    }
    goto LABEL_14;
  }
  if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
    WPP_SF_qqqI(
      17,
      WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids,
      a1,
      v10,
      *(_QWORD *)(a1 + 2144),
      *(_QWORD *)(a1 + 2128));
LABEL_52:
  if ( !v5 )
  {
LABEL_21:
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
      WPP_SF_q(35, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1);
    goto LABEL_23;
  }
  if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
    WPP_SF_qqD(34, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, v5, v5->IoStatus.Status);
  if ( ((__int64)v5->AssociatedIrp.MasterIrp->MdlAddress & 1) == 0
    || v5->IoStatus.Status
    || *(unsigned int *)(v55 + 8) <= v5->IoStatus.Information )
  {
    v47 = *(_QWORD *)(v55 + 32);
    *(_QWORD *)(v55 + 32) = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v47 + 48), 0xFFFFFFFF) == 1 )
      UlpQueueFreeHttpRequest(v47);
    UlDestroyGrip(v5);
    IofCompleteRequest(v5, 0);
  }
  else if ( !(unsigned int)UlSetReceiveEntityBodyIrpCancelRoutine(a1, v5) )
  {
    v43 = v5->MdlAddress;
    if ( (v43->MdlFlags & 1) != 0 )
      MmUnmapLockedPages(v43->MappedSystemVa, v5->MdlAddress);
    p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&v5->Tail.Overlay.ListEntry;
    v45 = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 **)(a1 + 488);
    v46 = *(struct _LIST_ENTRY **)(a1 + 488);
    if ( v46->Blink != (struct _LIST_ENTRY *)(a1 + 488) )
LABEL_140:
      __fastfail(3u);
    p_ListEntry->ListEntry.Flink = v46;
    p_ListEntry->ListEntry.Blink = (struct _LIST_ENTRY *)v45;
    v46->Blink = &p_ListEntry->ListEntry;
    *v45 = p_ListEntry;
  }
LABEL_23:
  result = HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink);
  if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
    result = WPP_SF_qqD(36, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, a1, *(_QWORD *)(a1 + 24), v4);
  if ( v4 )
    return UlConsumeBytesFromConnection(*(_QWORD *)(a1 + 24), v4);
  return result;
}

```

## disassembly

```asm
0x1c00aa2f8  mov     [rsp+arg_8], rdx
0x1c00aa2fd  mov     [rsp+arg_0], rcx
0x1c00aa302  push    rbx
0x1c00aa303  push    rsi
0x1c00aa304  push    rdi
0x1c00aa305  push    r12
0x1c00aa307  push    r13
0x1c00aa309  push    r14
0x1c00aa30b  push    r15
0x1c00aa30d  sub     rsp, 0B0h
0x1c00aa314  mov     rdi, rcx
0x1c00aa317  xor     esi, esi
0x1c00aa319  mov     [rsp+0E8h+arg_18], esi
0x1c00aa320  mov     [rsp+0E8h+var_60], rsi
0x1c00aa328  mov     [rsp+0E8h+var_58], rsi
0x1c00aa330  mov     dword ptr [rsp+0E8h+Size+4], esi
0x1c00aa334  mov     rax, [rcx+18h]
0x1c00aa338  mov     rax, [rax+3C0h]
0x1c00aa33f  mov     [rsp+0E8h+var_48], rax
0x1c00aa347  mov     r13d, esi
0x1c00aa34a  mov     [rsp+0E8h+var_80], esi
0x1c00aa34e  mov     r14d, esi
0x1c00aa351  mov     [rsp+0E8h+var_50], rsi
0x1c00aa359  mov     eax, [rcx+888h]
0x1c00aa35f  shr     eax, 8
0x1c00aa362  and     al, 1
0x1c00aa364  mov     [rsp+0E8h+var_70], eax
0x1c00aa368  jnz     loc_1C00AA671
0x1c00aa36e  test    rdx, rdx
0x1c00aa371  jnz     loc_1C00AA67E
0x1c00aa377  mov     r15b, 80h
0x1c00aa37a  lea     r12, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids
0x1c00aa381  mov     ebx, [rsp+0E8h+arg_18]
0x1c00aa388  lea     rdx, [rdi+860h]
0x1c00aa38f  mov     [rsp+0E8h+var_68], rdx
0x1c00aa397  lea     r8, [rdi+850h]
0x1c00aa39e  mov     [rsp+0E8h+var_78], r8
0x1c00aa3a3  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa3a9  test    r15b, al
0x1c00aa3ac  jnz     loc_1C00E0DF4
0x1c00aa3b2  mov     [rsp+0E8h+var_68], rdx
0x1c00aa3ba  mov     [rsp+0E8h+var_78], r8
0x1c00aa3bf  cmp     dword ptr [rdi+1E0h], 0Ah
0x1c00aa3c6  jnz     short loc_1C00AA3D4
0x1c00aa3c8  mov     rax, [r8]
0x1c00aa3cb  cmp     [rdx], rax
0x1c00aa3ce  jz      loc_1C00AA4A9
0x1c00aa3d4  mov     r9, [rdi+8B8h]
0x1c00aa3db  test    r9, r9
0x1c00aa3de  jz      loc_1C00AA654
0x1c00aa3e4  mov     rax, [rdi+850h]
0x1c00aa3eb  cmp     [rdi+860h], rax
0x1c00aa3f2  jz      loc_1C00AA654
0x1c00aa3f8  mov     ecx, [r9+70h]
0x1c00aa3fc  sub     ecx, [rdi+8C0h]
0x1c00aa402  mov     edx, r9d
0x1c00aa405  add     edx, 88h
0x1c00aa40b  add     edx, ecx
0x1c00aa40d  mov     dword ptr [rsp+0E8h+Size], edx
0x1c00aa411  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa417  test    r15b, al
0x1c00aa41a  jnz     loc_1C00E0E4F
0x1c00aa420  test    edx, edx
0x1c00aa422  jz      loc_1C00E0E6B
0x1c00aa428  test    ebx, ebx
0x1c00aa42a  jnz     loc_1C00AA4D3
0x1c00aa430  cmp     [rsp+0E8h+arg_8], rsi
0x1c00aa438  jnz     loc_1C00AA663
0x1c00aa43e  cmp     byte ptr [rsp+0E8h+var_70], sil
0x1c00aa443  jnz     loc_1C00AA663
0x1c00aa449  test    r14, r14
0x1c00aa44c  jnz     loc_1C00E0EA2
0x1c00aa452  lea     rbx, [rdi+1E8h]
0x1c00aa459  mov     rax, [rbx]
0x1c00aa45c  cmp     rax, rbx
0x1c00aa45f  jnz     loc_1C00E0F13
0x1c00aa465  test    r14, r14
0x1c00aa468  jnz     loc_1C00E0FDE
0x1c00aa46e  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa474  test    r15b, al
0x1c00aa477  jnz     loc_1C00E146A
0x1c00aa47d  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa483  test    r15b, al
0x1c00aa486  jnz     loc_1C00E1480
0x1c00aa48c  test    r13d, r13d
0x1c00aa48f  jnz     loc_1C00AA6AF
0x1c00aa495  add     rsp, 0B0h
0x1c00aa49c  pop     r15
0x1c00aa49e  pop     r14
0x1c00aa4a0  pop     r13
0x1c00aa4a2  pop     r12
0x1c00aa4a4  pop     rdi
0x1c00aa4a5  pop     rsi
0x1c00aa4a6  pop     rbx
0x1c00aa4a7  retn
0x1c00aa4a9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa4af  test    r15b, al
0x1c00aa4b2  jnz     loc_1C00E0E39
0x1c00aa4b8  add     r13d, [rdi+868h]
0x1c00aa4bf  mov     [rsp+0E8h+var_80], r13d
0x1c00aa4c4  mov     [rdi+868h], esi
0x1c00aa4ca  mov     dword ptr [rsp+0E8h+Size], esi
0x1c00aa4ce  jmp     loc_1C00AA428
0x1c00aa4d3  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa4d9  test    r15b, al
0x1c00aa4dc  jnz     loc_1C00E10A1
0x1c00aa4e2  mov     eax, ebx
0x1c00aa4e4  mov     edx, dword ptr [rsp+0E8h+Size]
0x1c00aa4e8  cmp     edx, ebx
0x1c00aa4ea  cmovbe  eax, edx
0x1c00aa4ed  mov     ebx, eax
0x1c00aa4ef  lea     rax, [rdi+858h]
0x1c00aa4f6  cmp     rbx, [rax]
0x1c00aa4f9  ja      loc_1C00AA784
0x1c00aa4ff  test    ebx, ebx
0x1c00aa501  jz      loc_1C00AA693
0x1c00aa507  cmp     byte ptr [rsp+0E8h+var_70], sil
0x1c00aa50c  jnz     loc_1C00AA5A1
0x1c00aa512  mov     eax, ebx
0x1c00aa514  mov     [rsp+0E8h+var_40], rax
0x1c00aa51c  mov     r8d, ebx; Size
0x1c00aa51f  mov     rdx, [rdi+8C0h]; Src
0x1c00aa526  mov     rcx, [rsp+0E8h+var_60]; void *
0x1c00aa52e  call    memmove
0x1c00aa533  jmp     short loc_1C00AA585
0x1c00aa535  mov     r14, [rsp+0E8h+var_50]
0x1c00aa53d  test    r14, r14
0x1c00aa540  jz      short loc_1C00AA567
0x1c00aa542  and     qword ptr [r14+38h], 0
0x1c00aa547  mov     ecx, eax
0x1c00aa549  and     ecx, 0C0000000h
0x1c00aa54f  cmp     ecx, 80000000h
0x1c00aa555  jnz     short loc_1C00AA563
0x1c00aa557  cmp     eax, 80000005h
0x1c00aa55c  jz      short loc_1C00AA563
0x1c00aa55e  mov     eax, 0C000000Dh
0x1c00aa563  mov     [r14+30h], eax
0x1c00aa567  xor     esi, esi
0x1c00aa569  mov     r15b, 80h
0x1c00aa56c  lea     r12, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids
0x1c00aa573  mov     rdi, [rsp+0E8h+arg_0]
0x1c00aa57b  mov     r13d, [rsp+0E8h+var_80]
0x1c00aa580  jmp     loc_1C00AA663
0x1c00aa585  test    r14, r14
0x1c00aa588  jnz     loc_1C00E10D5
0x1c00aa58e  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa594  test    r15b, al
0x1c00aa597  jnz     loc_1C00E10E6
0x1c00aa59d  mov     edx, dword ptr [rsp+0E8h+Size]
0x1c00aa5a1  mov     eax, ebx
0x1c00aa5a3  add     [rdi+8C0h], rax
0x1c00aa5aa  sub     edx, ebx
0x1c00aa5ac  mov     dword ptr [rsp+0E8h+Size], edx
0x1c00aa5b0  sub     [rdi+858h], rax
0x1c00aa5b7  mov     r9, [rsp+0E8h+var_68]
0x1c00aa5bf  add     [r9], rax
0x1c00aa5c2  add     [rsp+0E8h+var_60], rax
0x1c00aa5ca  sub     [rsp+0E8h+arg_18], ebx
0x1c00aa5d1  add     r13d, ebx
0x1c00aa5d4  mov     [rsp+0E8h+var_80], r13d
0x1c00aa5d9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa5df  lea     rbx, [rdi+858h]
0x1c00aa5e6  test    r15b, al
0x1c00aa5e9  jnz     loc_1C00E1134
0x1c00aa5ef  mov     r8, [rsp+0E8h+var_78]
0x1c00aa5f4  mov     rdx, [rsp+0E8h+var_68]
0x1c00aa5fc  cmp     dword ptr [rdi+1E0h], 0Ah
0x1c00aa603  jnz     loc_1C00AA6C0
0x1c00aa609  mov     rax, [r8]
0x1c00aa60c  cmp     [rdx], rax
0x1c00aa60f  jnz     loc_1C00AA6C0
0x1c00aa615  cmp     byte ptr [rsp+0E8h+var_70], sil
0x1c00aa61a  jnz     short loc_1C00AA625
0x1c00aa61c  test    r14, r14
0x1c00aa61f  jnz     loc_1C00E117E
0x1c00aa625  add     r13d, [rdi+868h]
0x1c00aa62c  mov     [rsp+0E8h+var_80], r13d
0x1c00aa631  mov     [rdi+868h], esi
0x1c00aa637  mov     ebx, esi
0x1c00aa639  mov     [rsp+0E8h+arg_18], ebx
0x1c00aa640  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa646  test    r15b, al
0x1c00aa649  jz      loc_1C00AA388
0x1c00aa64f  jmp     loc_1C00E1195
0x1c00aa654  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa65a  test    r15b, al
0x1c00aa65d  jnz     loc_1C00E1351
0x1c00aa663  test    r14, r14
0x1c00aa666  jz      loc_1C00AA46E
0x1c00aa66c  jmp     loc_1C00E137F
0x1c00aa671  or      [rsp+0E8h+arg_18], 0FFFFFFFFh
0x1c00aa679  jmp     loc_1C00AA377
0x1c00aa67e  mov     [rsp+0E8h+arg_18], r8d
0x1c00aa686  mov     [rsp+0E8h+var_60], rdx
0x1c00aa68e  jmp     loc_1C00AA377
0x1c00aa693  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa699  test    r15b, al
0x1c00aa69c  jnz     loc_1C00E111B
0x1c00aa6a2  mov     r9, [rsp+0E8h+var_68]
0x1c00aa6aa  jmp     loc_1C00AA5D9
0x1c00aa6af  mov     edx, r13d
0x1c00aa6b2  mov     rcx, [rdi+18h]
0x1c00aa6b6  call    UlConsumeBytesFromConnection
0x1c00aa6bb  jmp     loc_1C00AA495
0x1c00aa6c0  mov     ecx, dword ptr [rsp+0E8h+Size]
0x1c00aa6c4  test    ecx, ecx
0x1c00aa6c6  jnz     loc_1C00E12AD
0x1c00aa6cc  mov     rax, [r8]
0x1c00aa6cf  cmp     [rdx], rax
0x1c00aa6d2  jz      loc_1C00E11AE
0x1c00aa6d8  mov     rax, [rdi+8B8h]
0x1c00aa6df  mov     rcx, [rax+20h]
0x1c00aa6e3  mov     rax, [rdi+18h]
0x1c00aa6e7  add     rax, 1D8h
0x1c00aa6ed  lea     rbx, [rcx-20h]
0x1c00aa6f1  cmp     rcx, rax
0x1c00aa6f4  cmovz   rbx, rsi
0x1c00aa6f8  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa6fe  test    r15b, al
0x1c00aa701  jnz     loc_1C00E11DA
0x1c00aa707  test    rbx, rbx
0x1c00aa70a  jz      loc_1C00AA381
0x1c00aa710  cmp     [rbx+78h], esi
0x1c00aa713  jbe     loc_1C00AA381
0x1c00aa719  mov     r11, [rdi+8B8h]
0x1c00aa720  mov     [rsp+0E8h+var_78], r11
0x1c00aa725  mov     [rdi+8B8h], rbx
0x1c00aa72c  lea     r8, [rbx+88h]
0x1c00aa733  mov     [rdi+8C0h], r8
0x1c00aa73a  mov     r9d, [rbx+70h]
0x1c00aa73e  lea     rbx, [rdi+858h]
0x1c00aa745  cmp     [rbx], rsi
0x1c00aa748  jz      short loc_1C00AA78B
0x1c00aa74a  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa750  test    r15b, al
0x1c00aa753  jnz     loc_1C00E122C
0x1c00aa759  mov     rdx, [rsp+0E8h+var_78]
0x1c00aa75e  cmp     rdx, [rdi+8B0h]
0x1c00aa765  mov     ebx, [rsp+0E8h+arg_18]
0x1c00aa76c  jz      loc_1C00AA388
0x1c00aa772  mov     rcx, [rsp+0E8h+var_48]
0x1c00aa77a  call    UlReleaseRequestBuffer
0x1c00aa77f  jmp     loc_1C00AA388
0x1c00aa784  mov     ebx, [rax]
0x1c00aa786  jmp     loc_1C00AA4FF
0x1c00aa78b  mov     edx, [rdi+888h]
0x1c00aa791  shr     edx, 7
0x1c00aa794  and     edx, 1
0x1c00aa797  mov     [rsp+0E8h+var_B8], rsi
0x1c00aa79c  mov     qword ptr [rsp+0E8h+Priority], rbx
0x1c00aa7a1  lea     rax, [rsp+0E8h+Size+4]
0x1c00aa7a6  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax
0x1c00aa7ab  mov     rcx, [rsp+0E8h+var_48]
0x1c00aa7b3  call    ParseChunkLength
0x1c00aa7b8  mov     ecx, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00aa7be  test    r15b, cl
0x1c00aa7c1  jnz     loc_1C00E1203
0x1c00aa7c7  mov     eax, dword ptr [rsp+0E8h+Size+4]
0x1c00aa7cb  add     [rdi+8C0h], rax
0x1c00aa7d2  add     r13d, dword ptr [rsp+0E8h+Size+4]
0x1c00aa7d7  mov     [rsp+0E8h+var_80], r13d
0x1c00aa7dc  mov     r11, [rsp+0E8h+var_78]
0x1c00aa7e1  jmp     loc_1C00AA74A
0x1c00e0df4  mov     ecx, 0Fh
0x1c00e0df9  mov     rax, [rdi+8B8h]
0x1c00e0e00  mov     [rsp+0E8h+var_B8], rax
0x1c00e0e05  mov     rax, [r8]
0x1c00e0e08  mov     qword ptr [rsp+0E8h+Priority], rax
0x1c00e0e0d  mov     rax, [rdx]
0x1c00e0e10  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax
0x1c00e0e15  mov     r9d, [rdi+1E0h]
0x1c00e0e1c  mov     r8, rdi
0x1c00e0e1f  mov     rdx, r12
0x1c00e0e22  call    WPP_SF_qLIIq
0x1c00e0e27  mov     rdx, [rsp+0E8h+var_68]
0x1c00e0e2f  mov     r8, [rsp+0E8h+var_78]
0x1c00e0e34  jmp     loc_1C00AA3BF
0x1c00e0e39  mov     ecx, 10h
0x1c00e0e3e  mov     r8, rdi
0x1c00e0e41  mov     rdx, r12
0x1c00e0e44  call    WPP_SF_q
0x1c00e0e49  nop
0x1c00e0e4a  jmp     loc_1C00AA4B8
0x1c00e0e4f  mov     ecx, 12h
0x1c00e0e54  mov     r9d, edx
0x1c00e0e57  mov     r8, rdi
0x1c00e0e5a  mov     rdx, r12
0x1c00e0e5d  call    WPP_SF_qD
0x1c00e0e62  mov     edx, dword ptr [rsp+0E8h+Size]
0x1c00e0e66  jmp     loc_1C00AA420
0x1c00e0e6b  mov     rax, [rdi+8B8h]
0x1c00e0e72  mov     rcx, [rax+20h]
0x1c00e0e76  mov     rax, [rdi+18h]
0x1c00e0e7a  add     rax, 1D8h
0x1c00e0e80  lea     rdx, [rcx-20h]
0x1c00e0e84  cmp     rcx, rax
0x1c00e0e87  cmovz   rdx, rsi
0x1c00e0e8b  test    rdx, rdx
0x1c00e0e8e  jz      loc_1C00AA663
0x1c00e0e94  cmp     [rdx+78h], esi
  ... truncated ...
```
