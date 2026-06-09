# KsRemoveBusEnumInterface

- ea: `0x1800359e0`
- end: `0x180035abf`
- name: `KsRemoveBusEnumInterface`
- size: `223`
- prototype: `NTSTATUS __stdcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800359e0`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x180035a17`
- `ntoskrnl!ExGetPreviousMode` at `0x180035a17`
- `ntoskrnl!ExQueueWorkItem` at `0x180035a7d`
- `ntoskrnl!ExQueueWorkItem` at `0x180035a7d`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x180035a29`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x180035a29`
- `ntoskrnl!KeWaitForSingleObject` at `0x180035a9e`
- `ntoskrnl!KeWaitForSingleObject` at `0x180035a9e`
- `ntoskrnl!KeInitializeEvent` at `0x180035a49`
- `ntoskrnl!KeInitializeEvent` at `0x180035a49`

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
0x1800359e0  mov     [rsp-8+arg_0], rbx
0x1800359e5  push    rbp
0x1800359e6  mov     rbp, rsp
0x1800359e9  sub     rsp, 80h
0x1800359f0  xorps   xmm0, xmm0
0x1800359f3  mov     qword ptr [rbp+PrivilegeValue.LowPart], 0Ah
0x1800359fb  xorps   xmm1, xmm1
0x1800359fe  xor     eax, eax
0x180035a00  movups  xmmword ptr [rbp+WorkItem.List.Flink], xmm0
0x180035a04  mov     [rbp+var_10], rax
0x180035a08  mov     rbx, rcx
0x180035a0b  movups  xmmword ptr [rbp+WorkItem.WorkerRoutine], xmm0
0x180035a0f  movups  xmmword ptr [rbp+Event], xmm1
0x180035a13  movups  xmmword ptr [rbp+Event+10h], xmm1
0x180035a17  call    cs:__imp_ExGetPreviousMode
0x180035a1e  nop     dword ptr [rax+rax+00h]
0x180035a23  mov     rcx, qword ptr [rbp+PrivilegeValue.LowPart]; PrivilegeValue
0x180035a27  mov     dl, al; PreviousMode
0x180035a29  call    cs:__imp_SeSinglePrivilegeCheck
0x180035a30  nop     dword ptr [rax+rax+00h]
0x180035a35  test    al, al
0x180035a37  jnz     short loc_180035A40
0x180035a39  mov     eax, 0C0000061h
0x180035a3e  jmp     short loc_180035AAD
0x180035a40  xor     r8d, r8d; State
0x180035a43  lea     rcx, [rbp+Event+8]; Event
0x180035a47  xor     edx, edx; Type
0x180035a49  call    cs:__imp_KeInitializeEvent
0x180035a50  nop     dword ptr [rax+rax+00h]
0x180035a55  lea     rax, KspRemoveBusEnumInterface
0x180035a5c  mov     qword ptr [rbp+Event], rbx
0x180035a60  mov     [rbp+WorkItem.WorkerRoutine], rax
0x180035a64  lea     rcx, [rbp+WorkItem]; WorkItem
0x180035a68  lea     rax, [rbp+Event]
0x180035a6c  mov     [rbp+WorkItem.List.Flink], 0
0x180035a74  mov     edx, 1; QueueType
0x180035a79  mov     [rbp+WorkItem.Parameter], rax
0x180035a7d  call    cs:__imp_ExQueueWorkItem
0x180035a84  nop     dword ptr [rax+rax+00h]
0x180035a89  xor     r9d, r9d; Alertable
0x180035a8c  mov     [rsp+80h+Timeout], 0; Timeout
0x180035a95  xor     r8d, r8d; WaitMode
0x180035a98  lea     rcx, [rbp+Event+8]; Object
0x180035a9c  xor     edx, edx; WaitReason
0x180035a9e  call    cs:__imp_KeWaitForSingleObject
0x180035aa5  nop     dword ptr [rax+rax+00h]
0x180035aaa  mov     eax, dword ptr [rbp+var_10]
0x180035aad  mov     rbx, [rsp+80h+arg_0]
0x180035ab5  add     rsp, 80h
0x180035abc  pop     rbp
0x180035abd  retn
```
