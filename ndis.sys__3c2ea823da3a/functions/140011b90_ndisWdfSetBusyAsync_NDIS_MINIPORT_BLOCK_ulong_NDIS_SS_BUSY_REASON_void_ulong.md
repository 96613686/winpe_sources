# ndisWdfSetBusyAsync(_NDIS_MINIPORT_BLOCK *,ulong,_NDIS_SS_BUSY_REASON,void *,ulong)

- ea: `0x140011b90`
- end: `0x140011f3b`
- name: `?ndisWdfSetBusyAsync@@YAEPEAU_NDIS_MINIPORT_BLOCK@@KW4_NDIS_SS_BUSY_REASON@@PEAXK@Z`
- size: `939`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140011a40`
- `0x140012d00`
- `0x140067910`
- `0x140075510`

## callees

- `0x140004890`
- `0x14000de20`
- `0x140011b90`
- `0x140011f50`
- `0x140012180`
- `0x140012580`
- `0x140012a00`
- `0x14002c970`
- `0x1400347f0`
- `0x140086e00`
- `0x1400c1ea0`
- `0x1400c1f5c`
- `0x1400c20a4`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x140011c15`
- `ntoskrnl!KeReadStateEvent` at `0x140011c15`
- `ntoskrnl!KeClearEvent` at `0x140011e04`
- `ntoskrnl!KeClearEvent` at `0x140011e04`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c50`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011e27`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011e6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400e7947`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c50`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011e27`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011e6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400e7947`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011bca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011bca`

## pseudocode

```c
bool __fastcall ndisWdfSetBusyAsync(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // rbx
  unsigned __int64 (*v10)(void *, struct _NET_BUFFER_LIST *); // rdx
  KIRQL v11; // r13
  char v12; // di
  unsigned int v14; // edi
  _QWORD *v15; // r12
  _QWORD *v16; // rax
  char v17; // r15
  struct _NET_BUFFER_LIST *v18; // r12
  __int64 v19; // rcx
  int v20; // r8d
  _QWORD *v21; // rdx
  _QWORD *v22; // r12
  struct _NET_BUFFER_LIST *v23; // rcx
  struct _LIST_ENTRY v24; // [rsp+30h] [rbp-30h] BYREF
  __int64 v25; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v26; // [rsp+48h] [rbp-18h]
  _QWORD v27[2]; // [rsp+50h] [rbp-10h] BYREF

  v5 = *(_QWORD *)(a1 + 4448);
  v24.Blink = &v24;
  v24.Flink = &v24;
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5);
  if ( (*(_DWORD *)(v5 + 512)
     || *(_DWORD *)(v5 + 516)
     || *(_DWORD *)(v5 + 528)
     || *(_DWORD *)(v5 + 532)
     || *(_DWORD *)(v5 + 520)
     || *(_DWORD *)(v5 + 524)
     || *(_DWORD *)(v5 + 576)
     || *(_DWORD *)(v5 + 508))
    && KeReadStateEvent((PRKEVENT)(v5 + 272)) )
  {
    v12 = ndisIncrementAsyncIdleCountersLocked(v5, a2, a3);
    ndisSelectiveSuspendSetResumeBusyReason(v5, 0, a3, 0);
    KeReleaseSpinLock((PKSPIN_LOCK)v5, v11);
    return v12;
  }
  if ( a3 == 54 )
  {
    v14 = 0;
LABEL_26:
    v17 = 0;
    v18 = 0;
    if ( !*(_DWORD *)(v5 + 512)
      && !*(_DWORD *)(v5 + 516)
      && !*(_DWORD *)(v5 + 528)
      && !*(_DWORD *)(v5 + 532)
      && !*(_DWORD *)(v5 + 520)
      && !*(_DWORD *)(v5 + 524)
      && !*(_DWORD *)(v5 + 576)
      && !*(_DWORD *)(v5 + 508) )
    {
      v17 = 1;
      KeClearEvent((PRKEVENT)(v5 + 272));
      v14 = a3;
    }
    ndisIncrementAsyncIdleCountersLocked(v5, a2, a3);
    KeReleaseSpinLock((PKSPIN_LOCK)v5, v11);
    if ( v17 )
      ndisWdfAcquirePowerReferenceHelper((struct _NDIS_MINIPORT_BLOCK *)a1, 0, 1u);
LABEL_37:
    if ( v18 )
    {
      if ( byte_14011D730 && (*(_DWORD *)(a1 + 5872) & 2) != 0 )
        PktMonClientNblDropNdis(a1 + 5816, (_DWORD)v18, v20, 2, -1071448017, -536866804);
      NdisSetStatusInNblChain(v18, -1071448052);
      ndisMSendNetBufferListsCompleteInternal((struct _NDIS_MINIPORT_BLOCK *)a1, v18, 0, 0);
    }
    goto LABEL_38;
  }
  v24.Blink = &v24;
  v24.Flink = &v24;
  if ( a3 == 49 )
    goto LABEL_40;
  if ( a3 == 51 )
  {
    ndisDequeueDirectOidsByRequestId((struct _NDIS_SELECTIVE_SUSPEND *)v5, (void *)a4, &v24);
LABEL_40:
    v14 = 0;
    goto LABEL_41;
  }
  if ( a3 != 53 )
  {
    v14 = 0;
    if ( a3 == 52 )
    {
      v15 = 0;
      if ( *(_DWORD *)ndisNblTrackerMode )
        ndisNblTrackerTransferOwnershipInternal(
          (struct _NET_BUFFER_LIST *)a4,
          0,
          *(struct NDIS_NBL_TRACKER_HANDLE__ **)(v5 + 608),
          (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
          1u);
      v16 = (_QWORD *)a4;
      if ( a4 )
      {
        do
        {
          v16[14] = a5;
          v15 = v16;
          v16 = (_QWORD *)*v16;
        }
        while ( v16 );
      }
      **(_QWORD **)(v5 + 552) = a4;
      *(_QWORD *)(v5 + 552) = v15;
      *(_DWORD *)(v5 + 632) = 0;
    }
    else if ( a3 == 50 )
    {
      v21 = *(_QWORD **)(v5 + 592);
      if ( *v21 != v5 + 584 )
        __fastfail(3u);
      *(_QWORD *)(a4 + 72) = v5 + 584;
      *(_QWORD *)(a4 + 80) = v21;
      *v21 = a4 + 72;
      *(_QWORD *)(v5 + 592) = a4 + 72;
      *(_DWORD *)(v5 + 632) = *(_DWORD *)(a4 + 32);
    }
    goto LABEL_26;
  }
  v22 = (_QWORD *)(v5 + 544);
  v14 = 0;
  v23 = *(struct _NET_BUFFER_LIST **)(v5 + 544);
  if ( v23 )
  {
    v25 = 0;
    v26 = &v25;
    v27[0] = 0;
    v27[1] = v27;
    NdisClassifyNblChain2(v23, v10, (void *)a4, (struct NBL_QUEUE_t *)&v25, (struct NBL_QUEUE_t *)v27);
    if ( *v22 != v25 )
    {
      if ( v25 )
      {
        *v22 = v25;
        *(_QWORD *)(v5 + 552) = v26;
        v26 = &v25;
        v25 = 0;
      }
      else
      {
        *v22 = 0;
        *(_QWORD *)(v5 + 552) = v5 + 544;
      }
    }
    v18 = (struct _NET_BUFFER_LIST *)v27[0];
    KeReleaseSpinLock((PKSPIN_LOCK)v5, v11);
    goto LABEL_37;
  }
LABEL_41:
  KeReleaseSpinLock((PKSPIN_LOCK)v5, v11);
LABEL_38:
  if ( v24.Flink != &v24 )
    ndisCancelDequeuedDirectOidRequests((struct _NDIS_MINIPORT_BLOCK *)a1, &v24);
  if ( v14 )
  {
    if ( (byte_14011B001 & 8) != 0 )
      McTemplateK0qq_EtwWriteTransfer(
        v19,
        SSResumeRequested,
        a1 + 4008,
        (*(_QWORD *)(a1 + 4024) >> 24) & 0xFFFFFFLL,
        v14);
  }
  return a3 == 54;
}

