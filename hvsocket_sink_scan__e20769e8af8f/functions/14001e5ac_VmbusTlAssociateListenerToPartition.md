# VmbusTlAssociateListenerToPartition

- ea: `0x14001e5ac`
- end: `0x14001edca`
- name: `VmbusTlAssociateListenerToPartition`
- size: `2078`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140021550`

## callees

- `0x140001008`
- `0x140002ffc`
- `0x14000695c`
- `0x140006be0`
- `0x140008ab8`
- `0x1400098f4`
- `0x140009ec0`
- `0x14000a048`
- `0x14000a154`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x140018008`
- `0x1400188c4`
- `0x140018a88`
- `0x140018bc8`
- `0x14001d530`
- `0x14001e5ac`
- `0x14001f5e4`
- `0x140021da4`
- `0x140021ec0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e64c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001eb41`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ec5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e64c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001eb41`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ec5f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001e640`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001eb35`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ec53`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001e640`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001eb35`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ec53`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e797`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ecf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ed94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e797`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ecf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ed94`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e602`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e9ea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ead8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e602`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e9ea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ead8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e781`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ece3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ed7e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e781`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ece3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ed7e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001e612`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ea01`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001eae8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001e612`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ea01`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001eae8`
- `ntoskrnl!PsGetProcessId` at `0x14001e875`
- `ntoskrnl!PsGetProcessId` at `0x14001e951`
- `ntoskrnl!PsGetProcessId` at `0x14001e998`
- `ntoskrnl!PsGetProcessId` at `0x14001e875`
- `ntoskrnl!PsGetProcessId` at `0x14001e951`
- `ntoskrnl!PsGetProcessId` at `0x14001e998`

## string_xrefs

- `0x14001e985`: `A Hyper-V wildcard bind socket is listening for any connections to a service.`

## pseudocode

```c
__int64 __fastcall VmbusTlAssociateListenerToPartition(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  PVOID v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // r14
  __int64 v8; // rcx
  GUID v9; // xmm0
  int VmAddressInfo; // eax
  int PartitionListenerEndpoint; // eax
  const char *v12; // rdx
  PVOID v13; // rbx
  signed __int64 v14; // rax
  bool v15; // cc
  signed __int64 v16; // rax
  void (__fastcall *v17)(PVOID, const char *); // rax
  int v18; // ebx
  struct _KPROCESS *v19; // rcx
  unsigned int ProcessId; // eax
  int v21; // edx
  struct _KPROCESS *v22; // rcx
  struct _KPROCESS *v23; // rcx
  unsigned int v24; // eax
  int v25; // r8d
  int v26; // r9d
  __int128 v27; // xmm0
  signed __int64 v28; // rax
  signed __int64 v29; // rax
  void (__fastcall *v30)(__int64); // rax
  signed __int64 v31; // rax
  signed __int64 v32; // rax
  void (__fastcall *v33)(PVOID); // rax
  PVOID Entry; // [rsp+30h] [rbp-59h] BYREF
  PFAST_MUTEX FastMutex; // [rsp+38h] [rbp-51h] BYREF
  GUID v37; // [rsp+40h] [rbp-49h] BYREF
  __int64 v38[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v39; // [rsp+60h] [rbp-29h]
  __int128 v40; // [rsp+70h] [rbp-19h]
  PFAST_MUTEX *p_FastMutex; // [rsp+80h] [rbp-9h]
  __int64 v42; // [rsp+88h] [rbp-1h]
  __int64 v43; // [rsp+90h] [rbp+7h]
  __int64 v44; // [rsp+98h] [rbp+Fh]

  v2 = *(_QWORD *)(a1 + 112);
  Entry = 0;
  *(_OWORD *)v38 = 0;
  LODWORD(p_FastMutex) = 0;
  v39 = 0;
  v5 = 0;
  v40 = 0;
  v37 = 0;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v2 + 16));
  v6 = *(_QWORD *)(a1 + 112);
  FastMutex = (PFAST_MUTEX)(a1 + 376);
  v7 = HvSocketFindAndReferenceAnyPartition(v6, a1 + 376);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 112) + 16LL));
  KeLeaveCriticalRegion();
  v8 = *(_QWORD *)(a1 + 112);
  v37 = HV_GUID_ZERO;
  if ( (int)HvSocketLookupSystemId(v8, a1 + 140, v38) >= 0 )
  {
    v9 = *(GUID *)(a1 + 140);
LABEL_8:
    v37 = v9;
    goto LABEL_9;
  }
  if ( !v7 )
    goto LABEL_9;
  if ( (unsigned __int8)VmbusTlIsContainerPartition(v7) )
  {
    VmAddressInfo = HvSocketSearchAddressInfoBySiloId(*(_QWORD *)(a1 + 112), a1 + 376, v38);
LABEL_6:
    if ( VmAddressInfo < 0 )
      goto LABEL_9;
    v9 = *(GUID *)v38;
    goto LABEL_8;
  }
  if ( *(_BYTE *)(v7 + 248) )
  {
    VmAddressInfo = HvSocketGetVmAddressInfo(*(_QWORD *)(a1 + 112), a1 + 376, v38);
    goto LABEL_6;
  }
