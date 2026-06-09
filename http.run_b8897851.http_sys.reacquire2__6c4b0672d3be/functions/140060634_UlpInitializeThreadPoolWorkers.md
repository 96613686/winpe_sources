# UlpInitializeThreadPoolWorkers

- ea: `0x140060634`
- end: `0x140060ad6`
- name: `UlpInitializeThreadPoolWorkers`
- size: `1186`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140060480`
- `0x14013de0c`

## callees

- `0x140060634`
- `0x140060adc`
- `0x14009ce68`
- `0x140167700`
- `0x140167b40`
- `0x1401d620c`
- `0x1401d9e44`

## import_xrefs

- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14006082d`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400608ae`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140060a5e`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140060a7e`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14006082d`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400608ae`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140060a5e`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140060a7e`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x14006085b`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x14006085b`
- `ntoskrnl!PsCreateSystemThread` at `0x1400607a0`
- `ntoskrnl!PsCreateSystemThread` at `0x1400607a0`
- `ntoskrnl!KeSetBasePriorityThread` at `0x140060ac5`
- `ntoskrnl!KeSetBasePriorityThread` at `0x140060ac5`
- `ntoskrnl!PsThreadType` at `0x1400607be`
- `ntoskrnl!ZwSetInformationThread` at `0x140060888`
- `ntoskrnl!ZwSetInformationThread` at `0x1400608db`
- `ntoskrnl!ZwSetInformationThread` at `0x140060888`
- `ntoskrnl!ZwSetInformationThread` at `0x1400608db`
- `ntoskrnl!KeInitializeEvent` at `0x14006073d`
- `ntoskrnl!KeInitializeEvent` at `0x14006073d`
- `ntoskrnl!KeSetEvent` at `0x140060922`
- `ntoskrnl!KeSetEvent` at `0x140060922`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400607ea`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400607ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006098a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400609b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006098a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400609b0`
- `ntoskrnl!ExAllocatePool3` at `0x1400606e9`
- `ntoskrnl!ExAllocatePool3` at `0x1400606e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006097e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400609a4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006097e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400609a4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400606a1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140060956`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400606a1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140060956`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006068f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140060941`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006068f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140060941`

## pseudocode

