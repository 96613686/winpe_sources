# VmbusTlProviderListen

- ea: `0x140021550`
- end: `0x140021cad`
- name: `VmbusTlProviderListen`
- size: `1885`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x140004dec`
- `0x1400058d0`
- `0x140009834`
- `0x1400098f4`
- `0x140009cf8`
- `0x140009df0`
- `0x140009ec0`
- `0x14000a048`
- `0x14000a154`
- `0x14000a2c8`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14001b578`
- `0x14001b74c`
- `0x14001dfd8`
- `0x14001e5ac`
- `0x14001f540`
- `0x14001febc`
- `0x140021550`

## import_xrefs

- `ntoskrnl!PsGetSiloContainerId` at `0x1400216c9`
- `ntoskrnl!PsGetSiloContainerId` at `0x1400216c9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021741`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021a24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021741`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021a24`
- `ntoskrnl!PsGetProcessServerSilo` at `0x1400216ba`
- `ntoskrnl!PsGetProcessServerSilo` at `0x1400216ba`
- `ntoskrnl!PsGetThreadServerSilo` at `0x1400216a9`
- `ntoskrnl!PsGetThreadServerSilo` at `0x1400216a9`
- `ntoskrnl!PsGetCurrentProcess` at `0x140021690`
- `ntoskrnl!PsGetCurrentProcess` at `0x140021690`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140021735`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140021a18`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140021735`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140021a18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021adb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021be3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021adb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021be3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140021704`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400219f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140021704`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400219f1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140021ac2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140021bcd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140021ac2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140021bcd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140021717`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140021a01`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140021717`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140021a01`
- `ntoskrnl!PsGetProcessId` at `0x140021801`
- `ntoskrnl!PsGetProcessId` at `0x140021955`
- `ntoskrnl!PsGetProcessId` at `0x140021b09`
- `ntoskrnl!PsGetProcessId` at `0x140021801`
- `ntoskrnl!PsGetProcessId` at `0x140021955`
- `ntoskrnl!PsGetProcessId` at `0x140021b09`

## pseudocode

```c
__int64 __fastcall VmbusTlProviderListen(__int64 a1, __int64 a2)
{
  int v2; // eax
  __int64 v5; // rdi
  const char *v6; // rdx
  __int128 v7; // xmm6
  __int64 v8; // rbx
  struct _KPROCESS *CurrentProcess; // rsi
  __int64 v10; // r13
  signed __int64 v11; // rax
  bool v12; // cc
  signed __int64 v13; // rax
  __int64 v14; // rcx
  __int64 ThreadServerSilo; // rax
  __int64 SiloContainerId; // rax
  const GUID *v17; // rcx
  _QWORD *v18; // rax
  struct _FAST_MUTEX *v19; // rcx
  __int64 v20; // r14
  int v21; // ebx
  int v22; // eax
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // r13
  unsigned __int8 IsPassthruRequest; // al
  int ProcessId; // eax
  __int64 v28; // rax
  void (__fastcall *v29)(__int64); // rax
  unsigned int v30; // eax
  __int64 v31; // rax
  void (__fastcall *v32)(__int64); // rax
  __int64 v33; // rax
  __int64 v35; // [rsp+30h] [rbp-40h] BYREF
  __int64 v36; // [rsp+38h] [rbp-38h]
  __int64 v37; // [rsp+40h] [rbp-30h]
  GUID v38; // [rsp+48h] [rbp-28h] BYREF

  v2 = *(_DWORD *)(a2 + 16);
  v36 = a1;
  v35 = 0;
  v5 = 0;
  v6 = "Initial reference. (deref)";
  v7 = 0;
  v38 = 0;
  if ( v2 >= 0 )
  {
    v21 = -1073741808;
    if ( (unsigned int)dword_140013058 <= 2 )
      return (unsigned int)v21;
    HvsocketTraceError(
      (const int *)"VmbusTlProviderListen",
      191,
      3221225488LL,
      (const int *)"Required base endpoint not present.");
LABEL_69:
    if ( v5 )
    {
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (const int *)"VmbusTlProviderListen",
          332,
          v5,
          *(_QWORD *)(v5 + 8),
          (const int *)"Dereference object");
      v31 = _InterlockedDecrement64((volatile signed __int64 *)(v5 + 8));
      if ( v31 <= 0 )
      {
        if ( v31 )
          __fastfail(0xEu);
        v32 = *(void (__fastcall **)(__int64))(v5 + 80);
        if ( v32 )
          v32(v5);
        if ( *(_DWORD *)(v5 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v5, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v5 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 96), (PVOID)v5);
        }
      }
      if ( v21 < 0 )
      {
        *(_BYTE *)(v5 + 296) = 1;
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (const int *)"VmbusTlProviderListen",
            337,
            v5,
            *(_QWORD *)(v5 + 304),
            (const int *)"Initial reference. (deref)");
        v33 = _InterlockedDecrement64((volatile signed __int64 *)(v5 + 304));
        if ( v33 <= 0 )
        {
          if ( v33 )
            __fastfail(0xEu);
          if ( (unsigned int)dword_140013058 > 4 )
            HvsocketTraceEndpointEvent(
              (const int *)"VmbusTlDereferenceEndpointInternal cleaning up the endpoint.",
              v5,
              9);
          VmbusTlQueueEndpointAction(v5, v5 + 200, 9);
        }
      }
    }
    return (unsigned int)v21;
  }
  v8 = *(_QWORD *)(a2 + 24);
  if ( v8 )
  {
    CurrentProcess = *(struct _KPROCESS **)(v8 + 272);
    v10 = v8 + 136;
    v38 = *(GUID *)(v8 + 280);
    v7 = *(_OWORD *)(v8 + 176);
    if ( (v2 & 1) == 0 )
    {
      *(_BYTE *)(v8 + 296) = 1;
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (const int *)"VmbusTlProviderListen",
          220,
          v8,
          *(_QWORD *)(v8 + 304),
          (const int *)"Initial reference. (deref)");
      v11 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v8 + 304), 0xFFFFFFFFFFFFFFFFuLL);
      v12 = v11 <= 1;
      v13 = v11 - 1;
      if ( v12 )
      {
        if ( v13 )
          __fastfail(0xEu);
        if ( (unsigned int)dword_140013058 > 4 )
          HvsocketTraceEndpointEvent((const int *)"VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", v8, 9);
        VmbusTlQueueEndpointAction(v8, v8 + 200, 9);
      }
    }
  }
  else
  {
    CurrentProcess = *(struct _KPROCESS **)(a2 + 40);
    v10 = *(_QWORD *)(a2 + 64);
    if ( !CurrentProcess )
      CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(0, "Initial reference. (deref)");
    v14 = *(_QWORD *)(a2 + 48);
    if ( v14 )
      ThreadServerSilo = PsGetThreadServerSilo(v14, v6);
    else
      ThreadServerSilo = PsGetProcessServerSilo(CurrentProcess);
    SiloContainerId = PsGetSiloContainerId(ThreadServerSilo);
    v17 = &HV_GUID_CHILDREN;
    if ( SiloContainerId )
      v17 = (const GUID *)SiloContainerId;
    v38 = *v17;
  }
  if ( *(_WORD *)v10 == 34 && !*(_WORD *)(v10 + 2) )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v18 = VmbusTlFindAndReferencePartition(a1, &v38);
    v19 = (struct _FAST_MUTEX *)(a1 + 16);
    v20 = (__int64)v18;
    ExReleaseFastMutexUnsafe(v19);
    KeLeaveCriticalRegion();
    if ( !v20 )
    {
      v21 = -1073741275;
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceGuidError((const int *)"VmbusTlProviderListen", 246, 3221226021LL, (__int64)&v38);
      return (unsigned int)v21;
    }
    v37 = v10 + 4;
    v21 = HvSocketResolveUniversalAddress(v36, v20, v10 + 4, v10 + 4);
    if ( v21 >= 0 )
    {
      v21 = VmbusTlCreateListenEndpoint(v36, CurrentProcess, &v35);
      if ( v21 >= 0 )
      {
        v5 = v35;
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (const int *)"VmbusTlProviderListen",
            268,
            v35,
            *(_QWORD *)(v35 + 8),
            (const int *)"Reference object");
        if ( _InterlockedIncrement64((volatile signed __int64 *)(v5 + 8)) <= 1 )
          __fastfail(0xEu);
        v23 = v10;
        *(_OWORD *)(v5 + 136) = *(_OWORD *)v10;
        *(_OWORD *)(v5 + 152) = *(_OWORD *)(v10 + 16);
        v24 = *(_DWORD *)(v10 + 32);
        v25 = v36;
        *(_DWORD *)(v5 + 168) = v24;
        *(GUID *)(v5 + 280) = v38;
        *(_OWORD *)(v5 + 176) = v7;
        IsPassthruRequest = HvSocketIsPassthruRequest(v25, v23, v20, v5 + 392);
        *(_DWORD *)(v5 + 344) ^= (*(_DWORD *)(v5 + 344) ^ IsPassthruRequest) & 1;
        v21 = VmbusTlResolvePartitionId(v25, v20, (int)v5 + 140, 2 * (IsPassthruRequest & 1u) + 1, v5 + 376);
        if ( v21 >= 0 )
        {
          *(_QWORD *)(v5 + 336) = *(_QWORD *)(a2 + 88);
          *(_QWORD *)(v5 + 352) = *(_QWORD *)(a2 + 72);
          v21 = VmbusTlAssociateListenerToPartition(v5, v20);
          if ( v21 >= 0 )
          {
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64 (__fastcall **)()))a2)(
              *(_QWORD *)(a2 + 8),
              (unsigned int)v21,
              v5,
              VmbusTlProviderListenDispatch);
            KeEnterCriticalRegion();
            ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v5 + 16));
            *(_BYTE *)(v5 + 425) = 1;
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 16));
            KeLeaveCriticalRegion();
            _InterlockedIncrement((volatile signed __int32 *)(v25 + 1164));
            HvSocketListenerProcessPendingConnectionsList(v25, v5);
            v21 = 259;
          }
          else if ( (unsigned int)dword_140013058 > 2 )
          {
            HvsocketTraceEndpointGuidError((const int *)"VmbusTlProviderListen", 302, (unsigned int)v21, v5, v5 + 140);
          }
        }
        else
        {
          if ( (unsigned int)dword_140013058 > 2 )
            HvsocketTraceServiceError((const int *)"VmbusTlProviderListen", 286, (unsigned int)v21, v5 + 156, v5 + 140);
          if ( (unsigned int)dword_140013058 > 2 )
          {
            if ( CurrentProcess )
              ProcessId = (unsigned int)PsGetProcessId(CurrentProcess);
            else
              ProcessId = 0;
            HvsocketTraceGuidULongError(
              (const int *)"VmbusTlProviderListen",
              287,
              (unsigned int)v21,
              (__int64)&v38,
              ProcessId);
          }
        }
      }
      else
      {
        if ( (unsigned int)dword_140013058 > 2 )
        {
          if ( CurrentProcess )
            v22 = (unsigned int)PsGetProcessId(CurrentProcess);
          else
            v22 = 0;
          HvsocketTraceGuidULongError((const int *)"VmbusTlProviderListen", 262, (unsigned int)v21, v37, v22);
        }
        v5 = v35;
      }
    }
    else if ( (unsigned int)dword_140013058 > 2 )
    {
      HvsocketTraceServiceError((const int *)"VmbusTlProviderListen", 253, (unsigned int)v21, v10 + 20, v10 + 4);
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlProviderListen",
        326,
        v20,
        *(_QWORD *)(v20 + 8),
        (const int *)"Dereference object");
    v28 = _InterlockedDecrement64((volatile signed __int64 *)(v20 + 8));
    if ( v28 <= 0 )
    {
      if ( v28 )
        __fastfail(0xEu);
      v29 = *(void (__fastcall **)(__int64))(v20 + 80);
      if ( v29 )
        v29(v20);
      if ( *(_DWORD *)(v20 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v20, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v20 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v20 + 96), (PVOID)v20);
      }
    }
    goto LABEL_69;
  }
  v21 = -1073741811;
  if ( (unsigned int)dword_140013058 > 2 )
  {
    if ( CurrentProcess )
      v30 = (unsigned int)PsGetProcessId(CurrentProcess);
    else
      v30 = 0;
    HvsocketTraceULongError((const int *)"VmbusTlProviderListen", 235, 3221225485LL, v30);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140021550  mov     [rsp-38h+arg_10], rbx
0x140021555  push    rbp
0x140021556  push    rsi
0x140021557  push    rdi
0x140021558  push    r12
0x14002155a  push    r13
0x14002155c  push    r14
0x14002155e  push    r15
0x140021560  mov     rbp, rsp
0x140021563  sub     rsp, 70h
0x140021567  movaps  [rsp+70h+var_10], xmm6
0x14002156c  mov     rax, cs:__security_cookie
0x140021573  xor     rax, rsp
0x140021576  mov     [rbp+var_18], rax
0x14002157a  mov     eax, [rdx+10h]
0x14002157d  lea     r13, aDereferenceObj; "Dereference object"
0x140021584  mov     r14, rcx
0x140021587  mov     [rbp+var_38], rcx
0x14002158b  xor     ecx, ecx
0x14002158d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140021591  mov     [rbp+var_40], rcx
0x140021595  xorps   xmm0, xmm0
0x140021598  mov     r12, rdx
0x14002159b  mov     edi, ecx
0x14002159d  lea     rdx, aInitialReferen; "Initial reference. (deref)"
0x1400215a4  xorps   xmm6, xmm6
0x1400215a7  movups  [rbp+var_28], xmm0
0x1400215ab  test    eax, eax
0x1400215ad  jns     loc_140021B2D
0x1400215b3  mov     rbx, [r12+18h]
0x1400215b8  lea     r15, aVmbustlprovide_0; "VmbusTlProviderListen"
0x1400215bf  test    rbx, rbx
0x1400215c2  jz      loc_140021681
0x1400215c8  mov     rsi, [rbx+110h]
0x1400215cf  lea     r13, [rbx+88h]
0x1400215d6  movups  xmm0, xmmword ptr [rbx+118h]
0x1400215dd  movdqu  [rbp+var_28], xmm0
0x1400215e2  movups  xmm6, xmmword ptr [rbx+0B0h]
0x1400215e9  test    al, 1
0x1400215eb  jnz     loc_1400216ED
0x1400215f1  mov     byte ptr [rbx+128h], 1
0x1400215f8  mov     eax, cs:dword_140013058
0x1400215fe  cmp     eax, 5
0x140021601  jbe     short loc_140021621
0x140021603  mov     r9, [rbx+130h]
0x14002160a  mov     r8, rbx
0x14002160d  mov     [rsp+70h+var_50], rdx
0x140021612  mov     rcx, r15
0x140021615  mov     edx, 0DCh
0x14002161a  call    HvsocketTraceReferenceCount
0x14002161f  xor     ecx, ecx
0x140021621  or      rax, 0FFFFFFFFFFFFFFFFh
0x140021625  lock xadd [rbx+130h], rax
0x14002162e  sub     rax, 1
0x140021632  jg      loc_1400216ED
0x140021638  test    rax, rax
0x14002163b  jz      short loc_140021649
0x14002163d  mov     ecx, 0Eh
0x140021642  int     29h; Win8: RtlFailFast(ecx)
0x140021644  jmp     loc_1400216EB
0x140021649  mov     eax, cs:dword_140013058
0x14002164f  cmp     eax, 4
0x140021652  jbe     short loc_140021669
0x140021654  mov     r8d, 9
0x14002165a  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x140021661  mov     rdx, rbx
0x140021664  call    HvsocketTraceEndpointEvent
0x140021669  xor     r9d, r9d
0x14002166c  lea     rdx, [rbx+0C8h]
0x140021673  mov     rcx, rbx
0x140021676  lea     r8d, [r9+9]
0x14002167a  call    VmbusTlQueueEndpointAction
0x14002167f  jmp     short loc_1400216EB
0x140021681  mov     rsi, [r12+28h]
0x140021686  mov     r13, [r12+40h]
0x14002168b  test    rsi, rsi
0x14002168e  jnz     short loc_14002169F
0x140021690  call    cs:__imp_PsGetCurrentProcess
0x140021697  nop     dword ptr [rax+rax+00h]
0x14002169c  mov     rsi, rax
0x14002169f  mov     rcx, [r12+30h]
0x1400216a4  test    rcx, rcx
0x1400216a7  jz      short loc_1400216B7
0x1400216a9  call    cs:__imp_PsGetThreadServerSilo
0x1400216b0  nop     dword ptr [rax+rax+00h]
0x1400216b5  jmp     short loc_1400216C6
0x1400216b7  mov     rcx, rsi
0x1400216ba  call    cs:__imp_PsGetProcessServerSilo
0x1400216c1  nop     dword ptr [rax+rax+00h]
0x1400216c6  mov     rcx, rax
0x1400216c9  call    cs:__imp_PsGetSiloContainerId
0x1400216d0  nop     dword ptr [rax+rax+00h]
0x1400216d5  test    rax, rax
0x1400216d8  lea     rcx, HV_GUID_CHILDREN
0x1400216df  cmovnz  rcx, rax
0x1400216e3  movups  xmm0, xmmword ptr [rcx]
0x1400216e6  movdqu  [rbp+var_28], xmm0
0x1400216eb  xor     ecx, ecx
0x1400216ed  cmp     word ptr [r13+0], 22h ; '"'
0x1400216f3  jnz     loc_140021AE9
0x1400216f9  cmp     [r13+2], cx
0x1400216fe  jnz     loc_140021AE9
0x140021704  call    cs:__imp_KeEnterCriticalRegion
0x14002170b  nop     dword ptr [rax+rax+00h]
0x140021710  lea     rbx, [r14+10h]
0x140021714  mov     rcx, rbx; FastMutex
0x140021717  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002171e  nop     dword ptr [rax+rax+00h]
0x140021723  lea     rdx, [rbp+var_28]
0x140021727  mov     rcx, r14
0x14002172a  call    VmbusTlFindAndReferencePartition
0x14002172f  mov     rcx, rbx; FastMutex
0x140021732  mov     r14, rax
0x140021735  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002173c  nop     dword ptr [rax+rax+00h]
0x140021741  call    cs:__imp_KeLeaveCriticalRegion
0x140021748  nop     dword ptr [rax+rax+00h]
0x14002174d  test    r14, r14
0x140021750  jnz     short loc_14002177F
0x140021752  mov     eax, cs:dword_140013058
0x140021758  mov     ebx, 0C0000225h
0x14002175d  cmp     eax, 2
0x140021760  jbe     loc_140021C81
0x140021766  lea     r9, [rbp+var_28]
0x14002176a  mov     r8d, ebx
0x14002176d  mov     edx, 0F6h
0x140021772  mov     rcx, r15
0x140021775  call    HvsocketTraceGuidError
0x14002177a  jmp     loc_140021C81
0x14002177f  mov     rcx, [rbp+var_38]
0x140021783  lea     rax, [r13+4]
0x140021787  mov     r9, rax
0x14002178a  mov     [rbp+var_30], rax
0x14002178e  mov     r8, rax
0x140021791  mov     rdx, r14
0x140021794  call    HvSocketResolveUniversalAddress
0x140021799  mov     ebx, eax
0x14002179b  test    eax, eax
0x14002179d  jns     short loc_1400217D0
0x14002179f  mov     ecx, cs:dword_140013058
0x1400217a5  cmp     ecx, 2
0x1400217a8  jbe     loc_140021A48
0x1400217ae  lea     rax, [r13+4]
0x1400217b2  mov     r8d, ebx
0x1400217b5  lea     r9, [r13+14h]
0x1400217b9  mov     [rsp+70h+var_50], rax
0x1400217be  mov     edx, 0FDh
0x1400217c3  mov     rcx, r15
0x1400217c6  call    HvsocketTraceServiceError
0x1400217cb  jmp     loc_140021A48
0x1400217d0  mov     rcx, [rbp+var_38]
0x1400217d4  lea     r8, [rbp+var_40]
0x1400217d8  mov     rdx, rsi
0x1400217db  call    VmbusTlCreateListenEndpoint
0x1400217e0  mov     ebx, eax
0x1400217e2  test    eax, eax
0x1400217e4  mov     eax, cs:dword_140013058
0x1400217ea  jns     short loc_14002182E
0x1400217ec  cmp     eax, 2
0x1400217ef  jbe     short loc_140021825
0x1400217f1  xor     r12d, r12d
0x1400217f4  test    rsi, rsi
0x1400217f7  jnz     short loc_1400217FE
0x1400217f9  mov     eax, r12d
0x1400217fc  jmp     short loc_14002180D
0x1400217fe  mov     rcx, rsi; Process
0x140021801  call    cs:__imp_PsGetProcessId
0x140021808  nop     dword ptr [rax+rax+00h]
0x14002180d  mov     r9, [rbp+var_30]
0x140021811  mov     r8d, ebx
0x140021814  mov     edx, 106h
0x140021819  mov     dword ptr [rsp+70h+var_50], eax
0x14002181d  mov     rcx, r15
0x140021820  call    HvsocketTraceGuidULongError
0x140021825  mov     rdi, [rbp+var_40]
0x140021829  jmp     loc_140021A48
0x14002182e  mov     rdi, [rbp+var_40]
0x140021832  cmp     eax, 5
0x140021835  jbe     short loc_140021857
0x140021837  mov     r9, [rdi+8]
0x14002183b  lea     rax, aReferenceObjec; "Reference object"
0x140021842  mov     r8, rdi
0x140021845  mov     [rsp+70h+var_50], rax
0x14002184a  mov     edx, 10Ch
0x14002184f  mov     rcx, r15
0x140021852  call    HvsocketTraceReferenceCount
0x140021857  mov     ebx, 1
0x14002185c  mov     eax, ebx
0x14002185e  lock xadd [rdi+8], rax
0x140021864  add     rax, rbx
0x140021867  cmp     rax, rbx
0x14002186a  jg      short loc_140021871
0x14002186c  lea     ecx, [rbx+0Dh]
0x14002186f  int     29h; Win8: RtlFailFast(ecx)
0x140021871  movups  xmm0, xmmword ptr [r13+0]
0x140021876  mov     rdx, r13
0x140021879  lea     r9, [rdi+188h]
0x140021880  mov     r8, r14
0x140021883  movups  xmmword ptr [rdi+88h], xmm0
0x14002188a  movups  xmm1, xmmword ptr [r13+10h]
0x14002188f  movups  xmmword ptr [rdi+98h], xmm1
0x140021896  mov     eax, [r13+20h]
0x14002189a  mov     r13, [rbp+var_38]
0x14002189e  mov     [rdi+0A8h], eax
0x1400218a4  mov     rcx, r13
0x1400218a7  movups  xmm0, [rbp+var_28]
0x1400218ab  movdqu  xmmword ptr [rdi+118h], xmm0
0x1400218b3  movdqu  xmmword ptr [rdi+0B0h], xmm6
0x1400218bb  call    HvSocketIsPassthruRequest
0x1400218c0  mov     ecx, [rdi+158h]
0x1400218c6  lea     r8, [rdi+8Ch]
0x1400218cd  movzx   r9d, al
0x1400218d1  mov     rdx, r14
0x1400218d4  mov     eax, r9d
0x1400218d7  and     r9d, ebx
0x1400218da  xor     eax, ecx
0x1400218dc  and     eax, ebx
0x1400218de  xor     eax, ecx
0x1400218e0  mov     rcx, r13
0x1400218e3  mov     [rdi+158h], eax
0x1400218e9  lea     r9d, ds:1[r9*2]
0x1400218f1  lea     rax, [rdi+178h]
0x1400218f8  mov     [rsp+70h+var_50], rax
0x1400218fd  call    VmbusTlResolvePartitionId
0x140021902  mov     ebx, eax
0x140021904  test    eax, eax
0x140021906  jns     short loc_14002197E
0x140021908  mov     eax, cs:dword_140013058
0x14002190e  cmp     eax, 2
0x140021911  jbe     short loc_140021936
0x140021913  lea     rax, [rdi+8Ch]
0x14002191a  mov     r8d, ebx
0x14002191d  lea     r9, [rdi+9Ch]
0x140021924  mov     [rsp+70h+var_50], rax
0x140021929  mov     edx, 11Eh
0x14002192e  mov     rcx, r15
0x140021931  call    HvsocketTraceServiceError
0x140021936  mov     eax, cs:dword_140013058
0x14002193c  cmp     eax, 2
0x14002193f  jbe     loc_140021A48
0x140021945  xor     r12d, r12d
0x140021948  test    rsi, rsi
0x14002194b  jnz     short loc_140021952
0x14002194d  mov     eax, r12d
0x140021950  jmp     short loc_140021961
0x140021952  mov     rcx, rsi; Process
0x140021955  call    cs:__imp_PsGetProcessId
0x14002195c  nop     dword ptr [rax+rax+00h]
0x140021961  lea     r9, [rbp+var_28]
0x140021965  mov     dword ptr [rsp+70h+var_50], eax
0x140021969  mov     r8d, ebx
0x14002196c  mov     edx, 11Fh
0x140021971  mov     rcx, r15
0x140021974  call    HvsocketTraceGuidULongError
0x140021979  jmp     loc_140021A48
0x14002197e  mov     rax, [r12+58h]
0x140021983  mov     rdx, r14
0x140021986  mov     [rdi+150h], rax
0x14002198d  mov     rcx, rdi
0x140021990  mov     rax, [r12+48h]
0x140021995  mov     [rdi+160h], rax
0x14002199c  call    VmbusTlAssociateListenerToPartition
0x1400219a1  mov     ebx, eax
0x1400219a3  test    eax, eax
0x1400219a5  jns     short loc_1400219D7
0x1400219a7  mov     eax, cs:dword_140013058
0x1400219ad  cmp     eax, 2
0x1400219b0  jbe     loc_140021A48
0x1400219b6  lea     rax, [rdi+8Ch]
0x1400219bd  mov     r9, rdi
0x1400219c0  mov     r8d, ebx
0x1400219c3  mov     [rsp+70h+var_50], rax
0x1400219c8  mov     edx, 12Eh
0x1400219cd  mov     rcx, r15
0x1400219d0  call    HvsocketTraceEndpointGuidError
0x1400219d5  jmp     short loc_140021A48
0x1400219d7  mov     rax, [r12]
0x1400219db  lea     r9, VmbusTlProviderListenDispatch
0x1400219e2  mov     rcx, [r12+8]
0x1400219e7  mov     r8, rdi
0x1400219ea  mov     edx, ebx
0x1400219ec  call    _guard_dispatch_icall
0x1400219f1  call    cs:__imp_KeEnterCriticalRegion
0x1400219f8  nop     dword ptr [rax+rax+00h]
0x1400219fd  lea     rcx, [rdi+10h]; FastMutex
0x140021a01  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140021a08  nop     dword ptr [rax+rax+00h]
0x140021a0d  lea     rcx, [rdi+10h]; FastMutex
0x140021a11  mov     byte ptr [rdi+1A9h], 1
0x140021a18  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140021a1f  nop     dword ptr [rax+rax+00h]
0x140021a24  call    cs:__imp_KeLeaveCriticalRegion
0x140021a2b  nop     dword ptr [rax+rax+00h]
0x140021a30  lock inc dword ptr [r13+48Ch]
0x140021a38  mov     rdx, rdi
0x140021a3b  mov     rcx, r13
0x140021a3e  call    HvSocketListenerProcessPendingConnectionsList
0x140021a43  mov     ebx, 103h
0x140021a48  mov     eax, cs:dword_140013058
0x140021a4e  lea     r13, aDereferenceObj; "Dereference object"
  ... truncated ...
```