LABEL_9:
  PartitionListenerEndpoint = VmbusTlGetPartitionListenerEndpoint(a2, v7, a1 + 376, &v37, a1 + 156, &Entry);
  v12 = "Dereference object";
  if ( PartitionListenerEndpoint >= 0 )
  {
    v13 = Entry;
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlAssociateListenerToPartition",
        1157,
        (_DWORD)Entry,
        *((_QWORD *)Entry + 1),
        (__int64)"Dereference object");
    v14 = _InterlockedExchangeAdd64((volatile signed __int64 *)v13 + 1, 0xFFFFFFFFFFFFFFFFuLL);
    v15 = v14 <= 1;
    v16 = v14 - 1;
    if ( v15 )
    {
      if ( v16 )
        __fastfail(0xEu);
      v17 = (void (__fastcall *)(PVOID, const char *))*((_QWORD *)v13 + 10);
      if ( v17 )
        v17(v13, v12);
      if ( *((_DWORD *)v13 + 22) == 1 )
      {
        ExFreePoolWithTag(v13, 0x69706E56u);
      }
      else if ( *((_DWORD *)v13 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 12), v13);
      }
    }
    v18 = -1073741302;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceServiceError(
        (unsigned int)"VmbusTlAssociateListenerToPartition",
        1159,
        -1073741302,
        a1 + 156,
        a2 + 232);
LABEL_78:
    if ( !v7 )
    {
LABEL_90:
      if ( v5 )
      {
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (unsigned int)"VmbusTlAssociateListenerToPartition",
            1316,
            (_DWORD)v5,
            *((_QWORD *)v5 + 1),
            (__int64)"Dereference object");
        v31 = _InterlockedExchangeAdd64((volatile signed __int64 *)v5 + 1, 0xFFFFFFFFFFFFFFFFuLL);
        v15 = v31 <= 1;
        v32 = v31 - 1;
        if ( v15 )
        {
          if ( v32 )
            __fastfail(0xEu);
          v33 = (void (__fastcall *)(PVOID))*((_QWORD *)v5 + 10);
          if ( v33 )
            v33(v5);
          if ( *((_DWORD *)v5 + 22) == 1 )
          {
            ExFreePoolWithTag(v5, 0x69706E56u);
          }
          else if ( *((_DWORD *)v5 + 22) == 2 )
          {
            ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v5 + 12), v5);
          }
        }
      }
      return (unsigned int)v18;
    }
