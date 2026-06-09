# UlpInitializeThreadPoolWorkers

- ea: `0x1c00a75c4`
- end: `0x1c00a79c4`
- name: `UlpInitializeThreadPoolWorkers`
- size: `1024`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1c00a7550`
- `0x1c00db2d8`

## callees

- `0x1c0003db0`
- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c008f3a8`
- `0x1c009bb90`
- `0x1c00a75c4`
- `0x1c00d3698`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c00a76e5`
- `ntoskrnl!KeInitializeEvent` at `0x1c00a76e5`
- `ntoskrnl!KeSetEvent` at `0x1c00a78c3`
- `ntoskrnl!KeSetEvent` at `0x1c00a78c3`
- `ntoskrnl!PsCreateSystemThread` at `0x1c00a773c`
- `ntoskrnl!PsCreateSystemThread` at `0x1c00a773c`
- `ntoskrnl!PsThreadType` at `0x1c00a7752`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1c00a77c1`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1c00a7844`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1c00e67ed`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1c00e680d`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1c00a77c1`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1c00a7844`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1c00e67ed`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1c00e680d`
- `ntoskrnl!ZwSetInformationThread` at `0x1c00a781c`
- `ntoskrnl!ZwSetInformationThread` at `0x1c00a7871`
- `ntoskrnl!ZwSetInformationThread` at `0x1c00a781c`
- `ntoskrnl!ZwSetInformationThread` at `0x1c00a7871`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x1c00a77ef`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x1c00a77ef`
- `ntoskrnl!KeSetBasePriorityThread` at `0x1c00a799f`
- `ntoskrnl!KeSetBasePriorityThread` at `0x1c00a799f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1c00a777e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1c00a777e`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00a767c`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00a767c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a7923`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a7949`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a7923`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a7949`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a763a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a78f7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a763a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a78f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a792f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a7955`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a792f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a7955`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a7628`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a78e2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a7628`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a78e2`

## pseudocode

```c
__int64 __fastcall UlpInitializeThreadPoolWorkers(unsigned int **a1)
{
  NTSTATUS ProcessorNumberFromIndex; // esi
  SIZE_T v3; // rsi
  unsigned int *PoolWithTagPriority; // rax
  __int64 v5; // rdx
  unsigned int *v6; // rbx
  __int64 v7; // rcx
  unsigned int v8; // r15d
  unsigned __int64 v9; // r14
  void **StartContext; // rdx
  unsigned int *v11; // rbx
  LOGICAL_PROCESSOR_RELATIONSHIP v12; // edx
  GROUP_AFFINITY *GroupMask; // r8
  unsigned int v14; // ebx
  _PROCESSOR_NUMBER ProcNumber; // [rsp+48h] [rbp-79h] BYREF
  ULONG Length; // [rsp+4Ch] [rbp-75h] BYREF
  PVOID Object; // [rsp+50h] [rbp-71h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-69h] BYREF
  _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX Information; // [rsp+88h] [rbp-39h] BYREF
  __int128 v21; // [rsp+D8h] [rbp+17h] BYREF

  ProcNumber = 0;
  ProcessorNumberFromIndex = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v21 = 0;
  memset(&Information, 0, sizeof(Information));
  Length = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 9, 0);
  if ( !a1[10] )
  {
    if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x800000) != 0 )
      WPP_SF_DD(12, WPP_d5edf85a85d83196f44863df77394f8e_Traceguids, *((unsigned int *)a1 + 2), **a1);
    v3 = (unsigned __int64)*((unsigned __int8 *)*a1 + 24) << 6;
    PoolWithTagPriority = (unsigned int *)ExAllocatePoolWithTagPriority(
                                            (POOL_TYPE)516,
                                            v3,
                                            0x47546C55u,
                                            LowPoolPriority);
    v6 = PoolWithTagPriority;
    if ( PoolWithTagPriority )
      memset(PoolWithTagPriority, 0, v3);
    a1[10] = v6;
    if ( v6 )
    {
      v7 = (__int64)*a1;
      ProcessorNumberFromIndex = 0;
      v8 = 0;
      if ( *((_BYTE *)*a1 + 24) )
      {
        while ( 1 )
        {
          v9 = (unsigned __int64)v8 << 6;
          *(_QWORD *)((char *)a1[10] + v9) = a1;
          *(unsigned int *)((char *)a1[10] + v9 + 8) = v8;
          KeInitializeEvent((PRKEVENT)((char *)a1[10] + v9 + 32), NotificationEvent, 0);
          StartContext = (void **)((char *)a1[10] + v9);
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 512;
          ObjectAttributes.ObjectName = 0;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          ProcessorNumberFromIndex = PsCreateSystemThread(
                                       StartContext + 3,
                                       0x1FFFFFu,
                                       &ObjectAttributes,
                                       0,
                                       0,
                                       UlpThreadPoolWorker,
                                       StartContext);
          if ( ProcessorNumberFromIndex < 0 )
            goto LABEL_32;
          v11 = a1[10];
          Object = 0;
          ProcessorNumberFromIndex = ObReferenceObjectByHandle(
                                       *(HANDLE *)((char *)v11 + v9 + 24),
                                       1u,
                                       (POBJECT_TYPE)PsThreadType,
                                       0,
                                       &Object,
                                       0);
          *(_QWORD *)((char *)v11 + v9 + 16) = Object;
          if ( ProcessorNumberFromIndex < 0 )
            goto LABEL_32;
          if ( (*a1)[7] == 1 )
            break;
          if ( (*a1)[7] == 2 )
          {
            ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(*((_DWORD *)a1 + 2), &ProcNumber);
            if ( ProcessorNumberFromIndex < 0 )
              goto LABEL_32;
            v12 = RelationProcessorCore;
LABEL_15:
            Length = 80;
            ProcessorNumberFromIndex = KeQueryLogicalProcessorRelationship(&ProcNumber, v12, &Information, &Length);
            if ( ProcessorNumberFromIndex < 0 )
              goto LABEL_32;
            GroupMask = Information.Processor.GroupMask;
LABEL_17:
            ProcessorNumberFromIndex = ZwSetInformationThread(
                                         *(HANDLE *)((char *)a1[10] + v9 + 24),
                                         MaxThreadInfoClass|ThreadPriority,
                                         GroupMask,
                                         0x10u);
            if ( ProcessorNumberFromIndex < 0 )
              goto LABEL_32;
            goto LABEL_18;
          }
          if ( (*a1)[7] == 3 )
          {
            ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(*((_DWORD *)a1 + 2), &ProcNumber);
            if ( ProcessorNumberFromIndex < 0 )
              goto LABEL_32;
            v12 = RelationNumaNode;
            goto LABEL_15;
          }
LABEL_18:
          if ( (*a1)[1] == 1 )
          {
            ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(*((_DWORD *)a1 + 2), &ProcNumber);
            if ( ProcessorNumberFromIndex < 0 )
              goto LABEL_32;
            ProcessorNumberFromIndex = ZwSetInformationThread(
                                         *(HANDLE *)((char *)a1[10] + v9 + 24),
                                         (THREADINFOCLASS)33,
                                         &ProcNumber,
                                         4u);
            if ( ProcessorNumberFromIndex < 0 )
              goto LABEL_32;
          }
          v7 = (__int64)*a1;
          if ( *((_BYTE *)*a1 + 34) )
          {
            KeSetBasePriorityThread(*(PKTHREAD *)((char *)a1[10] + v9 + 16), 3);
            v7 = (__int64)*a1;
          }
          if ( ++v8 >= *(unsigned __int8 *)(v7 + 24) )
            goto LABEL_24;
        }
        ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(*((_DWORD *)a1 + 2), &ProcNumber);
        if ( ProcessorNumberFromIndex < 0 )
          goto LABEL_32;
        GroupMask = (GROUP_AFFINITY *)&v21;
        *((_QWORD *)&v21 + 1) = ProcNumber.Group;
        *(_QWORD *)&v21 = 1LL << ProcNumber.Number;
        goto LABEL_17;
      }
LABEL_24:
      v14 = 0;
      if ( *(_BYTE *)(v7 + 24) )
      {
        do
        {
          KeSetEvent((PRKEVENT)&a1[10][16 * (unsigned __int64)v14 + 8], 0, 0);
          v7 = (__int64)*a1;
          ++v14;
        }
        while ( v14 < *((unsigned __int8 *)*a1 + 24) );
      }
      if ( *(_BYTE *)(v7 + 33) )
      {
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(&UlThreadPoolOnDemandLock, 0);
        if ( ++UlThreadPoolOnDemandCount == 2 )
          UlEnablePeriodicScavenger(UlThreadPoolScavenger);
        ExReleasePushLockExclusiveEx(&UlThreadPoolOnDemandLock, 0);
        KeLeaveCriticalRegion();
      }
    }
    else
    {
      ProcessorNumberFromIndex = -1073741670;
LABEL_32:
      if ( (WPP_MAIN_CB.DeviceType & 0x800000) != 0 )
        WPP_SF_ddL(13, v5, (unsigned int)ProcessorNumberFromIndex, *((unsigned int *)a1 + 2), **a1);
      UlpTerminateThreadPoolWorkersLocked(a1);
    }
  }
  ExReleasePushLockExclusiveEx(a1 + 9, 0);
  KeLeaveCriticalRegion();
  return (unsigned int)ProcessorNumberFromIndex;
}

