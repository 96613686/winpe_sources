# VmbusTlConnectComplete

- ea: `0x1400023b0`
- end: `0x1400028c8`
- name: `VmbusTlConnectComplete`
- size: `1304`
- prototype: `bool __fastcall(char *P, int *)`
- caller_count: `12`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140001fa0`
- `0x1400059b8`
- `0x140008c0c`
- `0x14000af30`
- `0x14000b5f0`
- `0x140019110`
- `0x14001bd20`
- `0x14001c2d0`
- `0x14001cc80`
- `0x140020b80`
- `0x14002509c`
- `0x140025e9c`

## callees

- `0x140001008`
- `0x140001e90`
- `0x1400020c4`
- `0x14000227c`
- `0x1400022e4`
- `0x1400023b0`
- `0x140002d08`
- `0x140002e48`
- `0x1400058d0`
- `0x140007160`
- `0x140009834`
- `0x1400098f4`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400023f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400024a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400023f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400024a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002441`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400024c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002441`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400024c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400024e4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002500`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400024e4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002500`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400024d8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400024f4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400024d8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400024f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002889`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002889`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002464`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002487`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002464`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002487`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002873`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002873`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002474`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002497`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002474`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002497`
- `ntoskrnl!PsGetProcessId` at `0x1400026d4`
- `ntoskrnl!PsGetProcessId` at `0x1400026d4`

## string_xrefs

- `0x1400025dd`: `VmbusTlConnectComplete`
- `0x14000262c`: `VmbusTlConnectComplete`
- `0x1400027a6`: `VmbusTlConnectComplete`
- `0x140002826`: `VmbusTlConnectComplete`

## pseudocode

```c
bool __fastcall VmbusTlConnectComplete(char *P, int *a2)
{
  int v2; // r14d
  KSPIN_LOCK *v3; // r12
  KIRQL v5; // di
  int v6; // r15d
  int v7; // r13d
  bool v8; // r13
  __int64 v9; // rbx
  void (__fastcall *v10)(_QWORD, _QWORD, char *, __int64 (__fastcall **)()); // rax
  int v11; // edx
  __int64 v12; // rax
  struct _KPROCESS *v13; // rcx
  unsigned int ProcessId; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // rax
  void (__fastcall *v20)(char *); // rax
  bool result; // al
  char v22; // [rsp+30h] [rbp-89h] BYREF
  bool v23; // [rsp+31h] [rbp-88h]
  __int64 v24; // [rsp+38h] [rbp-81h] BYREF
  char *v25; // [rsp+40h] [rbp-79h] BYREF
  int *v26; // [rsp+48h] [rbp-71h]
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+50h] [rbp-69h] BYREF
  const char *v28; // [rsp+70h] [rbp-49h]
  __int64 v29; // [rsp+78h] [rbp-41h]
  __int64 *v30; // [rsp+80h] [rbp-39h]
  __int64 v31; // [rsp+88h] [rbp-31h]
  char *v32; // [rsp+90h] [rbp-29h]
  __int64 v33; // [rsp+98h] [rbp-21h]
  char *v34; // [rsp+A0h] [rbp-19h]
  __int64 v35; // [rsp+A8h] [rbp-11h]
  char **v36; // [rsp+B0h] [rbp-9h]
  __int64 v37; // [rsp+B8h] [rbp-1h]
  char *v38; // [rsp+C0h] [rbp+7h]
  __int64 v39; // [rsp+C8h] [rbp+Fh]

  v2 = *a2;
  v3 = (KSPIN_LOCK *)(P + 72);
  v26 = a2;
  LODWORD(v24) = v2;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 9);
  VmbusTlConnectCancelTimer(P);
  VmbusTlRemoveCancellable(*((_QWORD *)P + 14), P);
  v6 = *((_DWORD *)P + 129);
  v7 = *((_DWORD *)P + 238);
  v23 = (v6 & 0x200) == 0;
  *((_DWORD *)P + 129) = v6 | 0x200;
  KeReleaseSpinLock(v3, v5);
  if ( (v6 & 0x200) != 0 )
    goto LABEL_51;
  v8 = 0;
  if ( (v6 & 0x30) != 0 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(P + 16));
    v9 = *((_QWORD *)P + 109);
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 16));
    LOBYTE(v9) = KeAcquireSpinLockRaiseToDpc(v3);
    HvSocketUnPendConnectionLocked(P);
    KeReleaseSpinLock(v3, v9);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*((_QWORD *)P + 109) + 16LL));
    KeLeaveCriticalRegion();
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(P + 16));
    KeLeaveCriticalRegion();
  }
  if ( (*((_DWORD *)P + 129) & 2) != 0 )
  {
    if ( v2 >= 0 )
    {
      VmbusTlInboundConnectComplete(P, &v24);
      v2 = v24;
      v8 = (int)v24 < 0;
    }
  }
  else
  {
    if ( v2 >= 0 )
      VmbusTlCommonPrepareSuccessfulConnection((__int64)P);
    v10 = (void (__fastcall *)(_QWORD, _QWORD, char *, __int64 (__fastcall **)()))*((_QWORD *)P + 84);
    if ( v10 )
    {
      v10(*((_QWORD *)P + 85), (unsigned int)v2, P, VmbusTlProviderConnectDispatch);
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)P + 14) + 1224LL), 1u);
      if ( !v2 )
      {
        _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)P + 14) + 1228LL), 1u);
        _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)P + 14) + 1252LL), 1u);
      }
      VmbusTlEndpointClearPendingConnectRequest(P);
    }
  }
  VmbusTlCommonConnectCompletion((__int64)P, v2);
  if ( v2 >= 0 )
  {
    if ( (unsigned int)dword_140013058 > 4 )
    {
      v13 = (struct _KPROCESS *)*((_QWORD *)P + 34);
      v28 = "A Hyper-V socket connection has been established.";
      v29 = 50;
      ProcessId = (unsigned int)PsGetProcessId(v13);
      v33 = 16;
      v15 = ProcessId;
      v30 = &v24;
      v32 = P + 140;
      v34 = P + 156;
      v36 = &v25;
      LOBYTE(ProcessId) = (*((_DWORD *)P + 129) & 2) != 0;
      v24 = v15;
      v22 = ProcessId;
      v31 = 8;
      v38 = &v22;
      v37 = 8;
      v35 = 16;
      v25 = P;
      v39 = 1;
      tlgWriteTransfer_EtwWriteTransfer(
        (__int64)&dword_140013058,
        (unsigned __int8 *)&word_140011306,
        v16,
        v17,
        8u,
        &v27);
    }
    goto LABEL_31;
  }
  if ( (unsigned int)dword_140013058 > 2 )
    HvsocketTraceEndpointGuidError(
      (const int *)"VmbusTlConnectComplete",
      776,
      (unsigned int)v2,
      (__int64)P,
      (__int64)(P + 140));
  if ( !v8 )
  {
    P[296] = 1;
    if ( (unsigned int)dword_140013058 <= 5 )
    {
LABEL_21:
      v12 = _InterlockedDecrement64((volatile signed __int64 *)P + 38);
      if ( v12 <= 0 )
      {
        if ( v12 )
          __fastfail(0xEu);
        if ( (unsigned int)dword_140013058 > 4 )
          HvsocketTraceEndpointEvent(
            (const int *)"VmbusTlDereferenceEndpointInternal cleaning up the endpoint.",
            (__int64)P,
            9);
        VmbusTlQueueEndpointAction(P, P + 200, 9);
      }
      goto LABEL_31;
    }
    v11 = 790;
LABEL_20:
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlConnectComplete",
      v11,
      (__int64)P,
      *((_QWORD *)P + 38),
      (const int *)"Initial reference. (deref)");
    goto LABEL_21;
  }
  if ( !P[296] )
  {
    P[296] = 1;
    if ( (unsigned int)dword_140013058 <= 5 )
      goto LABEL_21;
    v11 = 786;
    goto LABEL_20;
  }
