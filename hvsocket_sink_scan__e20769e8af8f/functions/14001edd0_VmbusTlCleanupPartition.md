# VmbusTlCleanupPartition

- ea: `0x14001edd0`
- end: `0x14001f1e6`
- name: `VmbusTlCleanupPartition`
- size: `1046`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140018130`
- `0x140019a10`
- `0x140020124`
- `0x140023280`
- `0x1400234e0`
- `0x1400235a0`

## callees

- `0x140006de8`
- `0x140009fa4`
- `0x14000a048`
- `0x14000bfe0`
- `0x14001edd0`
- `0x14001f540`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001f002`
- `ntoskrnl!KeInitializeEvent` at `0x14001f002`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f05f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f05f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ee36`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ee61`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ef98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f039`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f0a0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ee36`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ee61`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ef98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f039`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f0a0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ee2a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ee55`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ef8c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f02d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f094`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ee2a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ee55`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ef8c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f02d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f094`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ef75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f137`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f1ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ef75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f137`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f1ce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001edff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ee74`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001efa4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f06b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001edff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ee74`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001efa4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f06b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ef5f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f121`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f1b5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ef5f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f121`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f1b5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ee12`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ee84`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001efb3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001f07a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ee12`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ee84`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001efb3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001f07a`
- `NETIO!NetioShutdownWorkQueue` at `0x14001efcf`
- `NETIO!NetioShutdownWorkQueue` at `0x14001efcf`

## pseudocode

```c
void __fastcall VmbusTlCleanupPartition(char *P)
{
  char *v1; // rbp
  struct _FAST_MUTEX *v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rbx
  _QWORD *v6; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  __int64 v9; // rax
  void (__fastcall *v10)(__int64); // rax
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rax
  void (__fastcall *v15)(__int64); // rax
  __int64 v16; // rax
  void (__fastcall *v17)(char *); // rax
  struct _KEVENT Event; // [rsp+30h] [rbp-48h] BYREF

  v1 = P + 232;
  if ( (unsigned int)dword_140013058 > 4 )
    HvsocketTraceMessage("Cleaning up partition.", P + 232);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(P + 16));
  v3 = (struct _FAST_MUTEX *)(P + 16);
  if ( P[393] )
  {
    ExReleaseFastMutexUnsafe(v3);
    KeLeaveCriticalRegion();
  }
  else
  {
    P[393] = 1;
    ExReleaseFastMutexUnsafe(v3);
    KeLeaveCriticalRegion();
    v4 = *((_QWORD *)P + 25);
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
    v5 = VmbusTlFindAndReferencePartition(*((_QWORD *)P + 25), v1);
    v6 = P + 216;
    v7 = *((_QWORD *)P + 27);
    if ( *(char **)(v7 + 8) != P + 216 || (v8 = (_QWORD *)*((_QWORD *)P + 28), (_QWORD *)*v8 != v6) )
      __fastfail(3u);
    *v8 = v7;
    *(_QWORD *)(v7 + 8) = v8;
    *((_QWORD *)P + 28) = P + 216;
    *v6 = v6;
    if ( v5 )
    {
      --*(_DWORD *)(*((_QWORD *)P + 25) + 160LL);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlCleanupPartition",
          484,
          v5,
          *(_QWORD *)(v5 + 8),
          (__int64)"Dereference object");
      v9 = _InterlockedDecrement64((volatile signed __int64 *)(v5 + 8));
      if ( v9 <= 0 )
      {
        if ( v9 )
          __fastfail(0xEu);
        v10 = *(void (__fastcall **)(__int64))(v5 + 80);
        if ( v10 )
          v10(v5);
        if ( *(_DWORD *)(v5 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v5, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v5 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 96), (PVOID)v5);
        }
      }
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*((_QWORD *)P + 25) + 16LL));
    KeLeaveCriticalRegion();
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(P + 16));
    if ( P[472] )
    {
      NetioShutdownWorkQueue(P + 424);
      P[472] = 0;
    }
    P[392] = 1;
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v11 = *((_DWORD *)P + 102);
    LOBYTE(v12) = 1;
    *((_QWORD *)P + 50) = &Event;
    VmbusTlDisconnectPartitionEndpoints(P, v12);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(P + 16));
    KeLeaveCriticalRegion();
    if ( v11 )
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(P + 16));
    *((_QWORD *)P + 50) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(P + 16));
    KeLeaveCriticalRegion();
    v13 = *((_QWORD *)P + 25);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlCleanupPartition",
        520,
        *((_QWORD *)P + 25),
        *(_QWORD *)(v13 + 8),
        (__int64)"Dereference object");
    v14 = _InterlockedDecrement64((volatile signed __int64 *)(v13 + 8));
    if ( v14 <= 0 )
    {
      if ( v14 )
        __fastfail(0xEu);
      v15 = *(void (__fastcall **)(__int64))(v13 + 80);
      if ( v15 )
        v15(v13);
      if ( *(_DWORD *)(v13 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v13, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v13 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v13 + 96), (PVOID)v13);
      }
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlCleanupPartition",
        525,
        (_DWORD)P,
        *((_QWORD *)P + 1),
        (__int64)"Dereference object");
    v16 = _InterlockedDecrement64((volatile signed __int64 *)P + 1);
    if ( v16 <= 0 )
    {
      if ( v16 )
        __fastfail(0xEu);
      v17 = (void (__fastcall *)(char *))*((_QWORD *)P + 10);
      if ( v17 )
        v17(P);
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
}

