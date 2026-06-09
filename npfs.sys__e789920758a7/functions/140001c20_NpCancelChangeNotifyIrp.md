# NpCancelChangeNotifyIrp

- ea: `0x140001c20`
- end: `0x140001cd0`
- name: `NpCancelChangeNotifyIrp`
- size: `176`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001c20`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140001c43`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001c43`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140001c58`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140001c58`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140001c8d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140001c8d`
- `ntoskrnl!IofCompleteRequest` at `0x140001cb1`
- `ntoskrnl!IofCompleteRequest` at `0x140001cb1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001c99`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001c99`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001c33`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001c33`

## pseudocode

```c
void __fastcall NpCancelChangeNotifyIrp(__int64 a1, IRP *a2)
{
  __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // r9
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY *Blink; // rax

  IoReleaseCancelSpinLock(a2->CancelIrql);
  v4 = *(_QWORD *)(a1 + 64);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v4 + 168, 0, v5, v6);
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (PVOID *)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  ExReleasePushLockExclusiveEx(v4 + 168, 0);
  KeLeaveCriticalRegion();
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 2);
}

```

## disassembly

```asm
0x140001c20  mov     [rsp+arg_0], rbx
0x140001c25  push    rdi
0x140001c26  sub     rsp, 20h
0x140001c2a  mov     rbx, rcx
0x140001c2d  mov     rdi, rdx
0x140001c30  mov     cl, [rdx+45h]; Irql
0x140001c33  call    cs:__imp_IoReleaseCancelSpinLock
0x140001c3a  nop     dword ptr [rax+rax+00h]
0x140001c3f  mov     rbx, [rbx+40h]
0x140001c43  call    cs:__imp_KeEnterCriticalRegion
0x140001c4a  nop     dword ptr [rax+rax+00h]
0x140001c4f  xor     edx, edx
0x140001c51  lea     rcx, [rbx+0A8h]
0x140001c58  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140001c5f  nop     dword ptr [rax+rax+00h]
0x140001c64  lea     r8, [rdi+0A8h]
0x140001c6b  mov     rdx, [r8]
0x140001c6e  cmp     [rdx+8], r8
0x140001c72  jnz     short loc_140001CC9
0x140001c74  mov     rax, [r8+8]
0x140001c78  cmp     [rax], r8
0x140001c7b  jnz     short loc_140001CC9
0x140001c7d  mov     [rax], rdx
0x140001c80  lea     rcx, [rbx+0A8h]
0x140001c87  mov     [rdx+8], rax
0x140001c8b  xor     edx, edx
0x140001c8d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140001c94  nop     dword ptr [rax+rax+00h]
0x140001c99  call    cs:__imp_KeLeaveCriticalRegion
0x140001ca0  nop     dword ptr [rax+rax+00h]
0x140001ca5  mov     dl, 2; PriorityBoost
0x140001ca7  mov     dword ptr [rdi+30h], 0C0000120h
0x140001cae  mov     rcx, rdi; Irp
0x140001cb1  call    cs:__imp_IofCompleteRequest
0x140001cb8  nop     dword ptr [rax+rax+00h]
0x140001cbd  mov     rbx, [rsp+28h+arg_0]
0x140001cc2  add     rsp, 20h
0x140001cc6  pop     rdi
0x140001cc7  retn
0x140001cc9  mov     ecx, 3
0x140001cce  int     29h; Win8: RtlFailFast(ecx)
```
