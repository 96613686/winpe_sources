# MspInitializeLazyWriter(void)

- ea: `0x1c00548e0`
- end: `0x1c0054b89`
- name: `?MspInitializeLazyWriter@@YAJXZ`
- size: `681`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1c0054b90`

## callees

- `0x1c0052b80`
- `0x1c005487c`
- `0x1c00548e0`
- `0x1c006ac80`
- `0x1c01734d0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c005493b`
- `ntoskrnl!KeInitializeEvent` at `0x1c0054954`
- `ntoskrnl!KeInitializeEvent` at `0x1c005496d`
- `ntoskrnl!KeInitializeEvent` at `0x1c005493b`
- `ntoskrnl!KeInitializeEvent` at `0x1c0054954`
- `ntoskrnl!KeInitializeEvent` at `0x1c005496d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c005490f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0054922`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c00549c5`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c005490f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0054922`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c00549c5`
- `ntoskrnl!ZwClose` at `0x1c0054af8`
- `ntoskrnl!ZwClose` at `0x1c0054af8`
- `ntoskrnl!PsCreateSystemThread` at `0x1c0054adc`
- `ntoskrnl!PsCreateSystemThread` at `0x1c0054adc`

## pseudocode

```c
NTSTATUS MspInitializeLazyWriter(void)
{
  int v0; // ebp
  struct _LIST_ENTRY near **v1; // rbx
  KSPIN_LOCK *v2; // rdi
  __int64 v3; // rsi
  unsigned __int64 v4; // rcx
  CmsVolume *v5; // rax
  NTSTATUS result; // eax
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *ThreadHandle; // [rsp+80h] [rbp+8h] BYREF

  v0 = 0;
  ThreadHandle = 0;
  MsInitializeFastResource(&VolumeLazyWriterResource, 0);
  KeInitializeSpinLock(&LazyWriterSpinLock);
  KeInitializeSpinLock(&DirtyPageCountSpinLock);
  KeInitializeEvent(&LazyWriterScanEvent, SynchronizationEvent, 0);
  KeInitializeEvent(&StopDeferredIoThreadEvent, SynchronizationEvent, 0);
  KeInitializeEvent(&DeferredIoThreadTerminatedEvent, SynchronizationEvent, 0);
  LazyWriterInitialized = 1;
  qword_1C01377C8 = (__int64)&DirtyTableList;
  v1 = &WorkerEntriesQueue;
  DirtyTableList = (struct _LIST_ENTRY *)&DirtyTableList;
  v2 = &LazyWriterQueueSpinLock;
  qword_1C01377A0 = (__int64)&VolumeList;
  v3 = 3;
  VolumeList.Flink = &VolumeList;
  do
  {
    v1[1] = (struct _LIST_ENTRY near *)v1;
    *v1 = (struct _LIST_ENTRY near *)v1;
    KeInitializeSpinLock(v2++);
    v1 += 2;
    --v3;
  }
  while ( v3 );
  v5 = (CmsVolume *)CmsVolume::operator new(v4);
  if ( v5 )
    v5 = CmsVolume::CmsVolume(v5);
  VolumeListCursor = v5;
  if ( !v5 )
    return -1073741670;
  dword_1C0136C58 = 503653170;
  word_1C0136C5D = 7680;
  byte_1C0136C5C = 35;
  if ( dword_1C0136C64 )
    LazyWriterLazyThresholdPerVolume = dword_1C0136C64;
  if ( dword_1C0136C68 )
    LazyWriterMaxWorkersPerVolume = dword_1C0136C68;
  if ( dword_1C0136C6C )
    LazyWriterMaxLogWorkersPerVolume = dword_1C0136C6C;
  if ( dword_1C0136C70 )
    LazyWriterMaxWorkersTotal = dword_1C0136C70;
  if ( dword_1C0136C74 )
    LazyWriterMaxLogWorkersTotal = dword_1C0136C74;
  if ( dword_1C0136C78 )
    LazyWriterScanThresholdPerVolume = dword_1C0136C78;
  dword_1C0136C7C = 50;
  if ( byte_1C0136979 || byte_1C0136978 )
  {
    memset(&ObjectAttributes.Length + 1, 0, 44);
    ObjectAttributes.Length = 48;
    result = PsCreateSystemThread(
               &ThreadHandle,
               0x1FFFFFu,
               &ObjectAttributes,
               0,
               0,
               (PKSTART_ROUTINE)MspDeferredIoThread,
               0);
    if ( result < 0 )
      return result;
    ZwClose(ThreadHandle);
    v0 = ((__int64 (__fastcall *)(void (__fastcall *)(void *, unsigned __int64, unsigned int), void **))qword_1C0136B08)(
           MspExternalCacheCallback,
           &ExternalCacheContext);
    if ( v0 >= 0 )
    {
      LazyWriterEnabled = byte_1C0136978;
      LazyCheckpointingEnabled = byte_1C0136979;
    }
  }
  dword_1C0136C88 = 128;
  result = v0;
  qword_1C0136C90 = 5;
  dword_1C0136C98 = 35;
  dword_1C0136C9C = 55;
  dword_1C0136CA0 = 1500;
  return result;
}

```

