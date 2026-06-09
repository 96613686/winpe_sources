# UlpInitializeThreadPoolWorkers

- ea: `0x140060614`
- end: `0x140060ab6`
- name: `UlpInitializeThreadPoolWorkers`
- size: `1186`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140060460`
- `0x14013defc`

## callees

- `0x140060614`
- `0x140060abc`
- `0x14009ce48`
- `0x140167810`
- `0x140167c40`
- `0x1401d620c`
- `0x1401d9e44`

## import_xrefs

- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14006080d`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14006088e`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140060a3e`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140060a5e`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14006080d`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14006088e`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140060a3e`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x140060a5e`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x14006083b`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x14006083b`
- `ntoskrnl!PsCreateSystemThread` at `0x140060780`
- `ntoskrnl!PsCreateSystemThread` at `0x140060780`
- `ntoskrnl!KeSetBasePriorityThread` at `0x140060aa5`
- `ntoskrnl!KeSetBasePriorityThread` at `0x140060aa5`
- `ntoskrnl!PsThreadType` at `0x14006079e`
- `ntoskrnl!ZwSetInformationThread` at `0x140060868`
- `ntoskrnl!ZwSetInformationThread` at `0x1400608bb`
- `ntoskrnl!ZwSetInformationThread` at `0x140060868`
- `ntoskrnl!ZwSetInformationThread` at `0x1400608bb`
- `ntoskrnl!KeInitializeEvent` at `0x14006071d`
- `ntoskrnl!KeInitializeEvent` at `0x14006071d`
- `ntoskrnl!KeSetEvent` at `0x140060902`
- `ntoskrnl!KeSetEvent` at `0x140060902`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400607ca`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400607ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006096a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140060990`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006096a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140060990`
- `ntoskrnl!ExAllocatePool3` at `0x1400606c9`
- `ntoskrnl!ExAllocatePool3` at `0x1400606c9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006095e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140060984`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006095e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140060984`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140060681`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140060936`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140060681`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140060936`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006066f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140060921`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006066f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140060921`

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
0x140060614  mov     [rsp-8+arg_8], rbx
0x140060619  mov     [rsp-8+arg_10], rsi
0x14006061e  push    rbp
0x14006061f  push    rdi
0x140060620  push    r12
0x140060622  push    r14
0x140060624  push    r15
0x140060626  lea     rbp, [rsp-37h]
0x14006062b  sub     rsp, 0F0h
0x140060632  mov     rax, cs:__security_cookie
0x140060639  xor     rax, rsp
0x14006063c  mov     [rbp+57h+var_30], rax
0x140060640  xorps   xmm0, xmm0
0x140060643  mov     rsi, rcx
0x140060646  xor     eax, eax
0x140060648  lea     rcx, [rbp+57h+Information]; void *
0x14006064c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140060650  xor     edi, edi
0x140060652  mov     dword ptr [rbp+57h+ProcNumber.Group], eax
0x140060655  xor     edx, edx; Val
0x140060657  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14006065b  lea     r8d, [rdi+50h]; Size
0x14006065f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140060663  movups  [rbp+57h+var_40], xmm0
0x140060667  call    memset
0x14006066c  mov     [rbp+57h+Length], edi
0x14006066f  call    cs:__imp_KeEnterCriticalRegion
0x140060676  nop     dword ptr [rax+rax+00h]
0x14006067b  xor     edx, edx
0x14006067d  lea     rcx, [rsi+48h]
0x140060681  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140060688  nop     dword ptr [rax+rax+00h]
0x14006068d  cmp     [rsi+50h], rdi
0x140060691  jnz     loc_14006097E
0x140060697  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 1
0x14006069e  jnz     loc_1400609D5
0x1400606a4  mov     rax, [rsi]
0x1400606a7  lea     r9, UxLowPriorityPool
0x1400606ae  mov     ecx, 48h ; 'H'
0x1400606b3  mov     dword ptr [rsp+110h+ClientId], 1
0x1400606bb  mov     r8d, 47546C55h
0x1400606c1  movzx   edx, byte ptr [rax+18h]
0x1400606c5  shl     rdx, 6
0x1400606c9  call    cs:__imp_ExAllocatePool3
0x1400606d0  nop     dword ptr [rax+rax+00h]
0x1400606d5  mov     [rsi+50h], rax
0x1400606d9  test    rax, rax
0x1400606dc  jz      loc_1400609FD
0x1400606e2  xor     r15d, r15d
0x1400606e5  mov     rcx, [rsi]
0x1400606e8  movzx   eax, byte ptr [rcx+18h]
0x1400606ec  cmp     r15d, eax
0x1400606ef  jnb     loc_1400608E6
0x1400606f5  mov     rax, [rsi+50h]
0x1400606f9  xor     r8d, r8d; State
0x1400606fc  mov     r14d, r15d
0x1400606ff  xor     edx, edx; Type
0x140060701  shl     r14, 6
0x140060705  mov     [r14+rax], rsi
0x140060709  mov     rax, [rsi+50h]
0x14006070d  mov     [r14+rax+8], r15d
0x140060712  mov     rcx, [rsi+50h]
0x140060716  add     rcx, 20h ; ' '
0x14006071a  add     rcx, r14; Event
0x14006071d  call    cs:__imp_KeInitializeEvent
0x140060724  nop     dword ptr [rax+rax+00h]
0x140060729  mov     rdx, [rsi+50h]
0x14006072d  lea     rax, UlpThreadPoolWorker
0x140060734  add     rdx, r14
0x140060737  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14006073e  mov     [rsp+110h+StartContext], rdx; StartContext
0x140060743  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140060747  xorps   xmm0, xmm0
0x14006074a  mov     [rsp+110h+StartRoutine], rax; StartRoutine
0x14006074f  xor     r9d, r9d; ProcessHandle
0x140060752  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14006075a  lea     rcx, [rdx+18h]; ThreadHandle
0x14006075e  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140060765  mov     edx, 1FFFFFh; DesiredAccess
0x14006076a  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140060772  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140060777  mov     [rsp+110h+ClientId], 0; ClientId
0x140060780  call    cs:__imp_PsCreateSystemThread
0x140060787  nop     dword ptr [rax+rax+00h]
0x14006078c  mov     edi, eax
0x14006078e  test    eax, eax
0x140060790  js      loc_140060A02
0x140060796  mov     rbx, [rsi+50h]
0x14006079a  lea     rax, [rbp+57h+Object]
0x14006079e  mov     r8, cs:__imp_PsThreadType
0x1400607a5  xor     r9d, r9d; AccessMode
0x1400607a8  mov     [rsp+110h+StartRoutine], 0; HandleInformation
0x1400607b1  mov     [rbp+57h+Object], 0
0x1400607b9  mov     rcx, [r14+rbx+18h]; Handle
0x1400607be  mov     r8, [r8]; ObjectType
0x1400607c1  lea     edx, [r9+1]; DesiredAccess
0x1400607c5  mov     [rsp+110h+ClientId], rax; Object
0x1400607ca  call    cs:__imp_ObReferenceObjectByHandle
0x1400607d1  nop     dword ptr [rax+rax+00h]
0x1400607d6  mov     edi, eax
0x1400607d8  mov     rax, [rbp+57h+Object]
0x1400607dc  mov     [r14+rbx+10h], rax
0x1400607e1  test    edi, edi
0x1400607e3  js      loc_140060A02
0x1400607e9  mov     rcx, [rsi]
0x1400607ec  mov     edx, [rcx+1Ch]
0x1400607ef  sub     edx, 1
0x1400607f2  jz      loc_140060A57
0x1400607f8  sub     edx, 1
0x1400607fb  jz      loc_140060A37
0x140060801  cmp     edx, 1
0x140060804  jnz     short loc_14006087E
0x140060806  mov     ecx, [rsi+8]; ProcIndex
0x140060809  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x14006080d  call    cs:__imp_KeGetProcessorNumberFromIndex
0x140060814  nop     dword ptr [rax+rax+00h]
0x140060819  mov     edi, eax
0x14006081b  test    eax, eax
0x14006081d  js      loc_140060A02
0x140060823  mov     edx, 1; RelationshipType
0x140060828  lea     r8, [rbp+57h+Information]; Information
0x14006082c  mov     [rbp+57h+Length], 50h ; 'P'
0x140060833  lea     r9, [rbp+57h+Length]; Length
0x140060837  lea     rcx, [rbp+57h+ProcNumber]; ProcessorNumber
0x14006083b  call    cs:__imp_KeQueryLogicalProcessorRelationship
0x140060842  nop     dword ptr [rax+rax+00h]
0x140060847  mov     edi, eax
0x140060849  test    eax, eax
0x14006084b  js      loc_140060A02
0x140060851  lea     r8, [rbp+57h+Information.8+18h]; ThreadInformation
0x140060855  mov     rcx, [rsi+50h]
0x140060859  mov     r9d, 10h; ThreadInformationLength
0x14006085f  mov     rcx, [r14+rcx+18h]; ThreadHandle
0x140060864  lea     edx, [r9+0Eh]; ThreadInformationClass
0x140060868  call    cs:__imp_ZwSetInformationThread
0x14006086f  nop     dword ptr [rax+rax+00h]
0x140060874  mov     edi, eax
0x140060876  test    eax, eax
0x140060878  js      loc_140060A02
0x14006087e  mov     rcx, [rsi]
0x140060881  cmp     dword ptr [rcx+4], 1
0x140060885  jnz     short loc_1400608D1
0x140060887  mov     ecx, [rsi+8]; ProcIndex
0x14006088a  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x14006088e  call    cs:__imp_KeGetProcessorNumberFromIndex
0x140060895  nop     dword ptr [rax+rax+00h]
0x14006089a  mov     edi, eax
0x14006089c  test    eax, eax
0x14006089e  js      loc_140060A02
0x1400608a4  mov     rcx, [rsi+50h]
0x1400608a8  lea     r8, [rbp+57h+ProcNumber]; ThreadInformation
0x1400608ac  mov     r9d, 4; ThreadInformationLength
0x1400608b2  mov     rcx, [r14+rcx+18h]; ThreadHandle
0x1400608b7  lea     edx, [r9+1Dh]; ThreadInformationClass
0x1400608bb  call    cs:__imp_ZwSetInformationThread
0x1400608c2  nop     dword ptr [rax+rax+00h]
0x1400608c7  mov     edi, eax
0x1400608c9  test    eax, eax
0x1400608cb  js      loc_140060A02
0x1400608d1  mov     rax, [rsi]
0x1400608d4  cmp     byte ptr [rax+22h], 0
0x1400608d8  jnz     loc_140060A97
0x1400608de  inc     r15d
0x1400608e1  jmp     loc_1400606E5
0x1400608e6  xor     ebx, ebx
0x1400608e8  test    eax, eax
0x1400608ea  jz      short loc_14006091B
0x1400608ec  mov     rax, [rsi+50h]
0x1400608f0  xor     r8d, r8d; Wait
0x1400608f3  add     rax, 20h ; ' '
0x1400608f7  mov     ecx, ebx
0x1400608f9  shl     rcx, 6
0x1400608fd  xor     edx, edx; Increment
0x1400608ff  add     rcx, rax; Event
0x140060902  call    cs:__imp_KeSetEvent
0x140060909  nop     dword ptr [rax+rax+00h]
0x14006090e  mov     rcx, [rsi]
0x140060911  inc     ebx
0x140060913  movzx   eax, byte ptr [rcx+18h]
0x140060917  cmp     ebx, eax
0x140060919  jb      short loc_1400608EC
0x14006091b  cmp     byte ptr [rcx+21h], 0
0x14006091f  jz      short loc_140060976
0x140060921  call    cs:__imp_KeEnterCriticalRegion
0x140060928  nop     dword ptr [rax+rax+00h]
0x14006092d  xor     edx, edx
0x14006092f  lea     rcx, UlThreadPoolOnDemandLock
0x140060936  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006093d  nop     dword ptr [rax+rax+00h]
0x140060942  mov     eax, cs:UlThreadPoolOnDemandCount
0x140060948  inc     eax
0x14006094a  mov     cs:UlThreadPoolOnDemandCount, eax
0x140060950  cmp     eax, 2
0x140060953  jz      short loc_1400609C7
0x140060955  xor     edx, edx
0x140060957  lea     rcx, UlThreadPoolOnDemandLock
0x14006095e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140060965  nop     dword ptr [rax+rax+00h]
0x14006096a  call    cs:__imp_KeLeaveCriticalRegion
0x140060971  nop     dword ptr [rax+rax+00h]
0x140060976  test    edi, edi
0x140060978  js      loc_140060A02
0x14006097e  xor     edx, edx
0x140060980  lea     rcx, [rsi+48h]
0x140060984  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006098b  nop     dword ptr [rax+rax+00h]
0x140060990  call    cs:__imp_KeLeaveCriticalRegion
0x140060997  nop     dword ptr [rax+rax+00h]
0x14006099c  mov     eax, edi
0x14006099e  mov     rcx, [rbp+57h+var_30]
0x1400609a2  xor     rcx, rsp; StackCookie
0x1400609a5  call    __security_check_cookie
0x1400609aa  lea     r11, [rsp+110h+var_20]
0x1400609b2  mov     rbx, [r11+38h]
0x1400609b6  mov     rsi, [r11+40h]
0x1400609ba  mov     rsp, r11
0x1400609bd  pop     r15
0x1400609bf  pop     r14
0x1400609c1  pop     r12
0x1400609c3  pop     rdi
0x1400609c4  pop     rbp
0x1400609c5  retn
0x1400609c7  lea     rcx, UlThreadPoolScavenger
0x1400609ce  call    UlEnablePeriodicScavenger
0x1400609d3  jmp     short loc_140060955
0x1400609d5  mov     rax, [rsi]
0x1400609d8  lea     r8, WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids
0x1400609df  mov     r9d, [rsi+8]
0x1400609e3  mov     edx, 0Ch
0x1400609e8  mov     ecx, 518h
0x1400609ed  mov     eax, [rax]
0x1400609ef  mov     dword ptr [rsp+110h+ClientId], eax
0x1400609f3  call    WPP_SF_Dd
0x1400609f8  jmp     loc_1400606A4
0x1400609fd  mov     edi, 0C000009Ah
0x140060a02  test    byte ptr cs:xmmword_1401A2C90+3, 1
0x140060a09  jz      loc_140177AD0
0x140060a0f  mov     rax, [rsi]
0x140060a12  mov     edx, 0Dh
0x140060a17  mov     ecx, 218h
0x140060a1c  mov     r9d, edi
0x140060a1f  mov     eax, [rax]
0x140060a21  mov     dword ptr [rsp+110h+StartRoutine], eax
0x140060a25  mov     eax, [rsi+8]
0x140060a28  mov     dword ptr [rsp+110h+ClientId], eax
0x140060a2c  call    WPP_SF_ddL
0x140060a31  nop
0x140060a32  jmp     loc_140177AD0
0x140060a37  mov     ecx, [rsi+8]; ProcIndex
0x140060a3a  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x140060a3e  call    cs:__imp_KeGetProcessorNumberFromIndex
0x140060a45  nop     dword ptr [rax+rax+00h]
0x140060a4a  mov     edi, eax
0x140060a4c  test    eax, eax
0x140060a4e  js      short loc_140060A02
0x140060a50  xor     edx, edx
0x140060a52  jmp     loc_140060828
0x140060a57  mov     ecx, [rsi+8]; ProcIndex
0x140060a5a  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x140060a5e  call    cs:__imp_KeGetProcessorNumberFromIndex
0x140060a65  nop     dword ptr [rax+rax+00h]
0x140060a6a  mov     edi, eax
0x140060a6c  test    eax, eax
0x140060a6e  js      short loc_140060A02
0x140060a70  movzx   eax, [rbp+57h+ProcNumber.Group]
0x140060a74  lea     r8, [rbp+57h+var_40]
0x140060a78  mov     cl, [rbp+57h+ProcNumber.Number]
0x140060a7b  xorps   xmm0, xmm0
0x140060a7e  movups  [rbp+57h+var_40], xmm0
0x140060a82  mov     word ptr [rbp+57h+var_40+8], ax
0x140060a86  mov     eax, 1
0x140060a8b  shl     rax, cl
0x140060a8e  mov     qword ptr [rbp+57h+var_40], rax
0x140060a92  jmp     loc_140060855
0x140060a97  mov     rcx, [rsi+50h]
0x140060a9b  mov     edx, 3; Increment
0x140060aa0  mov     rcx, [r14+rcx+10h]; Thread
0x140060aa5  call    cs:__imp_KeSetBasePriorityThread
0x140060aac  nop     dword ptr [rax+rax+00h]
0x140060ab1  jmp     loc_1400608DE
0x140177ad0  mov     rcx, rsi
0x140177ad3  call    UlpTerminateThreadPoolWorkersLocked
0x140177ad8  nop
0x140177ad9  jmp     loc_14006097E
```
