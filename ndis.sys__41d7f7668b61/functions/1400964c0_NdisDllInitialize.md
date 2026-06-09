# NdisDllInitialize

- ea: `0x1400964c0`
- end: `0x14009662b`
- name: `NdisDllInitialize`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140191240`

## callees

- `0x1400964c0`
- `0x1400c937c`
- `0x14014a0b8`

## import_xrefs

- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140096522`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140096522`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400965fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400965fe`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14009660f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14009660f`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400964ee`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140096502`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400964ee`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140096502`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140096510`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140096510`
- `ntoskrnl!KeInitializeSpinLock` at `0x14009654a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14009654a`
- `ntoskrnl!ExAllocatePool2` at `0x1400965d1`
- `ntoskrnl!ExAllocatePool2` at `0x1400965d1`

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
    qword_1401225D0 = (__int64)&ndisPerProcessorDescriptorList;
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
      || (qword_140122878 = ExAllocatePool2(64, 520LL * ndisMaxNumberOfProcessors, 538985550)) != 0 )
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
0x1400964c0  push    rbx
0x1400964c2  sub     rsp, 30h
0x1400964c6  xor     ebx, ebx
0x1400964c8  xorps   xmm0, xmm0
0x1400964cb  cmp     cs:?ndisDllInitialized@@3EA, bl; uchar ndisDllInitialized
0x1400964d1  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400964d6  mov     [rsp+38h+arg_0], ebx
0x1400964da  jnz     loc_140096622
0x1400964e0  mov     ebx, 0FFFFh
0x1400964e5  mov     cs:?ndisDllInitialized@@3EA, 1; uchar ndisDllInitialized
0x1400964ec  mov     ecx, ebx; GroupNumber
0x1400964ee  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400964f5  nop     dword ptr [rax+rax+00h]
0x1400964fa  xor     ecx, ecx; GroupNumber
0x1400964fc  mov     cs:?ndisNumberOfActiveProcessorsAtBoot@@3KA, eax; ulong ndisNumberOfActiveProcessorsAtBoot
0x140096502  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140096509  nop     dword ptr [rax+rax+00h]
0x14009650e  mov     ecx, ebx; GroupNumber
0x140096510  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140096517  nop     dword ptr [rax+rax+00h]
0x14009651c  mov     cs:?ndisMaxNumberOfProcessors@@3KA, eax; ulong ndisMaxNumberOfProcessors
0x140096522  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x140096529  nop     dword ptr [rax+rax+00h]
0x14009652e  mov     cs:?ndisMaxCacheLineSize@@3KA, eax; ulong ndisMaxCacheLineSize
0x140096534  cmp     eax, 40h ; '@'
0x140096537  jnb     short loc_140096543
0x140096539  mov     cs:?ndisMaxCacheLineSize@@3KA, 40h ; '@'; ulong ndisMaxCacheLineSize
0x140096543  lea     rcx, ?ndisPerProcessorDescriptorLock@@3_KA; SpinLock
0x14009654a  call    cs:__imp_KeInitializeSpinLock
0x140096551  nop     dword ptr [rax+rax+00h]
0x140096556  lea     rbx, ?ndisPerProcessorDescriptorList@@3U_LIST_ENTRY@@A; _LIST_ENTRY ndisPerProcessorDescriptorList
0x14009655d  mov     cs:qword_1401225D0, rbx
0x140096564  mov     cs:?ndisPerProcessorDescriptorList@@3U_LIST_ENTRY@@A, rbx; _LIST_ENTRY ndisPerProcessorDescriptorList
0x14009656b  call    ndisAllocatePerProcessorPageDescriptor
0x140096570  test    rax, rax
0x140096573  jz      short loc_14009659B
0x140096575  mov     rcx, cs:?ndisPerProcessorDescriptorList@@3U_LIST_ENTRY@@A; _LIST_ENTRY ndisPerProcessorDescriptorList
0x14009657c  cmp     [rcx+8], rbx
0x140096580  jz      short loc_140096589
0x140096582  mov     ecx, 3
0x140096587  int     29h; Win8: RtlFailFast(ecx)
0x140096589  mov     [rax], rcx
0x14009658c  mov     [rax+8], rbx
0x140096590  mov     [rcx+8], rax
0x140096594  mov     cs:?ndisPerProcessorDescriptorList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ndisPerProcessorDescriptorList
0x14009659b  mov     eax, 1
0x1400965a0  lock xadd [rsp+38h+arg_0], eax
0x1400965a6  inc     eax
0x1400965a8  cmp     eax, 1
0x1400965ab  jnz     short loc_1400965B2
0x1400965ad  call    ?NdispRegisterShim@@YAXXZ; NdispRegisterShim(void)
0x1400965b2  mov     eax, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x1400965b8  cmp     eax, 100h
0x1400965bd  jbe     short loc_1400965F0
0x1400965bf  imul    rdx, rax, 208h
0x1400965c6  mov     ecx, 40h ; '@'
0x1400965cb  mov     r8d, 2020444Eh
0x1400965d1  call    cs:__imp_ExAllocatePool2
0x1400965d8  nop     dword ptr [rax+rax+00h]
0x1400965dd  mov     cs:qword_140122878, rax
0x1400965e4  test    rax, rax
0x1400965e7  jnz     short loc_1400965F0
0x1400965e9  mov     ebx, 0C0000017h
0x1400965ee  jmp     short loc_1400965F2
0x1400965f0  xor     ebx, ebx
0x1400965f2  lea     rdx, aMmgetsystemrou; "MmGetSystemRoutineAddressEx"
0x1400965f9  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400965fe  call    cs:__imp_RtlInitUnicodeString
0x140096605  nop     dword ptr [rax+rax+00h]
0x14009660a  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x14009660f  call    cs:__imp_MmGetSystemRoutineAddress
0x140096616  nop     dword ptr [rax+rax+00h]
0x14009661b  mov     cs:?ndisGetSystemRoutineAddressEx@@3P6APEAXPEAU_UNICODE_STRING@@PEAD@ZEA, rax; void * (*ndisGetSystemRoutineAddressEx)(_UNICODE_STRING *,char *)
0x140096622  mov     eax, ebx
0x140096624  add     rsp, 30h
0x140096628  pop     rbx
0x140096629  retn
```
