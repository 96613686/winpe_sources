# ndisInitializePeriodicReceives(void)

- ea: `0x14018d7dc`
- end: `0x14018dac9`
- name: `?ndisInitializePeriodicReceives@@YAHXZ`
- size: `749`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14018b240`

## callees

- `0x140006e00`
- `0x140059ab0`
- `0x14005d080`
- `0x140075220`
- `0x14018d7dc`
- `0x14018dad0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14018da3e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14018da8e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14018da3e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14018da8e`
- `ntoskrnl!MmSizeOfMdl` at `0x14018d9ff`
- `ntoskrnl!MmSizeOfMdl` at `0x14018da56`
- `ntoskrnl!MmSizeOfMdl` at `0x14018d9ff`
- `ntoskrnl!MmSizeOfMdl` at `0x14018da56`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14018d954`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14018d954`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x14018d992`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x14018d992`
- `ntoskrnl!KeInitializeSemaphore` at `0x14018d8d4`
- `ntoskrnl!KeInitializeSemaphore` at `0x14018d8d4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018d8b5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018d8b5`
- `ntoskrnl!ExAllocatePool2` at `0x14018d81d`
- `ntoskrnl!ExAllocatePool2` at `0x14018d84f`
- `ntoskrnl!ExAllocatePool2` at `0x14018d879`
- `ntoskrnl!ExAllocatePool2` at `0x14018d8f8`
- `ntoskrnl!ExAllocatePool2` at `0x14018d926`
- `ntoskrnl!ExAllocatePool2` at `0x14018d81d`
- `ntoskrnl!ExAllocatePool2` at `0x14018d84f`
- `ntoskrnl!ExAllocatePool2` at `0x14018d879`
- `ntoskrnl!ExAllocatePool2` at `0x14018d8f8`
- `ntoskrnl!ExAllocatePool2` at `0x14018d926`

## pseudocode

```c
__int64 ndisInitializePeriodicReceives(void)
{
  unsigned int ProcessorNumberFromIndex; // edi
  unsigned int v1; // eax
  unsigned int i; // edi
  char *v3; // rbx
  ULONG j; // esi
  unsigned __int64 v5; // rbx
  SIZE_T v6; // rax
  SIZE_T v7; // rax
  struct _NET_BUFFER_LIST_POOL_PARAMETERS Parameters; // [rsp+40h] [rbp-20h] BYREF
  struct _PROCESSOR_NUMBER ProcNumber; // [rsp+80h] [rbp+20h] BYREF

  memset(&Parameters.Header.Revision, 0, 19);
  ProcNumber = 0;
  ndisPerCpuPoisonPills = (PVOID)ExAllocatePool2(64, 32LL * ndisMaxNumberOfProcessors, 538985550);
  if ( !ndisPerCpuPoisonPills )
    goto LABEL_2;
  qword_14011B448 = (PVOID)ExAllocatePool2(64, 8LL * ndisMaxNumberOfProcessors, 538985550);
  if ( !qword_14011B448 )
    goto LABEL_2;
  qword_14011B440 = (PVOID)ExAllocatePool2(66, (unsigned __int64)ndisMaxNumberOfProcessors << 6, 538985550);
  if ( !qword_14011B440 )
    goto LABEL_2;
  v1 = ndisMaxNumberOfProcessors;
  for ( i = 0; i < ndisMaxNumberOfProcessors; ++i )
  {
    v3 = (char *)qword_14011B440 + 64 * (unsigned __int64)i;
    *((_QWORD *)v3 + 1) = v3;
    *(_QWORD *)v3 = v3;
    KeInitializeSpinLock((PKSPIN_LOCK)v3 + 2);
    *((_DWORD *)v3 + 6) = 0;
    KeInitializeSemaphore((PRKSEMAPHORE)v3 + 1, 0, 0x7FFFFFFF);
    v1 = ndisMaxNumberOfProcessors;
  }
  qword_14011B438 = (PVOID)ExAllocatePool2(64, 4LL * v1, 538985550);
  if ( !qword_14011B438 )
    goto LABEL_2;
  qword_14011B430 = (PVOID)ExAllocatePool2(66, (unsigned __int64)ndisMaxNumberOfProcessors << 7, 538985550);
  if ( !qword_14011B430 )
    goto LABEL_2;
  ProcessorNumberFromIndex = 0;
  for ( j = 0; j < ndisNumberOfActiveProcessorsAtBoot; ++j )
  {
    v5 = (unsigned __int64)j << 7;
    ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(j, &ProcNumber);
    NdisInitializeTimer((PNDIS_TIMER)((char *)qword_14011B430 + v5), ndisPeriodicReceivesTimer, 0);
    KeSetTargetProcessorDpcEx((PKDPC)((char *)qword_14011B430 + v5 + 64), &ProcNumber);
  }
  Lock = NdisAllocateRWLock(&ndisDummyObject);
  if ( !Lock
    || (Parameters.Header = (_NDIS_OBJECT_HEADER)1048960,
        *(_DWORD *)&Parameters.ProtocolId = 256,
        *(_QWORD *)&Parameters.PoolTag = 1953645646,
        (PoolHandle = NdisAllocateNetBufferListPool(0, &Parameters)) == 0) )
  {
LABEL_2:
    ProcessorNumberFromIndex = -1073741823;
LABEL_14:
    ndisUnloadPeriodicReceives();
    return ProcessorNumberFromIndex;
  }
  v6 = MmSizeOfMdl((PVOID)0xFFF, 0x64u);
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, ((v6 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 100, 0x7270444Eu, 0);
  v7 = MmSizeOfMdl((PVOID)0xFFF, 0x5EEu);
  ExInitializeNPagedLookasideList(
    &stru_14011B500,
    0,
    0,
    0x200u,
    ((v7 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 1518,
    0x7270444Eu,
    0);
  ndisPeriodicReceives = 1;
  ndisConfigurePeriodicReceives(0);
  if ( ProcessorNumberFromIndex )
    goto LABEL_14;
  return ProcessorNumberFromIndex;
}

```

## disassembly

```asm
0x14018d7dc  mov     [rsp-18h+arg_8], rbx
0x14018d7e1  mov     [rsp-18h+arg_10], rsi
0x14018d7e6  push    rbp
0x14018d7e7  push    rdi
0x14018d7e8  push    r14
0x14018d7ea  mov     rbp, rsp
0x14018d7ed  sub     rsp, 60h
0x14018d7f1  mov     edx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x14018d7f7  xor     eax, eax
0x14018d7f9  xorps   xmm0, xmm0
0x14018d7fc  shl     rdx, 5
0x14018d800  movups  xmmword ptr [rbp+Parameters.Header.Revision], xmm0
0x14018d804  mov     esi, 2020444Eh
0x14018d809  mov     dword ptr [rbp+ProcNumber.Group], 0
0x14018d810  lea     r14d, [rax+40h]
0x14018d814  mov     [rbp+Parameters.Flags], eax
0x14018d817  mov     ecx, r14d
0x14018d81a  mov     r8d, esi
0x14018d81d  call    cs:__imp_ExAllocatePool2
0x14018d824  nop     dword ptr [rax+rax+00h]
0x14018d829  mov     cs:?ndisPerCpuPoisonPills@@3PEAU_WORK_QUEUE_ITEM@@EA, rax; _WORK_QUEUE_ITEM * ndisPerCpuPoisonPills
0x14018d830  test    rax, rax
0x14018d833  jnz     short loc_14018D83F
0x14018d835  mov     edi, 0C0000001h
0x14018d83a  jmp     loc_14018DAAC
0x14018d83f  mov     edx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x14018d845  mov     r8d, esi
0x14018d848  shl     rdx, 3
0x14018d84c  mov     rcx, r14
0x14018d84f  call    cs:__imp_ExAllocatePool2
0x14018d856  nop     dword ptr [rax+rax+00h]
0x14018d85b  mov     cs:qword_14011B448, rax
0x14018d862  test    rax, rax
0x14018d865  jz      short loc_14018D835
0x14018d867  mov     edx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x14018d86d  mov     r8d, esi
0x14018d870  shl     rdx, 6
0x14018d874  mov     ecx, 42h ; 'B'
0x14018d879  call    cs:__imp_ExAllocatePool2
0x14018d880  nop     dword ptr [rax+rax+00h]
0x14018d885  mov     cs:qword_14011B440, rax
0x14018d88c  test    rax, rax
0x14018d88f  jz      short loc_14018D835
0x14018d891  mov     eax, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x14018d897  xor     edi, edi
0x14018d899  test    eax, eax
0x14018d89b  jz      short loc_14018D8EC
0x14018d89d  mov     ebx, edi
0x14018d89f  shl     rbx, 6
0x14018d8a3  add     rbx, cs:qword_14011B440
0x14018d8aa  lea     rcx, [rbx+10h]; SpinLock
0x14018d8ae  mov     [rbx+8], rbx
0x14018d8b2  mov     [rbx], rbx
0x14018d8b5  call    cs:__imp_KeInitializeSpinLock
0x14018d8bc  nop     dword ptr [rax+rax+00h]
0x14018d8c1  lea     rcx, [rbx+20h]; Semaphore
0x14018d8c5  mov     dword ptr [rbx+18h], 0
0x14018d8cc  xor     edx, edx; Count
0x14018d8ce  mov     r8d, 7FFFFFFFh; Limit
0x14018d8d4  call    cs:__imp_KeInitializeSemaphore
0x14018d8db  nop     dword ptr [rax+rax+00h]
0x14018d8e0  mov     eax, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x14018d8e6  inc     edi
0x14018d8e8  cmp     edi, eax
0x14018d8ea  jb      short loc_14018D89D
0x14018d8ec  mov     edx, eax
0x14018d8ee  mov     r8d, esi
0x14018d8f1  shl     rdx, 2
0x14018d8f5  mov     rcx, r14
0x14018d8f8  call    cs:__imp_ExAllocatePool2
0x14018d8ff  nop     dword ptr [rax+rax+00h]
0x14018d904  mov     cs:qword_14011B438, rax
0x14018d90b  test    rax, rax
0x14018d90e  jz      loc_14018D835
0x14018d914  mov     edx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x14018d91a  mov     r8d, esi
0x14018d91d  shl     rdx, 7
0x14018d921  mov     ecx, 42h ; 'B'
0x14018d926  call    cs:__imp_ExAllocatePool2
0x14018d92d  nop     dword ptr [rax+rax+00h]
0x14018d932  mov     cs:qword_14011B430, rax
0x14018d939  test    rax, rax
0x14018d93c  jz      loc_14018D835
0x14018d942  xor     edi, edi
0x14018d944  xor     esi, esi
0x14018d946  cmp     cs:?ndisNumberOfActiveProcessorsAtBoot@@3KA, esi; ulong ndisNumberOfActiveProcessorsAtBoot
0x14018d94c  jbe     short loc_14018D9A8
0x14018d94e  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x14018d952  mov     ecx, esi; ProcIndex
0x14018d954  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14018d95b  nop     dword ptr [rax+rax+00h]
0x14018d960  mov     rcx, cs:qword_14011B430
0x14018d967  lea     rdx, ndisPeriodicReceivesTimer; TimerFunction
0x14018d96e  mov     ebx, esi
0x14018d970  xor     r8d, r8d; FunctionContext
0x14018d973  shl     rbx, 7
0x14018d977  mov     edi, eax
0x14018d979  add     rcx, rbx; Timer
0x14018d97c  call    NdisInitializeTimer
0x14018d981  mov     rcx, cs:qword_14011B430
0x14018d988  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x14018d98c  add     rcx, r14
0x14018d98f  add     rcx, rbx; Dpc
0x14018d992  call    cs:__imp_KeSetTargetProcessorDpcEx
0x14018d999  nop     dword ptr [rax+rax+00h]
0x14018d99e  inc     esi
0x14018d9a0  cmp     esi, cs:?ndisNumberOfActiveProcessorsAtBoot@@3KA; ulong ndisNumberOfActiveProcessorsAtBoot
0x14018d9a6  jb      short loc_14018D94E
0x14018d9a8  lea     rcx, ?ndisDummyObject@@3U_NDIS_OBJECT_HEADER@@A; NdisHandle
0x14018d9af  call    NdisAllocateRWLock
0x14018d9b4  mov     cs:Lock, rax
0x14018d9bb  test    rax, rax
0x14018d9be  jz      loc_14018D835
0x14018d9c4  lea     rdx, [rbp+Parameters]; Parameters
0x14018d9c8  mov     dword ptr [rbp+Parameters.Header.Type], 100180h
0x14018d9cf  xor     ecx, ecx; NdisHandle
0x14018d9d1  mov     dword ptr [rbp+Parameters.ProtocolId], 100h
0x14018d9d8  mov     qword ptr [rbp+Parameters.PoolTag], 7472444Eh
0x14018d9e0  call    NdisAllocateNetBufferListPool
0x14018d9e5  mov     cs:PoolHandle, rax
0x14018d9ec  test    rax, rax
0x14018d9ef  jz      loc_14018D835
0x14018d9f5  xor     ebx, ebx
0x14018d9f7  mov     ecx, 0FFFh; Base
0x14018d9fc  lea     edx, [rbx+64h]; Length
0x14018d9ff  call    cs:__imp_MmSizeOfMdl
0x14018da06  nop     dword ptr [rax+rax+00h]
0x14018da0b  mov     [rsp+60h+Depth], bx; Depth
0x14018da10  lea     rcx, Lookaside; Lookaside
0x14018da17  add     rax, 7
0x14018da1b  mov     [rsp+60h+Tag], 7270444Eh; Tag
0x14018da23  and     rax, 0FFFFFFFFFFFFFFF8h
0x14018da27  mov     r14d, 200h
0x14018da2d  add     rax, 64h ; 'd'
0x14018da31  mov     r9d, r14d; Flags
0x14018da34  xor     r8d, r8d; Free
0x14018da37  mov     [rsp+60h+Size], rax; Size
0x14018da3c  xor     edx, edx; Allocate
0x14018da3e  call    cs:__imp_ExInitializeNPagedLookasideList
0x14018da45  nop     dword ptr [rax+rax+00h]
0x14018da4a  mov     esi, 5EEh
0x14018da4f  mov     ecx, 0FFFh; Base
0x14018da54  mov     edx, esi; Length
0x14018da56  call    cs:__imp_MmSizeOfMdl
0x14018da5d  nop     dword ptr [rax+rax+00h]
0x14018da62  mov     [rsp+60h+Depth], bx; Depth
0x14018da67  lea     rcx, stru_14011B500; Lookaside
0x14018da6e  add     rax, 7
0x14018da72  mov     [rsp+60h+Tag], 7270444Eh; Tag
0x14018da7a  and     rax, 0FFFFFFFFFFFFFFF8h
0x14018da7e  mov     r9d, r14d; Flags
0x14018da81  add     rax, rsi
0x14018da84  xor     r8d, r8d; Free
0x14018da87  xor     edx, edx; Allocate
0x14018da89  mov     [rsp+60h+Size], rax; Size
0x14018da8e  call    cs:__imp_ExInitializeNPagedLookasideList
0x14018da95  nop     dword ptr [rax+rax+00h]
0x14018da9a  xor     ecx, ecx; struct _NDIS_SET_RECEIVE_RATE *
0x14018da9c  mov     cs:?ndisPeriodicReceives@@3U_NDIS_PERIODIC_RECEIVES@@A, 1; _NDIS_PERIODIC_RECEIVES ndisPeriodicReceives
0x14018daa3  call    ?ndisConfigurePeriodicReceives@@YAXPEAU_NDIS_SET_RECEIVE_RATE@@@Z; ndisConfigurePeriodicReceives(_NDIS_SET_RECEIVE_RATE *)
0x14018daa8  test    edi, edi
0x14018daaa  jz      short loc_14018DAB1
0x14018daac  call    ndisUnloadPeriodicReceives
0x14018dab1  lea     r11, [rsp+60h+var_s0]
0x14018dab6  mov     eax, edi
0x14018dab8  mov     rbx, [r11+28h]
0x14018dabc  mov     rsi, [r11+30h]
0x14018dac0  mov     rsp, r11
0x14018dac3  pop     r14
0x14018dac5  pop     rdi
0x14018dac6  pop     rbp
0x14018dac7  retn
```
