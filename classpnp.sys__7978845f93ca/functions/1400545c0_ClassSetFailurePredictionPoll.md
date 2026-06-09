# ClassSetFailurePredictionPoll

- ea: `0x1400545c0`
- end: `0x14005472b`
- name: `ClassSetFailurePredictionPoll`
- size: `363`
- prototype: `NTSTATUS __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, FAILURE_PREDICTION_METHOD FailurePredictionMethod, ULONG PollingPeriod)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140018018`
- `0x140018424`
- `0x14001fc38`
- `0x1400545c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14005464d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005464d`
- `ntoskrnl!KeSetEvent` at `0x140054705`
- `ntoskrnl!KeSetEvent` at `0x140054705`
- `ntoskrnl!ExAllocatePool2` at `0x1400545f3`
- `ntoskrnl!ExAllocatePool2` at `0x1400545f3`
- `ntoskrnl!KeInitializeEvent` at `0x14005461d`
- `ntoskrnl!KeInitializeEvent` at `0x14005461d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054670`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054670`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054711`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054711`

## pseudocode

```c
NTSTATUS __stdcall ClassSetFailurePredictionPoll(
        PFUNCTIONAL_DEVICE_EXTENSION FdoExtension,
        FAILURE_PREDICTION_METHOD FailurePredictionMethod,
        ULONG PollingPeriod)
{
  _FAILURE_PREDICTION_INFO *FailurePredictionInfo; // rbx
  struct _KEVENT *Pool2; // rax
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx

  FailurePredictionInfo = FdoExtension->FailurePredictionInfo;
  if ( FailurePredictionInfo )
    goto LABEL_6;
  if ( FailurePredictionMethod )
  {
    Pool2 = (struct _KEVENT *)ExAllocatePool2(64, 56, 1716282195);
    FailurePredictionInfo = (_FAILURE_PREDICTION_INFO *)Pool2;
    if ( !Pool2 )
      return -1073741670;
    KeInitializeEvent(Pool2 + 1, SynchronizationEvent, 1u);
    FailurePredictionInfo->WorkQueueItem = 0;
    FailurePredictionInfo->Period = 3600;
    FailurePredictionInfo->LastFailurePredictionQueryTime.QuadPart = MEMORY[0xFFFFF78000000014];
    FdoExtension->FailurePredictionInfo = FailurePredictionInfo;
LABEL_6:
    KeEnterCriticalRegion();
    KeWaitForSingleObject(&FailurePredictionInfo->Event, UserRequest, 0, 0, 0);
    if ( PollingPeriod )
      _InterlockedExchange((volatile __int32 *)&FailurePredictionInfo->Period, PollingPeriod);
    _InterlockedExchange((volatile __int32 *)&FailurePredictionInfo->CountDown, FailurePredictionInfo->Period);
    FailurePredictionInfo->Method = FailurePredictionMethod;
    if ( FailurePredictionMethod )
    {
      ClasspEnableTimer(FdoExtension);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_18;
      }
      v10 = 107;
    }
    else
    {
      ClasspDisableTimer(FdoExtension);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_18;
      }
      v10 = 108;
    }
    WPP_SF_q(v9->AttachedDevice, v10, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, FdoExtension->DeviceObject);
LABEL_18:
    KeSetEvent(&FailurePredictionInfo->Event, 0, 0);
    KeLeaveCriticalRegion();
  }
  return 0;
}

