# ndisQueueOidRequest(_NDIS_OID_REQUEST *,_NDIS_MINIPORT_BLOCK *,_NDIS_FILTER_BLOCK *,_NDIS_FILTER_BLOCK *)

- ea: `0x14001b6a0`
- end: `0x14001bfa2`
- name: `?ndisQueueOidRequest@@YAHPEAU_NDIS_OID_REQUEST@@PEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_FILTER_BLOCK@@2@Z`
- size: `2306`
- prototype: `__int64 __fastcall(struct _NDIS_OID_REQUEST *, struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_FILTER_BLOCK *, struct _NDIS_FILTER_BLOCK *)`
- caller_count: `5`
- callee_count: `23`
- tags: `loader_planting`

## callers

- `0x14001b000`
- `0x14001b340`
- `0x140035bb0`
- `0x14003c960`
- `0x1400bc270`

## callees

- `0x1400161d0`
- `0x140017780`
- `0x14001b6a0`
- `0x14001cc80`
- `0x14001e4b0`
- `0x1400208f0`
- `0x140020ce0`
- `0x1400230c0`
- `0x140025b00`
- `0x140025bc0`
- `0x140025c30`
- `0x140026220`
- `0x14003b510`
- `0x14003c460`
- `0x14003c930`
- `0x14004a560`
- `0x14004a830`
- `0x14004c090`
- `0x140083a40`
- `0x1400e1a70`
- `0x1400e2030`
- `0x1400e6160`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14001bb91`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001bb91`
- `ntoskrnl!PsIsSystemThread` at `0x14001bbae`
- `ntoskrnl!PsIsSystemThread` at `0x14001bbae`
- `ntoskrnl!EtwActivityIdControl` at `0x14001b7a3`
- `ntoskrnl!EtwActivityIdControl` at `0x14001b859`
- `ntoskrnl!EtwActivityIdControl` at `0x14001b7a3`
- `ntoskrnl!EtwActivityIdControl` at `0x14001b859`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001baa5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001baa5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b93c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bac9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bb1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bb56`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bb75`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bbf9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bd21`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001be06`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001be5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bed2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b93c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bac9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bb1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bb56`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bb75`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bbf9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bd21`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001be06`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001be5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bed2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b8af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b8f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b96b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001baec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001bbd5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001bc08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001be95`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b8af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b8f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b96b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001baec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001bbd5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001bc08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001be95`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001bd01`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001bde6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001be3c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001bd01`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001bde6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001be3c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001bc32`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001bc32`

## pseudocode

