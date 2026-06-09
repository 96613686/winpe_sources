# MupiPrefixCacheRegistryChangeHandler

- ea: `0x140010a80`
- end: `0x140010b54`
- name: `MupiPrefixCacheRegistryChangeHandler`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x140010a80`
- `0x140010b5c`
- `0x140010bb8`
- `0x140010c94`
- `0x140010d68`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010a99`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010a99`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010ae5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010ae5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010a84`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010a84`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140010b42`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140010b42`
- `ntoskrnl!KeCancelTimer` at `0x140010ab8`
- `ntoskrnl!KeCancelTimer` at `0x140010ab8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010af1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010af1`

## pseudocode

```c
NTSTATUS MupiPrefixCacheRegistryChangeHandler()
{
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  MupiReadPrefixCacheTimeoutFromRegistry(&qword_14000A9F0);
  if ( KeCancelTimer(&MupiPrefixGarbageCollectionTimer) )
    MupiPrefixScheduleGarbageCollectionTimeout();
  MupiReadPrefixCacheMaxSizeFromRegistry(&dword_14000A9F8);
  MupiPrefixCacheSizePolicyCheck();
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  return ZwNotifyChangeKey(
           WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink,
           0,
           (PIO_APC_ROUTINE)&WPP_MAIN_CB.Dpc.DpcData,
           (PVOID)1,
           (PIO_STATUS_BLOCK)&WPP_MAIN_CB.SectorSize,
           4u,
           1u,
           0,
           0,
           1u);
}

```

## disassembly

```asm
0x140010a80  sub     rsp, 58h
0x140010a84  call    cs:__imp_KeEnterCriticalRegion
0x140010a8b  nop     dword ptr [rax+rax+00h]
0x140010a90  mov     dl, 1; Wait
0x140010a92  lea     rcx, Resource; Resource
0x140010a99  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140010aa0  nop     dword ptr [rax+rax+00h]
0x140010aa5  lea     rcx, qword_14000A9F0
0x140010aac  call    MupiReadPrefixCacheTimeoutFromRegistry
0x140010ab1  lea     rcx, MupiPrefixGarbageCollectionTimer; PKTIMER
0x140010ab8  call    cs:__imp_KeCancelTimer
0x140010abf  nop     dword ptr [rax+rax+00h]
0x140010ac4  test    al, al
0x140010ac6  jz      short loc_140010ACD
0x140010ac8  call    MupiPrefixScheduleGarbageCollectionTimeout
0x140010acd  lea     rcx, dword_14000A9F8
0x140010ad4  call    MupiReadPrefixCacheMaxSizeFromRegistry
0x140010ad9  call    MupiPrefixCacheSizePolicyCheck
0x140010ade  lea     rcx, Resource; Resource
0x140010ae5  call    cs:__imp_ExReleaseResourceLite
0x140010aec  nop     dword ptr [rax+rax+00h]
0x140010af1  call    cs:__imp_KeLeaveCriticalRegion
0x140010af8  nop     dword ptr [rax+rax+00h]
0x140010afd  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink; KeyHandle
0x140010b04  lea     rax, WPP_MAIN_CB.SectorSize
0x140010b0b  mov     [rsp+58h+Asynchronous], 1; Asynchronous
0x140010b10  lea     r8, WPP_MAIN_CB.Dpc.DpcData; ApcRoutine
0x140010b17  mov     [rsp+58h+BufferSize], 0; BufferSize
0x140010b1f  mov     r9d, 1; ApcContext
0x140010b25  mov     [rsp+58h+Buffer], 0; Buffer
0x140010b2e  xor     edx, edx; Event
0x140010b30  mov     [rsp+58h+WatchTree], 1; WatchTree
0x140010b35  mov     [rsp+58h+CompletionFilter], 4; CompletionFilter
0x140010b3d  mov     [rsp+58h+IoStatusBlock], rax; IoStatusBlock
0x140010b42  call    cs:__imp_ZwNotifyChangeKey
0x140010b49  nop     dword ptr [rax+rax+00h]
0x140010b4e  add     rsp, 58h
0x140010b52  retn
```