```

## disassembly

```asm
0x1400545c0  push    rbx
0x1400545c2  push    rbp
0x1400545c3  push    rsi
0x1400545c4  push    rdi
0x1400545c5  push    r14
0x1400545c7  sub     rsp, 30h
0x1400545cb  mov     rbx, [rcx+338h]
0x1400545d2  mov     ebp, r8d
0x1400545d5  mov     esi, edx
0x1400545d7  mov     rdi, rcx
0x1400545da  test    rbx, rbx
0x1400545dd  jnz     short loc_14005464D
0x1400545df  test    edx, edx
0x1400545e1  jz      loc_14005471D
0x1400545e7  lea     edx, [rbx+38h]
0x1400545ea  mov     r8d, 664C6353h
0x1400545f0  lea     ecx, [rbx+40h]
0x1400545f3  call    cs:__imp_ExAllocatePool2
0x1400545fa  nop     dword ptr [rax+rax+00h]
0x1400545ff  mov     rbx, rax
0x140054602  test    rax, rax
0x140054605  jnz     short loc_140054611
0x140054607  mov     eax, 0C000009Ah
0x14005460c  jmp     loc_14005471F
0x140054611  lea     rcx, [rax+18h]; Event
0x140054615  mov     r8b, 1; State
0x140054618  mov     edx, 1; Type
0x14005461d  call    cs:__imp_KeInitializeEvent
0x140054624  nop     dword ptr [rax+rax+00h]
0x140054629  mov     qword ptr [rbx+10h], 0
0x140054631  mov     dword ptr [rbx+8], 0E10h
0x140054638  mov     rax, ds:0FFFFF78000000014h
0x140054642  mov     [rbx+30h], rax
0x140054646  mov     [rdi+338h], rbx
0x14005464d  call    cs:__imp_KeEnterCriticalRegion
0x140054654  nop     dword ptr [rax+rax+00h]
0x140054659  xor     r9d, r9d; Alertable
0x14005465c  mov     [rsp+58h+Timeout], 0; Timeout
0x140054665  xor     r8d, r8d; WaitMode
0x140054668  lea     rcx, [rbx+18h]; Object
0x14005466c  lea     edx, [r9+6]; WaitReason
0x140054670  call    cs:__imp_KeWaitForSingleObject
0x140054677  nop     dword ptr [rax+rax+00h]
0x14005467c  test    ebp, ebp
0x14005467e  jz      short loc_140054683
0x140054680  xchg    ebp, [rbx+8]
0x140054683  mov     eax, [rbx+8]
0x140054686  mov     rcx, rdi
0x140054689  xchg    eax, [rbx+4]
0x14005468c  mov     [rbx], esi
0x14005468e  test    esi, esi
0x140054690  jz      short loc_1400546BE
0x140054692  call    ClasspEnableTimer
0x140054697  mov     rcx, cs:WPP_GLOBAL_Control
0x14005469e  lea     rax, WPP_GLOBAL_Control
0x1400546a5  cmp     rcx, rax
0x1400546a8  jz      short loc_1400546FC
0x1400546aa  mov     eax, [rcx+2Ch]
0x1400546ad  test    al, 40h
0x1400546af  jz      short loc_1400546FC
0x1400546b1  cmp     byte ptr [rcx+29h], 4
0x1400546b5  jb      short loc_1400546FC
0x1400546b7  mov     edx, 6Bh ; 'k'
0x1400546bc  jmp     short loc_1400546E8
0x1400546be  call    ClasspDisableTimer
0x1400546c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400546ca  lea     rax, WPP_GLOBAL_Control
0x1400546d1  cmp     rcx, rax
0x1400546d4  jz      short loc_1400546FC
0x1400546d6  mov     eax, [rcx+2Ch]
0x1400546d9  test    al, 40h
0x1400546db  jz      short loc_1400546FC
0x1400546dd  cmp     byte ptr [rcx+29h], 4
0x1400546e1  jb      short loc_1400546FC
0x1400546e3  mov     edx, 6Ch ; 'l'
0x1400546e8  mov     r9, [rdi+8]
0x1400546ec  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x1400546f3  mov     rcx, [rcx+18h]
0x1400546f7  call    WPP_SF_q
0x1400546fc  xor     r8d, r8d; Wait
0x1400546ff  lea     rcx, [rbx+18h]; Event
0x140054703  xor     edx, edx; Increment
0x140054705  call    cs:__imp_KeSetEvent
0x14005470c  nop     dword ptr [rax+rax+00h]
0x140054711  call    cs:__imp_KeLeaveCriticalRegion
0x140054718  nop     dword ptr [rax+rax+00h]
0x14005471d  xor     eax, eax
0x14005471f  add     rsp, 30h
0x140054723  pop     r14
0x140054725  pop     rdi
0x140054726  pop     rsi
0x140054727  pop     rbp
0x140054728  pop     rbx
0x140054729  retn
```
