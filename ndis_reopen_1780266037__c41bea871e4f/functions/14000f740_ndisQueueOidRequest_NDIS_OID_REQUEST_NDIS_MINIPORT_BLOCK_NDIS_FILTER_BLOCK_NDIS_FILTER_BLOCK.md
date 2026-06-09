# ndisQueueOidRequest(_NDIS_OID_REQUEST *,_NDIS_MINIPORT_BLOCK *,_NDIS_FILTER_BLOCK *,_NDIS_FILTER_BLOCK *)

- ea: `0x14000f740`
- end: `0x140010042`
- name: `?ndisQueueOidRequest@@YAHPEAU_NDIS_OID_REQUEST@@PEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_FILTER_BLOCK@@2@Z`
- size: `2306`
- prototype: `__int64 __fastcall(struct _NDIS_OID_REQUEST *, struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_FILTER_BLOCK *, struct _NDIS_FILTER_BLOCK *)`
- caller_count: `5`
- callee_count: `23`
- tags: `loader_planting`

## callers

- `0x140004a30`
- `0x14000f0a0`
- `0x14000f3e0`
- `0x14003f110`
- `0x1400c16a0`

## callees

- `0x14000a270`
- `0x14000b820`
- `0x14000f740`
- `0x140010d20`
- `0x140012610`
- `0x140014a50`
- `0x140014e40`
- `0x140017220`
- `0x140019c60`
- `0x140019d20`
- `0x140019d90`
- `0x14001a380`
- `0x14003ec10`
- `0x14003f0e0`
- `0x14004eee0`
- `0x14004f040`
- `0x14004f290`
- `0x140050a60`
- `0x140088cc0`
- `0x1400e6c20`
- `0x1400e71e0`
- `0x1400eb380`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000fc31`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000fc31`
- `ntoskrnl!PsIsSystemThread` at `0x14000fc4e`
- `ntoskrnl!PsIsSystemThread` at `0x14000fc4e`
- `ntoskrnl!EtwActivityIdControl` at `0x14000f843`
- `ntoskrnl!EtwActivityIdControl` at `0x14000f8f9`
- `ntoskrnl!EtwActivityIdControl` at `0x14000f843`
- `ntoskrnl!EtwActivityIdControl` at `0x14000f8f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fb45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fb45`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f9dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fb69`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fbbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fbf6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fc15`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fc99`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fdc1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fea6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fefa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ff72`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f9dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fb69`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fbbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fbf6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fc15`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fc99`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fdc1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fea6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fefa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ff72`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f94f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f997`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fa0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fb8c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fc75`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fca8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ff35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f94f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f997`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fa0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fb8c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fc75`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fca8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ff35`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fcd2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fcd2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fda1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fe86`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fedc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fda1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fe86`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fedc`

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
    if ( (unsigned int)dword_1401206C0 <= 4 )
      goto LABEL_89;
    if ( (qword_1401206D0 & 0x400) == 0 )
      goto LABEL_89;
    if ( (qword_1401206D8 & 0x400) != qword_1401206D8 )
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
0x14000f740  push    rbp
0x14000f742  push    rbx
0x14000f743  push    rsi
0x14000f744  push    rdi
0x14000f745  push    r12
0x14000f747  push    r13
0x14000f749  push    r14
0x14000f74b  push    r15
0x14000f74d  lea     rbp, [rsp-68h]
0x14000f752  sub     rsp, 168h
0x14000f759  mov     rax, cs:__security_cookie
0x14000f760  xor     rax, rsp
0x14000f763  mov     [rbp+0A0h+var_50], rax
0x14000f767  mov     rdi, r8
0x14000f76a  mov     r15, rdx
0x14000f76d  mov     r13, rcx
0x14000f770  xor     bl, bl
0x14000f772  xor     edx, edx; Val
0x14000f774  mov     [rsp+1A0h+var_150.Header.Type], bl
0x14000f778  mov     r8d, 0F7h; Size
0x14000f77e  lea     rcx, [rsp+1A0h+var_150.Header.Revision]; void *
0x14000f783  mov     rsi, r9
0x14000f786  xor     r14d, r14d
0x14000f789  call    memset
0x14000f78e  mov     ecx, [r13+20h]
0x14000f792  mov     [rsp+1A0h+var_158], r14d
0x14000f797  cmp     ecx, 10207h
0x14000f79d  jz      short loc_14000F80F
0x14000f79f  mov     eax, ecx
0x14000f7a1  sub     eax, 10106h
0x14000f7a6  jz      short loc_14000F7BC
0x14000f7a8  sub     eax, 1
0x14000f7ab  jz      short loc_14000F7BC
0x14000f7ad  cmp     eax, 0Dh
0x14000f7b0  jz      short loc_14000F7BC
0x14000f7b2  test    dword ptr [r13+58h], 100000h
0x14000f7ba  jz      short loc_14000F7FB
0x14000f7bc  mov     bl, 1
0x14000f7be  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000f7c5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f7cc  jz      short loc_14000F7FB
0x14000f7ce  mov     qword ptr [rsp+1A0h+var_170], r13; char
0x14000f7d3  lea     rax, WPP_67e470a56b3938b4276b23606b3190b8_Traceguids
0x14000f7da  mov     dword ptr [rsp+1A0h+var_178], ecx; char
0x14000f7de  mov     r9d, 0CBh; int
0x14000f7e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7eb  mov     dl, 4; int
0x14000f7ed  mov     [rsp+1A0h+var_180], rax; struct _GUID *
0x14000f7f2  mov     rcx, [rcx+40h]; int
0x14000f7f6  call    WPP_RECORDER_SF_Dq
0x14000f7fb  lea     r12, [r15+60h]
0x14000f7ff  test    bl, bl
0x14000f801  jz      loc_14000F94C
0x14000f807  mov     rdi, r15
0x14000f80a  jmp     loc_14000FC21
0x14000f80f  cmp     byte ptr [r15+20h], 6
0x14000f814  jnb     short loc_14000F7FB
0x14000f816  xor     edx, edx; Val
0x14000f818  lea     rcx, [rsp+1A0h+var_150]; void *
0x14000f81d  mov     r8d, 0F8h; Size
0x14000f823  call    memset
0x14000f828  lea     rbx, ?ndisIntReqNsi@@3U_NDIS_INTERNAL_REQUEST_OBJECT@@A; _NDIS_INTERNAL_REQUEST_OBJECT ndisIntReqNsi
0x14000f82f  mov     dword ptr [rbp+0A0h+var_150.NdisReserved+10h], 8
0x14000f836  lea     rdx, [rbp+0A0h+var_150.NdisReserved+60h]; ActivityId
0x14000f83a  mov     qword ptr [rbp+0A0h+var_150.NdisReserved+20h], rbx
0x14000f83e  mov     ecx, 3; ControlCode
0x14000f843  call    cs:__imp_EtwActivityIdControl
0x14000f84a  nop     dword ptr [rax+rax+00h]
0x14000f84f  xor     ecx, ecx
0x14000f851  mov     dword ptr [rsp+1A0h+var_150.Header.Type], 0EC0196h
0x14000f859  mov     [rsp+1A0h+var_180], rcx; struct _NDIS_FILTER_BLOCK *
0x14000f85e  lea     rax, [rsp+1A0h+var_158]
0x14000f863  mov     rcx, r15; struct _NDIS_MINIPORT_BLOCK *
0x14000f866  mov     dword ptr [rsp+1A0h+var_150.DATA], 10107h
0x14000f86e  xor     r9d, r9d; unsigned __int8
0x14000f871  mov     qword ptr [rsp+1A0h+var_150.RequestType], 2
0x14000f87a  lea     r8, [rsp+1A0h+var_150]; struct _NDIS_OID_REQUEST *
0x14000f87f  mov     qword ptr [rsp+1A0h+var_150.DATA+8], rax
0x14000f884  xor     edx, edx; struct _NDIS_CO_VC_PTR_BLOCK *
0x14000f886  mov     dword ptr [rbp+0A0h+var_150.DATA+10h], 4
0x14000f88d  call    ?ndisQuerySetMiniport@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CO_VC_PTR_BLOCK@@PEAU_NDIS_OID_REQUEST@@EPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQuerySetMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_CO_VC_PTR_BLOCK *,_NDIS_OID_REQUEST *,uchar,_NDIS_FILTER_BLOCK *)
0x14000f892  xorps   xmm0, xmm0
0x14000f895  mov     qword ptr [rbp+0A0h+var_150.NdisReserved+20h], rbx
0x14000f899  xorps   xmm1, xmm1
0x14000f89c  movaps  xmmword ptr [rbp+0A0h+var_150.NdisReserved+28h], xmm0
0x14000f8a0  xor     eax, eax
0x14000f8a2  movaps  xmmword ptr [rbp-60h], xmm1
0x14000f8a6  mov     qword ptr [rbp+0A0h+var_150.NdisReserved+18h], rax
0x14000f8aa  lea     rdx, [rbp+0A0h+var_150.NdisReserved+60h]; ActivityId
0x14000f8ae  mov     [rbp+0A0h+var_60], rax
0x14000f8b2  mov     ecx, 3; ControlCode
0x14000f8b7  movups  xmmword ptr [rsp+1A0h+var_150.Header.Type], xmm1
0x14000f8bc  movups  xmmword ptr [rsp+1A0h+var_150.RequestId], xmm1
0x14000f8c1  movups  xmmword ptr [rsp+1A0h+var_150.DATA], xmm1
0x14000f8c6  movups  xmmword ptr [rbp+0A0h+var_150.DATA+10h], xmm1
0x14000f8ca  movups  xmmword ptr [rbp+0A0h+var_150.DATA+20h], xmm1
0x14000f8ce  psrldq  xmm1, 8
0x14000f8d3  movd    eax, xmm1
0x14000f8d7  movaps  xmmword ptr [rbp+0A0h+var_150.NdisReserved+38h], xmm0
0x14000f8db  movaps  xmmword ptr [rbp+0A0h+var_150.NdisReserved+48h], xmm0
0x14000f8df  or      eax, 8
0x14000f8e2  movaps  xmmword ptr [rbp-10h], xmm0
0x14000f8e6  mov     dword ptr [rbp+0A0h+var_150.NdisReserved+10h], eax
0x14000f8e9  movaps  xmmword ptr [rbp+0A0h+var_150.NdisReserved+68h], xmm0
0x14000f8ed  movaps  xmmword ptr [rbp+0A0h+var_150.NdisReserved+78h], xmm0
0x14000f8f1  movaps  xmmword ptr [rbp+0A0h+var_150.MiniportReserved+8], xmm0
0x14000f8f5  movaps  xmmword ptr [rbp+0A0h+var_150.SourceReserved+8], xmm0
0x14000f8f9  call    cs:__imp_EtwActivityIdControl
0x14000f900  nop     dword ptr [rax+rax+00h]
0x14000f905  xor     ecx, ecx
0x14000f907  mov     dword ptr [rsp+1A0h+var_150.Header.Type], 0EC0196h
0x14000f90f  mov     [rsp+1A0h+var_180], rcx; struct _NDIS_FILTER_BLOCK *
0x14000f914  lea     rax, [rsp+1A0h+var_158]
0x14000f919  mov     rcx, r15; struct _NDIS_MINIPORT_BLOCK *
0x14000f91c  mov     dword ptr [rsp+1A0h+var_150.DATA], 10114h
0x14000f924  xor     r9d, r9d; unsigned __int8
0x14000f927  mov     qword ptr [rsp+1A0h+var_150.RequestType], 2
0x14000f930  lea     r8, [rsp+1A0h+var_150]; struct _NDIS_OID_REQUEST *
0x14000f935  mov     qword ptr [rsp+1A0h+var_150.DATA+8], rax
0x14000f93a  xor     edx, edx; struct _NDIS_CO_VC_PTR_BLOCK *
0x14000f93c  mov     dword ptr [rbp+0A0h+var_150.DATA+10h], 4
0x14000f943  call    ?ndisQuerySetMiniport@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CO_VC_PTR_BLOCK@@PEAU_NDIS_OID_REQUEST@@EPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQuerySetMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_CO_VC_PTR_BLOCK *,_NDIS_OID_REQUEST *,uchar,_NDIS_FILTER_BLOCK *)
0x14000f948  lea     r12, [r15+60h]
0x14000f94c  mov     rcx, r12; SpinLock
0x14000f94f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f956  nop     dword ptr [rax+rax+00h]
0x14000f95b  mov     rcx, gs:188h
0x14000f964  mov     [r15+208h], rcx
0x14000f96b  mov     [rsp+1A0h+var_160], al
0x14000f96f  test    rdi, rdi
0x14000f972  jz      short loc_14000F97D
0x14000f974  mov     rdi, [rdi+1A0h]
0x14000f97b  jmp     short loc_14000F984
0x14000f97d  mov     rdi, [r15+0A28h]
0x14000f984  test    rsi, rsi
0x14000f987  jz      loc_14000FB79
0x14000f98d  lea     rbx, [rsi+138h]
0x14000f994  mov     rcx, rbx; SpinLock
0x14000f997  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f99e  nop     dword ptr [rax+rax+00h]
0x14000f9a3  movzx   r12d, al
0x14000f9a7  cmp     [rbx+0Ah], r14b
0x14000f9ab  jnz     loc_14000FB62
0x14000f9b1  movzx   ecx, word ptr [rbx+8]
0x14000f9b5  mov     eax, 0FFEBh
0x14000f9ba  cmp     cx, ax
0x14000f9bd  jnb     loc_14000FB5B
0x14000f9c3  inc     cx
0x14000f9c6  mov     dl, 11h
0x14000f9c8  mov     [rbx+8], cx
0x14000f9cc  mov     rcx, [rbx+10h]
0x14000f9d0  call    NdisReferenceWithTag
0x14000f9d5  movzx   edx, r12b; NewIrql
0x14000f9d9  mov     rcx, rbx; SpinLock
0x14000f9dc  call    cs:__imp_KeReleaseSpinLock
0x14000f9e3  nop     dword ptr [rax+rax+00h]
0x14000f9e8  mov     rax, [rsi+10h]
0x14000f9ec  cmp     [rax+0F8h], r14
0x14000f9f3  jz      short loc_14000F9FA
0x14000f9f5  mov     rdi, rsi
0x14000f9f8  jmp     short loc_14000FA08
0x14000f9fa  mov     rax, [rsi+1A0h]
0x14000fa01  test    rax, rax
0x14000fa04  cmovnz  rdi, rax
0x14000fa08  mov     rcx, rbx; SpinLock
0x14000fa0b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fa12  nop     dword ptr [rax+rax+00h]
0x14000fa17  mov     r8, [rbx+10h]; BugCheckParameter3
0x14000fa1b  movzx   r12d, al
0x14000fa1f  lea     rcx, [r8-2]
0x14000fa23  cmp     rcx, 1
0x14000fa27  jbe     short loc_14000FA85
0x14000fa29  cmp     r8, 2
0x14000fa2d  jb      loc_14000FFED
0x14000fa33  cmp     byte ptr [r8+2], 11h
0x14000fa38  jbe     loc_140010000
0x14000fa3e  movzx   ecx, byte ptr [r8+1]
0x14000fa43  test    ecx, ecx
0x14000fa45  jz      loc_14000FAD7
0x14000fa4b  cmp     ecx, 1
0x14000fa4e  jnz     short loc_14000FA85
0x14000fa50  lea     rsi, [r8+448h]
0x14000fa57  mov     edx, [rsi+38h]
0x14000fa5a  mov     ecx, edx
0x14000fa5c  shr     ecx, 1
0x14000fa5e  mov     eax, edx
0x14000fa60  and     ecx, 7FFFh
0x14000fa66  shr     eax, 11h
0x14000fa69  cmp     eax, 3FFEh
0x14000fa6e  jnb     short loc_14000FABE
0x14000fa70  inc     eax
0x14000fa72  cmp     ecx, eax
0x14000fa74  jnz     short loc_14000FABE
0x14000fa76  mov     rcx, rsi; struct _NDIS_REFCOUNT_STACK_BLOCK *
0x14000fa79  call    ?ndisFreeRefCountStackChain@@YAXPEAU_NDIS_REFCOUNT_STACK_BLOCK@@@Z; ndisFreeRefCountStackChain(_NDIS_REFCOUNT_STACK_BLOCK *)
0x14000fa7e  and     dword ptr [rsi+38h], 10001h
0x14000fa85  mov     eax, 0FFFFh
0x14000fa8a  add     [rbx+8], ax
0x14000fa8e  jnz     loc_14000FB62
0x14000fa94  cmp     [rbx+0Bh], r14b
0x14000fa98  jnz     loc_14000FB62
0x14000fa9e  mov     rsi, [rbx+10h]
0x14000faa2  test    rsi, rsi
0x14000faa5  jz      loc_14000FB51
0x14000faab  mov     rcx, rsi; struct NDIS_REFCOUNT_HANDLE__ *
0x14000faae  call    ?ndisGetAnyActiveRefTag@@YAKPEAUNDIS_REFCOUNT_HANDLE__@@@Z; ndisGetAnyActiveRefTag(NDIS_REFCOUNT_HANDLE__ *)
0x14000fab3  cmp     eax, 0FFFFFFFEh
0x14000fab6  jnz     loc_140010016
0x14000fabc  jmp     short loc_14000FB28
0x14000fabe  test    ecx, ecx
0x14000fac0  jnz     short loc_14000FACB
0x14000fac2  test    dl, 1
0x14000fac5  jz      loc_14001002C
0x14000facb  xor     edx, edx; unsigned __int8
0x14000facd  mov     rcx, rsi; struct _NDIS_REFCOUNT_WITH_STACK *
0x14000fad0  call    ?ndisReferenceWithTagStackTrace@@YAXPEAU_NDIS_REFCOUNT_WITH_STACK@@E@Z; ndisReferenceWithTagStackTrace(_NDIS_REFCOUNT_WITH_STACK *,uchar)
0x14000fad5  jmp     short loc_14000FA85
0x14000fad7  mov     r10, [r8+8]
0x14000fadb  test    r10, r10
0x14000fade  jz      short loc_14000FB0D
0x14000fae0  movzx   r9d, byte ptr [r8+3]
0x14000fae5  xor     cl, cl
0x14000fae7  test    r9b, r9b
0x14000faea  jz      short loc_14000FB0D
0x14000faec  nop     dword ptr [rax+00h]
0x14000faf0  movzx   eax, cl
0x14000faf3  cmp     byte ptr [r10+rax*2], 11h
0x14000faf8  lea     rdx, [r10+rax*2]
0x14000fafc  jnz     short loc_14000FB06
0x14000fafe  movzx   eax, byte ptr [rdx+1]
0x14000fb02  test    al, al
0x14000fb04  jnz     short loc_14000FB1E
0x14000fb06  inc     cl
0x14000fb08  cmp     cl, r9b
0x14000fb0b  jb      short loc_14000FAF0
0x14000fb0d  btr     dword ptr [r8+10h], 11h
0x14000fb13  jnb     loc_140010037
0x14000fb19  jmp     loc_14000FA85
0x14000fb1e  dec     al
0x14000fb20  mov     [rdx+1], al
0x14000fb23  jmp     loc_14000FA85
0x14000fb28  mov     rcx, rsi; BugCheckParameter3
0x14000fb2b  call    ?ndisRefCountBlockFromRefCountHandle@@YAPEAU_NDIS_REFCOUNT_BLOCK@@PEAUNDIS_REFCOUNT_HANDLE__@@@Z; ndisRefCountBlockFromRefCountHandle(NDIS_REFCOUNT_HANDLE__ *)
0x14000fb30  mov     rsi, rax
0x14000fb33  test    rax, rax
0x14000fb36  jz      short loc_14000FB51
0x14000fb38  mov     rcx, rax; struct _NDIS_REFCOUNT_BLOCK *
0x14000fb3b  call    ?ndisFreeRefCountAuxiliaryMemory@@YAXPEAU_NDIS_REFCOUNT_BLOCK@@@Z; ndisFreeRefCountAuxiliaryMemory(_NDIS_REFCOUNT_BLOCK *)
0x14000fb40  xor     edx, edx; Tag
0x14000fb42  mov     rcx, rsi; P
0x14000fb45  call    cs:__imp_ExFreePoolWithTag
0x14000fb4c  nop     dword ptr [rax+rax+00h]
0x14000fb51  mov     qword ptr [rbx+10h], 1
0x14000fb59  jmp     short loc_14000FB62
0x14000fb5b  mov     cs:?ndisRefCountReferenceCountOverflow@@3EC, 1; uchar volatile ndisRefCountReferenceCountOverflow
0x14000fb62  movzx   edx, r12b; NewIrql
0x14000fb66  mov     rcx, rbx; SpinLock
0x14000fb69  call    cs:__imp_KeReleaseSpinLock
0x14000fb70  nop     dword ptr [rax+rax+00h]
0x14000fb75  lea     r12, [r15+60h]
0x14000fb79  cmp     byte ptr [rdi], 5
0x14000fb7c  jnz     loc_14000FC02
0x14000fb82  lea     rbx, [rdi+138h]
0x14000fb89  mov     rcx, rbx; SpinLock
0x14000fb8c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fb93  nop     dword ptr [rax+rax+00h]
0x14000fb98  cmp     byte ptr [rbx+0Ah], 0
0x14000fb9c  movzx   esi, al
0x14000fb9f  jnz     short loc_14000FBB6
0x14000fba1  movzx   eax, word ptr [rbx+8]
0x14000fba5  mov     ecx, 0FFEBh
0x14000fbaa  cmp     ax, cx
0x14000fbad  jb      short loc_14000FBDA
0x14000fbaf  mov     cs:?ndisRefCountReferenceCountOverflow@@3EC, 1; uchar volatile ndisRefCountReferenceCountOverflow
0x14000fbb6  movzx   edx, sil; NewIrql
0x14000fbba  mov     rcx, rbx; SpinLock
0x14000fbbd  call    cs:__imp_KeReleaseSpinLock
0x14000fbc4  nop     dword ptr [rax+rax+00h]
0x14000fbc9  mov     rdi, [rdi+1A0h]
0x14000fbd0  xor     r14d, r14d
0x14000fbd3  cmp     byte ptr [rdi], 5
0x14000fbd6  jz      short loc_14000FB82
0x14000fbd8  jmp     short loc_14000FC02
0x14000fbda  mov     rcx, [rbx+10h]
0x14000fbde  inc     ax
0x14000fbe1  mov     dl, 0Fh
0x14000fbe3  mov     [rbx+8], ax
0x14000fbe7  mov     r14, rdi
0x14000fbea  call    NdisReferenceWithTag
0x14000fbef  movzx   edx, sil; NewIrql
0x14000fbf3  mov     rcx, rbx; SpinLock
0x14000fbf6  call    cs:__imp_KeReleaseSpinLock
0x14000fbfd  nop     dword ptr [rax+rax+00h]
0x14000fc02  movzx   edx, [rsp+1A0h+var_160]; NewIrql
0x14000fc07  mov     rcx, r12; SpinLock
0x14000fc0a  mov     qword ptr [r15+208h], 0
0x14000fc15  call    cs:__imp_KeReleaseSpinLock
0x14000fc1c  nop     dword ptr [rax+rax+00h]
0x14000fc21  cmp     byte ptr [rdi], 11h
0x14000fc24  jnz     short loc_14000FC31
  ... truncated ...
```
