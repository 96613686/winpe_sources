# ndisInitializePeriodicReceives(void)

- ea: `0x1401937ec`
- end: `0x140193ad9`
- name: `?ndisInitializePeriodicReceives@@YAHXZ`
- size: `749`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140191240`

## callees

- `0x14001ff40`
- `0x14005e1a0`
- `0x1400617b0`
- `0x14007a900`
- `0x1401937ec`
- `0x140193ae0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140193a4e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140193a9e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140193a4e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140193a9e`
- `ntoskrnl!MmSizeOfMdl` at `0x140193a0f`
- `ntoskrnl!MmSizeOfMdl` at `0x140193a66`
- `ntoskrnl!MmSizeOfMdl` at `0x140193a0f`
- `ntoskrnl!MmSizeOfMdl` at `0x140193a66`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140193964`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140193964`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x1401939a2`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x1401939a2`
- `ntoskrnl!KeInitializeSemaphore` at `0x1401938e4`
- `ntoskrnl!KeInitializeSemaphore` at `0x1401938e4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401938c5`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401938c5`
- `ntoskrnl!ExAllocatePool2` at `0x14019382d`
- `ntoskrnl!ExAllocatePool2` at `0x14019385f`
- `ntoskrnl!ExAllocatePool2` at `0x140193889`
- `ntoskrnl!ExAllocatePool2` at `0x140193908`
- `ntoskrnl!ExAllocatePool2` at `0x140193936`
- `ntoskrnl!ExAllocatePool2` at `0x14019382d`
- `ntoskrnl!ExAllocatePool2` at `0x14019385f`
- `ntoskrnl!ExAllocatePool2` at `0x140193889`
- `ntoskrnl!ExAllocatePool2` at `0x140193908`
- `ntoskrnl!ExAllocatePool2` at `0x140193936`

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
  qword_140121448 = (PVOID)ExAllocatePool2(64, 8LL * ndisMaxNumberOfProcessors, 538985550);
  if ( !qword_140121448 )
    goto LABEL_2;
  qword_140121440 = (PVOID)ExAllocatePool2(66, (unsigned __int64)ndisMaxNumberOfProcessors << 6, 538985550);
  if ( !qword_140121440 )
    goto LABEL_2;
  v1 = ndisMaxNumberOfProcessors;
  for ( i = 0; i < ndisMaxNumberOfProcessors; ++i )
  {
    v3 = (char *)qword_140121440 + 64 * (unsigned __int64)i;
    *((_QWORD *)v3 + 1) = v3;
    *(_QWORD *)v3 = v3;
    KeInitializeSpinLock((PKSPIN_LOCK)v3 + 2);
    *((_DWORD *)v3 + 6) = 0;
    KeInitializeSemaphore((PRKSEMAPHORE)v3 + 1, 0, 0x7FFFFFFF);
    v1 = ndisMaxNumberOfProcessors;
  }
  qword_140121438 = (PVOID)ExAllocatePool2(64, 4LL * v1, 538985550);
  if ( !qword_140121438 )
    goto LABEL_2;
  qword_140121430 = (PVOID)ExAllocatePool2(66, (unsigned __int64)ndisMaxNumberOfProcessors << 7, 538985550);
  if ( !qword_140121430 )
    goto LABEL_2;
  ProcessorNumberFromIndex = 0;
  for ( j = 0; j < ndisNumberOfActiveProcessorsAtBoot; ++j )
  {
    v5 = (unsigned __int64)j << 7;
    ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(j, &ProcNumber);
    NdisInitializeTimer((PNDIS_TIMER)((char *)qword_140121430 + v5), ndisPeriodicReceivesTimer, 0);
    KeSetTargetProcessorDpcEx((PKDPC)((char *)qword_140121430 + v5 + 64), &ProcNumber);
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
    &stru_140121500,
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
0x1401937ec  mov     [rsp-18h+arg_8], rbx
0x1401937f1  mov     [rsp-18h+arg_10], rsi
0x1401937f6  push    rbp
0x1401937f7  push    rdi
0x1401937f8  push    r14
0x1401937fa  mov     rbp, rsp
0x1401937fd  sub     rsp, 60h
0x140193801  mov     edx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x140193807  xor     eax, eax
0x140193809  xorps   xmm0, xmm0
0x14019380c  shl     rdx, 5
0x140193810  movups  xmmword ptr [rbp+Parameters.Header.Revision], xmm0
0x140193814  mov     esi, 2020444Eh
0x140193819  mov     dword ptr [rbp+ProcNumber.Group], 0
0x140193820  lea     r14d, [rax+40h]
0x140193824  mov     [rbp+Parameters.Flags], eax
0x140193827  mov     ecx, r14d
0x14019382a  mov     r8d, esi
0x14019382d  call    cs:__imp_ExAllocatePool2
0x140193834  nop     dword ptr [rax+rax+00h]
0x140193839  mov     cs:?ndisPerCpuPoisonPills@@3PEAU_WORK_QUEUE_ITEM@@EA, rax; _WORK_QUEUE_ITEM * ndisPerCpuPoisonPills
0x140193840  test    rax, rax
0x140193843  jnz     short loc_14019384F
0x140193845  mov     edi, 0C0000001h
0x14019384a  jmp     loc_140193ABC
0x14019384f  mov     edx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x140193855  mov     r8d, esi
0x140193858  shl     rdx, 3
0x14019385c  mov     rcx, r14
0x14019385f  call    cs:__imp_ExAllocatePool2
0x140193866  nop     dword ptr [rax+rax+00h]
0x14019386b  mov     cs:qword_140121448, rax
0x140193872  test    rax, rax
0x140193875  jz      short loc_140193845
0x140193877  mov     edx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x14019387d  mov     r8d, esi
0x140193880  shl     rdx, 6
0x140193884  mov     ecx, 42h ; 'B'
0x140193889  call    cs:__imp_ExAllocatePool2
0x140193890  nop     dword ptr [rax+rax+00h]
0x140193895  mov     cs:qword_140121440, rax
0x14019389c  test    rax, rax
0x14019389f  jz      short loc_140193845
0x1401938a1  mov     eax, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x1401938a7  xor     edi, edi
0x1401938a9  test    eax, eax
0x1401938ab  jz      short loc_1401938FC
0x1401938ad  mov     ebx, edi
0x1401938af  shl     rbx, 6
0x1401938b3  add     rbx, cs:qword_140121440
0x1401938ba  lea     rcx, [rbx+10h]; SpinLock
0x1401938be  mov     [rbx+8], rbx
0x1401938c2  mov     [rbx], rbx
0x1401938c5  call    cs:__imp_KeInitializeSpinLock
0x1401938cc  nop     dword ptr [rax+rax+00h]
0x1401938d1  lea     rcx, [rbx+20h]; Semaphore
0x1401938d5  mov     dword ptr [rbx+18h], 0
0x1401938dc  xor     edx, edx; Count
0x1401938de  mov     r8d, 7FFFFFFFh; Limit
0x1401938e4  call    cs:__imp_KeInitializeSemaphore
0x1401938eb  nop     dword ptr [rax+rax+00h]
0x1401938f0  mov     eax, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x1401938f6  inc     edi
0x1401938f8  cmp     edi, eax
0x1401938fa  jb      short loc_1401938AD
0x1401938fc  mov     edx, eax
0x1401938fe  mov     r8d, esi
0x140193901  shl     rdx, 2
0x140193905  mov     rcx, r14
0x140193908  call    cs:__imp_ExAllocatePool2
0x14019390f  nop     dword ptr [rax+rax+00h]
0x140193914  mov     cs:qword_140121438, rax
0x14019391b  test    rax, rax
0x14019391e  jz      loc_140193845
0x140193924  mov     edx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x14019392a  mov     r8d, esi
0x14019392d  shl     rdx, 7
0x140193931  mov     ecx, 42h ; 'B'
0x140193936  call    cs:__imp_ExAllocatePool2
0x14019393d  nop     dword ptr [rax+rax+00h]
0x140193942  mov     cs:qword_140121430, rax
0x140193949  test    rax, rax
0x14019394c  jz      loc_140193845
0x140193952  xor     edi, edi
0x140193954  xor     esi, esi
0x140193956  cmp     cs:?ndisNumberOfActiveProcessorsAtBoot@@3KA, esi; ulong ndisNumberOfActiveProcessorsAtBoot
0x14019395c  jbe     short loc_1401939B8
0x14019395e  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x140193962  mov     ecx, esi; ProcIndex
0x140193964  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14019396b  nop     dword ptr [rax+rax+00h]
0x140193970  mov     rcx, cs:qword_140121430
0x140193977  lea     rdx, ndisPeriodicReceivesTimer; TimerFunction
0x14019397e  mov     ebx, esi
0x140193980  xor     r8d, r8d; FunctionContext
0x140193983  shl     rbx, 7
0x140193987  mov     edi, eax
0x140193989  add     rcx, rbx; Timer
0x14019398c  call    NdisInitializeTimer
0x140193991  mov     rcx, cs:qword_140121430
0x140193998  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x14019399c  add     rcx, r14
0x14019399f  add     rcx, rbx; Dpc
0x1401939a2  call    cs:__imp_KeSetTargetProcessorDpcEx
0x1401939a9  nop     dword ptr [rax+rax+00h]
0x1401939ae  inc     esi
0x1401939b0  cmp     esi, cs:?ndisNumberOfActiveProcessorsAtBoot@@3KA; ulong ndisNumberOfActiveProcessorsAtBoot
0x1401939b6  jb      short loc_14019395E
0x1401939b8  lea     rcx, ?ndisDummyObject@@3U_NDIS_OBJECT_HEADER@@A; NdisHandle
0x1401939bf  call    NdisAllocateRWLock
0x1401939c4  mov     cs:Lock, rax
0x1401939cb  test    rax, rax
0x1401939ce  jz      loc_140193845
0x1401939d4  lea     rdx, [rbp+Parameters]; Parameters
0x1401939d8  mov     dword ptr [rbp+Parameters.Header.Type], 100180h
0x1401939df  xor     ecx, ecx; NdisHandle
0x1401939e1  mov     dword ptr [rbp+Parameters.ProtocolId], 100h
0x1401939e8  mov     qword ptr [rbp+Parameters.PoolTag], 7472444Eh
0x1401939f0  call    NdisAllocateNetBufferListPool
0x1401939f5  mov     cs:PoolHandle, rax
0x1401939fc  test    rax, rax
0x1401939ff  jz      loc_140193845
0x140193a05  xor     ebx, ebx
0x140193a07  mov     ecx, 0FFFh; Base
0x140193a0c  lea     edx, [rbx+64h]; Length
0x140193a0f  call    cs:__imp_MmSizeOfMdl
0x140193a16  nop     dword ptr [rax+rax+00h]
0x140193a1b  mov     [rsp+60h+Depth], bx; Depth
0x140193a20  lea     rcx, Lookaside; Lookaside
0x140193a27  add     rax, 7
0x140193a2b  mov     [rsp+60h+Tag], 7270444Eh; Tag
0x140193a33  and     rax, 0FFFFFFFFFFFFFFF8h
0x140193a37  mov     r14d, 200h
0x140193a3d  add     rax, 64h ; 'd'
0x140193a41  mov     r9d, r14d; Flags
0x140193a44  xor     r8d, r8d; Free
0x140193a47  mov     [rsp+60h+Size], rax; Size
0x140193a4c  xor     edx, edx; Allocate
0x140193a4e  call    cs:__imp_ExInitializeNPagedLookasideList
0x140193a55  nop     dword ptr [rax+rax+00h]
0x140193a5a  mov     esi, 5EEh
0x140193a5f  mov     ecx, 0FFFh; Base
0x140193a64  mov     edx, esi; Length
0x140193a66  call    cs:__imp_MmSizeOfMdl
0x140193a6d  nop     dword ptr [rax+rax+00h]
0x140193a72  mov     [rsp+60h+Depth], bx; Depth
0x140193a77  lea     rcx, stru_140121500; Lookaside
0x140193a7e  add     rax, 7
0x140193a82  mov     [rsp+60h+Tag], 7270444Eh; Tag
0x140193a8a  and     rax, 0FFFFFFFFFFFFFFF8h
0x140193a8e  mov     r9d, r14d; Flags
0x140193a91  add     rax, rsi
0x140193a94  xor     r8d, r8d; Free
0x140193a97  xor     edx, edx; Allocate
0x140193a99  mov     [rsp+60h+Size], rax; Size
0x140193a9e  call    cs:__imp_ExInitializeNPagedLookasideList
0x140193aa5  nop     dword ptr [rax+rax+00h]
0x140193aaa  xor     ecx, ecx; struct _NDIS_SET_RECEIVE_RATE *
0x140193aac  mov     cs:?ndisPeriodicReceives@@3U_NDIS_PERIODIC_RECEIVES@@A, 1; _NDIS_PERIODIC_RECEIVES ndisPeriodicReceives
0x140193ab3  call    ?ndisConfigurePeriodicReceives@@YAXPEAU_NDIS_SET_RECEIVE_RATE@@@Z; ndisConfigurePeriodicReceives(_NDIS_SET_RECEIVE_RATE *)
0x140193ab8  test    edi, edi
0x140193aba  jz      short loc_140193AC1
0x140193abc  call    ndisUnloadPeriodicReceives
0x140193ac1  lea     r11, [rsp+60h+var_s0]
0x140193ac6  mov     eax, edi
0x140193ac8  mov     rbx, [r11+28h]
0x140193acc  mov     rsi, [r11+30h]
0x140193ad0  mov     rsp, r11
0x140193ad3  pop     r14
0x140193ad5  pop     rdi
0x140193ad6  pop     rbp
0x140193ad7  retn
```