LABEL_31:
  v7 = *((_DWORD *)P + 238);
  if ( (*((_DWORD *)P + 129) & 8) != 0 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlConnectComplete",
        818,
        (__int64)P,
        *((_QWORD *)P + 38),
        (const int *)"Pending setup connection. (deref)");
    v18 = _InterlockedDecrement64((volatile signed __int64 *)P + 38);
    if ( v18 <= 0 )
    {
      if ( v18 )
        __fastfail(0xEu);
      if ( (unsigned int)dword_140013058 > 4 )
        HvsocketTraceEndpointEvent(
          (const int *)"VmbusTlDereferenceEndpointInternal cleaning up the endpoint.",
          (__int64)P,
          9);
      VmbusTlQueueEndpointAction(P, P + 200, 9);
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlConnectComplete",
        819,
        (__int64)P,
        *((_QWORD *)P + 1),
        (const int *)"Dereference object");
    v19 = _InterlockedDecrement64((volatile signed __int64 *)P + 1);
    if ( v19 <= 0 )
    {
      if ( v19 )
        __fastfail(0xEu);
      v20 = (void (__fastcall *)(char *))*((_QWORD *)P + 10);
      if ( v20 )
        v20(P);
      if ( *((_DWORD *)P + 22) == 1 )
      {
        ExFreePoolWithTag(P, 0x69706E56u);
      }
      else if ( *((_DWORD *)P + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)P + 12), P);
      }
    }
  }
