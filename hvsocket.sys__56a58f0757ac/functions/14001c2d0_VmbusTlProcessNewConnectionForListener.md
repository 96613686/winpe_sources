# VmbusTlProcessNewConnectionForListener

- ea: `0x14001c2d0`
- end: `0x14001cc79`
- name: `VmbusTlProcessNewConnectionForListener`
- size: `2473`
- prototype: `__int64 __fastcall(__int64, _QWORD *, GUID *, GUID *, GUID *, _OWORD *, _OWORD *, _OWORD *, char)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001bd20`

## callees

- `0x140001bf4`
- `0x1400023b0`
- `0x1400058d0`
- `0x1400059b8`
- `0x140007034`
- `0x14000727c`
- `0x14000975c`
- `0x140009834`
- `0x140009b84`
- `0x140009df0`
- `0x14000a048`
- `0x14000a154`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x1400193ec`
- `0x14001c2d0`
- `0x14001e1c0`
- `0x14001f540`
- `0x14001f5e4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c363`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c527`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c363`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c527`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001c357`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001c51b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001c357`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001c51b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c6a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ca74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ca99`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cb30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cc50`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c6a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ca74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ca99`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cb30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cc50`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c319`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c4e6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c319`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c4e6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c4d5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c5de`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ca37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cb1a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cc3a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c4d5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c5de`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ca37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cb1a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cc3a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001c32c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001c4f6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001c32c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001c4f6`

## pseudocode

```c
__int64 __fastcall VmbusTlProcessNewConnectionForListener(
        __int64 a1,
        _QWORD *a2,
        GUID *a3,
        GUID *a4,
        GUID *a5,
        _OWORD *a6,
        _OWORD *a7,
        _OWORD *a8,
        char a9)
{
  __int64 v9; // rsi
  GUID *v11; // r15
  volatile signed __int64 *v13; // r13
  _QWORD *v14; // rax
  struct _FAST_MUTEX *v15; // rcx
  __int64 v16; // r14
  unsigned int v17; // edi
  int PartitionListenerEndpoint; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  signed __int64 v21; // rax
  unsigned __int64 i; // rcx
  signed __int64 v23; // rtt
  signed __int64 v24; // rax
  bool v25; // cc
  signed __int64 v26; // rax
  void (__fastcall *v27)(__int64); // rax
  char v28; // di
  char v29; // r15
  char v30; // r12
  int v31; // edx
  signed __int64 v32; // rax
  signed __int64 v33; // rax
  void (__fastcall *v34)(volatile signed __int64 *); // rax
  int Connection; // eax
  char *v36; // rbx
  int v37; // edx
  GUID v38; // xmm0
  int v39; // edx
  signed __int64 v40; // rax
  signed __int64 v41; // rax
  void (__fastcall *v42)(char *); // rax
  signed __int64 v43; // rax
  signed __int64 v44; // rax
  void (__fastcall *v45)(__int64); // rax
  signed __int64 v46; // rax
  signed __int64 v47; // rax
  signed __int64 v48; // rax
  signed __int64 v49; // rax
  void (__fastcall *v50)(__int64); // rax
  _BYTE v52[12]; // [rsp+34h] [rbp-24h] BYREF
  PVOID P[3]; // [rsp+40h] [rbp-18h] BYREF

  v9 = 0;
  *(_DWORD *)&v52[8] = 0;
  P[0] = 0;
  *(_QWORD *)v52 = a9 & 0x20;
  v11 = a3;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v13 = VmbusTlFindAndReferencePartition(a1, v11);
  v14 = VmbusTlFindAndReferencePartition(a1, a4);
  v15 = (struct _FAST_MUTEX *)(a1 + 16);
  v16 = (__int64)v14;
  ExReleaseFastMutexUnsafe(v15);
  KeLeaveCriticalRegion();
  if ( !v13 )
  {
    v17 = -1073741275;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError((const int *)"VmbusTlProcessNewConnectionForListener", 545, 3221226021LL, (__int64)v11);
    goto LABEL_106;
  }
  PartitionListenerEndpoint = VmbusTlGetPartitionListenerEndpoint((__int64)v13, v16, a4, a5, a6, (__int64 *)&v52[4]);
  v9 = *(_QWORD *)&v52[4];
  if ( PartitionListenerEndpoint >= 0 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlProcessNewConnectionForListener",
        564,
        *(__int64 *)&v52[4],
        *(_QWORD *)(*(_QWORD *)&v52[4] + 304LL),
        (const int *)"Inbound Connection");
    _m_prefetchw((const void *)(v9 + 304));
    v21 = *(_QWORD *)(v9 + 304);
    for ( i = v21 + 1; ; i = v21 + 1 )
    {
      if ( i <= 1 )
      {
        if ( i != 1 )
          __fastfail(0xEu);
        if ( (unsigned int)dword_140013058 > 4 )
          HvsocketTraceEndpointMessage(
            (const int *)"VmbusTlTryReferenceEndpointInternal failed to reference the endpoint.",
            v9,
            v19,
            v20);
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (const int *)"VmbusTlProcessNewConnectionForListener",
            566,
            v9,
            *(_QWORD *)(v9 + 8),
            (const int *)"Dereference object");
        v24 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v9 + 8), 0xFFFFFFFFFFFFFFFFuLL);
        v25 = v24 <= 1;
        v26 = v24 - 1;
        if ( v25 )
        {
          if ( v26 )
            __fastfail(0xEu);
          v27 = *(void (__fastcall **)(__int64))(v9 + 80);
          if ( v27 )
            v27(v9);
          if ( *(_DWORD *)(v9 + 88) == 1 )
          {
            ExFreePoolWithTag((PVOID)v9, 0x69706E56u);
          }
          else if ( *(_DWORD *)(v9 + 88) == 2 )
          {
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v9 + 96), (PVOID)v9);
          }
        }
        v9 = 0;
        v17 = -1073741258;
        if ( (unsigned int)dword_140013058 > 2 )
          HvsocketTraceServiceError(
            (const int *)"VmbusTlProcessNewConnectionForListener",
            569,
            3221226038LL,
            (__int64)a6,
            (__int64)v11);
        goto LABEL_28;
      }
      v23 = v21;
      v21 = _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 304), i, v21);
      if ( v23 == v21 )
        break;
    }
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 16));
    v28 = *(_BYTE *)(v9 + 425);
    v29 = *(_BYTE *)(v9 + 184);
    v30 = *(_BYTE *)(v9 + 185);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 16));
    KeLeaveCriticalRegion();
    if ( !v28 )
    {
      v17 = -1073741258;
      if ( (unsigned int)dword_140013058 <= 2 )
        goto LABEL_28;
      v31 = 584;
      goto LABEL_27;
    }
    if ( v29 )
    {
      v17 = -1073741258;
      if ( (unsigned int)dword_140013058 > 2 )
      {
        v31 = 591;
LABEL_27:
        HvsocketTraceEndpointError((const int *)"VmbusTlProcessNewConnectionForListener", v31, 3221226038LL, v9);
        goto LABEL_28;
      }
    }
    else
    {
      if ( !*(_BYTE *)(v9 + 186) || *(_DWORD *)v52 )
      {
        v11 = a3;
        goto LABEL_45;
      }
      v17 = -1073741258;
      if ( (unsigned int)dword_140013058 > 2 )
      {
        v31 = 598;
        goto LABEL_27;
      }
    }
    goto LABEL_28;
  }
  v30 = 0;
  if ( memcmp(a4, &HV_GUID_PARENT, 0x10u) )
  {
    v17 = -1073741258;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceServiceError(
        (const int *)"VmbusTlProcessNewConnectionForListener",
        608,
        3221226038LL,
        (__int64)a6,
        (__int64)v11);
    v9 = *(_QWORD *)&v52[4];
    goto LABEL_28;
  }