```c
__int64 __fastcall ndisQueueOidRequest(
        struct _NDIS_OID_REQUEST *a1,
        struct _NDIS_MINIPORT_BLOCK *a2,
        struct _NDIS_FILTER_BLOCK *a3,
        struct _NDIS_FILTER_BLOCK *a4)
{
  struct _NDIS_MINIPORT_BLOCK *v5; // r15
  char v7; // bl
  struct _NDIS_FILTER_BLOCK *v9; // r14
  NDIS_OID Oid; // ecx
  KSPIN_LOCK *p_Lock; // r12
  struct _NDIS_FILTER_BLOCK *NextRequestHandle; // rdi
  KIRQL v13; // al
  _REFERENCE_EX *p_PnPRef; // rbx
  __int64 v15; // rdx
  KIRQL v16; // r12
  unsigned __int16 ReferenceCount; // cx
  KIRQL v18; // al
  NDIS_REFCOUNT_HANDLE__ *RefCountTracker; // r8
  NDIS_REFCOUNT_HANDLE__ *v20; // rsi
  unsigned int v21; // edx
  bool v22; // zf
  ULONG_PTR v23; // rsi
  unsigned int AnyActiveRefTag; // eax
  __int64 v25; // r10
  unsigned __int8 v26; // r9
  unsigned __int8 v27; // cl
  _BYTE *v28; // rdx
  char v29; // al
  struct _NDIS_REFCOUNT_BLOCK *v30; // rax
  struct _NDIS_REFCOUNT_BLOCK *v31; // rsi
  __int64 v32; // rdx
  KIRQL v33; // si
  unsigned __int16 v34; // ax
  NDIS_REFCOUNT_HANDLE__ *v35; // rcx
  KSPIN_LOCK *p_SpinLock; // rsi
  KIRQL v37; // al
  NDIS_REFCOUNT_HANDLE__ *v38; // rcx
  __int64 v39; // rdx
  KIRQL v40; // bl
  KIRQL v41; // bl
  UCHAR *NdisReserved; // rdi
  _LIST_ENTRY *p_OidRequestList; // rbx
  UCHAR *Flink; // rax
  int v45; // eax
  unsigned int v46; // edi
  char v47; // cl
  unsigned int v48; // eax
  unsigned __int64 i; // rax
  int v50; // ecx
  UCHAR **Blink; // rax
  KIRQL v52; // al
  KIRQL v53; // bl
  unsigned int v54; // eax
  KIRQL v56; // [rsp+40h] [rbp-C0h]
  KIRQL v57; // [rsp+40h] [rbp-C0h]
  int v58; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v59[248]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = a2;
  v7 = 0;
  memset(v59, 0, sizeof(v59));
  v9 = 0;
  Oid = a1->DATA.QUERY_INFORMATION.Oid;
  v58 = 0;
  if ( Oid != 66055 )
  {
    if ( Oid == 65798 || Oid == 65799 || Oid == 65812 || (*(_DWORD *)&a1->NdisReserved[16] & 0x100000) != 0 )
    {
      v7 = 1;
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_Dq(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          (int)a2,
          (int)a3,
          203,
          (struct _GUID *)&WPP_67e470a56b3938b4276b23606b3190b8_Traceguids,
          Oid,
          (char)a1);
      }
    }
LABEL_8:
    p_Lock = &v5->Lock;
    if ( v7 )
    {
      NextRequestHandle = (struct _NDIS_FILTER_BLOCK *)v5;
      goto LABEL_59;
    }
    goto LABEL_12;
  }
  if ( a2->MajorNdisVersion >= 6u )
    goto LABEL_8;
  memset(v59, 0, sizeof(v59));
  *(_DWORD *)&v59[88] = 8;
  *(_QWORD *)&v59[104] = &ndisIntReqNsi;
  EtwActivityIdControl(3u, (LPGUID)&v59[168]);
  *(_DWORD *)v59 = 15466902;
  *(_DWORD *)&v59[32] = 65799;
  *(_QWORD *)&v59[4] = 2;
  *(_QWORD *)&v59[40] = &v58;
  *(_DWORD *)&v59[48] = 4;
  ndisQuerySetMiniport(v5, 0, (struct _NDIS_OID_REQUEST *)v59, 0, 0);
  *(_QWORD *)&v59[104] = &ndisIntReqNsi;
  memset(&v59[112], 0, 136);
  memset(v59, 0, 104);
  *(_DWORD *)&v59[88] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) | 8;
  EtwActivityIdControl(3u, (LPGUID)&v59[168]);
  *(_DWORD *)v59 = 15466902;
  *(_DWORD *)&v59[32] = 65812;
  *(_QWORD *)&v59[4] = 2;
  *(_QWORD *)&v59[40] = &v58;
  *(_DWORD *)&v59[48] = 4;
  ndisQuerySetMiniport(v5, 0, (struct _NDIS_OID_REQUEST *)v59, 0, 0);
  p_Lock = &v5->Lock;
LABEL_12:
  v13 = KeAcquireSpinLockRaiseToDpc(p_Lock);
  v5->MiniportThread = KeGetCurrentThread();
  v56 = v13;
  if ( a3 )
    NextRequestHandle = (struct _NDIS_FILTER_BLOCK *)a3->NextRequestHandle;
  else
    NextRequestHandle = (struct _NDIS_FILTER_BLOCK *)v5->Next.RequestHandle;
  if ( a4 )
  {
    p_PnPRef = &a4->PnPRef;
    v16 = KeAcquireSpinLockRaiseToDpc(&a4->PnPRef.SpinLock);
    if ( !a4->PnPRef.Closing )
    {
      ReferenceCount = a4->PnPRef.ReferenceCount;
      if ( ReferenceCount >= 0xFFEBu )
      {
        ndisRefCountReferenceCountOverflow = 1;
      }
      else
      {
        LOBYTE(v15) = 17;
        a4->PnPRef.ReferenceCount = ReferenceCount + 1;
        NdisReferenceWithTag(a4->PnPRef.RefCountTracker, v15);
        KeReleaseSpinLock(&a4->PnPRef.SpinLock, v16);
        if ( a4->FilterDriver->DefaultFilterCharacteristics.OidRequestHandler )
        {
          NextRequestHandle = a4;
        }
        else if ( a4->NextRequestHandle )
        {
          NextRequestHandle = (struct _NDIS_FILTER_BLOCK *)a4->NextRequestHandle;
        }
        v18 = KeAcquireSpinLockRaiseToDpc(&a4->PnPRef.SpinLock);
        RefCountTracker = a4->PnPRef.RefCountTracker;
        v16 = v18;
        if ( (unsigned __int64)RefCountTracker - 2 > 1 )
        {
          if ( (unsigned __int64)RefCountTracker < 2 )
            ndisBugCheckEx(0x1Eu, 3u, (ULONG_PTR)RefCountTracker, 0);
          if ( *((_BYTE *)RefCountTracker + 2) <= 0x11u )
            ndisBugCheckEx(0x1Eu, 2u, (ULONG_PTR)RefCountTracker, 0x11u);
          if ( *((_BYTE *)RefCountTracker + 1) )
          {
            if ( *((_BYTE *)RefCountTracker + 1) == 1 )
            {
              v20 = RefCountTracker + 274;
              v21 = *((_DWORD *)RefCountTracker + 288);
              if ( v21 >> 17 < 0x3FFE && (unsigned __int16)v21 >> 1 == (v21 >> 17) + 1 )
              {
                ndisFreeRefCountStackChain((struct _NDIS_REFCOUNT_STACK_BLOCK *)(RefCountTracker + 274));
                *((_DWORD *)v20 + 14) &= 0x10001u;
              }
              else
              {
                if ( !((unsigned __int16)v21 >> 1) && (v21 & 1) == 0 )
                  ndisReportRefcountImbalance((ULONG_PTR)p_PnPRef->RefCountTracker, 0x11u);
                ndisReferenceWithTagStackTrace((struct _NDIS_REFCOUNT_WITH_STACK *)(RefCountTracker + 274), 0);
              }
            }
          }
          else
          {
            v25 = *((_QWORD *)RefCountTracker + 1);
            if ( v25 && (v26 = *((_BYTE *)RefCountTracker + 3), v27 = 0, v26) )
            {
              while ( 1 )
              {
                v28 = (_BYTE *)(v25 + 2LL * v27);
                if ( *v28 == 17 )
                {
                  v29 = v28[1];
                  if ( v29 )
                    break;
                }
                if ( ++v27 >= v26 )
                  goto LABEL_43;
              }
              v28[1] = v29 - 1;
            }
            else
            {
LABEL_43:
              if ( !_bittestandreset((signed __int32 *)RefCountTracker + 4, 0x11u) )
                ndisReportRefcountImbalance((ULONG_PTR)RefCountTracker, 0x11u);
            }
          }
        }
        v22 = p_PnPRef->ReferenceCount-- == 1;
        if ( v22 && !p_PnPRef->ZeroBased )
        {
          v23 = (ULONG_PTR)p_PnPRef->RefCountTracker;
          if ( v23 )
          {
            AnyActiveRefTag = ndisGetAnyActiveRefTag(p_PnPRef->RefCountTracker);
            if ( AnyActiveRefTag != -2 )
              ndisBugCheckEx(0x1Eu, 4u, v23, AnyActiveRefTag);
            v30 = ndisRefCountBlockFromRefCountHandle(v23);
            v31 = v30;
            if ( v30 )
            {
              ndisFreeRefCountAuxiliaryMemory(v30);
              ExFreePoolWithTag(v31, 0);
            }
          }
          p_PnPRef->RefCountTracker = (NDIS_REFCOUNT_HANDLE__ *)1;
        }
      }
    }
    KeReleaseSpinLock(&p_PnPRef->SpinLock, v16);
    p_Lock = &v5->Lock;
  }
  if ( NextRequestHandle->Header.Type != 5 )
    goto LABEL_58;
  while ( 1 )
  {
    v33 = KeAcquireSpinLockRaiseToDpc(&NextRequestHandle->PnPRef.SpinLock);
    if ( !NextRequestHandle->PnPRef.Closing )
      break;
LABEL_55:
    KeReleaseSpinLock(&NextRequestHandle->PnPRef.SpinLock, v33);
    NextRequestHandle = (struct _NDIS_FILTER_BLOCK *)NextRequestHandle->NextRequestHandle;
    v9 = 0;
    if ( NextRequestHandle->Header.Type != 5 )
      goto LABEL_58;
  }
  v34 = NextRequestHandle->PnPRef.ReferenceCount;
  if ( v34 >= 0xFFEBu )
  {
    ndisRefCountReferenceCountOverflow = 1;
    goto LABEL_55;
  }
  v35 = NextRequestHandle->PnPRef.RefCountTracker;
  LOBYTE(v32) = 15;
  NextRequestHandle->PnPRef.ReferenceCount = v34 + 1;
  v9 = NextRequestHandle;
  NdisReferenceWithTag(v35, v32);
  KeReleaseSpinLock(&NextRequestHandle->PnPRef.SpinLock, v33);
LABEL_58:
  v5->MiniportThread = 0;
  KeReleaseSpinLock(p_Lock, v56);
LABEL_59:
  if ( NextRequestHandle->Header.Type == 17 )
    ndisOidTranslateBetweenOids(v5, (unsigned __int8)a2, a1);
  if ( KeGetCurrentIrql() || !PsIsSystemThread(KeGetCurrentThread()) )
  {
    v46 = ndisQueueRequestWorkItem((struct _NDIS_MINIPORT_BLOCK *)NextRequestHandle, a1, NextRequestHandle->Header.Type);
    goto LABEL_99;
  }
  if ( !v9 )
  {
    if ( !ndisReferenceMiniport(v5, MPREF_OID_QUEUEING) )
      return (unsigned int)-1073741823;
    v52 = KeAcquireSpinLockRaiseToDpc(p_Lock);
    v5->MiniportThread = KeGetCurrentThread();
    v53 = v52;
    v54 = ndisMQueueOidRequest(v5, a1);
    v5->MiniportThread = 0;
    v46 = v54;
    KeReleaseSpinLock(p_Lock, v53);
    if ( !v46 )
    {
      ndisMDoOidRequest(v5);
      v46 = 259;
    }
    ndisDereferenceMiniport(v5, MPREF_OID_QUEUEING);
LABEL_99:
    p_SpinLock = &v9->PnPRef.SpinLock;
    goto LABEL_100;
  }
  p_SpinLock = &v9->PnPRef.SpinLock;
  v37 = KeAcquireSpinLockRaiseToDpc(&v9->PnPRef.SpinLock);
  v38 = v9->PnPRef.RefCountTracker;
  LOBYTE(v39) = 13;
  ++v9->PnPRef.ReferenceCount;
  v40 = v37;
  NdisReferenceWithTag(v38, v39);
  KeReleaseSpinLock(&v9->PnPRef.SpinLock, v40);
  v41 = KeAcquireSpinLockRaiseToDpc(p_Lock);
  v57 = v41;
  v5->MiniportThread = KeGetCurrentThread();
  KeAcquireSpinLockAtDpcLevel(&v9->Lock);
  NdisReserved = a1->NdisReserved;
  v9->LockThread = KeGetCurrentThread();
  *(_QWORD *)a1->NdisReserved = 0;
  *(_QWORD *)&a1->NdisReserved[8] = 0;
  if ( (v9->Miniport->PnPFlags & 0x100) != 0 )
  {
    v9->LockThread = 0;
    KeReleaseSpinLockFromDpcLevel(&v9->Lock);
    v5->MiniportThread = 0;
    KeReleaseSpinLock(&v5->Lock, v41);
    v46 = -1073741823;
    ndisDereferenceRef(&v9->PnPRef.SpinLock, 0xDu);
    goto LABEL_100;
  }
  p_OidRequestList = &v9->OidRequestList;
  Flink = (UCHAR *)v9->OidRequestList.Flink;
  if ( Flink == (UCHAR *)&v9->OidRequestList )
  {
LABEL_68:
    if ( (unsigned int)dword_14011A6C0 <= 4 )
      goto LABEL_89;
    if ( (qword_14011A6D0 & 0x400) == 0 )
      goto LABEL_89;
    if ( (qword_14011A6D8 & 0x400) != qword_14011A6D8 )
      goto LABEL_89;
    v45 = *(_DWORD *)&a1->NdisReserved[16] & 0x30000000;
    if ( v45 == 0x10000000 )
      goto LABEL_89;
    if ( v45 )
    {
      if ( v45 != 0x20000000 )
      {
LABEL_89:
        Blink = (UCHAR **)v9->OidRequestList.Blink;
        if ( *Blink != (UCHAR *)p_OidRequestList )
          __fastfail(3u);
        *(_QWORD *)NdisReserved = p_OidRequestList;
        *(_QWORD *)&a1->NdisReserved[8] = Blink;
        *Blink = NdisReserved;
        v9->OidRequestList.Blink = (_LIST_ENTRY *)NdisReserved;
        v9->LockThread = 0;
        KeReleaseSpinLockFromDpcLevel(&v9->Lock);
        v5->MiniportThread = 0;
        KeReleaseSpinLock(&v5->Lock, v57);
        ndisFDoOidRequest(v9);
        v46 = 259;
        ndisDereferenceRef(&v9->PnPRef.SpinLock, 0xDu);
        goto LABEL_100;
      }
    }
    else
    {
      if ( (ndisAzOidTelemetryFilter & 1) != 0 && Ndis::BindEngine::s_NumBindOperationsInProgress )
      {
LABEL_78:
        v47 = 1;
        v48 = *(_DWORD *)&a1->NdisReserved[16] & 0xCFFFFFFF | 0x20000000;
      }
      else
      {
        if ( (ndisAzOidTelemetryFilter & 2) != 0 )
        {
          for ( i = 0; i < 0x10; ++i )
          {
            v50 = *((_DWORD *)&ndisAzOidTelemetryList + i);
            if ( !v50 )
              break;
            if ( v50 == a1->DATA.QUERY_INFORMATION.Oid )
              goto LABEL_78;
          }
        }
        v47 = 0;
        v48 = *(_DWORD *)&a1->NdisReserved[16] & 0xCFFFFFFF | 0x10000000;
      }
      *(_DWORD *)&a1->NdisReserved[16] = v48;
      if ( !v47 )
        goto LABEL_89;
    }
    if ( *(_QWORD *)&a1->NdisReserved[24] )
      TraceLoggingWriteOidRequestQueuedActivity<0,_NDIS_FILTER_BLOCK>(v9, a1);
    else
      TraceLoggingWriteOidRequestQueuedActivity<1,_NDIS_FILTER_BLOCK>(v9, a1);
    goto LABEL_89;
  }
  while ( Flink != NdisReserved )
  {
    Flink = *(UCHAR **)Flink;
    if ( Flink == (UCHAR *)p_OidRequestList )
      goto LABEL_68;
  }
  v9->LockThread = 0;
  v46 = -1073741823;
  KeReleaseSpinLockFromDpcLevel(&v9->Lock);
  v5->MiniportThread = 0;
  KeReleaseSpinLock(&v5->Lock, v57);
  ndisDereferenceRef(&v9->PnPRef.SpinLock, 0xDu);
LABEL_100:
  if ( v46 != 259 && v9 )
    ndisDereferenceRef(p_SpinLock, 0xFu);
  return v46;
}

```