```

## disassembly

```asm
0x14001edd0  push    rbx
0x14001edd2  push    rbp
0x14001edd3  push    rsi
0x14001edd4  push    rdi
0x14001edd5  push    r15
0x14001edd7  sub     rsp, 50h
0x14001eddb  mov     eax, cs:dword_140013058
0x14001ede1  lea     rbp, [rcx+0E8h]
0x14001ede8  mov     rdi, rcx
0x14001edeb  cmp     eax, 4
0x14001edee  jbe     short loc_14001EDFF
0x14001edf0  mov     rdx, rbp
0x14001edf3  lea     rcx, aCleaningUpPart; "Cleaning up partition."
0x14001edfa  call    HvsocketTraceMessage
0x14001edff  call    cs:__imp_KeEnterCriticalRegion
0x14001ee06  nop     dword ptr [rax+rax+00h]
0x14001ee0b  lea     rsi, [rdi+10h]
0x14001ee0f  mov     rcx, rsi; FastMutex
0x14001ee12  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001ee19  nop     dword ptr [rax+rax+00h]
0x14001ee1e  cmp     byte ptr [rdi+189h], 0
0x14001ee25  mov     rcx, rsi; FastMutex
0x14001ee28  jz      short loc_14001EE4E
0x14001ee2a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001ee31  nop     dword ptr [rax+rax+00h]
0x14001ee36  call    cs:__imp_KeLeaveCriticalRegion
0x14001ee3d  nop     dword ptr [rax+rax+00h]
0x14001ee42  add     rsp, 50h
0x14001ee46  pop     r15
0x14001ee48  pop     rdi
0x14001ee49  pop     rsi
0x14001ee4a  pop     rbp
0x14001ee4b  pop     rbx
0x14001ee4c  retn
0x14001ee4e  mov     byte ptr [rdi+189h], 1
0x14001ee55  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001ee5c  nop     dword ptr [rax+rax+00h]
0x14001ee61  call    cs:__imp_KeLeaveCriticalRegion
0x14001ee68  nop     dword ptr [rax+rax+00h]
0x14001ee6d  mov     rbx, [rdi+0C8h]
0x14001ee74  call    cs:__imp_KeEnterCriticalRegion
0x14001ee7b  nop     dword ptr [rax+rax+00h]
0x14001ee80  lea     rcx, [rbx+10h]; FastMutex
0x14001ee84  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001ee8b  nop     dword ptr [rax+rax+00h]
0x14001ee90  mov     rcx, [rdi+0C8h]
0x14001ee97  mov     rdx, rbp
0x14001ee9a  call    VmbusTlFindAndReferencePartition
0x14001ee9f  mov     rbx, rax
0x14001eea2  lea     rax, [rdi+0D8h]
0x14001eea9  mov     rdx, [rax]
0x14001eeac  cmp     [rdx+8], rax
0x14001eeb0  jnz     loc_14001F1DF
0x14001eeb6  mov     rcx, [rax+8]
0x14001eeba  cmp     [rcx], rax
0x14001eebd  jnz     loc_14001F1DF
0x14001eec3  mov     [rcx], rdx
0x14001eec6  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14001eeca  mov     [rdx+8], rcx
0x14001eece  mov     r15d, 0Eh
0x14001eed4  mov     [rax+8], rax
0x14001eed8  lea     rcx, aDereferenceObj; "Dereference object"
0x14001eedf  mov     [rax], rax
0x14001eee2  test    rbx, rbx
0x14001eee5  jz      loc_14001EF81
0x14001eeeb  mov     rax, [rdi+0C8h]
0x14001eef2  dec     dword ptr [rax+0A0h]
0x14001eef8  mov     eax, cs:dword_140013058
0x14001eefe  cmp     eax, 5
0x14001ef01  jbe     short loc_14001EF20
0x14001ef03  mov     r9, [rbx+8]
0x14001ef07  mov     r8, rbx
0x14001ef0a  mov     [rsp+78h+Timeout], rcx
0x14001ef0f  mov     edx, 1E4h
0x14001ef14  lea     rcx, aVmbustlcleanup; "VmbusTlCleanupPartition"
0x14001ef1b  call    HvsocketTraceReferenceCount
0x14001ef20  mov     rax, rbp
0x14001ef23  lock xadd [rbx+8], rax
0x14001ef29  add     rax, rbp
0x14001ef2c  test    rax, rax
0x14001ef2f  jg      short loc_14001EF81
0x14001ef31  jz      short loc_14001EF3A
0x14001ef33  mov     rcx, r15
0x14001ef36  int     29h; Win8: RtlFailFast(ecx)
0x14001ef38  jmp     short loc_14001EF81
0x14001ef3a  mov     rax, [rbx+50h]
0x14001ef3e  test    rax, rax
0x14001ef41  jz      short loc_14001EF4B
0x14001ef43  mov     rcx, rbx
0x14001ef46  call    _guard_dispatch_icall
0x14001ef4b  mov     ecx, [rbx+58h]
0x14001ef4e  sub     ecx, 1
0x14001ef51  jz      short loc_14001EF6D
0x14001ef53  cmp     ecx, 1
0x14001ef56  jnz     short loc_14001EF81
0x14001ef58  mov     rcx, [rbx+60h]; Lookaside
0x14001ef5c  mov     rdx, rbx; Entry
0x14001ef5f  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001ef66  nop     dword ptr [rax+rax+00h]
0x14001ef6b  jmp     short loc_14001EF81
0x14001ef6d  mov     edx, 69706E56h; Tag
0x14001ef72  mov     rcx, rbx; P
0x14001ef75  call    cs:__imp_ExFreePoolWithTag
0x14001ef7c  nop     dword ptr [rax+rax+00h]
0x14001ef81  mov     rcx, [rdi+0C8h]
0x14001ef88  add     rcx, 10h; FastMutex
0x14001ef8c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001ef93  nop     dword ptr [rax+rax+00h]
0x14001ef98  call    cs:__imp_KeLeaveCriticalRegion
0x14001ef9f  nop     dword ptr [rax+rax+00h]
0x14001efa4  call    cs:__imp_KeEnterCriticalRegion
0x14001efab  nop     dword ptr [rax+rax+00h]
0x14001efb0  mov     rcx, rsi; FastMutex
0x14001efb3  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001efba  nop     dword ptr [rax+rax+00h]
0x14001efbf  cmp     byte ptr [rdi+1D8h], 0
0x14001efc6  jz      short loc_14001EFE2
0x14001efc8  lea     rcx, [rdi+1A8h]
0x14001efcf  call    cs:__imp_NetioShutdownWorkQueue
0x14001efd6  nop     dword ptr [rax+rax+00h]
0x14001efdb  mov     byte ptr [rdi+1D8h], 0
0x14001efe2  xorps   xmm0, xmm0
0x14001efe5  mov     byte ptr [rdi+188h], 1
0x14001efec  xor     eax, eax
0x14001efee  lea     rcx, [rsp+78h+Event]; Event
0x14001eff3  xor     r8d, r8d; State
0x14001eff6  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x14001effb  xor     edx, edx; Type
0x14001effd  movups  xmmword ptr [rsp+78h+Event.Header], xmm0
0x14001f002  call    cs:__imp_KeInitializeEvent
0x14001f009  nop     dword ptr [rax+rax+00h]
0x14001f00e  mov     ebx, [rdi+198h]
0x14001f014  lea     rax, [rsp+78h+Event]
0x14001f019  mov     dl, 1
0x14001f01b  mov     [rdi+190h], rax
0x14001f022  mov     rcx, rdi
0x14001f025  call    VmbusTlDisconnectPartitionEndpoints
0x14001f02a  mov     rcx, rsi; FastMutex
0x14001f02d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001f034  nop     dword ptr [rax+rax+00h]
0x14001f039  call    cs:__imp_KeLeaveCriticalRegion
0x14001f040  nop     dword ptr [rax+rax+00h]
0x14001f045  test    ebx, ebx
0x14001f047  jz      short loc_14001F06B
0x14001f049  xor     r9d, r9d; Alertable
0x14001f04c  mov     [rsp+78h+Timeout], 0; Timeout
0x14001f055  xor     r8d, r8d; WaitMode
0x14001f058  lea     rcx, [rsp+78h+Event]; Object
0x14001f05d  xor     edx, edx; WaitReason
0x14001f05f  call    cs:__imp_KeWaitForSingleObject
0x14001f066  nop     dword ptr [rax+rax+00h]
0x14001f06b  call    cs:__imp_KeEnterCriticalRegion
0x14001f072  nop     dword ptr [rax+rax+00h]
0x14001f077  mov     rcx, rsi; FastMutex
0x14001f07a  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001f081  nop     dword ptr [rax+rax+00h]
0x14001f086  mov     rcx, rsi; FastMutex
0x14001f089  mov     qword ptr [rdi+190h], 0
0x14001f094  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001f09b  nop     dword ptr [rax+rax+00h]
0x14001f0a0  call    cs:__imp_KeLeaveCriticalRegion
0x14001f0a7  nop     dword ptr [rax+rax+00h]
0x14001f0ac  mov     eax, cs:dword_140013058
0x14001f0b2  lea     rsi, aDereferenceObj; "Dereference object"
0x14001f0b9  mov     rbx, [rdi+0C8h]
0x14001f0c0  cmp     eax, 5
0x14001f0c3  jbe     short loc_14001F0E2
0x14001f0c5  mov     r9, [rbx+8]
0x14001f0c9  lea     rcx, aVmbustlcleanup; "VmbusTlCleanupPartition"
0x14001f0d0  mov     r8, rbx
0x14001f0d3  mov     [rsp+78h+Timeout], rsi
0x14001f0d8  mov     edx, 208h
0x14001f0dd  call    HvsocketTraceReferenceCount
0x14001f0e2  mov     rax, rbp
0x14001f0e5  lock xadd [rbx+8], rax
0x14001f0eb  add     rax, rbp
0x14001f0ee  test    rax, rax
0x14001f0f1  jg      short loc_14001F143
0x14001f0f3  jz      short loc_14001F0FC
0x14001f0f5  mov     rcx, r15
0x14001f0f8  int     29h; Win8: RtlFailFast(ecx)
0x14001f0fa  jmp     short loc_14001F143
0x14001f0fc  mov     rax, [rbx+50h]
0x14001f100  test    rax, rax
0x14001f103  jz      short loc_14001F10D
0x14001f105  mov     rcx, rbx
0x14001f108  call    _guard_dispatch_icall
0x14001f10d  mov     ecx, [rbx+58h]
0x14001f110  sub     ecx, 1
0x14001f113  jz      short loc_14001F12F
0x14001f115  cmp     ecx, 1
0x14001f118  jnz     short loc_14001F143
0x14001f11a  mov     rcx, [rbx+60h]; Lookaside
0x14001f11e  mov     rdx, rbx; Entry
0x14001f121  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001f128  nop     dword ptr [rax+rax+00h]
0x14001f12d  jmp     short loc_14001F143
0x14001f12f  mov     edx, 69706E56h; Tag
0x14001f134  mov     rcx, rbx; P
0x14001f137  call    cs:__imp_ExFreePoolWithTag
0x14001f13e  nop     dword ptr [rax+rax+00h]
0x14001f143  mov     eax, cs:dword_140013058
0x14001f149  cmp     eax, 5
0x14001f14c  jbe     short loc_14001F16B
0x14001f14e  mov     r9, [rdi+8]
0x14001f152  lea     rcx, aVmbustlcleanup; "VmbusTlCleanupPartition"
0x14001f159  mov     r8, rdi
0x14001f15c  mov     [rsp+78h+Timeout], rsi
0x14001f161  mov     edx, 20Dh
0x14001f166  call    HvsocketTraceReferenceCount
0x14001f16b  mov     rax, rbp
0x14001f16e  lock xadd [rdi+8], rax
0x14001f174  add     rax, rbp
0x14001f177  test    rax, rax
0x14001f17a  jg      loc_14001EE42
0x14001f180  jz      short loc_14001F18C
0x14001f182  mov     rcx, r15
0x14001f185  int     29h; Win8: RtlFailFast(ecx)
0x14001f187  jmp     loc_14001EE42
0x14001f18c  mov     rax, [rdi+50h]
0x14001f190  test    rax, rax
0x14001f193  jz      short loc_14001F19D
0x14001f195  mov     rcx, rdi
0x14001f198  call    _guard_dispatch_icall
0x14001f19d  mov     ecx, [rdi+58h]
0x14001f1a0  sub     ecx, 1
0x14001f1a3  jz      short loc_14001F1C6
0x14001f1a5  cmp     ecx, 1
0x14001f1a8  jnz     loc_14001EE42
0x14001f1ae  mov     rcx, [rdi+60h]; Lookaside
0x14001f1b2  mov     rdx, rdi; Entry
0x14001f1b5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001f1bc  nop     dword ptr [rax+rax+00h]
0x14001f1c1  jmp     loc_14001EE42
0x14001f1c6  mov     edx, 69706E56h; Tag
0x14001f1cb  mov     rcx, rdi; P
0x14001f1ce  call    cs:__imp_ExFreePoolWithTag
0x14001f1d5  nop     dword ptr [rax+rax+00h]
0x14001f1da  jmp     loc_14001EE42
0x14001f1df  mov     ecx, 3
0x14001f1e4  int     29h; Win8: RtlFailFast(ecx)
```
