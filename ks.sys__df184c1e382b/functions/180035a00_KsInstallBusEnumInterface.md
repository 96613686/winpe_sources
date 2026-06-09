# KsInstallBusEnumInterface

- ea: `0x180035a00`
- end: `0x180035adf`
- name: `KsInstallBusEnumInterface`
- size: `223`
- prototype: `NTSTATUS __stdcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180035a00`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x180035a37`
- `ntoskrnl!ExGetPreviousMode` at `0x180035a37`
- `ntoskrnl!ExQueueWorkItem` at `0x180035a9d`
- `ntoskrnl!ExQueueWorkItem` at `0x180035a9d`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x180035a49`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x180035a49`
- `ntoskrnl!KeWaitForSingleObject` at `0x180035abe`
- `ntoskrnl!KeWaitForSingleObject` at `0x180035abe`
- `ntoskrnl!KeInitializeEvent` at `0x180035a69`
- `ntoskrnl!KeInitializeEvent` at `0x180035a69`

## pseudocode

```c
NTSTATUS __stdcall KsInstallBusEnumInterface(PIRP Irp)
{
  KPROCESSOR_MODE PreviousMode; // al
  struct _WORK_QUEUE_ITEM WorkItem; // [rsp+30h] [rbp-50h] BYREF
  _QWORD Event[4]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v6; // [rsp+70h] [rbp-10h]

  memset(&WorkItem, 0, sizeof(WorkItem));
  v6 = 0;
  memset(Event, 0, sizeof(Event));
  PreviousMode = ExGetPreviousMode();
  if ( !SeSinglePrivilegeCheck((LUID)10LL, PreviousMode) )
    return -1073741727;
  KeInitializeEvent((PRKEVENT)&Event[1], NotificationEvent, 0);
  Event[0] = Irp;
  WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KspInstallBusEnumInterface;
  WorkItem.List.Flink = 0;
  WorkItem.Parameter = Event;
  ExQueueWorkItem(&WorkItem, DelayedWorkQueue);
  KeWaitForSingleObject(&Event[1], Executive, 0, 0, 0);
  return v6;
}

```

## disassembly

```asm
0x180035a00  mov     [rsp-8+arg_0], rbx
0x180035a05  push    rbp
0x180035a06  mov     rbp, rsp
0x180035a09  sub     rsp, 80h
0x180035a10  xorps   xmm0, xmm0
0x180035a13  mov     qword ptr [rbp+PrivilegeValue.LowPart], 0Ah
0x180035a1b  xorps   xmm1, xmm1
0x180035a1e  xor     eax, eax
0x180035a20  movups  xmmword ptr [rbp+WorkItem.List.Flink], xmm0
0x180035a24  mov     [rbp+var_10], rax
0x180035a28  mov     rbx, rcx
0x180035a2b  movups  xmmword ptr [rbp+WorkItem.WorkerRoutine], xmm0
0x180035a2f  movups  xmmword ptr [rbp+Event], xmm1
0x180035a33  movups  xmmword ptr [rbp+Event+10h], xmm1
0x180035a37  call    cs:__imp_ExGetPreviousMode
0x180035a3e  nop     dword ptr [rax+rax+00h]
0x180035a43  mov     rcx, qword ptr [rbp+PrivilegeValue.LowPart]; PrivilegeValue
0x180035a47  mov     dl, al; PreviousMode
0x180035a49  call    cs:__imp_SeSinglePrivilegeCheck
0x180035a50  nop     dword ptr [rax+rax+00h]
0x180035a55  test    al, al
0x180035a57  jnz     short loc_180035A60
0x180035a59  mov     eax, 0C0000061h
0x180035a5e  jmp     short loc_180035ACD
0x180035a60  xor     r8d, r8d; State
0x180035a63  lea     rcx, [rbp+Event+8]; Event
0x180035a67  xor     edx, edx; Type
0x180035a69  call    cs:__imp_KeInitializeEvent
0x180035a70  nop     dword ptr [rax+rax+00h]
0x180035a75  lea     rax, KspInstallBusEnumInterface
0x180035a7c  mov     qword ptr [rbp+Event], rbx
0x180035a80  mov     [rbp+WorkItem.WorkerRoutine], rax
0x180035a84  lea     rcx, [rbp+WorkItem]; WorkItem
0x180035a88  lea     rax, [rbp+Event]
0x180035a8c  mov     [rbp+WorkItem.List.Flink], 0
0x180035a94  mov     edx, 1; QueueType
0x180035a99  mov     [rbp+WorkItem.Parameter], rax
0x180035a9d  call    cs:__imp_ExQueueWorkItem
0x180035aa4  nop     dword ptr [rax+rax+00h]
0x180035aa9  xor     r9d, r9d; Alertable
0x180035aac  mov     [rsp+80h+Timeout], 0; Timeout
0x180035ab5  xor     r8d, r8d; WaitMode
0x180035ab8  lea     rcx, [rbp+Event+8]; Object
0x180035abc  xor     edx, edx; WaitReason
0x180035abe  call    cs:__imp_KeWaitForSingleObject
0x180035ac5  nop     dword ptr [rax+rax+00h]
0x180035aca  mov     eax, dword ptr [rbp+var_10]
0x180035acd  mov     rbx, [rsp+80h+arg_0]
0x180035ad5  add     rsp, 80h
0x180035adc  pop     rbp
0x180035add  retn
```
