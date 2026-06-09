# NdisDllInitialize

- ea: `0x140091240`
- end: `0x1400913ab`
- name: `NdisDllInitialize`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14018b240`

## callees

- `0x140091240`
- `0x1400c41cc`
- `0x140143118`

## import_xrefs

- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400912a2`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400912a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009137e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009137e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14009138f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14009138f`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14009126e`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140091282`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14009126e`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140091282`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140091290`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140091290`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400912ca`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400912ca`
- `ntoskrnl!ExAllocatePool2` at `0x140091351`
- `ntoskrnl!ExAllocatePool2` at `0x140091351`

## pseudocode

```c
__int64 NdisDllInitialize()
{
  unsigned int v0; // ebx
  __int64 v1; // rdx
  __int64 v2; // rcx
  _QWORD *PerProcessorPageDescriptor; // rax
  _QWORD *v4; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  signed __int32 v7; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  DestinationString = 0;
  v7 = 0;
  if ( !ndisDllInitialized )
  {
    ndisDllInitialized = 1;
    ndisNumberOfActiveProcessorsAtBoot = KeQueryActiveProcessorCountEx(0xFFFFu);
    KeQueryActiveProcessorCountEx(0);
    ndisMaxNumberOfProcessors = KeQueryMaximumProcessorCountEx(0xFFFFu);
    ndisMaxCacheLineSize = KeGetRecommendedSharedDataAlignment();
    if ( ndisMaxCacheLineSize < 0x40 )
      ndisMaxCacheLineSize = 64;
    KeInitializeSpinLock(&ndisPerProcessorDescriptorLock);
    qword_14011C5D0 = (__int64)&ndisPerProcessorDescriptorList;
    ndisPerProcessorDescriptorList = &ndisPerProcessorDescriptorList;
    PerProcessorPageDescriptor = (_QWORD *)ndisAllocatePerProcessorPageDescriptor(v2, v1);
    if ( PerProcessorPageDescriptor )
    {
      v4 = ndisPerProcessorDescriptorList;
      if ( *((void ***)ndisPerProcessorDescriptorList + 1) != &ndisPerProcessorDescriptorList )
        __fastfail(3u);
      *PerProcessorPageDescriptor = ndisPerProcessorDescriptorList;
      PerProcessorPageDescriptor[1] = &ndisPerProcessorDescriptorList;
      v4[1] = PerProcessorPageDescriptor;
      ndisPerProcessorDescriptorList = PerProcessorPageDescriptor;
    }
    if ( _InterlockedIncrement(&v7) == 1 )
      NdispRegisterShim();
    if ( ndisMaxNumberOfProcessors <= 0x100
      || (qword_14011C878 = ExAllocatePool2(64, 520LL * ndisMaxNumberOfProcessors, 538985550)) != 0 )
    {
      v0 = 0;
    }
    else
    {
      v0 = -1073741801;
    }
    RtlInitUnicodeString(&DestinationString, L"MmGetSystemRoutineAddressEx");
    ndisGetSystemRoutineAddressEx = (void *(*)(struct _UNICODE_STRING *, char *))MmGetSystemRoutineAddress(&DestinationString);
  }
  return v0;
}