LABEL_45:
  Connection = VmbusTlCreateConnection(a1, 0, P);
  v36 = (char *)P[0];
  v17 = Connection;
  *(_DWORD *)v52 = Connection;
  if ( Connection < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_88;
    v37 = 621;
    goto LABEL_48;
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlProcessNewConnectionForListener",
      627,
      (__int64)P[0],
      *((_QWORD *)P[0] + 1),
      (const int *)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)v36 + 1) <= 1 )
    __fastfail(0xEu);
  *((_DWORD *)v36 + 129) |= 2u;
  *((_OWORD *)v36 + 29) = *a8;
  *((_WORD *)v36 + 68) = 34;
  *(GUID *)(v36 + 140) = *a4;
  *(_OWORD *)(v36 + 156) = *a6;
  v36[185] = v30;
  v36[186] = (a9 & 0x20) != 0;
  *((GUID *)v36 + 55) = *v11;
  if ( (a9 & 4) != 0 )
    *((_DWORD *)v36 + 129) |= 4u;
  if ( (a9 & 8) != 0 )
    *((GUID *)v36 + 56) = *a5;
  if ( (a9 & 0x10) != 0 && v9 )
  {
    *((_DWORD *)v36 + 129) ^= ((unsigned __int8)*((_DWORD *)v36 + 129)
                             ^ (unsigned __int8)(4 * *(_DWORD *)(v9 + 344)))
                            & 4;
    *((_OWORD *)v36 + 56) = *(_OWORD *)(v9 + 392);
  }
  *((_WORD *)v36 + 240) = 34;
  if ( !memcmp(a4, v11, 0x10u) )
  {
    v38 = HV_GUID_LOOPBACK;
  }
  else if ( v16 && !memcmp((const void *)(v16 + 232), &HV_GUID_CHILDREN, 0x10u) )
  {
    v38 = HV_GUID_PARENT;
  }
  else if ( !memcmp(a5, &HV_GUID_ZERO, 0x10u) )
  {
    v38 = *a4;
  }
  else
  {
    v38 = *a5;
  }
  *(GUID *)(v36 + 484) = v38;
  *(_OWORD *)(v36 + 500) = *a7;
  *(GUID *)(v36 + 280) = *v11;
  *(_DWORD *)v52 = VmbusTlAssociateConnectionToPartition(a1, v11, a4, (__int64)v36);
  v17 = *(_DWORD *)v52;
  if ( *(int *)v52 >= 0 )
  {
    *(_DWORD *)v52 = VmbusTlSetEndpointId(v36, a8);
    v17 = *(_DWORD *)v52;
    if ( *(int *)v52 >= 0 )
    {
      *(_DWORD *)v52 = VmbusTlSetCancellable(a1, v36);
      v17 = *(_DWORD *)v52;
      if ( *(int *)v52 >= 0 )
      {
        *((_QWORD *)v36 + 117) = *a2;
        *a2 = 0;
        if ( v9 )
        {
          v17 = HvSocketAcceptIncomingConnection(v9, (__int64)v36);
          *(_DWORD *)v52 = v17;
          if ( (v17 & 0x80000000) == 0 )
            goto LABEL_90;
        }
        else
        {
          *(_DWORD *)v52 = HvSocketPendConnection(v36);
          v17 = *(_DWORD *)v52;
          if ( *(int *)v52 >= 0 )
          {
            v17 = 259;
LABEL_90:
            if ( v36 )
            {
              if ( (unsigned int)dword_140013058 > 5 )
                HvsocketTraceReferenceCount(
                  (const int *)"VmbusTlProcessNewConnectionForListener",
                  752,
                  (__int64)v36,
                  *((_QWORD *)v36 + 1),
                  (const int *)"Dereference object");
              v40 = _InterlockedExchangeAdd64((volatile signed __int64 *)v36 + 1, 0xFFFFFFFFFFFFFFFFuLL);
              v25 = v40 <= 1;
              v41 = v40 - 1;
              if ( v25 )
              {
                if ( v41 )
                  __fastfail(0xEu);
                v42 = (void (__fastcall *)(char *))*((_QWORD *)v36 + 10);
                if ( v42 )
                  v42(v36);
                if ( *((_DWORD *)v36 + 22) == 1 )
                {
                  ExFreePoolWithTag(v36, 0x69706E56u);
                }
                else if ( *((_DWORD *)v36 + 22) == 2 )
                {
                  ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v36 + 12), v36);
                }
              }
            }
            goto LABEL_28;
          }
        }
        goto LABEL_88;
      }
      if ( (unsigned int)dword_140013058 <= 2 )
        goto LABEL_88;
      v39 = 716;
    }
    else
    {
      if ( (unsigned int)dword_140013058 <= 2 )
        goto LABEL_88;
      v39 = 709;
    }
    HvsocketTraceEndpointError((const int *)"VmbusTlProcessNewConnectionForListener", v39, v17, (__int64)v36);
    goto LABEL_88;
  }
  if ( (unsigned int)dword_140013058 > 2 )
  {
    v37 = 702;
LABEL_48:
    HvsocketTraceServiceError(
      (const int *)"VmbusTlProcessNewConnectionForListener",
      v37,
      v17,
      (__int64)a6,
      (__int64)v11);
  }