LABEL_51:
  result = v23;
  *v26 = v7;
  return result;
}

```

## disassembly

```asm
0x1400023b0  mov     [rsp-8+arg_10], rbx
0x1400023b5  push    rbp
0x1400023b6  push    rsi
0x1400023b7  push    rdi
0x1400023b8  push    r12
0x1400023ba  push    r13
0x1400023bc  push    r14
0x1400023be  push    r15
0x1400023c0  lea     rbp, [rsp-27h]
0x1400023c5  sub     rsp, 0E0h
0x1400023cc  mov     rax, cs:__security_cookie
0x1400023d3  xor     rax, rsp
0x1400023d6  mov     [rbp+57h+var_40], rax
0x1400023da  mov     r14d, [rdx]
0x1400023dd  lea     r12, [rcx+48h]
0x1400023e1  mov     rsi, rcx
0x1400023e4  mov     [rbp+57h+var_C8], rdx
0x1400023e8  mov     rcx, r12; SpinLock
0x1400023eb  mov     dword ptr [rsp+110h+var_D8], r14d
0x1400023f0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400023f7  nop     dword ptr [rax+rax+00h]
0x1400023fc  mov     rcx, rsi; P
0x1400023ff  mov     dil, al
0x140002402  call    VmbusTlConnectCancelTimer
0x140002407  mov     rcx, [rsi+70h]
0x14000240b  mov     rdx, rsi
0x14000240e  call    VmbusTlRemoveCancellable
0x140002413  mov     r15d, [rsi+204h]
0x14000241a  mov     eax, 200h
0x14000241f  mov     r13d, [rsi+3B8h]
0x140002426  mov     ecx, r15d
0x140002429  mov     ebx, r15d
0x14000242c  mov     dl, dil; NewIrql
0x14000242f  and     ebx, eax
0x140002431  setz    [rsp+110h+var_DF]
0x140002436  or      ecx, eax
0x140002438  mov     [rsi+204h], ecx
0x14000243e  mov     rcx, r12; SpinLock
0x140002441  call    cs:__imp_KeReleaseSpinLock
0x140002448  nop     dword ptr [rax+rax+00h]
0x14000244d  xor     edi, edi
0x14000244f  test    ebx, ebx
0x140002451  jnz     loc_140002895
0x140002457  mov     r13b, dil
0x14000245a  test    r15b, 30h
0x14000245e  jz      loc_14000250C
0x140002464  call    cs:__imp_KeEnterCriticalRegion
0x14000246b  nop     dword ptr [rax+rax+00h]
0x140002470  lea     rcx, [rsi+10h]; FastMutex
0x140002474  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000247b  nop     dword ptr [rax+rax+00h]
0x140002480  mov     rbx, [rsi+368h]
0x140002487  call    cs:__imp_KeEnterCriticalRegion
0x14000248e  nop     dword ptr [rax+rax+00h]
0x140002493  lea     rcx, [rbx+10h]; FastMutex
0x140002497  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000249e  nop     dword ptr [rax+rax+00h]
0x1400024a3  mov     rcx, r12; SpinLock
0x1400024a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400024ad  nop     dword ptr [rax+rax+00h]
0x1400024b2  mov     rcx, rsi
0x1400024b5  mov     bl, al
0x1400024b7  call    HvSocketUnPendConnectionLocked
0x1400024bc  mov     dl, bl; NewIrql
0x1400024be  mov     rcx, r12; SpinLock
0x1400024c1  call    cs:__imp_KeReleaseSpinLock
0x1400024c8  nop     dword ptr [rax+rax+00h]
0x1400024cd  mov     rcx, [rsi+368h]
0x1400024d4  add     rcx, 10h; FastMutex
0x1400024d8  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400024df  nop     dword ptr [rax+rax+00h]
0x1400024e4  call    cs:__imp_KeLeaveCriticalRegion
0x1400024eb  nop     dword ptr [rax+rax+00h]
0x1400024f0  lea     rcx, [rsi+10h]; FastMutex
0x1400024f4  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400024fb  nop     dword ptr [rax+rax+00h]
0x140002500  call    cs:__imp_KeLeaveCriticalRegion
0x140002507  nop     dword ptr [rax+rax+00h]
0x14000250c  mov     eax, [rsi+204h]
0x140002512  mov     r15d, 1
0x140002518  test    al, 2
0x14000251a  jz      short loc_14000253C
0x14000251c  test    r14d, r14d
0x14000251f  js      short loc_14000259F
0x140002521  lea     rdx, [rsp+110h+var_D8]
0x140002526  mov     rcx, rsi
0x140002529  call    VmbusTlInboundConnectComplete
0x14000252e  mov     r14d, dword ptr [rsp+110h+var_D8]
0x140002533  test    r14d, r14d
0x140002536  sets    r13b
0x14000253a  jmp     short loc_14000259F
0x14000253c  test    r14d, r14d
0x14000253f  js      short loc_140002549
0x140002541  mov     rcx, rsi
0x140002544  call    VmbusTlCommonPrepareSuccessfulConnection
0x140002549  mov     rax, [rsi+2A0h]
0x140002550  test    rax, rax
0x140002553  jz      short loc_14000259F
0x140002555  mov     rcx, [rsi+2A8h]
0x14000255c  lea     r9, VmbusTlProviderConnectDispatch
0x140002563  mov     r8, rsi
0x140002566  mov     edx, r14d
0x140002569  call    _guard_dispatch_icall
0x14000256e  mov     rax, [rsi+70h]
0x140002572  lock add [rax+4C8h], r15d
0x14000257a  test    r14d, r14d
0x14000257d  jnz     short loc_140002597
0x14000257f  mov     rax, [rsi+70h]
0x140002583  lock add [rax+4CCh], r15d
0x14000258b  mov     rax, [rsi+70h]
0x14000258f  lock add [rax+4E4h], r15d
0x140002597  mov     rcx, rsi; P
0x14000259a  call    VmbusTlEndpointClearPendingConnectRequest
0x14000259f  mov     edx, r14d
0x1400025a2  mov     rcx, rsi
0x1400025a5  call    VmbusTlCommonConnectCompletion
0x1400025aa  mov     eax, cs:dword_140013058
0x1400025b0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400025b4  lea     r12d, [rbx+0Ah]
0x1400025b8  test    r14d, r14d
0x1400025bb  jns     loc_1400026B1
0x1400025c1  cmp     eax, 2
0x1400025c4  jbe     short loc_1400025E9
0x1400025c6  lea     rax, [rsi+8Ch]
0x1400025cd  mov     r9, rsi
0x1400025d0  mov     r8d, r14d
0x1400025d3  mov     qword ptr [rsp+110h+var_F0], rax
0x1400025d8  mov     edx, 308h
0x1400025dd  lea     rcx, aVmbustlconnect_4; "VmbusTlConnectComplete"
0x1400025e4  call    HvsocketTraceEndpointGuidError
0x1400025e9  test    r13b, r13b
0x1400025ec  jz      loc_140002689
0x1400025f2  cmp     [rsi+128h], dil
0x1400025f9  jnz     loc_14000276B
0x1400025ff  mov     [rsi+128h], r15b
0x140002606  mov     eax, cs:dword_140013058
0x14000260c  cmp     eax, 5
0x14000260f  jbe     short loc_140002638
0x140002611  mov     edx, 312h
0x140002616  mov     r9, [rsi+130h]
0x14000261d  lea     rax, aInitialReferen; "Initial reference. (deref)"
0x140002624  mov     r8, rsi
0x140002627  mov     qword ptr [rsp+110h+var_F0], rax
0x14000262c  lea     rcx, aVmbustlconnect_4; "VmbusTlConnectComplete"
0x140002633  call    HvsocketTraceReferenceCount
0x140002638  mov     rax, rbx
0x14000263b  lock xadd [rsi+130h], rax
0x140002644  add     rax, rbx
0x140002647  test    rax, rax
0x14000264a  jg      loc_14000276B
0x140002650  jnz     short loc_1400026A5
0x140002652  mov     eax, cs:dword_140013058
0x140002658  cmp     eax, 4
0x14000265b  jbe     short loc_14000266F
0x14000265d  mov     r8d, r12d
0x140002660  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x140002667  mov     rdx, rsi
0x14000266a  call    HvsocketTraceEndpointEvent
0x14000266f  lea     rdx, [rsi+0C8h]
0x140002676  xor     r9d, r9d
0x140002679  mov     r8d, r12d
0x14000267c  mov     rcx, rsi
0x14000267f  call    VmbusTlQueueEndpointAction
0x140002684  jmp     loc_14000276B
0x140002689  mov     [rsi+128h], r15b
0x140002690  mov     eax, cs:dword_140013058
0x140002696  cmp     eax, 5
0x140002699  jbe     short loc_140002638
0x14000269b  mov     edx, 316h
0x1400026a0  jmp     loc_140002616
0x1400026a5  mov     ecx, 0Eh
0x1400026aa  int     29h; Win8: RtlFailFast(ecx)
0x1400026ac  jmp     loc_14000276B
0x1400026b1  cmp     eax, 4
0x1400026b4  jbe     loc_14000276B
0x1400026ba  mov     rcx, [rsi+110h]; Process
0x1400026c1  lea     rax, aAHyperVSocketC_2; "A Hyper-V socket connection has been es"...
0x1400026c8  mov     [rbp+57h+var_A0], rax
0x1400026cc  mov     [rbp+57h+var_98], 32h ; '2'
0x1400026d4  call    cs:__imp_PsGetProcessId
0x1400026db  nop     dword ptr [rax+rax+00h]
0x1400026e0  lea     rdx, word_140011306; int
0x1400026e7  mov     [rbp+57h+var_78], 10h
0x1400026ef  mov     ecx, eax
0x1400026f1  lea     rax, [rsp+110h+var_D8]
0x1400026f6  mov     [rbp+57h+var_90], rax
0x1400026fa  lea     rax, [rsi+8Ch]
0x140002701  mov     [rbp+57h+var_80], rax
0x140002705  lea     rax, [rsi+9Ch]
0x14000270c  mov     [rbp+57h+var_70], rax
0x140002710  lea     rax, [rbp+57h+var_D0]
0x140002714  mov     [rbp+57h+var_60], rax
0x140002718  mov     eax, [rsi+204h]
0x14000271e  shr     eax, 1
0x140002720  and     al, r15b
0x140002723  mov     [rsp+110h+var_D8], rcx
0x140002728  mov     ecx, 8
0x14000272d  mov     [rsp+110h+var_E0], al
0x140002731  lea     rax, [rsp+110h+var_E0]
0x140002736  mov     [rbp+57h+var_88], rcx
0x14000273a  mov     [rbp+57h+var_50], rax
0x14000273e  lea     rax, [rbp+57h+var_C0]
0x140002742  mov     [rsp+110h+var_E8], rax; __int64
0x140002747  mov     [rsp+110h+var_F0], ecx; ULONG
0x14000274b  mov     [rbp+57h+var_58], rcx
0x14000274f  lea     rcx, dword_140013058; int
0x140002756  mov     [rbp+57h+var_68], 10h
0x14000275e  mov     [rbp+57h+var_D0], rsi
0x140002762  mov     [rbp+57h+var_48], r15
0x140002766  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000276b  mov     eax, [rsi+204h]
0x140002771  mov     r13d, [rsi+3B8h]
0x140002778  test    al, 8
0x14000277a  jz      loc_140002895
0x140002780  mov     eax, cs:dword_140013058
0x140002786  cmp     eax, 5
0x140002789  jbe     short loc_1400027B2
0x14000278b  mov     r9, [rsi+130h]
0x140002792  lea     rax, aPendingSetupCo_0; "Pending setup connection. (deref)"
0x140002799  mov     r8, rsi
0x14000279c  mov     qword ptr [rsp+110h+var_F0], rax
0x1400027a1  mov     edx, 332h
0x1400027a6  lea     rcx, aVmbustlconnect_4; "VmbusTlConnectComplete"
0x1400027ad  call    HvsocketTraceReferenceCount
0x1400027b2  mov     rax, rbx
0x1400027b5  lock xadd [rsi+130h], rax
0x1400027be  add     rax, rbx
0x1400027c1  test    rax, rax
0x1400027c4  jg      short loc_140002803
0x1400027c6  jz      short loc_1400027D1
0x1400027c8  mov     ecx, 0Eh
0x1400027cd  int     29h; Win8: RtlFailFast(ecx)
0x1400027cf  jmp     short loc_140002803
0x1400027d1  mov     eax, cs:dword_140013058
0x1400027d7  cmp     eax, 4
0x1400027da  jbe     short loc_1400027EE
0x1400027dc  mov     r8d, r12d
0x1400027df  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x1400027e6  mov     rdx, rsi
0x1400027e9  call    HvsocketTraceEndpointEvent
0x1400027ee  lea     rdx, [rsi+0C8h]
0x1400027f5  xor     r9d, r9d
0x1400027f8  mov     r8d, r12d
0x1400027fb  mov     rcx, rsi
0x1400027fe  call    VmbusTlQueueEndpointAction
0x140002803  mov     eax, cs:dword_140013058
0x140002809  cmp     eax, 5
0x14000280c  jbe     short loc_140002832
0x14000280e  mov     r9, [rsi+8]
0x140002812  lea     rax, aDereferenceObj; "Dereference object"
0x140002819  mov     r8, rsi
0x14000281c  mov     qword ptr [rsp+110h+var_F0], rax
0x140002821  mov     edx, 333h
0x140002826  lea     rcx, aVmbustlconnect_4; "VmbusTlConnectComplete"
0x14000282d  call    HvsocketTraceReferenceCount
0x140002832  mov     rax, rbx
0x140002835  lock xadd [rsi+8], rax
0x14000283b  add     rax, rbx
0x14000283e  test    rax, rax
0x140002841  jg      short loc_140002895
0x140002843  jz      short loc_14000284E
0x140002845  mov     ecx, 0Eh
0x14000284a  int     29h; Win8: RtlFailFast(ecx)
0x14000284c  jmp     short loc_140002895
0x14000284e  mov     rax, [rsi+50h]
0x140002852  test    rax, rax
0x140002855  jz      short loc_14000285F
0x140002857  mov     rcx, rsi
0x14000285a  call    _guard_dispatch_icall
0x14000285f  mov     edx, [rsi+58h]
0x140002862  sub     edx, r15d
0x140002865  jz      short loc_140002881
0x140002867  cmp     edx, r15d
0x14000286a  jnz     short loc_140002895
0x14000286c  mov     rcx, [rsi+60h]; Lookaside
0x140002870  mov     rdx, rsi; Entry
0x140002873  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000287a  nop     dword ptr [rax+rax+00h]
0x14000287f  jmp     short loc_140002895
0x140002881  mov     edx, 69706E56h; Tag
0x140002886  mov     rcx, rsi; P
0x140002889  call    cs:__imp_ExFreePoolWithTag
0x140002890  nop     dword ptr [rax+rax+00h]
0x140002895  mov     rcx, [rbp+57h+var_C8]
0x140002899  mov     al, [rsp+110h+var_DF]
0x14000289d  mov     [rcx], r13d
0x1400028a0  mov     rcx, [rbp+57h+var_40]
0x1400028a4  xor     rcx, rsp; StackCookie
0x1400028a7  call    __security_check_cookie
0x1400028ac  mov     rbx, [rsp+110h+arg_10]
0x1400028b4  add     rsp, 0E0h
0x1400028bb  pop     r15
0x1400028bd  pop     r14
0x1400028bf  pop     r13
0x1400028c1  pop     r12
0x1400028c3  pop     rdi
0x1400028c4  pop     rsi
0x1400028c5  pop     rbp
0x1400028c6  retn
```