LABEL_79:
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlAssociateListenerToPartition",
        1311,
        v7,
        *(_QWORD *)(v7 + 8),
        (__int64)"Dereference object");
    v28 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v7 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v15 = v28 <= 1;
    v29 = v28 - 1;
    if ( v15 )
    {
      if ( v29 )
        __fastfail(0xEu);
      v30 = *(void (__fastcall **)(__int64))(v7 + 80);
      if ( v30 )
        v30(v7);
      if ( *(_DWORD *)(v7 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v7, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v7 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v7 + 96), (PVOID)v7);
      }
    }
    goto LABEL_90;
  }
  if ( !memcmp((const void *)(a1 + 140), &HV_GUID_ZERO, 0x10u)
    || !memcmp((const void *)(a1 + 140), &HV_GUID_CHILDREN, 0x10u) )
  {
    v18 = VmbusTlAuthenticateWildcardListen(*(_QWORD *)(a1 + 112), a1 + 156, *(_QWORD *)(a1 + 272));
    if ( v18 < 0 )
    {
      if ( (unsigned int)dword_140013058 <= 2 )
        goto LABEL_78;
      v22 = *(struct _KPROCESS **)(a1 + 272);
      if ( v22 )
        ProcessId = (unsigned int)PsGetProcessId(v22);
      else
        ProcessId = 0;
      v21 = 1176;
      goto LABEL_46;
    }
    if ( (unsigned int)dword_140013058 > 4 )
    {
      v23 = *(struct _KPROCESS **)(a1 + 272);
      *(_QWORD *)&v40 = "A Hyper-V wildcard bind socket is listening for any connections to a service.";
      *((_QWORD *)&v40 + 1) = 78;
      v24 = (unsigned int)PsGetProcessId(v23);
      v42 = 8;
      p_FastMutex = &FastMutex;
      FastMutex = (PFAST_MUTEX)v24;
      v43 = a1 + 156;
      v44 = 16;
      tlgWriteTransfer_EtwWriteTransfer((int)&dword_140013058, (int)&byte_140011585, v25, v26, 5u, (__int64)v38);
    }
LABEL_49:
    KeEnterCriticalRegion();
    FastMutex = (PFAST_MUTEX)(a2 + 16);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
    if ( *(_BYTE *)(a2 + 393) || *(_BYTE *)(a2 + 392) && !*(_BYTE *)(a1 + 185) )
    {
      v18 = -1073741252;
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceEndpointGuidError(
          (unsigned int)"VmbusTlAssociateListenerToPartition",
          1239,
          -1073741252,
          a1,
          a2 + 232);
      goto LABEL_77;
    }
    Entry = (PVOID)VmbusTlFindAndReferenceService(a2, a1 + 156);
    v5 = Entry;
    if ( !Entry )
    {
      v18 = VmbusTlCreateTransientService(a2, a1 + 156, &Entry);
      if ( v18 < 0 )
      {
        if ( (unsigned int)dword_140013058 > 2 )
          HvsocketTraceServiceError((unsigned int)"VmbusTlAssociateListenerToPartition", 1252, v18, a1 + 156, a2 + 232);
        v5 = Entry;
LABEL_77:
        ExReleaseFastMutexUnsafe(FastMutex);
        KeLeaveCriticalRegion();
        goto LABEL_78;
      }
      v5 = Entry;
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlAssociateListenerToPartition",
          1256,
          (_DWORD)Entry,
          *((_QWORD *)Entry + 1),
          (__int64)"Reference object");
      if ( _InterlockedIncrement64((volatile signed __int64 *)v5 + 1) <= 1 )
        __fastfail(0xEu);
    }
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    if ( *(_QWORD *)(a1 + 360) )
    {
      v18 = -1073741436;
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceEndpointGuidError(
          (unsigned int)"VmbusTlAssociateListenerToPartition",
          1268,
          -1073741436,
          a1,
          *(_QWORD *)(a1 + 360) + 112LL);
    }
    else
    {
      if ( !memcmp((const void *)(a1 + 392), &HV_GUID_ZERO, 0x10u) )
        v27 = *(_OWORD *)(a1 + 376);
      else
        v27 = *(_OWORD *)(a1 + 392);
      *(_OWORD *)(a1 + 408) = v27;
      v18 = VmbusTlAssociateListenerToService(v5, a1);
      if ( v18 < 0 )
      {
        if ( (unsigned int)dword_140013058 > 2 )
          HvsocketTraceServiceError((unsigned int)"VmbusTlAssociateListenerToPartition", 1297, v18, a1 + 156, a1 + 376);
      }
      else
      {
        *(_QWORD *)(a1 + 368) = a2;
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (unsigned int)"VmbusTlAssociateListenerToPartition",
            1293,
            a2,
            *(_QWORD *)(a2 + 8),
            (__int64)"Reference object");
        if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 8)) <= 1 )
          __fastfail(0xEu);
      }
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    KeLeaveCriticalRegion();
    goto LABEL_77;
  }
  if ( !memcmp((const void *)(a1 + 140), &HV_GUID_LOOPBACK, 0x10u) )
  {
    v18 = VmbusTlEndpointAccessCheck(
            *(PEPROCESS *)(a1 + 272),
            *(PSECURITY_DESCRIPTOR *)(*(_QWORD *)(a1 + 112) + 1448LL));
    if ( v18 < 0 )
    {
      if ( (unsigned int)dword_140013058 <= 2 )
        goto LABEL_78;
      v19 = *(struct _KPROCESS **)(a1 + 272);
      if ( v19 )
        ProcessId = (unsigned int)PsGetProcessId(v19);
      else
        ProcessId = 0;
      v21 = 1201;
LABEL_46:
      HvsocketTraceGuidULongError((unsigned int)"VmbusTlAssociateListenerToPartition", v21, v18, a1 + 156, ProcessId);
      goto LABEL_78;
    }
    goto LABEL_49;
  }
  if ( v7 )
  {
    v18 = VmbusTlAuthenticateListenSockAddress(v7, a1 + 136, *(struct _KPROCESS **)(a1 + 272));
    if ( v18 < 0 )
    {
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceServiceError(
          (unsigned int)"VmbusTlAssociateListenerToPartition",
          1217,
          v18,
          a1 + 156,
          (__int64)FastMutex);
      goto LABEL_79;
    }
    goto LABEL_49;
  }
  v18 = -1073741275;
  if ( (unsigned int)dword_140013058 > 2 )
    HvsocketTraceServiceError(
      (unsigned int)"VmbusTlAssociateListenerToPartition",
      1224,
      -1073741275,
      a1 + 156,
      (__int64)FastMutex);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14001e5ac  mov     [rsp-8+arg_10], rbx
