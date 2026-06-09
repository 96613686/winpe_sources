# MountMgrShutdown

- ea: `0x14000d000`
- end: `0x14000d0b5`
- name: `MountMgrShutdown`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000d000`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14000d04e`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000d04e`
- `ntoskrnl!KeInitializeEvent` at `0x14000d028`
- `ntoskrnl!KeInitializeEvent` at `0x14000d028`
- `ntoskrnl!IofCompleteRequest` at `0x14000d09b`
- `ntoskrnl!IofCompleteRequest` at `0x14000d09b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d072`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d072`

## pseudocode

```c
__int64 __fastcall MountMgrShutdown(__int64 a1, IRP *a2)
{
  __int64 v2; // rbx
  int v4; // et0
  char v5; // of

  v2 = *(_QWORD *)(a1 + 64);
  _InterlockedExchange(&gUnloading, 1);
  KeInitializeEvent(&gUnloadEvent, NotificationEvent, 0);
  v4 = _InterlockedAdd((volatile signed __int32 *)(v2 + 248), 1u);
  if ( (v4 < 0) ^ v5 | (v4 == 0) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v2 + 248));
  }
  else
  {
    KeReleaseSemaphore((PRKSEMAPHORE)(v2 + 216), 0, 1, 0);
    KeWaitForSingleObject(&gUnloadEvent, Executive, 0, 0, 0);
  }
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000d000  mov     [rsp+arg_0], rbx
0x14000d005  push    rdi
0x14000d006  sub     rsp, 30h
0x14000d00a  mov     rbx, [rcx+40h]
0x14000d00e  mov     eax, 1
0x14000d013  xchg    eax, cs:gUnloading
0x14000d019  mov     rdi, rdx
0x14000d01c  lea     rcx, gUnloadEvent; Event
0x14000d023  xor     r8d, r8d; State
0x14000d026  xor     edx, edx; Type
0x14000d028  call    cs:__imp_KeInitializeEvent
0x14000d02f  nop     dword ptr [rax+rax+00h]
0x14000d034  lock add dword ptr [rbx+0F8h], 1
0x14000d03c  jle     short loc_14000D080
0x14000d03e  xor     r9d, r9d; Wait
0x14000d041  lea     rcx, [rbx+0D8h]; Semaphore
0x14000d048  xor     edx, edx; Increment
0x14000d04a  lea     r8d, [r9+1]; Adjustment
0x14000d04e  call    cs:__imp_KeReleaseSemaphore
0x14000d055  nop     dword ptr [rax+rax+00h]
0x14000d05a  xor     r9d, r9d; Alertable
0x14000d05d  mov     [rsp+38h+Timeout], 0; Timeout
0x14000d066  xor     r8d, r8d; WaitMode
0x14000d069  lea     rcx, gUnloadEvent; Object
0x14000d070  xor     edx, edx; WaitReason
0x14000d072  call    cs:__imp_KeWaitForSingleObject
0x14000d079  nop     dword ptr [rax+rax+00h]
0x14000d07e  jmp     short loc_14000D087
0x14000d080  lock dec dword ptr [rbx+0F8h]
0x14000d087  xor     edx, edx; PriorityBoost
0x14000d089  mov     dword ptr [rdi+30h], 0
0x14000d090  mov     rcx, rdi; Irp
0x14000d093  mov     qword ptr [rdi+38h], 0
0x14000d09b  call    cs:__imp_IofCompleteRequest
0x14000d0a2  nop     dword ptr [rax+rax+00h]
0x14000d0a7  mov     rbx, [rsp+38h+arg_0]
0x14000d0ac  xor     eax, eax
0x14000d0ae  add     rsp, 30h
0x14000d0b2  pop     rdi
0x14000d0b3  retn
```