```c
__int64 __fastcall UlpInitializeThreadPoolWorkers(_DWORD **a1)
{
  NTSTATUS ProcessorNumberFromIndex; // edi
  __int64 Pool3; // rax
  __int64 v4; // r8
  unsigned int i; // r15d
  _DWORD *v6; // rcx
  unsigned __int64 v7; // r14
  void **StartContext; // rdx
  _DWORD *v9; // rbx
  LOGICAL_PROCESSOR_RELATIONSHIP v10; // edx
  GROUP_AFFINITY *GroupMask; // r8
  unsigned int j; // ebx
  _PROCESSOR_NUMBER ProcNumber; // [rsp+40h] [rbp-79h] BYREF
  ULONG Length; // [rsp+44h] [rbp-75h] BYREF
  PVOID Object; // [rsp+48h] [rbp-71h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-69h] BYREF
  _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX Information; // [rsp+80h] [rbp-39h] BYREF
  __int128 v19; // [rsp+D0h] [rbp+17h] BYREF

  ProcessorNumberFromIndex = 0;
  ProcNumber = 0;
  memset(&ObjectAttributes, 0, 44);
  v19 = 0;
  memset(&Information, 0, sizeof(Information));
  Length = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 9, 0);
  if ( a1[10] )
    goto LABEL_29;
  if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_Dd(1304, 12, WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids, *((unsigned int *)a1 + 2), **a1);
  Pool3 = ExAllocatePool3(72, (unsigned __int64)*((unsigned __int8 *)*a1 + 24) << 6, 1196715093, UxLowPriorityPool, 1);
  a1[10] = (_DWORD *)Pool3;
  if ( Pool3 )
  {
    for ( i = 0; ; ++i )
    {
      v6 = *a1;
      if ( i >= *((unsigned __int8 *)*a1 + 24) )
      {
        for ( j = 0; j < *((unsigned __int8 *)*a1 + 24); ++j )
        {
          KeSetEvent((PRKEVENT)&a1[10][16 * (unsigned __int64)j + 8], 0, 0);
          v6 = *a1;
        }
        if ( *((_BYTE *)v6 + 33) )
        {
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(&UlThreadPoolOnDemandLock, 0);
          if ( ++UlThreadPoolOnDemandCount == 2 )
            UlEnablePeriodicScavenger(UlThreadPoolScavenger);
          ExReleasePushLockExclusiveEx(&UlThreadPoolOnDemandLock, 0);
          KeLeaveCriticalRegion();
        }
        goto LABEL_29;
      }
      v7 = (unsigned __int64)i << 6;
      *(_QWORD *)((char *)a1[10] + v7) = a1;
      *(_DWORD *)((char *)a1[10] + v7 + 8) = i;
      KeInitializeEvent((PRKEVENT)((char *)a1[10] + v7 + 32), NotificationEvent, 0);
      StartContext = (void **)((char *)a1[10] + v7);
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
        goto LABEL_31;
      v9 = a1[10];
      Object = 0;
      ProcessorNumberFromIndex = ObReferenceObjectByHandle(
                                   *(HANDLE *)((char *)v9 + v7 + 24),
                                   1u,
                                   (POBJECT_TYPE)PsThreadType,
                                   0,
                                   &Object,
                                   0);
      *(_QWORD *)((char *)v9 + v7 + 16) = Object;
      if ( ProcessorNumberFromIndex < 0 )
        goto LABEL_31;
      if ( (*a1)[7] == 1 )
      {
        ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(*((_DWORD *)a1 + 2), &ProcNumber);
        if ( ProcessorNumberFromIndex < 0 )
          goto LABEL_31;
        GroupMask = (GROUP_AFFINITY *)&v19;
        *((_QWORD *)&v19 + 1) = ProcNumber.Group;
        *(_QWORD *)&v19 = 1LL << ProcNumber.Number;
      }
      else
      {
        if ( (*a1)[7] == 2 )
        {
          ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(*((_DWORD *)a1 + 2), &ProcNumber);
          if ( ProcessorNumberFromIndex < 0 )
            goto LABEL_31;
          v10 = RelationProcessorCore;
        }
        else
        {
          if ( (*a1)[7] != 3 )
            goto LABEL_17;
          ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(*((_DWORD *)a1 + 2), &ProcNumber);
          if ( ProcessorNumberFromIndex < 0 )
            goto LABEL_31;
          v10 = RelationNumaNode;
        }
        Length = 80;
        ProcessorNumberFromIndex = KeQueryLogicalProcessorRelationship(&ProcNumber, v10, &Information, &Length);
        if ( ProcessorNumberFromIndex < 0 )
          goto LABEL_31;
        GroupMask = Information.Processor.GroupMask;
      }
      ProcessorNumberFromIndex = ZwSetInformationThread(
                                   *(HANDLE *)((char *)a1[10] + v7 + 24),
                                   MaxThreadInfoClass|ThreadPriority,
                                   GroupMask,
                                   0x10u);
      if ( ProcessorNumberFromIndex < 0 )
        goto LABEL_31;
LABEL_17:
      if ( (*a1)[1] == 1 )
      {
        ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(*((_DWORD *)a1 + 2), &ProcNumber);
        if ( ProcessorNumberFromIndex < 0 )
          goto LABEL_31;
        ProcessorNumberFromIndex = ZwSetInformationThread(
                                     *(HANDLE *)((char *)a1[10] + v7 + 24),
                                     (THREADINFOCLASS)33,
                                     &ProcNumber,
                                     4u);
        if ( ProcessorNumberFromIndex < 0 )
          goto LABEL_31;
      }
      if ( *((_BYTE *)*a1 + 34) )
        KeSetBasePriorityThread(*(PKTHREAD *)((char *)a1[10] + v7 + 16), 3);
    }
  }
  ProcessorNumberFromIndex = -1073741670;
LABEL_31:
  if ( (BYTE3(xmmword_1401A2C90) & 1) != 0 )
    WPP_SF_ddL(536, 13, v4, (unsigned int)ProcessorNumberFromIndex, *((_DWORD *)a1 + 2), **a1);
  UlpTerminateThreadPoolWorkersLocked(a1);
LABEL_29:
  ExReleasePushLockExclusiveEx(a1 + 9, 0);
  KeLeaveCriticalRegion();
  return (unsigned int)ProcessorNumberFromIndex;
}

```