## disassembly

```asm
0x1c00548e0  mov     rax, rsp
0x1c00548e3  mov     [rax+10h], rbx
0x1c00548e7  mov     [rax+18h], rbp
0x1c00548eb  mov     [rax+20h], rsi
0x1c00548ef  push    rdi
0x1c00548f0  sub     rsp, 70h
0x1c00548f4  xor     ebp, ebp
0x1c00548f6  lea     rcx, ?VolumeLazyWriterResource@@3U_MS_ERESOURCE@@A; _MS_ERESOURCE VolumeLazyWriterResource
0x1c00548fd  and     [rax+8], rbp
0x1c0054901  xor     edx, edx
0x1c0054903  call    MsInitializeFastResource
0x1c0054908  lea     rcx, ?LazyWriterSpinLock@@3_KA; SpinLock
0x1c005490f  call    cs:__imp_KeInitializeSpinLock
0x1c0054916  nop     dword ptr [rax+rax+00h]
0x1c005491b  lea     rcx, ?DirtyPageCountSpinLock@@3_KA; SpinLock
0x1c0054922  call    cs:__imp_KeInitializeSpinLock
0x1c0054929  nop     dword ptr [rax+rax+00h]
0x1c005492e  xor     r8d, r8d; State
0x1c0054931  lea     edx, [rbp+1]; Type
0x1c0054934  lea     rcx, ?LazyWriterScanEvent@@3U_KEVENT@@A; Event
0x1c005493b  call    cs:__imp_KeInitializeEvent
0x1c0054942  nop     dword ptr [rax+rax+00h]
0x1c0054947  xor     r8d, r8d; State
0x1c005494a  lea     edx, [rbp+1]; Type
0x1c005494d  lea     rcx, ?StopDeferredIoThreadEvent@@3U_KEVENT@@A; Event
0x1c0054954  call    cs:__imp_KeInitializeEvent
0x1c005495b  nop     dword ptr [rax+rax+00h]
0x1c0054960  xor     r8d, r8d; State
0x1c0054963  lea     edx, [rbp+1]; Type
0x1c0054966  lea     rcx, ?DeferredIoThreadTerminatedEvent@@3U_KEVENT@@A; Event
0x1c005496d  call    cs:__imp_KeInitializeEvent
0x1c0054974  nop     dword ptr [rax+rax+00h]
0x1c0054979  lea     rax, ?DirtyTableList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DirtyTableList
0x1c0054980  mov     cs:?LazyWriterInitialized@@3EA, 1; uchar LazyWriterInitialized
0x1c0054987  mov     cs:qword_1C01377C8, rax
0x1c005498e  lea     rbx, ?WorkerEntriesQueue@@3PAU_LIST_ENTRY@@A; _LIST_ENTRY near * WorkerEntriesQueue
0x1c0054995  mov     cs:?DirtyTableList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY DirtyTableList
0x1c005499c  lea     rdi, ?LazyWriterQueueSpinLock@@3PA_KA; unsigned __int64 near * LazyWriterQueueSpinLock
0x1c00549a3  lea     rax, ?VolumeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY VolumeList
0x1c00549aa  mov     cs:qword_1C01377A0, rax
0x1c00549b1  lea     esi, [rbp+3]
0x1c00549b4  mov     cs:?VolumeList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY VolumeList
0x1c00549bb  mov     rcx, rdi; SpinLock
0x1c00549be  mov     [rbx+8], rbx
0x1c00549c2  mov     [rbx], rbx
0x1c00549c5  call    cs:__imp_KeInitializeSpinLock
0x1c00549cc  nop     dword ptr [rax+rax+00h]
0x1c00549d1  add     rdi, 8
0x1c00549d5  add     rbx, 10h
0x1c00549d9  sub     rsi, 1
0x1c00549dd  jnz     short loc_1C00549BB
0x1c00549df  call    ??2CmsVolume@@SAPEAX_K@Z; CmsVolume::operator new(unsigned __int64)
0x1c00549e4  test    rax, rax
0x1c00549e7  jz      loc_1C00896E4
0x1c00549ed  mov     rcx, rax; this
0x1c00549f0  call    ??0CmsVolume@@QEAA@XZ; CmsVolume::CmsVolume(void)
0x1c00549f5  mov     cs:?VolumeListCursor@@3PEAVCmsVolume@@EA, rax; CmsVolume * VolumeListCursor
0x1c00549fc  test    rax, rax
0x1c00549ff  jz      loc_1C00896E9
0x1c0054a05  mov     eax, cs:dword_1C0136C64
0x1c0054a0b  mov     cs:dword_1C0136C58, 1E052332h
0x1c0054a15  mov     cs:word_1C0136C5D, 1E00h
0x1c0054a1e  mov     cs:byte_1C0136C5C, 23h ; '#'
0x1c0054a25  test    eax, eax
0x1c0054a27  jnz     loc_1C00896F3
0x1c0054a2d  mov     eax, cs:dword_1C0136C68
0x1c0054a33  test    eax, eax
0x1c0054a35  jnz     loc_1C00896FE
0x1c0054a3b  mov     eax, cs:dword_1C0136C6C
0x1c0054a41  test    eax, eax
0x1c0054a43  jnz     loc_1C0089709
0x1c0054a49  mov     eax, cs:dword_1C0136C70
0x1c0054a4f  test    eax, eax
0x1c0054a51  jnz     loc_1C0089714
0x1c0054a57  mov     eax, cs:dword_1C0136C74
0x1c0054a5d  test    eax, eax
0x1c0054a5f  jnz     loc_1C008971F
0x1c0054a65  mov     eax, cs:dword_1C0136C78
0x1c0054a6b  test    eax, eax
0x1c0054a6d  jnz     loc_1C008972A
0x1c0054a73  cmp     cs:byte_1C0136979, bpl
0x1c0054a7a  mov     cs:dword_1C0136C7C, 32h ; '2'
0x1c0054a84  jz      loc_1C0089735
0x1c0054a8a  and     [rsp+78h+var_48], rbp
0x1c0054a8f  lea     rax, ?MspDeferredIoThread@@YAXPEAX@Z; MspDeferredIoThread(void *)
0x1c0054a96  and     dword ptr [rsp+78h+ObjectAttributes+4], ebp
0x1c0054a9a  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x1c0054a9f  and     dword ptr [rsp+78h+ObjectAttributes+1Ch], ebp
0x1c0054aa3  lea     rcx, [rsp+78h+ThreadHandle]; ThreadHandle
0x1c0054aab  and     [rsp+78h+ObjectAttributes.RootDirectory], rbp
0x1c0054ab0  xorps   xmm0, xmm0
0x1c0054ab3  and     [rsp+78h+ObjectAttributes.Attributes], ebp
0x1c0054ab7  xor     r9d, r9d; ProcessHandle
0x1c0054aba  and     [rsp+78h+ObjectAttributes.ObjectName], rbp
0x1c0054abf  mov     edx, 1FFFFFh; DesiredAccess
0x1c0054ac4  mov     [rsp+78h+StartRoutine], rax; StartRoutine
0x1c0054ac9  and     [rsp+78h+var_58], rbp
0x1c0054ace  mov     [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x1c0054ad6  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c0054adc  call    cs:__imp_PsCreateSystemThread
0x1c0054ae3  nop     dword ptr [rax+rax+00h]
0x1c0054ae8  test    eax, eax
0x1c0054aea  js      loc_1C0054B72
0x1c0054af0  mov     rcx, [rsp+78h+ThreadHandle]; Handle
0x1c0054af8  call    cs:__imp_ZwClose
0x1c0054aff  nop     dword ptr [rax+rax+00h]
0x1c0054b04  mov     rax, cs:qword_1C0136B08
0x1c0054b0b  lea     rdx, ?ExternalCacheContext@@3PEAXEA; void * ExternalCacheContext
0x1c0054b12  lea     rcx, ?MspExternalCacheCallback@@YAXPEAX_KK@Z; MspExternalCacheCallback(void *,unsigned __int64,ulong)
0x1c0054b19  call    cs:__guard_dispatch_icall_fptr
0x1c0054b1f  mov     ebp, eax
0x1c0054b21  test    eax, eax
0x1c0054b23  js      short loc_1C0054B3D
0x1c0054b25  mov     cl, cs:byte_1C0136978
0x1c0054b2b  mov     cs:?LazyWriterEnabled@@3EA, cl; uchar LazyWriterEnabled
0x1c0054b31  mov     cl, cs:byte_1C0136979
0x1c0054b37  mov     cs:?LazyCheckpointingEnabled@@3EA, cl; uchar LazyCheckpointingEnabled
0x1c0054b3d  mov     cs:dword_1C0136C88, 80h
0x1c0054b47  mov     eax, ebp
0x1c0054b49  mov     cs:qword_1C0136C90, 5
0x1c0054b54  mov     cs:dword_1C0136C98, 23h ; '#'
0x1c0054b5e  mov     cs:dword_1C0136C9C, 37h ; '7'
0x1c0054b68  mov     cs:dword_1C0136CA0, 5DCh
0x1c0054b72  lea     r11, [rsp+78h+var_8]
0x1c0054b77  mov     rbx, [r11+18h]
0x1c0054b7b  mov     rbp, [r11+20h]
0x1c0054b7f  mov     rsi, [r11+28h]
0x1c0054b83  mov     rsp, r11
0x1c0054b86  pop     rdi
0x1c0054b87  retn
0x1c00896e4  jmp     loc_1C00549F5
0x1c00896e9  mov     eax, 0C000009Ah
0x1c00896ee  jmp     loc_1C0054B72
0x1c00896f3  mov     cs:?LazyWriterLazyThresholdPerVolume@@3JA, eax; long LazyWriterLazyThresholdPerVolume
0x1c00896f9  jmp     loc_1C0054A2D
0x1c00896fe  mov     cs:?LazyWriterMaxWorkersPerVolume@@3JA, eax; long LazyWriterMaxWorkersPerVolume
0x1c0089704  jmp     loc_1C0054A3B
0x1c0089709  mov     cs:?LazyWriterMaxLogWorkersPerVolume@@3JA, eax; long LazyWriterMaxLogWorkersPerVolume
0x1c008970f  jmp     loc_1C0054A49
0x1c0089714  mov     cs:?LazyWriterMaxWorkersTotal@@3JA, eax; long LazyWriterMaxWorkersTotal
0x1c008971a  jmp     loc_1C0054A57
0x1c008971f  mov     cs:?LazyWriterMaxLogWorkersTotal@@3JA, eax; long LazyWriterMaxLogWorkersTotal
0x1c0089725  jmp     loc_1C0054A65
0x1c008972a  mov     cs:?LazyWriterScanThresholdPerVolume@@3JA, eax; long LazyWriterScanThresholdPerVolume
0x1c0089730  jmp     loc_1C0054A73
0x1c0089735  cmp     cs:byte_1C0136978, bpl
0x1c008973c  jz      loc_1C0054B3D
0x1c0089742  jmp     loc_1C0054A8A
```
