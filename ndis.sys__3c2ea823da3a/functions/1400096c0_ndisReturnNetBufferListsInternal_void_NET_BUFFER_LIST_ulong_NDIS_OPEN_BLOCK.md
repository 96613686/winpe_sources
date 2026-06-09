# ndisReturnNetBufferListsInternal(void *,_NET_BUFFER_LIST *,ulong,_NDIS_OPEN_BLOCK *)

- ea: `0x1400096c0`
- end: `0x140009e66`
- name: `?ndisReturnNetBufferListsInternal@@YAXPEAXPEAU_NET_BUFFER_LIST@@KPEAU_NDIS_OPEN_BLOCK@@@Z`
- size: `1958`
- prototype: `void __fastcall(struct _NDIS_FILTER_BLOCK *, struct _NET_BUFFER_LIST *, unsigned int, struct _NDIS_OPEN_BLOCK *)`
- caller_count: `9`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400044a0`
- `0x140004d70`
- `0x1400054e0`
- `0x140005a30`
- `0x140005f10`
- `0x1400076a0`
- `0x14000a600`
- `0x140072200`
- `0x1400870f0`

## callees

- `0x1400096c0`
- `0x140009e70`
- `0x14000a5a0`
- `0x14000de20`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140009c5b`
- `ntoskrnl!KfRaiseIrql` at `0x140009c5b`
- `ntoskrnl!KeLowerIrql` at `0x140009996`
- `ntoskrnl!KeLowerIrql` at `0x140009996`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009873`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009873`
- `ntoskrnl!MmUnmapLockedPages` at `0x140009e02`
- `ntoskrnl!MmUnmapLockedPages` at `0x140009e02`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400097b7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400097b7`
- `ntoskrnl!IoGetStackLimits` at `0x1400098ef`
- `ntoskrnl!IoGetStackLimits` at `0x1400098ef`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140009b08`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140009b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009cea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009cea`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009b80`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009b80`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009b30`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009b30`

## pseudocode

```c
void __fastcall ndisReturnNetBufferListsInternal(
        struct _NDIS_FILTER_BLOCK *a1,
        struct _NET_BUFFER_LIST *a2,
        unsigned int a3,
        struct _NDIS_OPEN_BLOCK *a4)
{
  struct _NET_BUFFER_LIST *v4; // rbx
  int v6; // r15d
  struct _NET_BUFFER_LIST *i; // rcx
  unsigned __int64 v8; // rax
  struct _NET_BUFFER_LIST *v9; // r12
  _QWORD *p_Alignment; // r15
  struct _NET_BUFFER_LIST *Alignment; // rbp
  _NET_BUFFER *FirstNetBuffer; // rax
  struct _NPAGED_LOOKASIDE_LIST *v13; // r14
  _MDL *CurrentMdl; // r13
  unsigned int v15; // ebp
  unsigned int Number; // r13d
  NDIS_NBL_TRACKER_HANDLE__ *NblTracker; // rdx
  __int64 v18; // r14
  void (__fastcall *v19)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64); // r15
  struct _NET_BUFFER_LIST *v20; // r12
  __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  char *v23; // r8
  unsigned __int64 v24; // rax
  struct _NET_BUFFER_LIST **p_Parameter; // rsi
  struct _NET_BUFFER_LIST *v26; // rdx
  __int64 v27; // rbp
  __int64 v28; // rax
  struct _NET_BUFFER_LIST *v29; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v30; // rax
  __int64 v31; // r8
  struct _NET_BUFFER_LIST *v32; // rbx
  int v33; // ecx
  KIRQL v34; // r14
  _NET_BUFFER_LIST **p_ReceivedNblsToComplete; // rcx
  _NET_BUFFER_LIST *j; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v37; // rax
  __int64 ChildRefCount; // r8
  struct _NET_BUFFER_LIST *Scratch; // rbx
  struct _NET_BUFFER_LIST *v40; // rdx
  struct _VF_NDIS_DISPATCH_TABLE *v41; // rax
  __int64 v42; // r8
  struct _NET_BUFFER_LIST *v43; // rbx
  Rtl::KString *value; // [rsp+30h] [rbp-98h]
  unsigned __int64 LowLimit; // [rsp+38h] [rbp-90h] BYREF
  unsigned __int64 HighLimit; // [rsp+40h] [rbp-88h] BYREF
  int v47; // [rsp+48h] [rbp-80h]
  struct _NET_BUFFER_LIST *Parameter; // [rsp+50h] [rbp-78h] BYREF
  struct _NET_BUFFER_LIST *v49; // [rsp+58h] [rbp-70h]
  void (__fastcall *v50)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64); // [rsp+60h] [rbp-68h]
  struct _NET_BUFFER_LIST *v51; // [rsp+68h] [rbp-60h]
  __int64 v52; // [rsp+70h] [rbp-58h]
  unsigned int v53; // [rsp+78h] [rbp-50h]
  int v54; // [rsp+7Ch] [rbp-4Ch]
  _UNKNOWN *retaddr; // [rsp+C8h] [rbp+0h] BYREF
  char v56; // [rsp+D0h] [rbp+8h]
  KIRQL v57; // [rsp+D0h] [rbp+8h]
  unsigned int v58; // [rsp+D8h] [rbp+10h]
  unsigned int v59; // [rsp+D8h] [rbp+10h]
  unsigned int v60; // [rsp+E0h] [rbp+18h]
  struct _NDIS_OPEN_BLOCK *v61; // [rsp+E8h] [rbp+20h]

  v61 = a4;
  v60 = a3;
  v4 = a2;
  if ( LODWORD(a1->FilterFriendlyName) || (LOBYTE(v6) = 0, value = 0, v56 = 0, *(_DWORD *)&a1->Ref.ReferenceCount) )
  {
    v6 = *(_DWORD *)&a1->Ref.ReferenceCount;
    v56 = v6;
    value = a1->FilterInstanceName.__ptr_.__value_;
    if ( !value )
      value = a1->FilterInstanceName.__ptr_.__value_;
  }
  for ( i = a2; i; i = (struct _NET_BUFFER_LIST *)i->Link.Alignment )
    i->Flags = i->Flags & 0xFFFFFFF4 | 8;
  v8 = (unsigned int)Microsoft_Windows_Networking_CorrelationEnabled;
  if ( (Microsoft_Windows_Networking_CorrelationEnabled
     || byte_14011D730 != (_BYTE)Microsoft_Windows_Networking_CorrelationEnabled)
    && a2 )
  {
    v8 = (unsigned __int64)a2;
    if ( byte_14011D730 )
    {
      do
      {
        *(_QWORD *)(v8 + 248) = 0;
        v8 = *(_QWORD *)v8;
      }
      while ( v8 );
    }
    else
    {
      do
      {
        *(_QWORD *)(v8 + 248) |= 0x8000000000000000uLL;
        v8 = *(_QWORD *)v8;
      }
      while ( v8 );
    }
  }
  if ( *(_DWORD *)&a1[2].XState )
  {
    v9 = 0;
    if ( a2 )
    {
      p_Alignment = 0;
      do
      {
        Alignment = (struct _NET_BUFFER_LIST *)v4->Link.Alignment;
        v4->Link.Alignment = 0;
        HIDWORD(v8) = HIDWORD(PoolHandle);
        if ( v4->NdisPoolHandle == PoolHandle )
        {
          _InterlockedDecrement((volatile signed __int32 *)&a1[2].XState);
          FirstNetBuffer = v4->FirstNetBuffer;
          v13 = (struct _NPAGED_LOOKASIDE_LIST *)v4->MiniportReserved[1];
          CurrentMdl = FirstNetBuffer->CurrentMdl;
          if ( (CurrentMdl->MdlFlags & 0x20) != 0 )
            MmUnmapLockedPages(CurrentMdl->MappedSystemVa, FirstNetBuffer->CurrentMdl);
          if ( v13 )
            ExFreeToNPagedLookasideList(v13, CurrentMdl);
          else
            ExFreePoolWithTag(CurrentMdl, 0);
          NdisFreeNetBufferList(v4);
        }
        else
        {
          if ( v9 )
            *p_Alignment = v4;
          else
            v9 = v4;
          p_Alignment = &v4->Link.Alignment;
        }
        v4 = Alignment;
      }
      while ( Alignment );
      LOBYTE(v6) = v56;
      a4 = v61;
      LOBYTE(a3) = v60;
    }
    v4 = v9;
  }
  if ( v4 )
  {
    v57 = 2;
    v15 = a3 & 1;
    Number = -1;
    if ( *(_DWORD *)ndisNblTrackerMode )
    {
      if ( a4 )
        NblTracker = a4->NblTracker;
      else
        NblTracker = 0;
      ndisNblTrackerTransferOwnershipInternal(
        v4,
        NblTracker,
        *(struct NDIS_NBL_TRACKER_HANDLE__ **)&a1[1].NicSwitchHwCapabilities.MaxNumQueuePairsForDefaultVPort,
        NdisNblTrackerEvent_ProtocolReturned,
        v15);
    }
    v47 = v6 & 0x20;
    if ( (v6 & 0x20) != 0 )
    {
      if ( !v15 )
        v57 = KfRaiseIrql(2u);
      Number = KeGetPcr()->Prcb.Number;
      v8 = __rdtsc();
      *(wchar_t **)((char *)&value[21].Buffer + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData) = (wchar_t *)v8;
    }
    v18 = *(_QWORD *)&a1[1].NicSwitchCurrentCapabilities.Flags;
    v19 = *(void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))&a1[1].NicSwitchCurrentCapabilities.NdisReserved14;
    v20 = *(struct _NET_BUFFER_LIST **)&a1[1].NicSwitchHwCapabilities.NumberOfIndirectionTableEntriesForDefaultVPort;
    if ( *(_BYTE *)v18 == 17 )
      goto LABEL_33;
    if ( v15 || KeGetCurrentIrql() == 2 )
    {
      LODWORD(v8) = KeGetPcr()->Prcb.Number;
      p_Parameter = &Parameter;
      v59 = v8;
      v50 = 0;
      Parameter = v4;
      v49 = v4;
      v4->Scratch = 0;
      v4->ChildRefCount = v60;
      while ( *(_BYTE *)v18 == 5 )
      {
        v26 = *p_Parameter;
        if ( !*p_Parameter )
          break;
        v27 = *(_QWORD *)(v18 + 424) + 96 * v8;
        if ( *(_BYTE *)(v27 + 88) )
        {
          *p_Parameter = 0;
          do
          {
            v37 = ndisVerifierNdisDispatch;
            ChildRefCount = (unsigned int)v26->ChildRefCount;
            Scratch = (struct _NET_BUFFER_LIST *)v26->Scratch;
            v26->ChildRefCount = 0;
            if ( v37 && *(_BYTE *)v18 == 5 && *(_QWORD *)(v18 + 776) )
              (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))v37 + 17))(
                v20,
                v26,
                ChildRefCount);
            else
              v19(v20, v26, ChildRefCount);
            v26 = Scratch;
          }
          while ( Scratch );
          break;
        }
        *(_BYTE *)(v27 + 88) = 1;
        v28 = v18;
        v29 = *p_Parameter;
        *p_Parameter = 0;
        if ( v29 )
        {
          do
          {
            v30 = ndisVerifierNdisDispatch;
            v31 = (unsigned int)v29->ChildRefCount;
            v32 = (struct _NET_BUFFER_LIST *)v29->Scratch;
            v29->ChildRefCount = 0;
            if ( v30 && *(_BYTE *)v18 == 5 && *(_QWORD *)(v18 + 776) )
              (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))v30 + 17))(
                v20,
                v29,
                v31);
            else
              v19(v20, v29, v31);
            v29 = v32;
          }
          while ( v32 );
          v28 = v18;
        }
        *(_BYTE *)(v27 + 88) = 0;
        p_Parameter = (struct _NET_BUFFER_LIST **)(v27 + 72);
        v19 = *(void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))(v28 + 528);
        v20 = *(struct _NET_BUFFER_LIST **)(v28 + 536);
        v8 = v59;
        v18 = *(_QWORD *)(v18 + 552);
      }
      v40 = *p_Parameter;
      if ( *p_Parameter )
      {
        *p_Parameter = 0;
        do
        {
          v41 = ndisVerifierNdisDispatch;
          v42 = (unsigned int)v40->ChildRefCount;
          v43 = (struct _NET_BUFFER_LIST *)v40->Scratch;
          v40->ChildRefCount = 0;
          if ( v41 && *(_BYTE *)v18 == 5 && *(_QWORD *)(v18 + 776) )
            (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, __int64))v41 + 17))(
              v20,
              v40,
              v42);
          else
            v19(v20, v40, v42);
          v40 = v43;
        }
        while ( v43 );
      }
      goto LABEL_34;
    }
    if ( a1->Header.Type != 5 )
      goto LABEL_33;
    v58 = Size;
    LowLimit = 0;
    HighLimit = 0;
    v21 = KeGetPcr()->Prcb.Number << 12;
    v22 = *(_QWORD *)(qword_14011CF78 + v21);
    LowLimit = v22;
    HighLimit = *(_QWORD *)(qword_14011CF70 + v21);
    if ( (unsigned __int64)&retaddr >= HighLimit || v22 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v22 = LowLimit;
    }
    if ( (unsigned __int64)&retaddr - v22 < v58 )
    {
      v33 = 24576;
      v54 = 0;
      Parameter = (struct _NET_BUFFER_LIST *)v18;
      v49 = v20;
      v50 = v19;
      v51 = v4;
      v52 = 0;
      v53 = v60;
      if ( (unsigned int)Size > 0x6000 )
        v33 = Size;
      if ( KeExpandKernelStackAndCalloutEx(
             ndisDataPathExpandStackCallback<3,void (void *,_NET_BUFFER_LIST *,unsigned long)>,
             &Parameter,
             v33,
             0,
             0) < 0 )
      {
        if ( *(_DWORD *)ndisNblTrackerMode )
          ndisNblTrackerTransferOwnershipInternal(
            v4,
            a1->NblTracker,
            (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA0,
            (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)1,
            0);
        v34 = KeAcquireSpinLockRaiseToDpc(&a1->Lock);
        a1->LockThread = KeGetCurrentThread();
        p_ReceivedNblsToComplete = &a1->StackExpansionFallback.PendingWork.ReceivedNblsToComplete;
        for ( j = a1->StackExpansionFallback.PendingWork.ReceivedNblsToComplete;
              j;
              j = (_NET_BUFFER_LIST *)j->Link.Alignment )
        {
          p_ReceivedNblsToComplete = &j->Next;
        }
        *p_ReceivedNblsToComplete = v4;
        ndisQueueStackExpansionFallbackWorkItem(a1);
        a1->LockThread = 0;
        KeReleaseSpinLock(&a1->Lock, v34);
      }
      goto LABEL_34;
    }
    if ( ndisVerifierNdisDispatch && *(_BYTE *)v18 == 5 && *(_QWORD *)(v18 + 776) )
      (*((void (__fastcall **)(struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, _QWORD))ndisVerifierNdisDispatch
       + 17))(
        v20,
        v4,
        v60);
    else
LABEL_33:
      v19(v20, v4, v60);
LABEL_34:
    if ( v47 )
    {
      if ( Number == -1 )
        Number = KeGetPcr()->Prcb.Number;
      v23 = (char *)value + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData;
      v24 = __rdtsc();
      *((_QWORD *)v23 + 18) += (((unsigned __int64)HIDWORD(v24) << 32) | (unsigned int)v24) - *((_QWORD *)v23 + 43);
      *((_QWORD *)v23 + 43) = 0;
      if ( v57 != 2 )
        KeLowerIrql(v57);
    }
  }
}

