# KsInstallBusEnumInterface

- ea: `0x1800358f0`
- end: `0x1800359cf`
- name: `KsInstallBusEnumInterface`
- size: `223`
- prototype: `NTSTATUS __stdcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800358f0`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x180035927`
- `ntoskrnl!ExGetPreviousMode` at `0x180035927`
- `ntoskrnl!ExQueueWorkItem` at `0x18003598d`
- `ntoskrnl!ExQueueWorkItem` at `0x18003598d`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x180035939`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x180035939`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800359ae`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800359ae`
- `ntoskrnl!KeInitializeEvent` at `0x180035959`
- `ntoskrnl!KeInitializeEvent` at `0x180035959`

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
0x1800358f0  mov     [rsp-8+arg_0], rbx
0x1800358f5  push    rbp
0x1800358f6  mov     rbp, rsp
0x1800358f9  sub     rsp, 80h
0x180035900  xorps   xmm0, xmm0
0x180035903  mov     qword ptr [rbp+PrivilegeValue.LowPart], 0Ah
0x18003590b  xorps   xmm1, xmm1
0x18003590e  xor     eax, eax
0x180035910  movups  xmmword ptr [rbp+WorkItem.List.Flink], xmm0
0x180035914  mov     [rbp+var_10], rax
0x180035918  mov     rbx, rcx
0x18003591b  movups  xmmword ptr [rbp+WorkItem.WorkerRoutine], xmm0
0x18003591f  movups  xmmword ptr [rbp+Event], xmm1
0x180035923  movups  xmmword ptr [rbp+Event+10h], xmm1
0x180035927  call    cs:__imp_ExGetPreviousMode
0x18003592e  nop     dword ptr [rax+rax+00h]
0x180035933  mov     rcx, qword ptr [rbp+PrivilegeValue.LowPart]; PrivilegeValue
0x180035937  mov     dl, al; PreviousMode
0x180035939  call    cs:__imp_SeSinglePrivilegeCheck
0x180035940  nop     dword ptr [rax+rax+00h]
0x180035945  test    al, al
0x180035947  jnz     short loc_180035950
0x180035949  mov     eax, 0C0000061h
0x18003594e  jmp     short loc_1800359BD
0x180035950  xor     r8d, r8d; State
0x180035953  lea     rcx, [rbp+Event+8]; Event
0x180035957  xor     edx, edx; Type
0x180035959  call    cs:__imp_KeInitializeEvent
0x180035960  nop     dword ptr [rax+rax+00h]
0x180035965  lea     rax, KspInstallBusEnumInterface
0x18003596c  mov     qword ptr [rbp+Event], rbx
0x180035970  mov     [rbp+WorkItem.WorkerRoutine], rax
0x180035974  lea     rcx, [rbp+WorkItem]; WorkItem
0x180035978  lea     rax, [rbp+Event]
0x18003597c  mov     [rbp+WorkItem.List.Flink], 0
0x180035984  mov     edx, 1; QueueType
0x180035989  mov     [rbp+WorkItem.Parameter], rax
0x18003598d  call    cs:__imp_ExQueueWorkItem
0x180035994  nop     dword ptr [rax+rax+00h]
0x180035999  xor     r9d, r9d; Alertable
0x18003599c  mov     [rsp+80h+Timeout], 0; Timeout
0x1800359a5  xor     r8d, r8d; WaitMode
0x1800359a8  lea     rcx, [rbp+Event+8]; Object
0x1800359ac  xor     edx, edx; WaitReason
0x1800359ae  call    cs:__imp_KeWaitForSingleObject
0x1800359b5  nop     dword ptr [rax+rax+00h]
0x1800359ba  mov     eax, dword ptr [rbp+var_10]
0x1800359bd  mov     rbx, [rsp+80h+arg_0]
0x1800359c5  add     rsp, 80h
0x1800359cc  pop     rbp
0x1800359cd  retn
```