```

## disassembly

```asm
0x140091240  push    rbx
0x140091242  sub     rsp, 30h
0x140091246  xor     ebx, ebx
0x140091248  xorps   xmm0, xmm0
0x14009124b  cmp     cs:?ndisDllInitialized@@3EA, bl; uchar ndisDllInitialized
0x140091251  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140091256  mov     [rsp+38h+arg_0], ebx
0x14009125a  jnz     loc_1400913A2
0x140091260  mov     ebx, 0FFFFh
0x140091265  mov     cs:?ndisDllInitialized@@3EA, 1; uchar ndisDllInitialized
0x14009126c  mov     ecx, ebx; GroupNumber
0x14009126e  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140091275  nop     dword ptr [rax+rax+00h]
0x14009127a  xor     ecx, ecx; GroupNumber
0x14009127c  mov     cs:?ndisNumberOfActiveProcessorsAtBoot@@3KA, eax; ulong ndisNumberOfActiveProcessorsAtBoot
0x140091282  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140091289  nop     dword ptr [rax+rax+00h]
0x14009128e  mov     ecx, ebx; GroupNumber
0x140091290  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140091297  nop     dword ptr [rax+rax+00h]
0x14009129c  mov     cs:?ndisMaxNumberOfProcessors@@3KA, eax; ulong ndisMaxNumberOfProcessors
0x1400912a2  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400912a9  nop     dword ptr [rax+rax+00h]
0x1400912ae  mov     cs:?ndisMaxCacheLineSize@@3KA, eax; ulong ndisMaxCacheLineSize
0x1400912b4  cmp     eax, 40h ; '@'
0x1400912b7  jnb     short loc_1400912C3
0x1400912b9  mov     cs:?ndisMaxCacheLineSize@@3KA, 40h ; '@'; ulong ndisMaxCacheLineSize
0x1400912c3  lea     rcx, ?ndisPerProcessorDescriptorLock@@3_KA; SpinLock
0x1400912ca  call    cs:__imp_KeInitializeSpinLock
0x1400912d1  nop     dword ptr [rax+rax+00h]
0x1400912d6  lea     rbx, ?ndisPerProcessorDescriptorList@@3U_LIST_ENTRY@@A; _LIST_ENTRY ndisPerProcessorDescriptorList
0x1400912dd  mov     cs:qword_14011C5D0, rbx
0x1400912e4  mov     cs:?ndisPerProcessorDescriptorList@@3U_LIST_ENTRY@@A, rbx; _LIST_ENTRY ndisPerProcessorDescriptorList
0x1400912eb  call    ndisAllocatePerProcessorPageDescriptor
0x1400912f0  test    rax, rax
0x1400912f3  jz      short loc_14009131B
0x1400912f5  mov     rcx, cs:?ndisPerProcessorDescriptorList@@3U_LIST_ENTRY@@A; _LIST_ENTRY ndisPerProcessorDescriptorList
0x1400912fc  cmp     [rcx+8], rbx
0x140091300  jz      short loc_140091309
0x140091302  mov     ecx, 3
0x140091307  int     29h; Win8: RtlFailFast(ecx)
0x140091309  mov     [rax], rcx
0x14009130c  mov     [rax+8], rbx
0x140091310  mov     [rcx+8], rax
0x140091314  mov     cs:?ndisPerProcessorDescriptorList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ndisPerProcessorDescriptorList
0x14009131b  mov     eax, 1
0x140091320  lock xadd [rsp+38h+arg_0], eax
0x140091326  inc     eax
0x140091328  cmp     eax, 1
0x14009132b  jnz     short loc_140091332
0x14009132d  call    ?NdispRegisterShim@@YAXXZ; NdispRegisterShim(void)
0x140091332  mov     eax, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x140091338  cmp     eax, 100h
0x14009133d  jbe     short loc_140091370
0x14009133f  imul    rdx, rax, 208h
0x140091346  mov     ecx, 40h ; '@'
0x14009134b  mov     r8d, 2020444Eh
0x140091351  call    cs:__imp_ExAllocatePool2
0x140091358  nop     dword ptr [rax+rax+00h]
0x14009135d  mov     cs:qword_14011C878, rax
0x140091364  test    rax, rax
0x140091367  jnz     short loc_140091370
0x140091369  mov     ebx, 0C0000017h
0x14009136e  jmp     short loc_140091372
0x140091370  xor     ebx, ebx
0x140091372  lea     rdx, aMmgetsystemrou; "MmGetSystemRoutineAddressEx"
0x140091379  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14009137e  call    cs:__imp_RtlInitUnicodeString
0x140091385  nop     dword ptr [rax+rax+00h]
0x14009138a  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x14009138f  call    cs:__imp_MmGetSystemRoutineAddress
0x140091396  nop     dword ptr [rax+rax+00h]
0x14009139b  mov     cs:?ndisGetSystemRoutineAddressEx@@3P6APEAXPEAU_UNICODE_STRING@@PEAD@ZEA, rax; void * (*ndisGetSystemRoutineAddressEx)(_UNICODE_STRING *,char *)
0x1400913a2  mov     eax, ebx
0x1400913a4  add     rsp, 30h
0x1400913a8  pop     rbx
0x1400913a9  retn
```
