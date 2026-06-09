# KsRemoveBusEnumInterface

- ea: `0x180035af0`
- end: `0x180035bcf`
- name: `KsRemoveBusEnumInterface`
- size: `223`
- prototype: `NTSTATUS __stdcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180035af0`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x180035b27`
- `ntoskrnl!ExGetPreviousMode` at `0x180035b27`
- `ntoskrnl!ExQueueWorkItem` at `0x180035b8d`
- `ntoskrnl!ExQueueWorkItem` at `0x180035b8d`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x180035b39`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x180035b39`
- `ntoskrnl!KeWaitForSingleObject` at `0x180035bae`
- `ntoskrnl!KeWaitForSingleObject` at `0x180035bae`
- `ntoskrnl!KeInitializeEvent` at `0x180035b59`
- `ntoskrnl!KeInitializeEvent` at `0x180035b59`

## pseudocode

```c
NTSTATUS __stdcall KsRemoveBusEnumInterface(PIRP Irp)
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
  WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KspRemoveBusEnumInterface;
  WorkItem.List.Flink = 0;
  WorkItem.Parameter = Event;
  ExQueueWorkItem(&WorkItem, DelayedWorkQueue);
  KeWaitForSingleObject(&Event[1], Executive, 0, 0, 0);
  return v6;
}

```

## disassembly

```asm
0x180035af0  mov     [rsp-8+arg_0], rbx
0x180035af5  push    rbp
0x180035af6  mov     rbp, rsp
0x180035af9  sub     rsp, 80h
0x180035b00  xorps   xmm0, xmm0
0x180035b03  mov     qword ptr [rbp+PrivilegeValue.LowPart], 0Ah
0x180035b0b  xorps   xmm1, xmm1
0x180035b0e  xor     eax, eax
0x180035b10  movups  xmmword ptr [rbp+WorkItem.List.Flink], xmm0
0x180035b14  mov     [rbp+var_10], rax
0x180035b18  mov     rbx, rcx
0x180035b1b  movups  xmmword ptr [rbp+WorkItem.WorkerRoutine], xmm0
0x180035b1f  movups  xmmword ptr [rbp+Event], xmm1
0x180035b23  movups  xmmword ptr [rbp+Event+10h], xmm1
0x180035b27  call    cs:__imp_ExGetPreviousMode
0x180035b2e  nop     dword ptr [rax+rax+00h]
0x180035b33  mov     rcx, qword ptr [rbp+PrivilegeValue.LowPart]; PrivilegeValue
0x180035b37  mov     dl, al; PreviousMode
0x180035b39  call    cs:__imp_SeSinglePrivilegeCheck
0x180035b40  nop     dword ptr [rax+rax+00h]
0x180035b45  test    al, al
0x180035b47  jnz     short loc_180035B50
0x180035b49  mov     eax, 0C0000061h
0x180035b4e  jmp     short loc_180035BBD
0x180035b50  xor     r8d, r8d; State
0x180035b53  lea     rcx, [rbp+Event+8]; Event
0x180035b57  xor     edx, edx; Type
0x180035b59  call    cs:__imp_KeInitializeEvent
0x180035b60  nop     dword ptr [rax+rax+00h]
0x180035b65  lea     rax, KspRemoveBusEnumInterface
0x180035b6c  mov     qword ptr [rbp+Event], rbx
0x180035b70  mov     [rbp+WorkItem.WorkerRoutine], rax
0x180035b74  lea     rcx, [rbp+WorkItem]; WorkItem
0x180035b78  lea     rax, [rbp+Event]
0x180035b7c  mov     [rbp+WorkItem.List.Flink], 0
0x180035b84  mov     edx, 1; QueueType
0x180035b89  mov     [rbp+WorkItem.Parameter], rax
0x180035b8d  call    cs:__imp_ExQueueWorkItem
0x180035b94  nop     dword ptr [rax+rax+00h]
0x180035b99  xor     r9d, r9d; Alertable
0x180035b9c  mov     [rsp+80h+Timeout], 0; Timeout
0x180035ba5  xor     r8d, r8d; WaitMode
0x180035ba8  lea     rcx, [rbp+Event+8]; Object
0x180035bac  xor     edx, edx; WaitReason
0x180035bae  call    cs:__imp_KeWaitForSingleObject
0x180035bb5  nop     dword ptr [rax+rax+00h]
0x180035bba  mov     eax, dword ptr [rbp+var_10]
0x180035bbd  mov     rbx, [rsp+80h+arg_0]
0x180035bc5  add     rsp, 80h
0x180035bcc  pop     rbp
0x180035bcd  retn
```