## disassembly

```asm
0x140060634  mov     [rsp-8+arg_8], rbx
0x140060639  mov     [rsp-8+arg_10], rsi
0x14006063e  push    rbp
0x14006063f  push    rdi
0x140060640  push    r12
0x140060642  push    r14
0x140060644  push    r15
0x140060646  lea     rbp, [rsp-37h]
0x14006064b  sub     rsp, 0F0h
0x140060652  mov     rax, cs:__security_cookie
0x140060659  xor     rax, rsp
0x14006065c  mov     [rbp+57h+var_30], rax
0x140060660  xorps   xmm0, xmm0
0x140060663  mov     rsi, rcx
0x140060666  xor     eax, eax
0x140060668  lea     rcx, [rbp+57h+Information]; void *
0x14006066c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140060670  xor     edi, edi
0x140060672  mov     dword ptr [rbp+57h+ProcNumber.Group], eax
0x140060675  xor     edx, edx; Val
0x140060677  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14006067b  lea     r8d, [rdi+50h]; Size
0x14006067f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140060683  movups  [rbp+57h+var_40], xmm0
0x140060687  call    memset
0x14006068c  mov     [rbp+57h+Length], edi
0x14006068f  call    cs:__imp_KeEnterCriticalRegion
0x140060696  nop     dword ptr [rax+rax+00h]
0x14006069b  xor     edx, edx
0x14006069d  lea     rcx, [rsi+48h]
0x1400606a1  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400606a8  nop     dword ptr [rax+rax+00h]
0x1400606ad  cmp     [rsi+50h], rdi
0x1400606b1  jnz     loc_14006099E
0x1400606b7  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 1
0x1400606be  jnz     loc_1400609F5
0x1400606c4  mov     rax, [rsi]
0x1400606c7  lea     r9, UxLowPriorityPool
0x1400606ce  mov     ecx, 48h ; 'H'
0x1400606d3  mov     dword ptr [rsp+110h+ClientId], 1
0x1400606db  mov     r8d, 47546C55h
0x1400606e1  movzx   edx, byte ptr [rax+18h]
0x1400606e5  shl     rdx, 6
0x1400606e9  call    cs:__imp_ExAllocatePool3
0x1400606f0  nop     dword ptr [rax+rax+00h]
0x1400606f5  mov     [rsi+50h], rax
0x1400606f9  test    rax, rax
0x1400606fc  jz      loc_140060A1D
0x140060702  xor     r15d, r15d
0x140060705  mov     rcx, [rsi]
0x140060708  movzx   eax, byte ptr [rcx+18h]
0x14006070c  cmp     r15d, eax
0x14006070f  jnb     loc_140060906
0x140060715  mov     rax, [rsi+50h]
0x140060719  xor     r8d, r8d; State
0x14006071c  mov     r14d, r15d
0x14006071f  xor     edx, edx; Type
0x140060721  shl     r14, 6
0x140060725  mov     [r14+rax], rsi
0x140060729  mov     rax, [rsi+50h]
0x14006072d  mov     [r14+rax+8], r15d
0x140060732  mov     rcx, [rsi+50h]
0x140060736  add     rcx, 20h ; ' '
0x14006073a  add     rcx, r14; Event
0x14006073d  call    cs:__imp_KeInitializeEvent
0x140060744  nop     dword ptr [rax+rax+00h]
0x140060749  mov     rdx, [rsi+50h]
0x14006074d  lea     rax, UlpThreadPoolWorker
0x140060754  add     rdx, r14
0x140060757  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14006075e  mov     [rsp+110h+StartContext], rdx; StartContext
0x140060763  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140060767  xorps   xmm0, xmm0
0x14006076a  mov     [rsp+110h+StartRoutine], rax; StartRoutine
0x14006076f  xor     r9d, r9d; ProcessHandle
0x140060772  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14006077a  lea     rcx, [rdx+18h]; ThreadHandle
0x14006077e  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140060785  mov     edx, 1FFFFFh; DesiredAccess
0x14006078a  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140060792  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140060797  mov     [rsp+110h+ClientId], 0; ClientId
0x1400607a0  call    cs:__imp_PsCreateSystemThread
0x1400607a7  nop     dword ptr [rax+rax+00h]
0x1400607ac  mov     edi, eax
0x1400607ae  test    eax, eax
0x1400607b0  js      loc_140060A22
0x1400607b6  mov     rbx, [rsi+50h]
0x1400607ba  lea     rax, [rbp+57h+Object]
0x1400607be  mov     r8, cs:__imp_PsThreadType
0x1400607c5  xor     r9d, r9d; AccessMode
0x1400607c8  mov     [rsp+110h+StartRoutine], 0; HandleInformation
0x1400607d1  mov     [rbp+57h+Object], 0
0x1400607d9  mov     rcx, [r14+rbx+18h]; Handle
0x1400607de  mov     r8, [r8]; ObjectType
0x1400607e1  lea     edx, [r9+1]; DesiredAccess
0x1400607e5  mov     [rsp+110h+ClientId], rax; Object
0x1400607ea  call    cs:__imp_ObReferenceObjectByHandle
0x1400607f1  nop     dword ptr [rax+rax+00h]
0x1400607f6  mov     edi, eax
0x1400607f8  mov     rax, [rbp+57h+Object]
0x1400607fc  mov     [r14+rbx+10h], rax
0x140060801  test    edi, edi
0x140060803  js      loc_140060A22
0x140060809  mov     rcx, [rsi]
0x14006080c  mov     edx, [rcx+1Ch]
0x14006080f  sub     edx, 1
0x140060812  jz      loc_140060A77
0x140060818  sub     edx, 1
0x14006081b  jz      loc_140060A57
0x140060821  cmp     edx, 1
0x140060824  jnz     short loc_14006089E
0x140060826  mov     ecx, [rsi+8]; ProcIndex
0x140060829  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x14006082d  call    cs:__imp_KeGetProcessorNumberFromIndex
0x140060834  nop     dword ptr [rax+rax+00h]
0x140060839  mov     edi, eax
0x14006083b  test    eax, eax
0x14006083d  js      loc_140060A22
0x140060843  mov     edx, 1; RelationshipType
0x140060848  lea     r8, [rbp+57h+Information]; Information
0x14006084c  mov     [rbp+57h+Length], 50h ; 'P'
0x140060853  lea     r9, [rbp+57h+Length]; Length
0x140060857  lea     rcx, [rbp+57h+ProcNumber]; ProcessorNumber
0x14006085b  call    cs:__imp_KeQueryLogicalProcessorRelationship
0x140060862  nop     dword ptr [rax+rax+00h]
0x140060867  mov     edi, eax
0x140060869  test    eax, eax
0x14006086b  js      loc_140060A22
0x140060871  lea     r8, [rbp+57h+Information.8+18h]; ThreadInformation
0x140060875  mov     rcx, [rsi+50h]
0x140060879  mov     r9d, 10h; ThreadInformationLength
0x14006087f  mov     rcx, [r14+rcx+18h]; ThreadHandle
0x140060884  lea     edx, [r9+0Eh]; ThreadInformationClass
0x140060888  call    cs:__imp_ZwSetInformationThread
0x14006088f  nop     dword ptr [rax+rax+00h]
0x140060894  mov     edi, eax
0x140060896  test    eax, eax
0x140060898  js      loc_140060A22
0x14006089e  mov     rcx, [rsi]
0x1400608a1  cmp     dword ptr [rcx+4], 1
0x1400608a5  jnz     short loc_1400608F1
0x1400608a7  mov     ecx, [rsi+8]; ProcIndex
0x1400608aa  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x1400608ae  call    cs:__imp_KeGetProcessorNumberFromIndex
0x1400608b5  nop     dword ptr [rax+rax+00h]
0x1400608ba  mov     edi, eax
0x1400608bc  test    eax, eax
0x1400608be  js      loc_140060A22
0x1400608c4  mov     rcx, [rsi+50h]
0x1400608c8  lea     r8, [rbp+57h+ProcNumber]; ThreadInformation
0x1400608cc  mov     r9d, 4; ThreadInformationLength
0x1400608d2  mov     rcx, [r14+rcx+18h]; ThreadHandle
0x1400608d7  lea     edx, [r9+1Dh]; ThreadInformationClass
0x1400608db  call    cs:__imp_ZwSetInformationThread
0x1400608e2  nop     dword ptr [rax+rax+00h]
0x1400608e7  mov     edi, eax
0x1400608e9  test    eax, eax
0x1400608eb  js      loc_140060A22
0x1400608f1  mov     rax, [rsi]
0x1400608f4  cmp     byte ptr [rax+22h], 0
0x1400608f8  jnz     loc_140060AB7
0x1400608fe  inc     r15d
0x140060901  jmp     loc_140060705
0x140060906  xor     ebx, ebx
0x140060908  test    eax, eax
0x14006090a  jz      short loc_14006093B
0x14006090c  mov     rax, [rsi+50h]
0x140060910  xor     r8d, r8d; Wait
0x140060913  add     rax, 20h ; ' '
0x140060917  mov     ecx, ebx
0x140060919  shl     rcx, 6
0x14006091d  xor     edx, edx; Increment
0x14006091f  add     rcx, rax; Event
0x140060922  call    cs:__imp_KeSetEvent
0x140060929  nop     dword ptr [rax+rax+00h]
0x14006092e  mov     rcx, [rsi]
0x140060931  inc     ebx
0x140060933  movzx   eax, byte ptr [rcx+18h]
0x140060937  cmp     ebx, eax
0x140060939  jb      short loc_14006090C
0x14006093b  cmp     byte ptr [rcx+21h], 0
0x14006093f  jz      short loc_140060996
0x140060941  call    cs:__imp_KeEnterCriticalRegion
0x140060948  nop     dword ptr [rax+rax+00h]
0x14006094d  xor     edx, edx
0x14006094f  lea     rcx, UlThreadPoolOnDemandLock
0x140060956  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006095d  nop     dword ptr [rax+rax+00h]
0x140060962  mov     eax, cs:UlThreadPoolOnDemandCount
0x140060968  inc     eax
0x14006096a  mov     cs:UlThreadPoolOnDemandCount, eax
0x140060970  cmp     eax, 2
0x140060973  jz      short loc_1400609E7
0x140060975  xor     edx, edx
0x140060977  lea     rcx, UlThreadPoolOnDemandLock
0x14006097e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140060985  nop     dword ptr [rax+rax+00h]
0x14006098a  call    cs:__imp_KeLeaveCriticalRegion
0x140060991  nop     dword ptr [rax+rax+00h]
0x140060996  test    edi, edi
0x140060998  js      loc_140060A22
0x14006099e  xor     edx, edx
0x1400609a0  lea     rcx, [rsi+48h]
0x1400609a4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400609ab  nop     dword ptr [rax+rax+00h]
0x1400609b0  call    cs:__imp_KeLeaveCriticalRegion
0x1400609b7  nop     dword ptr [rax+rax+00h]
0x1400609bc  mov     eax, edi
0x1400609be  mov     rcx, [rbp+57h+var_30]
0x1400609c2  xor     rcx, rsp; StackCookie
0x1400609c5  call    __security_check_cookie
0x1400609ca  lea     r11, [rsp+110h+var_20]
0x1400609d2  mov     rbx, [r11+38h]
0x1400609d6  mov     rsi, [r11+40h]
0x1400609da  mov     rsp, r11
0x1400609dd  pop     r15
0x1400609df  pop     r14
0x1400609e1  pop     r12
0x1400609e3  pop     rdi
0x1400609e4  pop     rbp
0x1400609e5  retn
0x1400609e7  lea     rcx, UlThreadPoolScavenger
0x1400609ee  call    UlEnablePeriodicScavenger
0x1400609f3  jmp     short loc_140060975
0x1400609f5  mov     rax, [rsi]
0x1400609f8  lea     r8, WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids
0x1400609ff  mov     r9d, [rsi+8]
0x140060a03  mov     edx, 0Ch
0x140060a08  mov     ecx, 518h
0x140060a0d  mov     eax, [rax]
0x140060a0f  mov     dword ptr [rsp+110h+ClientId], eax
0x140060a13  call    WPP_SF_Dd
0x140060a18  jmp     loc_1400606C4
0x140060a1d  mov     edi, 0C000009Ah
0x140060a22  test    byte ptr cs:xmmword_1401A2C90+3, 1
0x140060a29  jz      loc_1401779D0
0x140060a2f  mov     rax, [rsi]
0x140060a32  mov     edx, 0Dh
0x140060a37  mov     ecx, 218h
0x140060a3c  mov     r9d, edi
0x140060a3f  mov     eax, [rax]
0x140060a41  mov     dword ptr [rsp+110h+StartRoutine], eax
0x140060a45  mov     eax, [rsi+8]
0x140060a48  mov     dword ptr [rsp+110h+ClientId], eax
0x140060a4c  call    WPP_SF_ddL
0x140060a51  nop
0x140060a52  jmp     loc_1401779D0
0x140060a57  mov     ecx, [rsi+8]; ProcIndex
0x140060a5a  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x140060a5e  call    cs:__imp_KeGetProcessorNumberFromIndex
0x140060a65  nop     dword ptr [rax+rax+00h]
0x140060a6a  mov     edi, eax
0x140060a6c  test    eax, eax
0x140060a6e  js      short loc_140060A22
0x140060a70  xor     edx, edx
0x140060a72  jmp     loc_140060848
0x140060a77  mov     ecx, [rsi+8]; ProcIndex
0x140060a7a  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x140060a7e  call    cs:__imp_KeGetProcessorNumberFromIndex
0x140060a85  nop     dword ptr [rax+rax+00h]
0x140060a8a  mov     edi, eax
0x140060a8c  test    eax, eax
0x140060a8e  js      short loc_140060A22
0x140060a90  movzx   eax, [rbp+57h+ProcNumber.Group]
0x140060a94  lea     r8, [rbp+57h+var_40]
0x140060a98  mov     cl, [rbp+57h+ProcNumber.Number]
0x140060a9b  xorps   xmm0, xmm0
0x140060a9e  movups  [rbp+57h+var_40], xmm0
0x140060aa2  mov     word ptr [rbp+57h+var_40+8], ax
0x140060aa6  mov     eax, 1
0x140060aab  shl     rax, cl
0x140060aae  mov     qword ptr [rbp+57h+var_40], rax
0x140060ab2  jmp     loc_140060875
0x140060ab7  mov     rcx, [rsi+50h]
0x140060abb  mov     edx, 3; Increment
0x140060ac0  mov     rcx, [r14+rcx+10h]; Thread
0x140060ac5  call    cs:__imp_KeSetBasePriorityThread
0x140060acc  nop     dword ptr [rax+rax+00h]
0x140060ad1  jmp     loc_1400608FE
0x1401779d0  mov     rcx, rsi
0x1401779d3  call    UlpTerminateThreadPoolWorkersLocked
0x1401779d8  nop
0x1401779d9  jmp     loc_14006099E
```
