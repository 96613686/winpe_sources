# CdInitializeGlobalData

- ea: `0x14001c078`
- end: `0x14001c340`
- name: `CdInitializeGlobalData`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001c348`

## callees

- `0x140003300`
- `0x14001c078`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14001c2a2`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001c2a2`
- `ntoskrnl!FsRtlCopyRead` at `0x14001c0be`
- `ntoskrnl!FsRtlMdlReadDev` at `0x14001c14f`
- `ntoskrnl!FsRtlMdlReadCompleteDev` at `0x14001c15d`
- `ntoskrnl!FsRtlPrepareMdlWriteDev` at `0x14001c16b`
- `ntoskrnl!FsRtlMdlWriteCompleteDev` at `0x14001c179`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001c1c0`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001c1c0`
- `ntoskrnl!KeInitializeEvent` at `0x14001c24a`
- `ntoskrnl!KeInitializeEvent` at `0x14001c24a`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001c283`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001c283`
- `ntoskrnl!MmQuerySystemSize` at `0x14001c2b5`
- `ntoskrnl!MmQuerySystemSize` at `0x14001c2b5`

## pseudocode

```c
__int64 __fastcall CdInitializeGlobalData(struct _DRIVER_OBJECT *a1, struct _DEVICE_OBJECT *a2)
{
  MM_SYSTEMSIZE SystemSize; // eax
  __int32 v6; // eax

  memset(&CdFastIoDispatch, 0, 0xE0u);
  CdFastIoDispatch = 224;
  qword_1400071E8 = (__int64)CdFastIoCheckIfPossible;
  qword_1400071F0 = (__int64)FsRtlCopyRead;
  qword_140007238 = 0;
  qword_140007200 = (__int64)&CdFastQueryBasicInfo;
  qword_140007208 = (__int64)&CdFastQueryStdInfo;
  qword_140007210 = (__int64)CdFastLock;
  qword_140007218 = (__int64)CdFastUnlockSingle;
  qword_140007220 = (__int64)CdFastUnlockAll;
  qword_140007228 = (__int64)CdFastUnlockAllByKey;
  qword_140007240 = (__int64)CdReleaseForCreateSection;
  qword_140007250 = (__int64)CdFastQueryNetworkInfo;
  qword_140007260 = (__int64)FsRtlMdlReadDev;
  qword_140007268 = (__int64)FsRtlMdlReadCompleteDev;
  qword_140007270 = (__int64)FsRtlPrepareMdlWriteDev;
  qword_140007278 = (__int64)FsRtlMdlWriteCompleteDev;
  memset(&CdData, 0, 0x160u);
  CdData = 23069441;
  qword_1400072F8 = (__int64)&qword_1400072F0;
  qword_1400072F0 = (__int64)&qword_1400072F0;
  DriverObject = a1;
  DeviceObject = a2;
  ExInitializeResourceLite(&Resource);
  FastMutex.Owner = 0;
  Callbacks.AcquireForLazyWrite = (PACQUIRE_FOR_LAZY_WRITE)&CdAcquireForCache;
  Callbacks.AcquireForReadAhead = (PACQUIRE_FOR_READ_AHEAD)&CdAcquireForCache;
  Callbacks.ReleaseFromLazyWrite = (PRELEASE_FROM_LAZY_WRITE)CdReleaseFromCache;
  Callbacks.ReleaseFromReadAhead = (PRELEASE_FROM_READ_AHEAD)CdReleaseFromCache;
  qword_140007418 = (__int64)CdNoopAcquire;
  qword_140007428 = (__int64)CdNoopAcquire;
  qword_140007420 = (__int64)CdNoopRelease;
  qword_140007430 = (__int64)CdNoopRelease;
  FastMutex.Count = 1;
  FastMutex.Contention = 0;
  KeInitializeEvent(&FastMutex.Event, SynchronizationEvent, 0);
  qword_140007320 = (__int64)&qword_140007318;
  qword_140007318 = (__int64)&qword_140007318;
  qword_140007338 = (__int64)&qword_140007330;
  qword_140007330 = (__int64)&qword_140007330;
  IoWorkItem = IoAllocateWorkItem(a2);
  if ( IoWorkItem )
  {
    SystemSize = MmQuerySystemSize();
    if ( SystemSize )
    {
      v6 = SystemSize - 1;
      if ( v6 )
      {
        if ( v6 == 1 )
        {
          dword_140007304 = 32;
          dword_140007344 = 72;
          dword_140007348 = 18;
        }
      }
      else
      {
        dword_140007304 = 8;
        dword_140007344 = 24;
        dword_140007348 = 6;
      }
    }
    else
    {
      dword_140007304 = 4;
      dword_140007344 = 8;
      dword_140007348 = 2;
    }
    return 0;
  }
  else
  {
    ExDeleteResourceLite(&Resource);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14001c078  mov     [rsp+arg_0], rbx
0x14001c07d  mov     [rsp+arg_8], rsi
0x14001c082  push    rdi
0x14001c083  sub     rsp, 20h
0x14001c087  mov     rdi, rdx
0x14001c08a  mov     rbx, rcx
0x14001c08d  mov     esi, 0E0h
0x14001c092  lea     rcx, CdFastIoDispatch; void *
0x14001c099  mov     r8d, esi; Size
0x14001c09c  xor     edx, edx; Val
0x14001c09e  call    memset
0x14001c0a3  lea     rax, CdFastIoCheckIfPossible
0x14001c0aa  mov     cs:CdFastIoDispatch, esi
0x14001c0b0  mov     cs:qword_1400071E8, rax
0x14001c0b7  lea     rcx, CdData; void *
0x14001c0be  mov     rax, cs:__imp_FsRtlCopyRead
0x14001c0c5  xor     edx, edx; Val
0x14001c0c7  mov     cs:qword_1400071F0, rax
0x14001c0ce  mov     r8d, 160h; Size
0x14001c0d4  lea     rax, CdFastQueryBasicInfo
0x14001c0db  mov     cs:qword_140007238, 0
0x14001c0e6  mov     cs:qword_140007200, rax
0x14001c0ed  lea     rax, CdFastQueryStdInfo
0x14001c0f4  mov     cs:qword_140007208, rax
0x14001c0fb  lea     rax, CdFastLock
0x14001c102  mov     cs:qword_140007210, rax
0x14001c109  lea     rax, CdFastUnlockSingle
0x14001c110  mov     cs:qword_140007218, rax
0x14001c117  lea     rax, CdFastUnlockAll
0x14001c11e  mov     cs:qword_140007220, rax
0x14001c125  lea     rax, CdFastUnlockAllByKey
0x14001c12c  mov     cs:qword_140007228, rax
0x14001c133  lea     rax, CdReleaseForCreateSection
0x14001c13a  mov     cs:qword_140007240, rax
0x14001c141  lea     rax, CdFastQueryNetworkInfo
0x14001c148  mov     cs:qword_140007250, rax
0x14001c14f  mov     rax, cs:__imp_FsRtlMdlReadDev
0x14001c156  mov     cs:qword_140007260, rax
0x14001c15d  mov     rax, cs:__imp_FsRtlMdlReadCompleteDev
0x14001c164  mov     cs:qword_140007268, rax
0x14001c16b  mov     rax, cs:__imp_FsRtlPrepareMdlWriteDev
0x14001c172  mov     cs:qword_140007270, rax
0x14001c179  mov     rax, cs:__imp_FsRtlMdlWriteCompleteDev
0x14001c180  mov     cs:qword_140007278, rax
0x14001c187  call    memset
0x14001c18c  lea     rax, qword_1400072F0
0x14001c193  mov     cs:CdData, 1600301h
0x14001c19d  lea     rcx, Resource; Resource
0x14001c1a4  mov     cs:qword_1400072F8, rax
0x14001c1ab  mov     cs:qword_1400072F0, rax
0x14001c1b2  mov     cs:DriverObject, rbx
0x14001c1b9  mov     cs:DeviceObject, rdi
0x14001c1c0  call    cs:__imp_ExInitializeResourceLite
0x14001c1c7  nop     dword ptr [rax+rax+00h]
0x14001c1cc  lea     rcx, CdAcquireForCache
0x14001c1d3  mov     cs:FastMutex.Owner, 0
0x14001c1de  mov     cs:Callbacks.AcquireForLazyWrite, rcx
0x14001c1e5  lea     rax, CdReleaseFromCache
0x14001c1ec  mov     cs:Callbacks.AcquireForReadAhead, rcx
0x14001c1f3  mov     edx, 1; Type
0x14001c1f8  lea     rcx, CdNoopAcquire
0x14001c1ff  mov     cs:Callbacks.ReleaseFromLazyWrite, rax
0x14001c206  mov     cs:Callbacks.ReleaseFromReadAhead, rax
0x14001c20d  xor     r8d, r8d; State
0x14001c210  lea     rax, CdNoopRelease
0x14001c217  mov     cs:qword_140007418, rcx
0x14001c21e  mov     cs:qword_140007428, rcx
0x14001c225  lea     rcx, FastMutex.Event; Event
0x14001c22c  mov     cs:qword_140007420, rax
0x14001c233  mov     cs:qword_140007430, rax
0x14001c23a  mov     cs:FastMutex.Count, edx
0x14001c240  mov     cs:FastMutex.Contention, 0
0x14001c24a  call    cs:__imp_KeInitializeEvent
0x14001c251  nop     dword ptr [rax+rax+00h]
0x14001c256  lea     rax, qword_140007318
0x14001c25d  mov     rcx, rdi; DeviceObject
0x14001c260  mov     cs:qword_140007320, rax
0x14001c267  mov     cs:qword_140007318, rax
0x14001c26e  lea     rax, qword_140007330
0x14001c275  mov     cs:qword_140007338, rax
0x14001c27c  mov     cs:qword_140007330, rax
0x14001c283  call    cs:__imp_IoAllocateWorkItem
0x14001c28a  nop     dword ptr [rax+rax+00h]
0x14001c28f  mov     cs:IoWorkItem, rax
0x14001c296  test    rax, rax
0x14001c299  jnz     short loc_14001C2B5
0x14001c29b  lea     rcx, Resource; Resource
0x14001c2a2  call    cs:__imp_ExDeleteResourceLite
0x14001c2a9  nop     dword ptr [rax+rax+00h]
0x14001c2ae  mov     eax, 0C000009Ah
0x14001c2b3  jmp     short loc_14001C32F
0x14001c2b5  call    cs:__imp_MmQuerySystemSize
0x14001c2bc  nop     dword ptr [rax+rax+00h]
0x14001c2c1  test    eax, eax
0x14001c2c3  jz      short loc_14001C30F
0x14001c2c5  sub     eax, 1
0x14001c2c8  jz      short loc_14001C2EF
0x14001c2ca  cmp     eax, 1
0x14001c2cd  jnz     short loc_14001C32D
0x14001c2cf  mov     cs:dword_140007304, 20h ; ' '
0x14001c2d9  mov     cs:dword_140007344, 48h ; 'H'
0x14001c2e3  mov     cs:dword_140007348, 12h
0x14001c2ed  jmp     short loc_14001C32D
0x14001c2ef  mov     cs:dword_140007304, 8
0x14001c2f9  mov     cs:dword_140007344, 18h
0x14001c303  mov     cs:dword_140007348, 6
0x14001c30d  jmp     short loc_14001C32D
0x14001c30f  mov     cs:dword_140007304, 4
0x14001c319  mov     cs:dword_140007344, 8
0x14001c323  mov     cs:dword_140007348, 2
0x14001c32d  xor     eax, eax
0x14001c32f  mov     rbx, [rsp+28h+arg_0]
0x14001c334  mov     rsi, [rsp+28h+arg_8]
0x14001c339  add     rsp, 20h
0x14001c33d  pop     rdi
0x14001c33e  retn
```
