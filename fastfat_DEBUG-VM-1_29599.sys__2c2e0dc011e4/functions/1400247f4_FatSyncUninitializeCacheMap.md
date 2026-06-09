# FatSyncUninitializeCacheMap

- ea: `0x1400247f4`
- end: `0x140024866`
- name: `FatSyncUninitializeCacheMap`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000363c`
- `0x140023cc4`
- `0x140048848`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140024816`
- `ntoskrnl!KeInitializeEvent` at `0x140024816`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024853`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024853`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140024831`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140024831`

## pseudocode

```c
NTSTATUS __fastcall FatSyncUninitializeCacheMap(__int64 a1, struct _FILE_OBJECT *a2)
{
  _CACHE_UNINITIALIZE_EVENT UninitializeEvent; // [rsp+30h] [rbp-28h] BYREF

  memset(&UninitializeEvent, 0, sizeof(UninitializeEvent));
  KeInitializeEvent(&UninitializeEvent.Event, SynchronizationEvent, 0);
  CcUninitializeCacheMap(a2, &FatLargeZero, &UninitializeEvent);
  return KeWaitForSingleObject(&UninitializeEvent.Event, Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x1400247f4  push    rbx
0x1400247f6  sub     rsp, 50h
0x1400247fa  xorps   xmm0, xmm0
0x1400247fd  lea     rcx, [rsp+58h+UninitializeEvent.Event]; Event
0x140024802  xor     r8d, r8d; State
0x140024805  mov     rbx, rdx
0x140024808  movups  xmmword ptr [rsp+30h], xmm0
0x14002480d  movups  xmmword ptr [rsp+58h+UninitializeEvent.Event.Header.WaitListHead.Flink], xmm0
0x140024812  lea     edx, [r8+1]; Type
0x140024816  call    cs:__imp_KeInitializeEvent
0x14002481d  nop     dword ptr [rax+rax+00h]
0x140024822  lea     r8, [rsp+58h+UninitializeEvent]; UninitializeEvent
0x140024827  mov     rcx, rbx; FileObject
0x14002482a  lea     rdx, FatLargeZero; TruncateSize
0x140024831  call    cs:__imp_CcUninitializeCacheMap
0x140024838  nop     dword ptr [rax+rax+00h]
0x14002483d  xor     r9d, r9d; Alertable
0x140024840  mov     [rsp+58h+Timeout], 0; Timeout
0x140024849  xor     r8d, r8d; WaitMode
0x14002484c  lea     rcx, [rsp+58h+UninitializeEvent.Event]; Object
0x140024851  xor     edx, edx; WaitReason
0x140024853  call    cs:__imp_KeWaitForSingleObject
0x14002485a  nop     dword ptr [rax+rax+00h]
0x14002485f  add     rsp, 50h
0x140024863  pop     rbx
0x140024864  retn
```