LABEL_88:
  if ( v36 )
  {
    VmbusTlConnectComplete(v36, (int *)v52);
    v17 = *(_DWORD *)v52;
    goto LABEL_90;
  }
LABEL_28:
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlProcessNewConnectionForListener",
      757,
      (__int64)v13,
      *((_QWORD *)v13 + 1),
      (const int *)"Dereference object");
  v32 = _InterlockedExchangeAdd64(v13 + 1, 0xFFFFFFFFFFFFFFFFuLL);
  v25 = v32 <= 1;
  v33 = v32 - 1;
  if ( v25 )
  {
    if ( v33 )
      __fastfail(0xEu);
    v34 = (void (__fastcall *)(volatile signed __int64 *))*((_QWORD *)v13 + 10);
    if ( v34 )
      v34(v13);
    if ( *((_DWORD *)v13 + 22) == 1 )
    {
      ExFreePoolWithTag((PVOID)v13, 0x69706E56u);
    }
    else if ( *((_DWORD *)v13 + 22) == 2 )
    {
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 12), (PVOID)v13);
    }
  }
LABEL_106:
  if ( v16 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlProcessNewConnectionForListener",
        762,
        v16,
        *(_QWORD *)(v16 + 8),
        (const int *)"Dereference object");
    v43 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v16 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v25 = v43 <= 1;
    v44 = v43 - 1;
    if ( v25 )
    {
      if ( v44 )
        __fastfail(0xEu);
      v45 = *(void (__fastcall **)(__int64))(v16 + 80);
      if ( v45 )
        v45(v16);
      if ( *(_DWORD *)(v16 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v16, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v16 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v16 + 96), (PVOID)v16);
      }
    }
  }
  if ( v9 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlProcessNewConnectionForListener",
        767,
        v9,
        *(_QWORD *)(v9 + 304),
        (const int *)"Inbound Connection (deref)");
    v46 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v9 + 304), 0xFFFFFFFFFFFFFFFFuLL);
    v25 = v46 <= 1;
    v47 = v46 - 1;
    if ( v25 )
    {
      if ( v47 )
        __fastfail(0xEu);
      if ( (unsigned int)dword_140013058 > 4 )
        HvsocketTraceEndpointEvent((const int *)"VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", v9, 9);
      VmbusTlQueueEndpointAction(v9, v9 + 200, 9);
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlProcessNewConnectionForListener",
        768,
        v9,
        *(_QWORD *)(v9 + 8),
        (const int *)"Dereference object");
    v48 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v9 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v25 = v48 <= 1;
    v49 = v48 - 1;
    if ( v25 )
    {
      if ( v49 )
        __fastfail(0xEu);
      v50 = *(void (__fastcall **)(__int64))(v9 + 80);
      if ( v50 )
        v50(v9);
      if ( *(_DWORD *)(v9 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v9, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v9 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v9 + 96), (PVOID)v9);
      }
    }
  }
  return v17;
}