```

## disassembly

```asm
0x140011b90  mov     [rsp-38h+arg_8], edx
0x140011b94  push    rbp
0x140011b95  push    rbx
0x140011b96  push    rsi
0x140011b97  push    rdi
0x140011b98  push    r13
0x140011b9a  push    r14
0x140011b9c  push    r15
0x140011b9e  mov     rbp, rsp
0x140011ba1  sub     rsp, 60h
0x140011ba5  mov     rbx, [rcx+1160h]
0x140011bac  lea     rax, [rbp+var_30]
0x140011bb0  mov     [rbp+var_30.Blink], rax
0x140011bb4  mov     r14, rcx
0x140011bb7  lea     rax, [rbp+var_30]
0x140011bbb  mov     rcx, rbx; SpinLock
0x140011bbe  mov     [rbp+var_30.Flink], rax
0x140011bc2  mov     r15, r9
0x140011bc5  mov     esi, r8d
0x140011bc8  mov     edi, edx
0x140011bca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011bd1  nop     dword ptr [rax+rax+00h]
0x140011bd6  cmp     dword ptr [rbx+200h], 0
0x140011bdd  movzx   r13d, al
0x140011be1  mov     [rbp+arg_0], al
0x140011be4  jnz     short loc_140011C0E
0x140011be6  cmp     dword ptr [rbx+204h], 0
0x140011bed  jnz     short loc_140011C0E
0x140011bef  cmp     dword ptr [rbx+210h], 0
0x140011bf6  jnz     short loc_140011C0E
0x140011bf8  cmp     dword ptr [rbx+214h], 0
0x140011bff  jnz     short loc_140011C0E
0x140011c01  cmp     dword ptr [rbx+208h], 0
0x140011c08  jz      loc_140011CD0
0x140011c0e  lea     rcx, [rbx+110h]; Event
0x140011c15  call    cs:__imp_KeReadStateEvent
0x140011c1c  nop     dword ptr [rax+rax+00h]
0x140011c21  test    eax, eax
0x140011c23  jz      loc_140011CF7
0x140011c29  mov     r8d, esi
0x140011c2c  mov     edx, edi
0x140011c2e  mov     rcx, rbx
0x140011c31  call    ?ndisIncrementAsyncIdleCountersLocked@@YAEPEAU_NDIS_SELECTIVE_SUSPEND@@KW4_NDIS_SS_BUSY_REASON@@@Z; ndisIncrementAsyncIdleCountersLocked(_NDIS_SELECTIVE_SUSPEND *,ulong,_NDIS_SS_BUSY_REASON)
0x140011c36  xor     r9d, r9d
0x140011c39  mov     r8d, esi
0x140011c3c  xor     edx, edx
0x140011c3e  mov     rcx, rbx
0x140011c41  movzx   edi, al
0x140011c44  call    ndisSelectiveSuspendSetResumeBusyReason
0x140011c49  movzx   edx, r13b; NewIrql
0x140011c4d  mov     rcx, rbx; SpinLock
0x140011c50  call    cs:__imp_KeReleaseSpinLock
0x140011c57  nop     dword ptr [rax+rax+00h]
0x140011c5c  movzx   eax, dil
0x140011c60  add     rsp, 60h
0x140011c64  pop     r15
0x140011c66  pop     r14
0x140011c68  pop     r13
0x140011c6a  pop     rdi
0x140011c6b  pop     rsi
0x140011c6c  pop     rbx
0x140011c6d  pop     rbp
0x140011c6e  retn
0x140011c70  lea     rdx, [rbp+var_30]; struct _LIST_ENTRY *
0x140011c74  mov     rcx, r14; struct _NDIS_MINIPORT_BLOCK *
0x140011c77  call    ?ndisCancelDequeuedDirectOidRequests@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_LIST_ENTRY@@@Z; ndisCancelDequeuedDirectOidRequests(_NDIS_MINIPORT_BLOCK *,_LIST_ENTRY *)
0x140011c7c  test    edi, edi
0x140011c7e  jz      short loc_140011CB2
0x140011c80  test    cs:byte_14011B001, 8
0x140011c87  jz      short loc_140011CB2
0x140011c89  mov     r9, [r14+0FB8h]
0x140011c90  lea     r8, [r14+0FA8h]
0x140011c97  shr     r9, 18h
0x140011c9b  lea     rdx, SSResumeRequested
0x140011ca2  and     r9d, 0FFFFFFh
0x140011ca9  mov     dword ptr [rsp+60h+var_40], edi
0x140011cad  call    McTemplateK0qq_EtwWriteTransfer
0x140011cb2  mov     r12, [rsp+60h+arg_10]
0x140011cba  cmp     esi, 36h ; '6'
0x140011cbd  setz    al
0x140011cc0  add     rsp, 60h
0x140011cc4  pop     r15
0x140011cc6  pop     r14
0x140011cc8  pop     r13
0x140011cca  pop     rdi
0x140011ccb  pop     rsi
0x140011ccc  pop     rbx
0x140011ccd  pop     rbp
0x140011cce  retn
0x140011cd0  cmp     dword ptr [rbx+20Ch], 0
0x140011cd7  jnz     loc_140011C0E
0x140011cdd  cmp     dword ptr [rbx+240h], 0
0x140011ce4  jnz     loc_140011C0E
0x140011cea  cmp     dword ptr [rbx+1FCh], 0
0x140011cf1  jnz     loc_140011C0E
0x140011cf7  mov     [rsp+60h+arg_10], r12
0x140011cff  cmp     esi, 36h ; '6'
0x140011d02  jz      loc_140011DA6
0x140011d08  lea     rax, [rbp+var_30]
0x140011d0c  mov     ecx, esi
0x140011d0e  mov     [rbp+var_30.Blink], rax
0x140011d12  lea     rax, [rbp+var_30]
0x140011d16  mov     [rbp+var_30.Flink], rax
0x140011d1a  sub     ecx, 31h ; '1'
0x140011d1d  jz      loc_140011E66
0x140011d23  sub     ecx, 2
0x140011d26  jz      loc_140011F27
0x140011d2c  sub     ecx, 2
0x140011d2f  jz      loc_140011EB5
0x140011d35  cmp     ecx, 1
0x140011d38  jz      loc_140011ED7
0x140011d3e  xor     edi, edi
0x140011d40  cmp     esi, 34h ; '4'
0x140011d43  jnz     loc_140011ECC
0x140011d49  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, edi; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140011d4f  mov     r12d, edi
0x140011d52  jz      short loc_140011D73
0x140011d54  mov     r8, [rbx+260h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140011d5b  mov     r9d, 1; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x140011d61  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140011d63  mov     dword ptr [rsp+60h+var_40], 1; unsigned int
0x140011d6b  mov     rcx, r15; struct _NET_BUFFER_LIST *
0x140011d6e  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x140011d73  mov     rax, r15
0x140011d76  test    r15, r15
0x140011d79  jz      short loc_140011D8D
0x140011d7b  mov     ecx, [rbp+arg_20]
0x140011d7e  mov     [rax+70h], rcx
0x140011d82  mov     r12, rax
0x140011d85  mov     rax, [rax]
0x140011d88  test    rax, rax
0x140011d8b  jnz     short loc_140011D7E
0x140011d8d  mov     rax, [rbx+228h]
0x140011d94  mov     [rax], r15
0x140011d97  mov     [rbx+228h], r12
0x140011d9e  mov     [rbx+278h], edi
0x140011da4  jmp     short loc_140011DA8
0x140011da6  xor     edi, edi
0x140011da8  xor     r15b, r15b
0x140011dab  mov     r13b, 1
0x140011dae  cmp     dword ptr [rbx+200h], 0
0x140011db5  mov     r12, rdi
0x140011db8  jnz     short loc_140011E12
0x140011dba  cmp     dword ptr [rbx+204h], 0
0x140011dc1  jnz     short loc_140011E12
0x140011dc3  cmp     dword ptr [rbx+210h], 0
0x140011dca  jnz     short loc_140011E12
0x140011dcc  cmp     dword ptr [rbx+214h], 0
0x140011dd3  jnz     short loc_140011E12
0x140011dd5  cmp     dword ptr [rbx+208h], 0
0x140011ddc  jnz     short loc_140011E12
0x140011dde  cmp     dword ptr [rbx+20Ch], 0
0x140011de5  jnz     short loc_140011E12
0x140011de7  cmp     dword ptr [rbx+240h], 0
0x140011dee  jnz     short loc_140011E12
0x140011df0  cmp     dword ptr [rbx+1FCh], 0
0x140011df7  jnz     short loc_140011E12
0x140011df9  lea     rcx, [rbx+110h]; Event
0x140011e00  movzx   r15d, r13b
0x140011e04  call    cs:__imp_KeClearEvent
0x140011e0b  nop     dword ptr [rax+rax+00h]
0x140011e10  mov     edi, esi
0x140011e12  mov     edx, [rbp+arg_8]
0x140011e15  mov     r8d, esi
0x140011e18  mov     rcx, rbx
0x140011e1b  call    ?ndisIncrementAsyncIdleCountersLocked@@YAEPEAU_NDIS_SELECTIVE_SUSPEND@@KW4_NDIS_SS_BUSY_REASON@@@Z; ndisIncrementAsyncIdleCountersLocked(_NDIS_SELECTIVE_SUSPEND *,ulong,_NDIS_SS_BUSY_REASON)
0x140011e20  movzx   edx, [rbp+arg_0]; NewIrql
0x140011e24  mov     rcx, rbx; SpinLock
0x140011e27  call    cs:__imp_KeReleaseSpinLock
0x140011e2e  nop     dword ptr [rax+rax+00h]
0x140011e33  test    r13b, r13b
0x140011e36  jz      short loc_140011E4A
0x140011e38  test    r15b, r15b
0x140011e3b  jz      short loc_140011E4A
0x140011e3d  mov     r8b, 1; unsigned __int8
0x140011e40  xor     edx, edx; unsigned __int8
0x140011e42  mov     rcx, r14; struct _NDIS_MINIPORT_BLOCK *
0x140011e45  call    ?ndisWdfAcquirePowerReferenceHelper@@YAXPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisWdfAcquirePowerReferenceHelper(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x140011e4a  test    r12, r12
0x140011e4d  jnz     loc_140011EE4
0x140011e53  lea     rax, [rbp+var_30]
0x140011e57  cmp     [rbp+var_30.Flink], rax
0x140011e5b  jz      loc_140011C7C
0x140011e61  jmp     loc_140011C70
0x140011e66  xor     edi, edi
0x140011e68  movzx   edx, r13b; NewIrql
0x140011e6c  mov     rcx, rbx; SpinLock
0x140011e6f  call    cs:__imp_KeReleaseSpinLock
0x140011e76  nop     dword ptr [rax+rax+00h]
0x140011e7b  jmp     short loc_140011E53
0x140011e7d  lea     rcx, [rbx+248h]
0x140011e84  mov     rdx, [rcx+8]
0x140011e88  cmp     [rdx], rcx
0x140011e8b  jz      short loc_140011E94
0x140011e8d  mov     ecx, 3
0x140011e92  int     29h; Win8: RtlFailFast(ecx)
0x140011e94  lea     rax, [r15+48h]
0x140011e98  mov     [rax], rcx
0x140011e9b  mov     [rax+8], rdx
0x140011e9f  mov     [rdx], rax
0x140011ea2  mov     [rcx+8], rax
0x140011ea6  mov     eax, [r15+20h]
0x140011eaa  mov     [rbx+278h], eax
0x140011eb0  jmp     loc_140011DA8
0x140011eb5  lea     r12, [rbx+220h]
0x140011ebc  xor     edi, edi
0x140011ebe  mov     rcx, [r12]; struct _NET_BUFFER_LIST *
0x140011ec2  test    rcx, rcx
0x140011ec5  jz      short loc_140011E68
0x140011ec7  jmp     loc_1400E78DC
0x140011ecc  cmp     esi, 32h ; '2'
0x140011ecf  jnz     loc_140011DA8
0x140011ed5  jmp     short loc_140011E7D
0x140011ed7  mov     rdx, r15; struct _NET_BUFFER_LIST *
0x140011eda  mov     rcx, rbx; struct _NDIS_SELECTIVE_SUSPEND *
0x140011edd  call    ?ndisQueueReceiveNblsOnMiniport@@YAXPEAU_NDIS_SELECTIVE_SUSPEND@@PEAU_NET_BUFFER_LIST@@@Z; ndisQueueReceiveNblsOnMiniport(_NDIS_SELECTIVE_SUSPEND *,_NET_BUFFER_LIST *)
0x140011ee2  jmp     short loc_140011E66
0x140011ee4  cmp     cs:byte_14011D730, 0
0x140011eeb  jz      loc_1400E7959
0x140011ef1  lea     rcx, [r14+16B8h]
0x140011ef8  mov     eax, [rcx+38h]
0x140011efb  test    al, 2
0x140011efd  jz      loc_1400E7959
0x140011f03  mov     [rsp+60h+var_38], 0E000100Ch
0x140011f0b  mov     r9d, 2
0x140011f11  mov     rdx, r12
0x140011f14  mov     dword ptr [rsp+60h+var_40], 0C023002Fh
0x140011f1c  call    PktMonClientNblDropNdis
0x140011f21  nop
0x140011f22  jmp     loc_1400E7959
0x140011f27  lea     r8, [rbp+var_30]; struct _LIST_ENTRY *
0x140011f2b  mov     rdx, r15; void *
0x140011f2e  mov     rcx, rbx; struct _NDIS_SELECTIVE_SUSPEND *
0x140011f31  call    ?ndisDequeueDirectOidsByRequestId@@YAXPEAU_NDIS_SELECTIVE_SUSPEND@@PEAXPEAU_LIST_ENTRY@@@Z; ndisDequeueDirectOidsByRequestId(_NDIS_SELECTIVE_SUSPEND *,void *,_LIST_ENTRY *)
0x140011f36  jmp     loc_140011E66
0x1400e78dc  lea     rax, [rbp+var_20]
0x1400e78e0  mov     [rbp+var_20], rdi
0x1400e78e4  mov     [rbp+var_18], rax
0x1400e78e8  lea     r9, [rbp+var_20]; struct NBL_QUEUE_t *
0x1400e78ec  lea     rax, [rbp+var_10]
0x1400e78f0  mov     [rbp+var_10], rdi
0x1400e78f4  mov     [rbp+var_8], rax
0x1400e78f8  mov     r8, r15; void *
0x1400e78fb  lea     rax, [rbp+var_10]
0x1400e78ff  mov     [rsp+60h+var_40], rax; struct NBL_QUEUE_t *
0x1400e7904  call    ?NdisClassifyNblChain2@@YAXPEAU_NET_BUFFER_LIST@@P6A_KPEAX0@Z1PEAUNBL_QUEUE_t@@3@Z; NdisClassifyNblChain2(_NET_BUFFER_LIST *,unsigned __int64 (*)(void *,_NET_BUFFER_LIST *),void *,NBL_QUEUE_t *,NBL_QUEUE_t *)
0x1400e7909  mov     rax, [rbp+var_20]
0x1400e790d  cmp     [r12], rax
0x1400e7911  jz      short loc_1400E793C
0x1400e7913  test    rax, rax
0x1400e7916  jz      short loc_1400E7933
0x1400e7918  mov     [r12], rax
0x1400e791c  mov     rax, [rbp+var_18]
0x1400e7920  mov     [r12+8], rax
0x1400e7925  lea     rax, [rbp+var_20]
0x1400e7929  mov     [rbp+var_18], rax
0x1400e792d  mov     [rbp+var_20], rdi
0x1400e7931  jmp     short loc_1400E793C
0x1400e7933  mov     [r12], rdi
0x1400e7937  mov     [r12+8], r12
0x1400e793c  mov     r12, [rbp+var_10]
0x1400e7940  movzx   edx, r13b; NewIrql
0x1400e7944  mov     rcx, rbx; SpinLock
0x1400e7947  call    cs:__imp_KeReleaseSpinLock
0x1400e794e  nop     dword ptr [rax+rax+00h]
0x1400e7953  nop
0x1400e7954  jmp     loc_140011E4A
0x1400e7959  mov     edx, 0C023000Ch; int
0x1400e795e  mov     rcx, r12; struct _NET_BUFFER_LIST *
0x1400e7961  call    ?NdisSetStatusInNblChain@@YAXPEAU_NET_BUFFER_LIST@@H@Z; NdisSetStatusInNblChain(_NET_BUFFER_LIST *,int)
0x1400e7966  mov     rcx, r14; struct _NDIS_MINIPORT_BLOCK *
0x1400e7969  xor     r9d, r9d; unsigned __int8
0x1400e796c  xor     r8d, r8d; unsigned int
0x1400e796f  mov     rdx, r12; struct _NET_BUFFER_LIST *
0x1400e7972  call    ?ndisMSendNetBufferListsCompleteInternal@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NET_BUFFER_LIST@@KE@Z; ndisMSendNetBufferListsCompleteInternal(_NDIS_MINIPORT_BLOCK *,_NET_BUFFER_LIST *,ulong,uchar)
0x1400e7977  nop
0x1400e7978  jmp     loc_140011E53
```