## disassembly

```asm
0x14001b6a0  push    rbp
0x14001b6a2  push    rbx
0x14001b6a3  push    rsi
0x14001b6a4  push    rdi
0x14001b6a5  push    r12
0x14001b6a7  push    r13
0x14001b6a9  push    r14
0x14001b6ab  push    r15
0x14001b6ad  lea     rbp, [rsp-68h]
0x14001b6b2  sub     rsp, 168h
0x14001b6b9  mov     rax, cs:__security_cookie
0x14001b6c0  xor     rax, rsp
0x14001b6c3  mov     [rbp+0A0h+var_50], rax
0x14001b6c7  mov     rdi, r8
0x14001b6ca  mov     r15, rdx
0x14001b6cd  mov     r13, rcx
0x14001b6d0  xor     bl, bl
0x14001b6d2  xor     edx, edx; Val
0x14001b6d4  mov     [rsp+1A0h+var_150.Header.Type], bl
0x14001b6d8  mov     r8d, 0F7h; Size
0x14001b6de  lea     rcx, [rsp+1A0h+var_150.Header.Revision]; void *
0x14001b6e3  mov     rsi, r9
0x14001b6e6  xor     r14d, r14d
0x14001b6e9  call    memset
0x14001b6ee  mov     ecx, [r13+20h]
0x14001b6f2  mov     [rsp+1A0h+var_158], r14d
0x14001b6f7  cmp     ecx, 10207h
0x14001b6fd  jz      short loc_14001B76F
0x14001b6ff  mov     eax, ecx
0x14001b701  sub     eax, 10106h
0x14001b706  jz      short loc_14001B71C
0x14001b708  sub     eax, 1
0x14001b70b  jz      short loc_14001B71C
0x14001b70d  cmp     eax, 0Dh
0x14001b710  jz      short loc_14001B71C
0x14001b712  test    dword ptr [r13+58h], 100000h
0x14001b71a  jz      short loc_14001B75B
0x14001b71c  mov     bl, 1
0x14001b71e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b725  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b72c  jz      short loc_14001B75B
0x14001b72e  mov     qword ptr [rsp+1A0h+var_170], r13; char
0x14001b733  lea     rax, WPP_67e470a56b3938b4276b23606b3190b8_Traceguids
0x14001b73a  mov     dword ptr [rsp+1A0h+var_178], ecx; char
0x14001b73e  mov     r9d, 0CBh; int
0x14001b744  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b74b  mov     dl, 4; int
0x14001b74d  mov     [rsp+1A0h+var_180], rax; struct _GUID *
0x14001b752  mov     rcx, [rcx+40h]; int
0x14001b756  call    WPP_RECORDER_SF_Dq
0x14001b75b  lea     r12, [r15+60h]
0x14001b75f  test    bl, bl
0x14001b761  jz      loc_14001B8AC
0x14001b767  mov     rdi, r15
0x14001b76a  jmp     loc_14001BB81
0x14001b76f  cmp     byte ptr [r15+20h], 6
0x14001b774  jnb     short loc_14001B75B
0x14001b776  xor     edx, edx; Val
0x14001b778  lea     rcx, [rsp+1A0h+var_150]; void *
0x14001b77d  mov     r8d, 0F8h; Size
0x14001b783  call    memset
0x14001b788  lea     rbx, ?ndisIntReqNsi@@3U_NDIS_INTERNAL_REQUEST_OBJECT@@A; _NDIS_INTERNAL_REQUEST_OBJECT ndisIntReqNsi
0x14001b78f  mov     dword ptr [rbp+0A0h+var_150.NdisReserved+10h], 8
0x14001b796  lea     rdx, [rbp+0A0h+var_150.NdisReserved+60h]; ActivityId
0x14001b79a  mov     qword ptr [rbp+0A0h+var_150.NdisReserved+20h], rbx
0x14001b79e  mov     ecx, 3; ControlCode
0x14001b7a3  call    cs:__imp_EtwActivityIdControl
0x14001b7aa  nop     dword ptr [rax+rax+00h]
0x14001b7af  xor     ecx, ecx
0x14001b7b1  mov     dword ptr [rsp+1A0h+var_150.Header.Type], 0EC0196h
0x14001b7b9  mov     [rsp+1A0h+var_180], rcx; struct _NDIS_FILTER_BLOCK *
0x14001b7be  lea     rax, [rsp+1A0h+var_158]
0x14001b7c3  mov     rcx, r15; struct _NDIS_MINIPORT_BLOCK *
0x14001b7c6  mov     dword ptr [rsp+1A0h+var_150.DATA], 10107h
0x14001b7ce  xor     r9d, r9d; unsigned __int8
0x14001b7d1  mov     qword ptr [rsp+1A0h+var_150.RequestType], 2
0x14001b7da  lea     r8, [rsp+1A0h+var_150]; struct _NDIS_OID_REQUEST *
0x14001b7df  mov     qword ptr [rsp+1A0h+var_150.DATA+8], rax
0x14001b7e4  xor     edx, edx; struct _NDIS_CO_VC_PTR_BLOCK *
0x14001b7e6  mov     dword ptr [rbp+0A0h+var_150.DATA+10h], 4
0x14001b7ed  call    ?ndisQuerySetMiniport@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CO_VC_PTR_BLOCK@@PEAU_NDIS_OID_REQUEST@@EPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQuerySetMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_CO_VC_PTR_BLOCK *,_NDIS_OID_REQUEST *,uchar,_NDIS_FILTER_BLOCK *)
0x14001b7f2  xorps   xmm0, xmm0
0x14001b7f5  mov     qword ptr [rbp+0A0h+var_150.NdisReserved+20h], rbx
0x14001b7f9  xorps   xmm1, xmm1
0x14001b7fc  movaps  xmmword ptr [rbp+0A0h+var_150.NdisReserved+28h], xmm0
0x14001b800  xor     eax, eax
0x14001b802  movaps  xmmword ptr [rbp-60h], xmm1
0x14001b806  mov     qword ptr [rbp+0A0h+var_150.NdisReserved+18h], rax
0x14001b80a  lea     rdx, [rbp+0A0h+var_150.NdisReserved+60h]; ActivityId
0x14001b80e  mov     [rbp+0A0h+var_60], rax
0x14001b812  mov     ecx, 3; ControlCode
0x14001b817  movups  xmmword ptr [rsp+1A0h+var_150.Header.Type], xmm1
0x14001b81c  movups  xmmword ptr [rsp+1A0h+var_150.RequestId], xmm1
0x14001b821  movups  xmmword ptr [rsp+1A0h+var_150.DATA], xmm1
0x14001b826  movups  xmmword ptr [rbp+0A0h+var_150.DATA+10h], xmm1
0x14001b82a  movups  xmmword ptr [rbp+0A0h+var_150.DATA+20h], xmm1
0x14001b82e  psrldq  xmm1, 8
0x14001b833  movd    eax, xmm1
0x14001b837  movaps  xmmword ptr [rbp+0A0h+var_150.NdisReserved+38h], xmm0
0x14001b83b  movaps  xmmword ptr [rbp+0A0h+var_150.NdisReserved+48h], xmm0
0x14001b83f  or      eax, 8
0x14001b842  movaps  xmmword ptr [rbp-10h], xmm0
0x14001b846  mov     dword ptr [rbp+0A0h+var_150.NdisReserved+10h], eax
0x14001b849  movaps  xmmword ptr [rbp+0A0h+var_150.NdisReserved+68h], xmm0
0x14001b84d  movaps  xmmword ptr [rbp+0A0h+var_150.NdisReserved+78h], xmm0
0x14001b851  movaps  xmmword ptr [rbp+0A0h+var_150.MiniportReserved+8], xmm0
0x14001b855  movaps  xmmword ptr [rbp+0A0h+var_150.SourceReserved+8], xmm0
0x14001b859  call    cs:__imp_EtwActivityIdControl
0x14001b860  nop     dword ptr [rax+rax+00h]
0x14001b865  xor     ecx, ecx
0x14001b867  mov     dword ptr [rsp+1A0h+var_150.Header.Type], 0EC0196h
0x14001b86f  mov     [rsp+1A0h+var_180], rcx; struct _NDIS_FILTER_BLOCK *
0x14001b874  lea     rax, [rsp+1A0h+var_158]
0x14001b879  mov     rcx, r15; struct _NDIS_MINIPORT_BLOCK *
0x14001b87c  mov     dword ptr [rsp+1A0h+var_150.DATA], 10114h
0x14001b884  xor     r9d, r9d; unsigned __int8
0x14001b887  mov     qword ptr [rsp+1A0h+var_150.RequestType], 2
0x14001b890  lea     r8, [rsp+1A0h+var_150]; struct _NDIS_OID_REQUEST *
0x14001b895  mov     qword ptr [rsp+1A0h+var_150.DATA+8], rax
0x14001b89a  xor     edx, edx; struct _NDIS_CO_VC_PTR_BLOCK *
0x14001b89c  mov     dword ptr [rbp+0A0h+var_150.DATA+10h], 4
0x14001b8a3  call    ?ndisQuerySetMiniport@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CO_VC_PTR_BLOCK@@PEAU_NDIS_OID_REQUEST@@EPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQuerySetMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_CO_VC_PTR_BLOCK *,_NDIS_OID_REQUEST *,uchar,_NDIS_FILTER_BLOCK *)
0x14001b8a8  lea     r12, [r15+60h]
0x14001b8ac  mov     rcx, r12; SpinLock
0x14001b8af  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b8b6  nop     dword ptr [rax+rax+00h]
0x14001b8bb  mov     rcx, gs:188h
0x14001b8c4  mov     [r15+208h], rcx
0x14001b8cb  mov     [rsp+1A0h+var_160], al
0x14001b8cf  test    rdi, rdi
0x14001b8d2  jz      short loc_14001B8DD
0x14001b8d4  mov     rdi, [rdi+1A0h]
0x14001b8db  jmp     short loc_14001B8E4
0x14001b8dd  mov     rdi, [r15+0A28h]
0x14001b8e4  test    rsi, rsi
0x14001b8e7  jz      loc_14001BAD9
0x14001b8ed  lea     rbx, [rsi+138h]
0x14001b8f4  mov     rcx, rbx; SpinLock
0x14001b8f7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b8fe  nop     dword ptr [rax+rax+00h]
0x14001b903  movzx   r12d, al
0x14001b907  cmp     [rbx+0Ah], r14b
0x14001b90b  jnz     loc_14001BAC2
0x14001b911  movzx   ecx, word ptr [rbx+8]
0x14001b915  mov     eax, 0FFEBh
0x14001b91a  cmp     cx, ax
0x14001b91d  jnb     loc_14001BABB
0x14001b923  inc     cx
0x14001b926  mov     dl, 11h
0x14001b928  mov     [rbx+8], cx
0x14001b92c  mov     rcx, [rbx+10h]
0x14001b930  call    NdisReferenceWithTag
0x14001b935  movzx   edx, r12b; NewIrql
0x14001b939  mov     rcx, rbx; SpinLock
0x14001b93c  call    cs:__imp_KeReleaseSpinLock
0x14001b943  nop     dword ptr [rax+rax+00h]
0x14001b948  mov     rax, [rsi+10h]
0x14001b94c  cmp     [rax+0F8h], r14
0x14001b953  jz      short loc_14001B95A
0x14001b955  mov     rdi, rsi
0x14001b958  jmp     short loc_14001B968
0x14001b95a  mov     rax, [rsi+1A0h]
0x14001b961  test    rax, rax
0x14001b964  cmovnz  rdi, rax
0x14001b968  mov     rcx, rbx; SpinLock
0x14001b96b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b972  nop     dword ptr [rax+rax+00h]
0x14001b977  mov     r8, [rbx+10h]; BugCheckParameter3
0x14001b97b  movzx   r12d, al
0x14001b97f  lea     rcx, [r8-2]
0x14001b983  cmp     rcx, 1
0x14001b987  jbe     short loc_14001B9E5
0x14001b989  cmp     r8, 2
0x14001b98d  jb      loc_14001BF4D
0x14001b993  cmp     byte ptr [r8+2], 11h
0x14001b998  jbe     loc_14001BF60
0x14001b99e  movzx   ecx, byte ptr [r8+1]
0x14001b9a3  test    ecx, ecx
0x14001b9a5  jz      loc_14001BA37
0x14001b9ab  cmp     ecx, 1
0x14001b9ae  jnz     short loc_14001B9E5
0x14001b9b0  lea     rsi, [r8+448h]
0x14001b9b7  mov     edx, [rsi+38h]
0x14001b9ba  mov     ecx, edx
0x14001b9bc  shr     ecx, 1
0x14001b9be  mov     eax, edx
0x14001b9c0  and     ecx, 7FFFh
0x14001b9c6  shr     eax, 11h
0x14001b9c9  cmp     eax, 3FFEh
0x14001b9ce  jnb     short loc_14001BA1E
0x14001b9d0  inc     eax
0x14001b9d2  cmp     ecx, eax
0x14001b9d4  jnz     short loc_14001BA1E
0x14001b9d6  mov     rcx, rsi; struct _NDIS_REFCOUNT_STACK_BLOCK *
0x14001b9d9  call    ?ndisFreeRefCountStackChain@@YAXPEAU_NDIS_REFCOUNT_STACK_BLOCK@@@Z; ndisFreeRefCountStackChain(_NDIS_REFCOUNT_STACK_BLOCK *)
0x14001b9de  and     dword ptr [rsi+38h], 10001h
0x14001b9e5  mov     eax, 0FFFFh
0x14001b9ea  add     [rbx+8], ax
0x14001b9ee  jnz     loc_14001BAC2
0x14001b9f4  cmp     [rbx+0Bh], r14b
0x14001b9f8  jnz     loc_14001BAC2
0x14001b9fe  mov     rsi, [rbx+10h]
0x14001ba02  test    rsi, rsi
0x14001ba05  jz      loc_14001BAB1
0x14001ba0b  mov     rcx, rsi; struct NDIS_REFCOUNT_HANDLE__ *
0x14001ba0e  call    ?ndisGetAnyActiveRefTag@@YAKPEAUNDIS_REFCOUNT_HANDLE__@@@Z; ndisGetAnyActiveRefTag(NDIS_REFCOUNT_HANDLE__ *)
0x14001ba13  cmp     eax, 0FFFFFFFEh
0x14001ba16  jnz     loc_14001BF76
0x14001ba1c  jmp     short loc_14001BA88
0x14001ba1e  test    ecx, ecx
0x14001ba20  jnz     short loc_14001BA2B
0x14001ba22  test    dl, 1
0x14001ba25  jz      loc_14001BF8C
0x14001ba2b  xor     edx, edx; unsigned __int8
0x14001ba2d  mov     rcx, rsi; struct _NDIS_REFCOUNT_WITH_STACK *
0x14001ba30  call    ?ndisReferenceWithTagStackTrace@@YAXPEAU_NDIS_REFCOUNT_WITH_STACK@@E@Z; ndisReferenceWithTagStackTrace(_NDIS_REFCOUNT_WITH_STACK *,uchar)
0x14001ba35  jmp     short loc_14001B9E5
0x14001ba37  mov     r10, [r8+8]
0x14001ba3b  test    r10, r10
0x14001ba3e  jz      short loc_14001BA6D
0x14001ba40  movzx   r9d, byte ptr [r8+3]
0x14001ba45  xor     cl, cl
0x14001ba47  test    r9b, r9b
0x14001ba4a  jz      short loc_14001BA6D
0x14001ba4c  nop     dword ptr [rax+00h]
0x14001ba50  movzx   eax, cl
0x14001ba53  cmp     byte ptr [r10+rax*2], 11h
0x14001ba58  lea     rdx, [r10+rax*2]
0x14001ba5c  jnz     short loc_14001BA66
0x14001ba5e  movzx   eax, byte ptr [rdx+1]
0x14001ba62  test    al, al
0x14001ba64  jnz     short loc_14001BA7E
0x14001ba66  inc     cl
0x14001ba68  cmp     cl, r9b
0x14001ba6b  jb      short loc_14001BA50
0x14001ba6d  btr     dword ptr [r8+10h], 11h
0x14001ba73  jnb     loc_14001BF97
0x14001ba79  jmp     loc_14001B9E5
0x14001ba7e  dec     al
0x14001ba80  mov     [rdx+1], al
0x14001ba83  jmp     loc_14001B9E5
0x14001ba88  mov     rcx, rsi; BugCheckParameter3
0x14001ba8b  call    ?ndisRefCountBlockFromRefCountHandle@@YAPEAU_NDIS_REFCOUNT_BLOCK@@PEAUNDIS_REFCOUNT_HANDLE__@@@Z; ndisRefCountBlockFromRefCountHandle(NDIS_REFCOUNT_HANDLE__ *)
0x14001ba90  mov     rsi, rax
0x14001ba93  test    rax, rax
0x14001ba96  jz      short loc_14001BAB1
0x14001ba98  mov     rcx, rax; struct _NDIS_REFCOUNT_BLOCK *
0x14001ba9b  call    ?ndisFreeRefCountAuxiliaryMemory@@YAXPEAU_NDIS_REFCOUNT_BLOCK@@@Z; ndisFreeRefCountAuxiliaryMemory(_NDIS_REFCOUNT_BLOCK *)
0x14001baa0  xor     edx, edx; Tag
0x14001baa2  mov     rcx, rsi; P
0x14001baa5  call    cs:__imp_ExFreePoolWithTag
0x14001baac  nop     dword ptr [rax+rax+00h]
0x14001bab1  mov     qword ptr [rbx+10h], 1
0x14001bab9  jmp     short loc_14001BAC2
0x14001babb  mov     cs:?ndisRefCountReferenceCountOverflow@@3EC, 1; uchar volatile ndisRefCountReferenceCountOverflow
0x14001bac2  movzx   edx, r12b; NewIrql
0x14001bac6  mov     rcx, rbx; SpinLock
0x14001bac9  call    cs:__imp_KeReleaseSpinLock
0x14001bad0  nop     dword ptr [rax+rax+00h]
0x14001bad5  lea     r12, [r15+60h]
0x14001bad9  cmp     byte ptr [rdi], 5
0x14001badc  jnz     loc_14001BB62
0x14001bae2  lea     rbx, [rdi+138h]
0x14001bae9  mov     rcx, rbx; SpinLock
0x14001baec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001baf3  nop     dword ptr [rax+rax+00h]
0x14001baf8  cmp     byte ptr [rbx+0Ah], 0
0x14001bafc  movzx   esi, al
0x14001baff  jnz     short loc_14001BB16
0x14001bb01  movzx   eax, word ptr [rbx+8]
0x14001bb05  mov     ecx, 0FFEBh
0x14001bb0a  cmp     ax, cx
0x14001bb0d  jb      short loc_14001BB3A
0x14001bb0f  mov     cs:?ndisRefCountReferenceCountOverflow@@3EC, 1; uchar volatile ndisRefCountReferenceCountOverflow
0x14001bb16  movzx   edx, sil; NewIrql
0x14001bb1a  mov     rcx, rbx; SpinLock
0x14001bb1d  call    cs:__imp_KeReleaseSpinLock
0x14001bb24  nop     dword ptr [rax+rax+00h]
0x14001bb29  mov     rdi, [rdi+1A0h]
0x14001bb30  xor     r14d, r14d
0x14001bb33  cmp     byte ptr [rdi], 5
0x14001bb36  jz      short loc_14001BAE2
0x14001bb38  jmp     short loc_14001BB62
0x14001bb3a  mov     rcx, [rbx+10h]
0x14001bb3e  inc     ax
0x14001bb41  mov     dl, 0Fh
0x14001bb43  mov     [rbx+8], ax
0x14001bb47  mov     r14, rdi
0x14001bb4a  call    NdisReferenceWithTag
0x14001bb4f  movzx   edx, sil; NewIrql
0x14001bb53  mov     rcx, rbx; SpinLock
0x14001bb56  call    cs:__imp_KeReleaseSpinLock
0x14001bb5d  nop     dword ptr [rax+rax+00h]
0x14001bb62  movzx   edx, [rsp+1A0h+var_160]; NewIrql
0x14001bb67  mov     rcx, r12; SpinLock
0x14001bb6a  mov     qword ptr [r15+208h], 0
0x14001bb75  call    cs:__imp_KeReleaseSpinLock
0x14001bb7c  nop     dword ptr [rax+rax+00h]
0x14001bb81  cmp     byte ptr [rdi], 11h
0x14001bb84  jnz     short loc_14001BB91
  ... truncated ...
```