```

## disassembly

```asm
0x1400096c0  mov     [rsp+arg_18], r9
0x1400096c5  mov     [rsp+arg_10], r8d
0x1400096ca  push    rbx
0x1400096cb  push    rsi
0x1400096cc  push    rdi
0x1400096cd  push    r15
0x1400096cf  sub     rsp, 0A8h
0x1400096d6  xor     edi, edi
0x1400096d8  mov     rbx, rdx
0x1400096db  mov     rsi, rcx
0x1400096de  cmp     [rcx+30h], edi
0x1400096e1  jnz     loc_140009C29
0x1400096e7  mov     r15d, edi
0x1400096ea  mov     [rsp+0C8h+var_98], rdi
0x1400096ef  mov     [rsp+0C8h+arg_0], edi
0x1400096f6  cmp     [rcx+50h], edi
0x1400096f9  jnz     loc_140009C29
0x1400096ff  mov     rcx, rdx
0x140009702  test    rdx, rdx
0x140009705  jz      short loc_140009721
0x140009707  mov     eax, [rcx+88h]
0x14000970d  and     eax, 0FFFFFFFCh
0x140009710  or      eax, 8
0x140009713  mov     [rcx+88h], eax
0x140009719  mov     rcx, [rcx]
0x14000971c  test    rcx, rcx
0x14000971f  jnz     short loc_140009707
0x140009721  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140009727  test    eax, eax
0x140009729  jnz     loc_140009CA6
0x14000972f  cmp     cs:byte_14011D730, al
0x140009735  jnz     loc_140009CA6
0x14000973b  cmp     dword ptr [rsi+0C98h], 0
0x140009742  mov     [rsp+0C8h+var_28], rbp
0x14000974a  mov     [rsp+0C8h+var_30], r12
0x140009752  mov     [rsp+0C8h+var_38], r13
0x14000975a  mov     [rsp+0C8h+var_40], r14
0x140009762  jz      loc_1400097EE
0x140009768  mov     r12, rdi
0x14000976b  test    rdx, rdx
0x14000976e  jz      short loc_1400097EB
0x140009770  mov     r15, rdi
0x140009773  mov     rbp, [rbx]
0x140009776  mov     [rbx], rdi
0x140009779  mov     rax, cs:PoolHandle
0x140009780  cmp     [rbx+20h], rax
0x140009784  jnz     loc_140009E13
0x14000978a  lock dec dword ptr [rsi+0C98h]
0x140009791  mov     rax, [rbx+8]
0x140009795  mov     r14, [rbx+68h]
0x140009799  mov     r13, [rax+8]
0x14000979d  test    byte ptr [r13+0Ah], 20h
0x1400097a2  jnz     loc_140009DFB
0x1400097a8  test    r14, r14
0x1400097ab  jz      loc_140009CE5
0x1400097b1  mov     rdx, r13; Entry
0x1400097b4  mov     rcx, r14; Lookaside
0x1400097b7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400097be  nop     dword ptr [rax+rax+00h]
0x1400097c3  mov     rcx, rbx; NetBufferList
0x1400097c6  call    NdisFreeNetBufferList
0x1400097cb  mov     rbx, rbp
0x1400097ce  test    rbp, rbp
0x1400097d1  jnz     short loc_140009773
0x1400097d3  mov     r15d, [rsp+0C8h+arg_0]
0x1400097db  mov     r9, [rsp+0C8h+arg_18]
0x1400097e3  mov     r8d, [rsp+0C8h+arg_10]
0x1400097eb  mov     rbx, r12
0x1400097ee  test    rbx, rbx
0x1400097f1  jz      loc_1400099A2
0x1400097f7  mov     ebp, r8d
0x1400097fa  mov     byte ptr [rsp+0C8h+arg_0], 2
0x140009802  and     ebp, 1
0x140009805  mov     r13d, 0FFFFFFFFh
0x14000980b  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140009812  jz      short loc_14000983D
0x140009814  mov     r8, [rsi+9E8h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000981b  test    r9, r9
0x14000981e  jz      loc_140009CDD
0x140009824  mov     rdx, [r9+248h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000982b  mov     r9d, 87h; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x140009831  mov     dword ptr [rsp+0C8h+Context], ebp; unsigned int
0x140009835  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x140009838  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14000983d  and     r15d, 20h
0x140009841  mov     [rsp+0C8h+var_80], r15d
0x140009846  jnz     loc_140009C55
0x14000984c  mov     r14, [rsi+9F0h]
0x140009853  mov     r15, [rsi+0A50h]
0x14000985a  mov     r12, [rsi+9E0h]
0x140009861  cmp     byte ptr [r14], 11h
0x140009865  jz      loc_140009923
0x14000986b  test    ebp, ebp
0x14000986d  jnz     loc_1400099D0
0x140009873  call    cs:__imp_KeGetCurrentIrql
0x14000987a  nop     dword ptr [rax+rax+00h]
0x14000987f  cmp     al, 2
0x140009881  jz      loc_1400099D0
0x140009887  cmp     byte ptr [rsi], 5
0x14000988a  jnz     loc_140009923
0x140009890  mov     eax, cs:Size
0x140009896  lea     rbp, [rsp+0C8h]
0x14000989e  mov     [rsp+0C8h+arg_8], eax
0x1400098a5  mov     [rsp+0C8h+LowLimit], rdi
0x1400098aa  mov     [rsp+0C8h+HighLimit], rdi
0x1400098af  mov     eax, gs:1A4h
0x1400098b7  shl     eax, 0Ch
0x1400098ba  mov     ecx, eax
0x1400098bc  mov     rax, cs:qword_14011CF78
0x1400098c3  mov     rdx, [rax+rcx]
0x1400098c7  mov     rax, cs:qword_14011CF70
0x1400098ce  mov     [rsp+0C8h+LowLimit], rdx
0x1400098d3  mov     r8, [rax+rcx]
0x1400098d7  mov     [rsp+0C8h+HighLimit], r8
0x1400098dc  cmp     rbp, r8
0x1400098df  jb      loc_140009CCF
0x1400098e5  lea     rdx, [rsp+0C8h+HighLimit]; HighLimit
0x1400098ea  lea     rcx, [rsp+0C8h+LowLimit]; LowLimit
0x1400098ef  call    cs:__imp_IoGetStackLimits
0x1400098f6  nop     dword ptr [rax+rax+00h]
0x1400098fb  mov     rdx, [rsp+0C8h+LowLimit]
0x140009900  mov     eax, [rsp+0C8h+arg_8]
0x140009907  sub     rbp, rdx
0x14000990a  cmp     rbp, rax
0x14000990d  jb      loc_140009AB0
0x140009913  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x14000991a  test    rax, rax
0x14000991d  jnz     loc_140009DBD
0x140009923  mov     r8d, [rsp+0C8h+arg_10]
0x14000992b  mov     rdx, rbx
0x14000992e  mov     rcx, r12
0x140009931  mov     rax, r15
0x140009934  call    _guard_dispatch_icall
0x140009939  cmp     [rsp+0C8h+var_80], 0
0x14000993e  jz      short loc_1400099A2
0x140009940  cmp     r13d, 0FFFFFFFFh
0x140009944  jnz     short loc_14000994F
0x140009946  mov     r13d, gs:1A4h
0x14000994f  imul    r13d, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140009957  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x14000995e  mov     eax, r13d
0x140009961  add     rax, [rsp+0C8h+var_98]
0x140009966  add     r8, rax
0x140009969  rdtsc
0x14000996b  shl     rdx, 20h
0x14000996f  or      rax, rdx
0x140009972  sub     rax, [r8+158h]
0x140009979  add     [r8+90h], rax
0x140009980  movzx   eax, byte ptr [rsp+0C8h+arg_0]
0x140009988  mov     [r8+158h], rdi
0x14000998f  cmp     al, 2
0x140009991  jz      short loc_1400099A2
0x140009993  movzx   ecx, al; NewIrql
0x140009996  call    cs:__imp_KeLowerIrql
0x14000999d  nop     dword ptr [rax+rax+00h]
0x1400099a2  mov     r14, [rsp+0C8h+var_40]
0x1400099aa  mov     r13, [rsp+0C8h+var_38]
0x1400099b2  mov     r12, [rsp+0C8h+var_30]
0x1400099ba  mov     rbp, [rsp+0C8h+var_28]
0x1400099c2  add     rsp, 0A8h
0x1400099c9  pop     r15
0x1400099cb  pop     rdi
0x1400099cc  pop     rsi
0x1400099cd  pop     rbx
0x1400099ce  retn
0x1400099d0  mov     eax, gs:1A4h
0x1400099d8  lea     rsi, [rsp+0C8h+Parameter]
0x1400099dd  mov     r8d, [rsp+0C8h+arg_10]
0x1400099e5  mov     [rsp+0C8h+arg_8], eax
0x1400099ec  mov     [rsp+0C8h+var_68], rdi
0x1400099f1  mov     [rsp+0C8h+Parameter], rbx
0x1400099f6  mov     [rsp+0C8h+var_70], rbx
0x1400099fb  mov     [rbx+70h], rdi
0x1400099ff  mov     [rbx+84h], r8d
0x140009a06  cmp     byte ptr [r14], 5
0x140009a0a  jnz     loc_140009BD4
0x140009a10  mov     rdx, [rsi]
0x140009a13  test    rdx, rdx
0x140009a16  jz      loc_140009BD4
0x140009a1c  lea     rbp, [rax+rax*2]
0x140009a20  shl     rbp, 5
0x140009a24  add     rbp, [r14+1A8h]
0x140009a2b  cmp     byte ptr [rbp+58h], 0
0x140009a2f  jnz     loc_140009B91
0x140009a35  mov     byte ptr [rbp+58h], 1
0x140009a39  mov     rax, r14
0x140009a3c  mov     rdx, [rsi]
0x140009a3f  mov     [rsi], rdi
0x140009a42  test    rdx, rdx
0x140009a45  jz      short loc_140009A87
0x140009a47  nop     word ptr [rax+rax+00000000h]
0x140009a50  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140009a57  mov     r8d, [rdx+84h]
0x140009a5e  mov     rbx, [rdx+70h]
0x140009a62  mov     [rdx+84h], edi
0x140009a68  test    rax, rax
0x140009a6b  jnz     loc_140009D24
0x140009a71  mov     rcx, r12
0x140009a74  mov     rax, r15
0x140009a77  call    _guard_dispatch_icall
0x140009a7c  mov     rdx, rbx
0x140009a7f  test    rbx, rbx
0x140009a82  jnz     short loc_140009A50
0x140009a84  mov     rax, r14
0x140009a87  mov     byte ptr [rbp+58h], 0
0x140009a8b  lea     rsi, [rbp+48h]
0x140009a8f  mov     r15, [rax+210h]
0x140009a96  mov     r12, [rax+218h]
0x140009a9d  mov     eax, [rsp+0C8h+arg_8]
0x140009aa4  mov     r14, [r14+228h]
0x140009aab  jmp     loc_140009A06
0x140009ab0  mov     eax, cs:Size
0x140009ab6  mov     ecx, 6000h
0x140009abb  mov     r8d, [rsp+0C8h+arg_10]
0x140009ac3  mov     [rsp+0C8h+var_4C], edi
0x140009ac7  mov     [rsp+0C8h+Parameter], r14
0x140009acc  mov     [rsp+0C8h+var_70], r12
0x140009ad1  mov     [rsp+0C8h+var_68], r15
0x140009ad6  mov     [rsp+0C8h+var_60], rbx
0x140009adb  mov     [rsp+0C8h+var_58], 0
0x140009ae4  mov     [rsp+0C8h+var_50], r8d
0x140009ae9  cmp     eax, ecx
0x140009aeb  ja      loc_140009E24
0x140009af1  movsxd  r8, ecx; Size
0x140009af4  lea     rdx, [rsp+0C8h+Parameter]; Parameter
0x140009af9  lea     rcx, ??$ndisDataPathExpandStackCallback@$02$$A6AXPEAXPEAU_NET_BUFFER_LIST@@K@Z@@YAXPEAX@Z; Callout
0x140009b00  mov     [rsp+0C8h+Context], rdi; Context
0x140009b05  xor     r9d, r9d; Wait
0x140009b08  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140009b0f  nop     dword ptr [rax+rax+00h]
0x140009b14  test    eax, eax
0x140009b16  jns     loc_140009939
0x140009b1c  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140009b23  jnz     loc_140009E2F
0x140009b29  lea     rcx, [rsi+90h]; SpinLock
0x140009b30  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009b37  nop     dword ptr [rax+rax+00h]
0x140009b3c  mov     rcx, gs:188h
0x140009b45  movzx   r14d, al
0x140009b49  mov     [rsi+98h], rcx
0x140009b50  lea     rcx, [rsi+118h]
0x140009b57  mov     rdx, [rcx]
0x140009b5a  test    rdx, rdx
0x140009b5d  jnz     loc_140009E53
0x140009b63  mov     [rcx], rbx
0x140009b66  mov     rcx, rsi; struct _NDIS_FILTER_BLOCK *
0x140009b69  call    ?ndisQueueStackExpansionFallbackWorkItem@@YAXPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQueueStackExpansionFallbackWorkItem(_NDIS_FILTER_BLOCK *)
0x140009b6e  movzx   edx, r14b; NewIrql
0x140009b72  mov     [rsi+98h], rdi
0x140009b79  lea     rcx, [rsi+90h]; SpinLock
0x140009b80  call    cs:__imp_KeReleaseSpinLock
0x140009b87  nop     dword ptr [rax+rax+00h]
0x140009b8c  jmp     loc_140009939
0x140009b91  mov     [rsi], rdi
0x140009b94  nop     dword ptr [rax+00h]
0x140009b98  nop     dword ptr [rax+rax+00000000h]
0x140009ba0  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140009ba7  mov     r8d, [rdx+84h]
0x140009bae  mov     rbx, [rdx+70h]
0x140009bb2  mov     [rdx+84h], edi
0x140009bb8  test    rax, rax
0x140009bbb  jnz     loc_140009D8A
0x140009bc1  mov     rcx, r12
0x140009bc4  mov     rax, r15
0x140009bc7  call    _guard_dispatch_icall
0x140009bcc  mov     rdx, rbx
0x140009bcf  test    rbx, rbx
0x140009bd2  jnz     short loc_140009BA0
0x140009bd4  mov     rdx, [rsi]
0x140009bd7  test    rdx, rdx
0x140009bda  jz      loc_140009939
0x140009be0  mov     [rsi], rdi
0x140009be3  nop     dword ptr [rax+00h]
0x140009be7  nop     word ptr [rax+rax+00000000h]
0x140009bf0  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140009bf7  mov     r8d, [rdx+84h]
0x140009bfe  mov     rbx, [rdx+70h]
0x140009c02  mov     [rdx+84h], edi
0x140009c08  test    rax, rax
0x140009c0b  jnz     loc_140009D57
0x140009c11  mov     rcx, r12
0x140009c14  mov     rax, r15
0x140009c17  call    _guard_dispatch_icall
0x140009c1c  mov     rdx, rbx
0x140009c1f  test    rbx, rbx
0x140009c22  jnz     short loc_140009BF0
0x140009c24  jmp     loc_140009939
0x140009c29  mov     rax, [rcx+28h]
0x140009c2d  mov     r15d, [rcx+50h]
0x140009c31  mov     [rsp+0C8h+arg_0], r15d
0x140009c39  mov     [rsp+0C8h+var_98], rax
0x140009c3e  test    rax, rax
0x140009c41  jnz     loc_1400096FF
0x140009c47  mov     rax, [rcx+28h]
0x140009c4b  mov     [rsp+0C8h+var_98], rax
0x140009c50  jmp     loc_1400096FF
0x140009c55  test    ebp, ebp
0x140009c57  jnz     short loc_140009C6E
0x140009c59  mov     cl, 2; NewIrql
0x140009c5b  call    cs:__imp_KfRaiseIrql
  ... truncated ...
```