```

## disassembly

```asm
0x1c00a75c4  mov     rax, rsp
0x1c00a75c7  mov     [rax+10h], rbx
0x1c00a75cb  mov     [rax+18h], rsi
0x1c00a75cf  mov     [rax+20h], rdi
0x1c00a75d3  push    rbp
0x1c00a75d4  push    r12
0x1c00a75d6  push    r13
0x1c00a75d8  push    r14
0x1c00a75da  push    r15
0x1c00a75dc  lea     rbp, [rax-5Fh]
0x1c00a75e0  sub     rsp, 0F0h
0x1c00a75e7  mov     rax, cs:__security_cookie
0x1c00a75ee  xor     rax, rsp
0x1c00a75f1  mov     [rbp+57h+var_30], rax
0x1c00a75f5  xorps   xmm0, xmm0
0x1c00a75f8  xor     r13d, r13d
0x1c00a75fb  mov     rdi, rcx
0x1c00a75fe  mov     dword ptr [rbp+57h+ProcNumber.Group], r13d
0x1c00a7602  xor     edx, edx; Val
0x1c00a7604  lea     rcx, [rbp+57h+Information]; void *
0x1c00a7608  mov     esi, r13d
0x1c00a760b  lea     r8d, [r13+50h]; Size
0x1c00a760f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1c00a7613  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1c00a7617  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00a761b  movups  [rbp+57h+var_40], xmm0
0x1c00a761f  call    memset
0x1c00a7624  mov     [rbp+57h+Length], r13d
0x1c00a7628  call    cs:__imp_KeEnterCriticalRegion
0x1c00a762f  nop     dword ptr [rax+rax+00h]
0x1c00a7634  xor     edx, edx
0x1c00a7636  lea     rcx, [rdi+48h]
0x1c00a763a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00a7641  nop     dword ptr [rax+rax+00h]
0x1c00a7646  cmp     [rdi+50h], r13
0x1c00a764a  jnz     loc_1C00A7943
0x1c00a7650  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 800000h
0x1c00a765a  jnz     loc_1C00E678C
0x1c00a7660  mov     rax, [rdi]
0x1c00a7663  xor     r9d, r9d; Priority
0x1c00a7666  mov     r8d, 47546C55h; Tag
0x1c00a766c  mov     ecx, 204h; PoolType
0x1c00a7671  movzx   esi, byte ptr [rax+18h]
0x1c00a7675  shl     rsi, 6
0x1c00a7679  mov     rdx, rsi; NumberOfBytes
0x1c00a767c  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00a7683  nop     dword ptr [rax+rax+00h]
0x1c00a7688  mov     rbx, rax
0x1c00a768b  test    rax, rax
0x1c00a768e  jz      short loc_1C00A769D
0x1c00a7690  mov     r8, rsi; Size
0x1c00a7693  xor     edx, edx; Val
0x1c00a7695  mov     rcx, rax; void *
0x1c00a7698  call    memset
0x1c00a769d  mov     [rdi+50h], rbx
0x1c00a76a1  test    rbx, rbx
0x1c00a76a4  jz      loc_1C00E67AD
0x1c00a76aa  mov     rcx, [rdi]
0x1c00a76ad  mov     esi, r13d
0x1c00a76b0  mov     r15d, r13d
0x1c00a76b3  cmp     [rcx+18h], r13b
0x1c00a76b7  jbe     loc_1C00A78A4
0x1c00a76bd  mov     rax, [rdi+50h]
0x1c00a76c1  xor     r8d, r8d; State
0x1c00a76c4  mov     r14d, r15d
0x1c00a76c7  xor     edx, edx; Type
0x1c00a76c9  shl     r14, 6
0x1c00a76cd  mov     [r14+rax], rdi
0x1c00a76d1  mov     rax, [rdi+50h]
0x1c00a76d5  mov     [r14+rax+8], r15d
0x1c00a76da  mov     rcx, [rdi+50h]
0x1c00a76de  add     rcx, 20h ; ' '
0x1c00a76e2  add     rcx, r14; Event
0x1c00a76e5  call    cs:__imp_KeInitializeEvent
0x1c00a76ec  nop     dword ptr [rax+rax+00h]
0x1c00a76f1  mov     rdx, [rdi+50h]
0x1c00a76f5  lea     rax, UlpThreadPoolWorker
0x1c00a76fc  add     rdx, r14
0x1c00a76ff  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1c00a7706  mov     [rsp+110h+StartContext], rdx; StartContext
0x1c00a770b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1c00a770f  xorps   xmm0, xmm0
0x1c00a7712  mov     [rsp+110h+StartRoutine], rax; StartRoutine
0x1c00a7717  xor     r9d, r9d; ProcessHandle
0x1c00a771a  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x1c00a771e  lea     rcx, [rdx+18h]; ThreadHandle
0x1c00a7722  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x1c00a7729  mov     edx, 1FFFFFh; DesiredAccess
0x1c00a772e  mov     [rbp+57h+ObjectAttributes.ObjectName], r13
0x1c00a7732  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00a7737  mov     [rsp+110h+ClientId], r13; ClientId
0x1c00a773c  call    cs:__imp_PsCreateSystemThread
0x1c00a7743  nop     dword ptr [rax+rax+00h]
0x1c00a7748  mov     esi, eax
0x1c00a774a  test    eax, eax
0x1c00a774c  js      loc_1C00E67B2
0x1c00a7752  mov     rax, cs:__imp_PsThreadType
0x1c00a7759  xor     r9d, r9d; AccessMode
0x1c00a775c  mov     rbx, [rdi+50h]
0x1c00a7760  mov     [rsp+110h+StartRoutine], r13; HandleInformation
0x1c00a7765  mov     [rbp+57h+Object], r13
0x1c00a7769  mov     r8, [rax]; ObjectType
0x1c00a776c  lea     edx, [r9+1]; DesiredAccess
0x1c00a7770  mov     rcx, [r14+rbx+18h]; Handle
0x1c00a7775  lea     rax, [rbp+57h+Object]
0x1c00a7779  mov     [rsp+110h+ClientId], rax; Object
0x1c00a777e  call    cs:__imp_ObReferenceObjectByHandle
0x1c00a7785  nop     dword ptr [rax+rax+00h]
0x1c00a778a  mov     esi, eax
0x1c00a778c  mov     rax, [rbp+57h+Object]
0x1c00a7790  mov     [r14+rbx+10h], rax
0x1c00a7795  test    esi, esi
0x1c00a7797  js      loc_1C00E67B2
0x1c00a779d  mov     rcx, [rdi]
0x1c00a77a0  mov     edx, [rcx+1Ch]
0x1c00a77a3  sub     edx, 1
0x1c00a77a6  jz      loc_1C00E6806
0x1c00a77ac  sub     edx, 1
0x1c00a77af  jz      loc_1C00E67E6
0x1c00a77b5  cmp     edx, 1
0x1c00a77b8  jnz     short loc_1C00A7832
0x1c00a77ba  mov     ecx, [rdi+8]; ProcIndex
0x1c00a77bd  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x1c00a77c1  call    cs:__imp_KeGetProcessorNumberFromIndex
0x1c00a77c8  nop     dword ptr [rax+rax+00h]
0x1c00a77cd  mov     esi, eax
0x1c00a77cf  test    eax, eax
0x1c00a77d1  js      loc_1C00E67B2
0x1c00a77d7  mov     edx, 1; RelationshipType
0x1c00a77dc  lea     r8, [rbp+57h+Information]; Information
0x1c00a77e0  mov     [rbp+57h+Length], 50h ; 'P'
0x1c00a77e7  lea     r9, [rbp+57h+Length]; Length
0x1c00a77eb  lea     rcx, [rbp+57h+ProcNumber]; ProcessorNumber
0x1c00a77ef  call    cs:__imp_KeQueryLogicalProcessorRelationship
0x1c00a77f6  nop     dword ptr [rax+rax+00h]
0x1c00a77fb  mov     esi, eax
0x1c00a77fd  test    eax, eax
0x1c00a77ff  js      loc_1C00E67B2
0x1c00a7805  lea     r8, [rbp+57h+Information.8+18h]; ThreadInformation
0x1c00a7809  mov     rcx, [rdi+50h]
0x1c00a780d  mov     r9d, 10h; ThreadInformationLength
0x1c00a7813  mov     rcx, [r14+rcx+18h]; ThreadHandle
0x1c00a7818  lea     edx, [r9+0Eh]; ThreadInformationClass
0x1c00a781c  call    cs:__imp_ZwSetInformationThread
0x1c00a7823  nop     dword ptr [rax+rax+00h]
0x1c00a7828  mov     esi, eax
0x1c00a782a  test    eax, eax
0x1c00a782c  js      loc_1C00E67B2
0x1c00a7832  mov     rcx, [rdi]
0x1c00a7835  mov     ecx, [rcx+4]
0x1c00a7838  cmp     ecx, 1
0x1c00a783b  jnz     short loc_1C00A7887
0x1c00a783d  mov     ecx, [rdi+8]; ProcIndex
0x1c00a7840  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x1c00a7844  call    cs:__imp_KeGetProcessorNumberFromIndex
0x1c00a784b  nop     dword ptr [rax+rax+00h]
0x1c00a7850  mov     esi, eax
0x1c00a7852  test    eax, eax
0x1c00a7854  js      loc_1C00E67B2
0x1c00a785a  mov     rcx, [rdi+50h]
0x1c00a785e  lea     r8, [rbp+57h+ProcNumber]; ThreadInformation
0x1c00a7862  mov     r9d, 4; ThreadInformationLength
0x1c00a7868  mov     rcx, [r14+rcx+18h]; ThreadHandle
0x1c00a786d  lea     edx, [r9+1Dh]; ThreadInformationClass
0x1c00a7871  call    cs:__imp_ZwSetInformationThread
0x1c00a7878  nop     dword ptr [rax+rax+00h]
0x1c00a787d  mov     esi, eax
0x1c00a787f  test    eax, eax
0x1c00a7881  js      loc_1C00E67B2
0x1c00a7887  mov     rcx, [rdi]
0x1c00a788a  cmp     [rcx+22h], r13b
0x1c00a788e  jnz     loc_1C00A7991
0x1c00a7894  movzx   eax, byte ptr [rcx+18h]
0x1c00a7898  inc     r15d
0x1c00a789b  cmp     r15d, eax
0x1c00a789e  jb      loc_1C00A76BD
0x1c00a78a4  mov     ebx, r13d
0x1c00a78a7  cmp     [rcx+18h], r13b
0x1c00a78ab  jbe     short loc_1C00A78DC
0x1c00a78ad  mov     rax, [rdi+50h]
0x1c00a78b1  xor     r8d, r8d; Wait
0x1c00a78b4  add     rax, 20h ; ' '
0x1c00a78b8  mov     ecx, ebx
0x1c00a78ba  shl     rcx, 6
0x1c00a78be  xor     edx, edx; Increment
0x1c00a78c0  add     rcx, rax; Event
0x1c00a78c3  call    cs:__imp_KeSetEvent
0x1c00a78ca  nop     dword ptr [rax+rax+00h]
0x1c00a78cf  mov     rcx, [rdi]
0x1c00a78d2  inc     ebx
0x1c00a78d4  movzx   eax, byte ptr [rcx+18h]
0x1c00a78d8  cmp     ebx, eax
0x1c00a78da  jb      short loc_1C00A78AD
0x1c00a78dc  cmp     [rcx+21h], r13b
0x1c00a78e0  jz      short loc_1C00A793B
0x1c00a78e2  call    cs:__imp_KeEnterCriticalRegion
0x1c00a78e9  nop     dword ptr [rax+rax+00h]
0x1c00a78ee  xor     edx, edx
0x1c00a78f0  lea     rcx, UlThreadPoolOnDemandLock
0x1c00a78f7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00a78fe  nop     dword ptr [rax+rax+00h]
0x1c00a7903  mov     eax, cs:UlThreadPoolOnDemandCount
0x1c00a7909  inc     eax
0x1c00a790b  mov     cs:UlThreadPoolOnDemandCount, eax
0x1c00a7911  cmp     eax, 2
0x1c00a7914  jz      loc_1C00A79B3
0x1c00a791a  xor     edx, edx
0x1c00a791c  lea     rcx, UlThreadPoolOnDemandLock
0x1c00a7923  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00a792a  nop     dword ptr [rax+rax+00h]
0x1c00a792f  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a7936  nop     dword ptr [rax+rax+00h]
0x1c00a793b  test    esi, esi
0x1c00a793d  js      loc_1C00E67B2
0x1c00a7943  xor     edx, edx
0x1c00a7945  lea     rcx, [rdi+48h]
0x1c00a7949  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00a7950  nop     dword ptr [rax+rax+00h]
0x1c00a7955  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a795c  nop     dword ptr [rax+rax+00h]
0x1c00a7961  mov     eax, esi
0x1c00a7963  mov     rcx, [rbp+57h+var_30]
0x1c00a7967  xor     rcx, rsp; StackCookie
0x1c00a796a  call    __security_check_cookie
0x1c00a796f  lea     r11, [rsp+110h+var_20]
0x1c00a7977  mov     rbx, [r11+38h]
0x1c00a797b  mov     rsi, [r11+40h]
0x1c00a797f  mov     rdi, [r11+48h]
0x1c00a7983  mov     rsp, r11
0x1c00a7986  pop     r15
0x1c00a7988  pop     r14
0x1c00a798a  pop     r13
0x1c00a798c  pop     r12
0x1c00a798e  pop     rbp
0x1c00a798f  retn
0x1c00a7991  mov     rcx, [rdi+50h]
0x1c00a7995  mov     edx, 3; Increment
0x1c00a799a  mov     rcx, [r14+rcx+10h]; Thread
0x1c00a799f  call    cs:__imp_KeSetBasePriorityThread
0x1c00a79a6  nop     dword ptr [rax+rax+00h]
0x1c00a79ab  mov     rcx, [rdi]
0x1c00a79ae  jmp     loc_1C00A7894
0x1c00a79b3  lea     rcx, UlThreadPoolScavenger
0x1c00a79ba  call    UlEnablePeriodicScavenger
0x1c00a79bf  jmp     loc_1C00A791A
0x1c00e678c  mov     rax, [rdi]
0x1c00e678f  lea     rdx, WPP_d5edf85a85d83196f44863df77394f8e_Traceguids
0x1c00e6796  mov     r8d, [rdi+8]
0x1c00e679a  mov     ecx, 0Ch
0x1c00e679f  mov     r9d, [rax]
0x1c00e67a2  call    WPP_SF_DD
0x1c00e67a7  nop
0x1c00e67a8  jmp     loc_1C00A7660
0x1c00e67ad  mov     esi, 0C000009Ah
0x1c00e67b2  test    cs:WPP_MAIN_CB.DeviceType, 800000h
0x1c00e67bc  jz      short loc_1C00E67D8
0x1c00e67be  mov     rax, [rdi]
0x1c00e67c1  mov     ecx, 0Dh
0x1c00e67c6  mov     r9d, [rdi+8]
0x1c00e67ca  mov     r8d, esi
0x1c00e67cd  mov     eax, [rax]
0x1c00e67cf  mov     dword ptr [rsp+110h+ClientId], eax
0x1c00e67d3  call    WPP_SF_ddL
0x1c00e67d8  mov     rcx, rdi
0x1c00e67db  call    UlpTerminateThreadPoolWorkersLocked
0x1c00e67e0  nop
0x1c00e67e1  jmp     loc_1C00A7943
0x1c00e67e6  mov     ecx, [rdi+8]; ProcIndex
0x1c00e67e9  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x1c00e67ed  call    cs:__imp_KeGetProcessorNumberFromIndex
0x1c00e67f4  nop     dword ptr [rax+rax+00h]
0x1c00e67f9  mov     esi, eax
0x1c00e67fb  test    eax, eax
0x1c00e67fd  js      short loc_1C00E67B2
0x1c00e67ff  xor     edx, edx
0x1c00e6801  jmp     loc_1C00A77DC
0x1c00e6806  mov     ecx, [rdi+8]; ProcIndex
0x1c00e6809  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x1c00e680d  call    cs:__imp_KeGetProcessorNumberFromIndex
0x1c00e6814  nop     dword ptr [rax+rax+00h]
0x1c00e6819  mov     esi, eax
0x1c00e681b  test    eax, eax
0x1c00e681d  js      short loc_1C00E67B2
0x1c00e681f  movzx   eax, [rbp+57h+ProcNumber.Group]
0x1c00e6823  lea     r8, [rbp+57h+var_40]
0x1c00e6827  mov     cl, [rbp+57h+ProcNumber.Number]
0x1c00e682a  xorps   xmm0, xmm0
0x1c00e682d  movups  [rbp+57h+var_40], xmm0
0x1c00e6831  mov     word ptr [rbp+57h+var_40+8], ax
0x1c00e6835  mov     eax, 1
0x1c00e683a  shl     rax, cl
0x1c00e683d  mov     qword ptr [rbp+57h+var_40], rax
0x1c00e6841  jmp     loc_1C00A7809
```