```

## disassembly

```asm
0x14001c2d0  mov     rax, rsp
0x14001c2d3  mov     [rax+20h], r9
0x14001c2d7  mov     [rax+18h], r8
0x14001c2db  mov     [rax+10h], rdx
0x14001c2df  mov     [rax+8], rcx
0x14001c2e3  push    rbp
0x14001c2e4  push    rbx
0x14001c2e5  push    rsi
0x14001c2e6  push    rdi
0x14001c2e7  push    r12
0x14001c2e9  push    r13
0x14001c2eb  push    r14
0x14001c2ed  push    r15
0x14001c2ef  mov     rbp, rsp
0x14001c2f2  sub     rsp, 58h
0x14001c2f6  mov     eax, [rbp+arg_40]
0x14001c2fc  xor     esi, esi
0x14001c2fe  and     eax, 20h
0x14001c301  mov     [rbp+Entry], rsi
0x14001c305  mov     rdi, r9
0x14001c308  mov     [rbp+P], rsi
0x14001c30c  setnz   [rbp+var_28]
0x14001c310  mov     [rbp+var_24], eax
0x14001c313  mov     r15, r8
0x14001c316  mov     r14, rcx
0x14001c319  call    cs:__imp_KeEnterCriticalRegion
0x14001c320  nop     dword ptr [rax+rax+00h]
0x14001c325  lea     rbx, [r14+10h]
0x14001c329  mov     rcx, rbx; FastMutex
0x14001c32c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001c333  nop     dword ptr [rax+rax+00h]
0x14001c338  mov     rdx, r15
0x14001c33b  mov     rcx, r14
0x14001c33e  call    VmbusTlFindAndReferencePartition
0x14001c343  mov     rdx, rdi
0x14001c346  mov     rcx, r14
0x14001c349  mov     r13, rax
0x14001c34c  call    VmbusTlFindAndReferencePartition
0x14001c351  mov     rcx, rbx; FastMutex
0x14001c354  mov     r14, rax
0x14001c357  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001c35e  nop     dword ptr [rax+rax+00h]
0x14001c363  call    cs:__imp_KeLeaveCriticalRegion
0x14001c36a  nop     dword ptr [rax+rax+00h]
0x14001c36f  lea     r12, aDereferenceObj; "Dereference object"
0x14001c376  test    r13, r13
0x14001c379  jnz     short loc_14001C3AB
0x14001c37b  mov     eax, cs:dword_140013058
0x14001c381  mov     edi, 0C0000225h
0x14001c386  cmp     eax, 2
0x14001c389  jbe     loc_14001CAAE
0x14001c38f  mov     r9, r15
0x14001c392  lea     rcx, aVmbustlprocess_2; "VmbusTlProcessNewConnectionForListener"
0x14001c399  mov     r8d, edi
0x14001c39c  mov     edx, 221h
0x14001c3a1  call    HvsocketTraceGuidError
0x14001c3a6  jmp     loc_14001CAAE
0x14001c3ab  mov     rbx, [rbp+arg_28]
0x14001c3af  lea     rax, [rbp+Entry]
0x14001c3b3  mov     r9, [rbp+arg_20]
0x14001c3b7  mov     r8, rdi
0x14001c3ba  mov     [rsp+58h+var_30], rax
0x14001c3bf  mov     rdx, r14
0x14001c3c2  mov     rcx, r13
0x14001c3c5  mov     [rsp+58h+var_38], rbx
0x14001c3ca  call    VmbusTlGetPartitionListenerEndpoint
0x14001c3cf  mov     rsi, [rbp+Entry]
0x14001c3d3  test    eax, eax
0x14001c3d5  js      loc_14001C6F1
0x14001c3db  mov     eax, cs:dword_140013058
0x14001c3e1  cmp     eax, 5
0x14001c3e4  jbe     short loc_14001C40D
0x14001c3e6  mov     r9, [rsi+130h]
0x14001c3ed  lea     rax, aInboundConnect; "Inbound Connection"
0x14001c3f4  mov     r8, rsi
0x14001c3f7  mov     [rsp+58h+var_38], rax
0x14001c3fc  mov     edx, 234h
0x14001c401  lea     rcx, aVmbustlprocess_2; "VmbusTlProcessNewConnectionForListener"
0x14001c408  call    HvsocketTraceReferenceCount
0x14001c40d  prefetchw byte ptr [rsi+130h]
0x14001c414  mov     rax, [rsi+130h]
0x14001c41b  lea     rcx, [rax+1]
0x14001c41f  jmp     short loc_14001C436
0x14001c421  lock cmpxchg [rsi+130h], rcx
0x14001c42a  mov     rcx, rax
0x14001c42d  jz      loc_14001C4E6
0x14001c433  inc     rcx
0x14001c436  cmp     rcx, 1
0x14001c43a  ja      short loc_14001C421
0x14001c43c  cmp     rcx, 1
0x14001c440  jz      short loc_14001C449
0x14001c442  mov     ecx, 0Eh
0x14001c447  int     29h; Win8: RtlFailFast(ecx)
0x14001c449  mov     eax, cs:dword_140013058
0x14001c44f  cmp     eax, 4
0x14001c452  jbe     short loc_14001C463
0x14001c454  mov     rdx, rsi
0x14001c457  lea     rcx, aVmbustltryrefe; "VmbusTlTryReferenceEndpointInternal fai"...
0x14001c45e  call    HvsocketTraceEndpointMessage
0x14001c463  mov     eax, cs:dword_140013058
0x14001c469  cmp     eax, 5
0x14001c46c  jbe     short loc_14001C48B
0x14001c46e  mov     r9, [rsi+8]
0x14001c472  lea     rcx, aVmbustlprocess_2; "VmbusTlProcessNewConnectionForListener"
0x14001c479  mov     r8, rsi
0x14001c47c  mov     [rsp+58h+var_38], r12
0x14001c481  mov     edx, 236h
0x14001c486  call    HvsocketTraceReferenceCount
0x14001c48b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c48f  lock xadd [rsi+8], rax
0x14001c495  sub     rax, 1
0x14001c499  jg      loc_14001C6B9
0x14001c49f  test    rax, rax
0x14001c4a2  jnz     loc_14001C6B2
0x14001c4a8  mov     rax, [rsi+50h]
0x14001c4ac  test    rax, rax
0x14001c4af  jz      short loc_14001C4B9
0x14001c4b1  mov     rcx, rsi
0x14001c4b4  call    _guard_dispatch_icall
0x14001c4b9  mov     ecx, [rsi+58h]
0x14001c4bc  sub     ecx, 1
0x14001c4bf  jz      loc_14001C69C
0x14001c4c5  cmp     ecx, 1
0x14001c4c8  jnz     loc_14001C6B9
0x14001c4ce  mov     rcx, [rsi+60h]; Lookaside
0x14001c4d2  mov     rdx, rsi; Entry
0x14001c4d5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001c4dc  nop     dword ptr [rax+rax+00h]
0x14001c4e1  jmp     loc_14001C6B9
0x14001c4e6  call    cs:__imp_KeEnterCriticalRegion
0x14001c4ed  nop     dword ptr [rax+rax+00h]
0x14001c4f2  lea     rcx, [rsi+10h]; FastMutex
0x14001c4f6  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001c4fd  nop     dword ptr [rax+rax+00h]
0x14001c502  mov     dil, [rsi+1A9h]
0x14001c509  lea     rcx, [rsi+10h]; FastMutex
0x14001c50d  mov     r15b, [rsi+0B8h]
0x14001c514  mov     r12b, [rsi+0B9h]
0x14001c51b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001c522  nop     dword ptr [rax+rax+00h]
0x14001c527  call    cs:__imp_KeLeaveCriticalRegion
0x14001c52e  nop     dword ptr [rax+rax+00h]
0x14001c533  test    dil, dil
0x14001c536  jnz     loc_14001C5EF
0x14001c53c  mov     eax, cs:dword_140013058
0x14001c542  mov     r8d, 0C0000236h
0x14001c548  mov     edi, r8d
0x14001c54b  cmp     eax, 2
0x14001c54e  jbe     short loc_14001C564
0x14001c550  mov     edx, 248h
0x14001c555  mov     r9, rsi
0x14001c558  lea     rcx, aVmbustlprocess_2; "VmbusTlProcessNewConnectionForListener"
0x14001c55f  call    HvsocketTraceEndpointError
0x14001c564  lea     r12, aDereferenceObj; "Dereference object"
0x14001c56b  mov     eax, cs:dword_140013058
0x14001c571  cmp     eax, 5
0x14001c574  jbe     short loc_14001C593
0x14001c576  mov     r9, [r13+8]
0x14001c57a  lea     rcx, aVmbustlprocess_2; "VmbusTlProcessNewConnectionForListener"
0x14001c581  mov     r8, r13
0x14001c584  mov     [rsp+58h+var_38], r12
0x14001c589  mov     edx, 2F5h
0x14001c58e  call    HvsocketTraceReferenceCount
0x14001c593  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c597  lock xadd [r13+8], rax
0x14001c59d  sub     rax, 1
0x14001c5a1  jg      loc_14001CAAE
0x14001c5a7  test    rax, rax
0x14001c5aa  jnz     loc_14001CAA7
0x14001c5b0  mov     rax, [r13+50h]
0x14001c5b4  test    rax, rax
0x14001c5b7  jz      short loc_14001C5C1
0x14001c5b9  mov     rcx, r13
0x14001c5bc  call    _guard_dispatch_icall
0x14001c5c1  mov     ecx, [r13+58h]
0x14001c5c5  sub     ecx, 1
0x14001c5c8  jz      loc_14001CA91
0x14001c5ce  cmp     ecx, 1
0x14001c5d1  jnz     loc_14001CAAE
0x14001c5d7  mov     rcx, [r13+60h]; Lookaside
0x14001c5db  mov     rdx, r13; Entry
0x14001c5de  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001c5e5  nop     dword ptr [rax+rax+00h]
0x14001c5ea  jmp     loc_14001CAAE
0x14001c5ef  test    r15b, r15b
0x14001c5f2  jz      short loc_14001C616
0x14001c5f4  mov     eax, cs:dword_140013058
0x14001c5fa  mov     r8d, 0C0000236h
0x14001c600  mov     edi, r8d
0x14001c603  cmp     eax, 2
0x14001c606  jbe     loc_14001C564
0x14001c60c  mov     edx, 24Fh
0x14001c611  jmp     loc_14001C555
0x14001c616  cmp     byte ptr [rsi+0BAh], 0
0x14001c61d  jz      short loc_14001C647
0x14001c61f  cmp     [rbp+var_24], 0
0x14001c623  jnz     short loc_14001C647
0x14001c625  mov     eax, cs:dword_140013058
0x14001c62b  mov     r8d, 0C0000236h
0x14001c631  mov     edi, r8d
0x14001c634  cmp     eax, 2
0x14001c637  jbe     loc_14001C564
0x14001c63d  mov     edx, 256h
0x14001c642  jmp     loc_14001C555
0x14001c647  mov     r15, [rbp+Buf2]
0x14001c64b  mov     rcx, [rbp+arg_0]
0x14001c64f  lea     r8, [rbp+P]
0x14001c653  xor     edx, edx
0x14001c655  call    VmbusTlCreateConnection
0x14001c65a  mov     rbx, [rbp+P]
0x14001c65e  mov     edi, eax
0x14001c660  mov     [rbp+var_24], eax
0x14001c663  test    eax, eax
0x14001c665  mov     eax, cs:dword_140013058
0x14001c66b  jns     loc_14001C747
0x14001c671  cmp     eax, 2
0x14001c674  jbe     loc_14001C9A5
0x14001c67a  mov     edx, 26Dh
0x14001c67f  mov     r9, [rbp+arg_28]
0x14001c683  lea     rcx, aVmbustlprocess_2; "VmbusTlProcessNewConnectionForListener"
0x14001c68a  mov     r8d, edi
0x14001c68d  mov     [rsp+58h+var_38], r15
0x14001c692  call    HvsocketTraceServiceError
0x14001c697  jmp     loc_14001C9A5
0x14001c69c  mov     edx, 69706E56h; Tag
0x14001c6a1  mov     rcx, rsi; P
0x14001c6a4  call    cs:__imp_ExFreePoolWithTag
0x14001c6ab  nop     dword ptr [rax+rax+00h]
0x14001c6b0  jmp     short loc_14001C6B9
0x14001c6b2  mov     ecx, 0Eh
0x14001c6b7  int     29h; Win8: RtlFailFast(ecx)
0x14001c6b9  mov     eax, cs:dword_140013058
0x14001c6bf  xor     esi, esi
0x14001c6c1  mov     r8d, 0C0000236h
0x14001c6c7  mov     edi, r8d
0x14001c6ca  cmp     eax, 2
0x14001c6cd  jbe     loc_14001C56B
0x14001c6d3  mov     r9, rbx
0x14001c6d6  mov     [rsp+58h+var_38], r15
0x14001c6db  mov     edx, 239h
0x14001c6e0  lea     rcx, aVmbustlprocess_2; "VmbusTlProcessNewConnectionForListener"
0x14001c6e7  call    HvsocketTraceServiceError
0x14001c6ec  jmp     loc_14001C56B
0x14001c6f1  mov     r8d, 10h; Size
0x14001c6f7  lea     rdx, HV_GUID_PARENT; Buf2
0x14001c6fe  mov     rcx, rdi; Buf1
0x14001c701  xor     r12b, r12b
0x14001c704  call    memcmp
0x14001c709  test    eax, eax
0x14001c70b  jz      loc_14001C64B
0x14001c711  mov     eax, cs:dword_140013058
0x14001c717  mov     r8d, 0C0000236h
0x14001c71d  mov     edi, r8d
0x14001c720  cmp     eax, 2
0x14001c723  jbe     short loc_14001C73E
0x14001c725  mov     r9, rbx
0x14001c728  mov     [rsp+58h+var_38], r15
0x14001c72d  mov     edx, 260h
0x14001c732  lea     rcx, aVmbustlprocess_2; "VmbusTlProcessNewConnectionForListener"
0x14001c739  call    HvsocketTraceServiceError
0x14001c73e  mov     rsi, [rbp+Entry]
0x14001c742  jmp     loc_14001C564
0x14001c747  cmp     eax, 5
0x14001c74a  jbe     short loc_14001C770
0x14001c74c  mov     r9, [rbx+8]
0x14001c750  lea     rax, aReferenceObjec; "Reference object"
0x14001c757  mov     r8, rbx
0x14001c75a  mov     [rsp+58h+var_38], rax
0x14001c75f  mov     edx, 273h
0x14001c764  lea     rcx, aVmbustlprocess_2; "VmbusTlProcessNewConnectionForListener"
0x14001c76b  call    HvsocketTraceReferenceCount
0x14001c770  mov     eax, 1
0x14001c775  lock xadd [rbx+8], rax
0x14001c77b  inc     rax
0x14001c77e  cmp     rax, 1
0x14001c782  jg      short loc_14001C78B
0x14001c784  mov     ecx, 0Eh
0x14001c789  int     29h; Win8: RtlFailFast(ecx)
0x14001c78b  or      dword ptr [rbx+204h], 2
0x14001c792  mov     edx, 22h ; '"'
0x14001c797  mov     rax, [rbp+arg_38]
0x14001c79e  mov     rdi, [rbp+Buf1]
0x14001c7a2  movups  xmm0, xmmword ptr [rax]
0x14001c7a5  mov     rax, [rbp+arg_28]
0x14001c7a9  movdqu  xmmword ptr [rbx+1D0h], xmm0
0x14001c7b1  mov     [rbx+88h], dx
0x14001c7b8  movups  xmm0, xmmword ptr [rdi]
0x14001c7bb  movdqu  xmmword ptr [rbx+8Ch], xmm0
0x14001c7c3  movups  xmm1, xmmword ptr [rax]
0x14001c7c6  mov     al, [rbp+var_28]
0x14001c7c9  movdqu  xmmword ptr [rbx+9Ch], xmm1
0x14001c7d1  mov     [rbx+0B9h], r12b
0x14001c7d8  mov     [rbx+0BAh], al
0x14001c7de  movups  xmm0, xmmword ptr [r15]
0x14001c7e2  mov     eax, [rbp+arg_40]
0x14001c7e8  movdqu  xmmword ptr [rbx+370h], xmm0
0x14001c7f0  test    al, 4
0x14001c7f2  jz      short loc_14001C7FB
0x14001c7f4  or      dword ptr [rbx+204h], 4
0x14001c7fb  mov     r12, [rbp+arg_20]
  ... truncated ...
```