0x14001e5b1  push    rbp
0x14001e5b2  push    rsi
0x14001e5b3  push    rdi
0x14001e5b4  push    r12
0x14001e5b6  push    r13
0x14001e5b8  push    r14
0x14001e5ba  push    r15
0x14001e5bc  lea     rbp, [rsp-27h]
0x14001e5c1  sub     rsp, 0B0h
0x14001e5c8  mov     rax, cs:__security_cookie
0x14001e5cf  xor     rax, rsp
0x14001e5d2  mov     [rbp+57h+var_40], rax
0x14001e5d6  mov     rbx, [rcx+70h]
0x14001e5da  xorps   xmm0, xmm0
0x14001e5dd  xor     eax, eax
0x14001e5df  mov     [rbp+57h+Entry], 0
0x14001e5e7  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x14001e5eb  mov     dword ptr [rbp+57h+var_60], eax
0x14001e5ee  mov     r13, rdx
0x14001e5f1  movups  [rbp+57h+var_80], xmm0
0x14001e5f5  mov     rdi, rcx
0x14001e5f8  xor     esi, esi
0x14001e5fa  movups  [rbp+57h+var_70], xmm0
0x14001e5fe  movups  [rbp+57h+var_A0], xmm0
0x14001e602  call    cs:__imp_KeEnterCriticalRegion
0x14001e609  nop     dword ptr [rax+rax+00h]
0x14001e60e  lea     rcx, [rbx+10h]; FastMutex
0x14001e612  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001e619  nop     dword ptr [rax+rax+00h]
0x14001e61e  mov     rcx, [rdi+70h]
0x14001e622  lea     rbx, [rdi+178h]
0x14001e629  mov     rdx, rbx
0x14001e62c  mov     [rbp+57h+FastMutex], rbx
0x14001e630  call    HvSocketFindAndReferenceAnyPartition
0x14001e635  mov     rcx, [rdi+70h]
0x14001e639  mov     r14, rax
0x14001e63c  add     rcx, 10h; FastMutex
0x14001e640  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001e647  nop     dword ptr [rax+rax+00h]
0x14001e64c  call    cs:__imp_KeLeaveCriticalRegion
0x14001e653  nop     dword ptr [rax+rax+00h]
0x14001e658  movups  xmm0, xmmword ptr cs:HV_GUID_ZERO.Data1
0x14001e65f  mov     rcx, [rdi+70h]
0x14001e663  lea     r15, [rdi+8Ch]
0x14001e66a  lea     r8, [rbp+57h+var_90]
0x14001e66e  mov     rdx, r15
0x14001e671  movdqu  [rbp+57h+var_A0], xmm0
0x14001e676  call    HvSocketLookupSystemId
0x14001e67b  test    eax, eax
0x14001e67d  js      short loc_14001E685
0x14001e67f  movups  xmm0, xmmword ptr [r15]
0x14001e683  jmp     short loc_14001E6B2
0x14001e685  test    r14, r14
0x14001e688  jz      short loc_14001E6B7
0x14001e68a  mov     rcx, r14
0x14001e68d  call    VmbusTlIsContainerPartition
0x14001e692  test    al, al
0x14001e694  jz      loc_14001E73A
0x14001e69a  mov     rcx, [rdi+70h]
0x14001e69e  lea     r8, [rbp+57h+var_90]
0x14001e6a2  mov     rdx, rbx
0x14001e6a5  call    HvSocketSearchAddressInfoBySiloId
0x14001e6aa  test    eax, eax
0x14001e6ac  js      short loc_14001E6B7
0x14001e6ae  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x14001e6b2  movdqu  [rbp+57h+var_A0], xmm0
0x14001e6b7  lea     rax, [rbp+57h+Entry]
0x14001e6bb  mov     r8, rbx
0x14001e6be  mov     [rsp+0E0h+var_B8], rax
0x14001e6c3  lea     r12, [rdi+9Ch]
0x14001e6ca  lea     r9, [rbp+57h+var_A0]
0x14001e6ce  mov     qword ptr [rsp+0E0h+var_C0], r12
0x14001e6d3  mov     rdx, r14
0x14001e6d6  mov     rcx, r13
0x14001e6d9  call    VmbusTlGetPartitionListenerEndpoint
0x14001e6de  lea     rdx, aDereferenceObj; "Dereference object"
0x14001e6e5  lea     r15, aVmbustlassocia; "VmbusTlAssociateListenerToPartition"
0x14001e6ec  test    eax, eax
0x14001e6ee  js      loc_14001E7DB
0x14001e6f4  mov     eax, cs:dword_140013058
0x14001e6fa  mov     rbx, [rbp+57h+Entry]
0x14001e6fe  cmp     eax, 5
0x14001e701  jbe     short loc_14001E71C
0x14001e703  mov     r9, [rbx+8]
0x14001e707  mov     r8, rbx
0x14001e70a  mov     qword ptr [rsp+0E0h+var_C0], rdx
0x14001e70f  mov     rcx, r15
0x14001e712  mov     edx, 485h
0x14001e717  call    HvsocketTraceReferenceCount
0x14001e71c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001e720  lock xadd [rbx+8], rax
0x14001e726  sub     rax, 1
0x14001e72a  jg      short loc_14001E7A3
0x14001e72c  test    rax, rax
0x14001e72f  jz      short loc_14001E75C
0x14001e731  mov     ecx, 0Eh
0x14001e736  int     29h; Win8: RtlFailFast(ecx)
0x14001e738  jmp     short loc_14001E7A3
0x14001e73a  cmp     [r14+0F8h], sil
0x14001e741  jz      loc_14001E6B7
0x14001e747  mov     rcx, [rdi+70h]
0x14001e74b  lea     r8, [rbp+57h+var_90]
0x14001e74f  mov     rdx, rbx
0x14001e752  call    HvSocketGetVmAddressInfo
0x14001e757  jmp     loc_14001E6AA
0x14001e75c  mov     rax, [rbx+50h]
0x14001e760  test    rax, rax
0x14001e763  jz      short loc_14001E76D
0x14001e765  mov     rcx, rbx
0x14001e768  call    _guard_dispatch_icall
0x14001e76d  mov     ecx, [rbx+58h]
0x14001e770  sub     ecx, 1
0x14001e773  jz      short loc_14001E78F
0x14001e775  cmp     ecx, 1
0x14001e778  jnz     short loc_14001E7A3
0x14001e77a  mov     rcx, [rbx+60h]; Lookaside
0x14001e77e  mov     rdx, rbx; Entry
0x14001e781  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001e788  nop     dword ptr [rax+rax+00h]
0x14001e78d  jmp     short loc_14001E7A3
0x14001e78f  mov     edx, 69706E56h; Tag
0x14001e794  mov     rcx, rbx; P
0x14001e797  call    cs:__imp_ExFreePoolWithTag
0x14001e79e  nop     dword ptr [rax+rax+00h]
0x14001e7a3  mov     eax, cs:dword_140013058
0x14001e7a9  mov     ebx, 0C000020Ah
0x14001e7ae  cmp     eax, 2
0x14001e7b1  jbe     loc_14001EC6B
0x14001e7b7  lea     rax, [r13+0E8h]
0x14001e7be  mov     r9, r12
0x14001e7c1  mov     r8d, ebx
0x14001e7c4  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14001e7c9  mov     edx, 487h
0x14001e7ce  mov     rcx, r15
0x14001e7d1  call    HvsocketTraceServiceError
0x14001e7d6  jmp     loc_14001EC6B
0x14001e7db  lea     rbx, [rdi+8Ch]
0x14001e7e2  mov     r8d, 10h; Size
0x14001e7e8  mov     rcx, rbx; Buf1
0x14001e7eb  lea     rdx, HV_GUID_ZERO; Buf2
0x14001e7f2  call    memcmp
0x14001e7f7  test    eax, eax
0x14001e7f9  jz      loc_14001E919
0x14001e7ff  mov     r8d, 10h; Size
0x14001e805  lea     rdx, HV_GUID_CHILDREN; Buf2
0x14001e80c  mov     rcx, rbx; Buf1
0x14001e80f  call    memcmp
0x14001e814  test    eax, eax
0x14001e816  jz      loc_14001E919
0x14001e81c  mov     r8d, 10h; Size
0x14001e822  lea     rdx, HV_GUID_LOOPBACK; Buf2
0x14001e829  mov     rcx, rbx; Buf1
0x14001e82c  call    memcmp
0x14001e831  test    eax, eax
0x14001e833  jnz     short loc_14001E88B
0x14001e835  mov     rdx, [rdi+70h]
0x14001e839  mov     rcx, [rdi+110h]; Process
0x14001e840  mov     rdx, [rdx+5A8h]; SecurityDescriptor
0x14001e847  call    VmbusTlEndpointAccessCheck
0x14001e84c  mov     ebx, eax
0x14001e84e  test    eax, eax
0x14001e850  jns     loc_14001E9EA
0x14001e856  mov     ecx, cs:dword_140013058
0x14001e85c  cmp     ecx, 2
0x14001e85f  jbe     loc_14001EC6B
0x14001e865  mov     rcx, [rdi+110h]; Process
0x14001e86c  test    rcx, rcx
0x14001e86f  jnz     short loc_14001E875
0x14001e871  xor     eax, eax
0x14001e873  jmp     short loc_14001E881
0x14001e875  call    cs:__imp_PsGetProcessId
0x14001e87c  nop     dword ptr [rax+rax+00h]
0x14001e881  mov     edx, 4B1h
0x14001e886  jmp     loc_14001E962
0x14001e88b  test    r14, r14
0x14001e88e  jz      short loc_14001E8E0
0x14001e890  mov     r8, [rdi+110h]
0x14001e897  lea     rdx, [rdi+88h]
0x14001e89e  mov     rcx, r14
0x14001e8a1  call    VmbusTlAuthenticateListenSockAddress
0x14001e8a6  mov     ebx, eax
0x14001e8a8  test    eax, eax
0x14001e8aa  jns     loc_14001E9EA
0x14001e8b0  mov     eax, cs:dword_140013058
0x14001e8b6  cmp     eax, 2
0x14001e8b9  jbe     loc_14001EC74
0x14001e8bf  mov     rax, [rbp+57h+FastMutex]
0x14001e8c3  mov     r9, r12
0x14001e8c6  mov     r8d, ebx
0x14001e8c9  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14001e8ce  mov     edx, 4C1h
0x14001e8d3  mov     rcx, r15
0x14001e8d6  call    HvsocketTraceServiceError
0x14001e8db  jmp     loc_14001EC74
0x14001e8e0  mov     eax, cs:dword_140013058
0x14001e8e6  mov     ebx, 0C0000225h
0x14001e8eb  cmp     eax, 2
0x14001e8ee  jbe     loc_14001EDA0
0x14001e8f4  mov     rax, [rbp+57h+FastMutex]
0x14001e8f8  lea     rcx, aVmbustlassocia; "VmbusTlAssociateListenerToPartition"
0x14001e8ff  mov     r9, r12
0x14001e902  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14001e907  mov     r8d, ebx
0x14001e90a  mov     edx, 4C8h
0x14001e90f  call    HvsocketTraceServiceError
0x14001e914  jmp     loc_14001EDA0
0x14001e919  mov     r8, [rdi+110h]
0x14001e920  mov     rdx, r12
0x14001e923  mov     rcx, [rdi+70h]
0x14001e927  call    VmbusTlAuthenticateWildcardListen
0x14001e92c  mov     ebx, eax
0x14001e92e  test    eax, eax
0x14001e930  mov     eax, cs:dword_140013058
0x14001e936  jns     short loc_14001E979
0x14001e938  cmp     eax, 2
0x14001e93b  jbe     loc_14001EC6B
0x14001e941  mov     rcx, [rdi+110h]; Process
0x14001e948  test    rcx, rcx
0x14001e94b  jnz     short loc_14001E951
0x14001e94d  xor     eax, eax
0x14001e94f  jmp     short loc_14001E95D
0x14001e951  call    cs:__imp_PsGetProcessId
0x14001e958  nop     dword ptr [rax+rax+00h]
0x14001e95d  mov     edx, 498h
0x14001e962  mov     r8d, ebx
0x14001e965  mov     [rsp+0E0h+var_C0], eax
0x14001e969  mov     r9, r12
0x14001e96c  mov     rcx, r15
0x14001e96f  call    HvsocketTraceGuidULongError
0x14001e974  jmp     loc_14001EC6B
0x14001e979  cmp     eax, 4
0x14001e97c  jbe     short loc_14001E9EA
0x14001e97e  mov     rcx, [rdi+110h]; Process
0x14001e985  lea     rax, aAHyperVWildcar; "A Hyper-V wildcard bind socket is liste"...
0x14001e98c  mov     qword ptr [rbp+57h+var_70], rax
0x14001e990  mov     qword ptr [rbp+57h+var_70+8], 4Eh ; 'N'
0x14001e998  call    cs:__imp_PsGetProcessId
0x14001e99f  nop     dword ptr [rax+rax+00h]
0x14001e9a4  lea     rdx, byte_140011585; int
0x14001e9ab  mov     [rbp+57h+var_58], 8
0x14001e9b3  mov     ecx, eax
0x14001e9b5  lea     rax, [rbp+57h+FastMutex]
0x14001e9b9  mov     [rbp+57h+var_60], rax
0x14001e9bd  lea     rax, [rbp+57h+var_90]
0x14001e9c1  mov     [rbp+57h+FastMutex], rcx
0x14001e9c5  lea     rcx, dword_140013058; int
0x14001e9cc  mov     [rsp+0E0h+var_B8], rax; __int64
0x14001e9d1  mov     [rsp+0E0h+var_C0], 5; ULONG
0x14001e9d9  mov     [rbp+57h+var_50], r12
0x14001e9dd  mov     [rbp+57h+var_48], 10h
0x14001e9e5  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001e9ea  call    cs:__imp_KeEnterCriticalRegion
0x14001e9f1  nop     dword ptr [rax+rax+00h]
0x14001e9f6  lea     rax, [r13+10h]
0x14001e9fa  mov     rcx, rax; FastMutex
0x14001e9fd  mov     [rbp+57h+FastMutex], rax
0x14001ea01  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001ea08  nop     dword ptr [rax+rax+00h]
0x14001ea0d  xor     eax, eax
0x14001ea0f  cmp     [r13+189h], al
0x14001ea16  jnz     loc_14001EC20
0x14001ea1c  cmp     [r13+188h], al
0x14001ea23  jz      short loc_14001EA31
0x14001ea25  cmp     [rdi+0B9h], al
0x14001ea2b  jz      loc_14001EC20
0x14001ea31  mov     rdx, r12
0x14001ea34  mov     rcx, r13
0x14001ea37  call    VmbusTlFindAndReferenceService
0x14001ea3c  mov     [rbp+57h+Entry], rax
0x14001ea40  mov     rsi, rax
0x14001ea43  test    rax, rax
0x14001ea46  jnz     loc_14001EAD8
0x14001ea4c  lea     r8, [rbp+57h+Entry]
0x14001ea50  mov     rdx, r12
0x14001ea53  mov     rcx, r13
0x14001ea56  call    VmbusTlCreateTransientService
0x14001ea5b  mov     ebx, eax
0x14001ea5d  test    eax, eax
0x14001ea5f  mov     eax, cs:dword_140013058
0x14001ea65  jns     short loc_14001EA94
0x14001ea67  cmp     eax, 2
0x14001ea6a  jbe     short loc_14001EA8B
0x14001ea6c  lea     rax, [r13+0E8h]
0x14001ea73  mov     r9, r12
0x14001ea76  mov     r8d, ebx
0x14001ea79  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14001ea7e  mov     edx, 4E4h
0x14001ea83  mov     rcx, r15
0x14001ea86  call    HvsocketTraceServiceError
0x14001ea8b  mov     rsi, [rbp+57h+Entry]
0x14001ea8f  jmp     loc_14001EC4F
0x14001ea94  mov     rsi, [rbp+57h+Entry]
0x14001ea98  cmp     eax, 5
0x14001ea9b  jbe     short loc_14001EABD
0x14001ea9d  mov     r9, [rsi+8]
0x14001eaa1  lea     rax, aReferenceObjec; "Reference object"
0x14001eaa8  mov     r8, rsi
0x14001eaab  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14001eab0  mov     edx, 4E8h
  ... truncated ...
```
