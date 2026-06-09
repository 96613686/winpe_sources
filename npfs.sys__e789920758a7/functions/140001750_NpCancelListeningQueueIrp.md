# NpCancelListeningQueueIrp

- ea: `0x140001750`
- end: `0x140001806`
- name: `NpCancelListeningQueueIrp`
- size: `182`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001750`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000177b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000177b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140001791`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140001791`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400017c3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400017c3`
- `ntoskrnl!IofCompleteRequest` at `0x1400017e7`
- `ntoskrnl!IofCompleteRequest` at `0x1400017e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400017cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400017cf`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001760`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001760`

## pseudocode

```c
void __fastcall NpCancelListeningQueueIrp(__int64 a1, IRP *a2)
{
  unsigned __int64 FsContext2; // rbx
  unsigned __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // r9
  struct _LIST_ENTRY *Flink; // r8
  struct _LIST_ENTRY *Blink; // rax

  IoReleaseCancelSpinLock(a2->CancelIrql);
  FsContext2 = (unsigned __int64)a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext2;
  KeEnterCriticalRegion();
  v4 = FsContext2 & 0xFFFFFFFFFFFFFFFCuLL;
  ExAcquirePushLockExclusiveEx(v4 + 64, 0, v5, v6);
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (PVOID *)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  ExReleasePushLockExclusiveEx(v4 + 64, 0);
  KeLeaveCriticalRegion();
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 2);
}

```

## disassembly

```asm
0x140001750  mov     [rsp+arg_0], rbx
0x140001755  push    rdi
0x140001756  sub     rsp, 20h
0x14000175a  mov     cl, [rdx+45h]; Irql
0x14000175d  mov     rdi, rdx
0x140001760  call    cs:__imp_IoReleaseCancelSpinLock
0x140001767  nop     dword ptr [rax+rax+00h]
0x14000176c  mov     rax, [rdi+0B8h]
0x140001773  mov     rcx, [rax+30h]
0x140001777  mov     rbx, [rcx+20h]
0x14000177b  call    cs:__imp_KeEnterCriticalRegion
0x140001782  nop     dword ptr [rax+rax+00h]
0x140001787  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000178b  xor     edx, edx
0x14000178d  lea     rcx, [rbx+40h]
0x140001791  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140001798  nop     dword ptr [rax+rax+00h]
0x14000179d  lea     rdx, [rdi+0A8h]
0x1400017a4  mov     r8, [rdx]
0x1400017a7  cmp     [r8+8], rdx
0x1400017ab  jnz     short loc_1400017FF
0x1400017ad  mov     rax, [rdx+8]
0x1400017b1  cmp     [rax], rdx
0x1400017b4  jnz     short loc_1400017FF
0x1400017b6  mov     [rax], r8
0x1400017b9  lea     rcx, [rbx+40h]
0x1400017bd  xor     edx, edx
0x1400017bf  mov     [r8+8], rax
0x1400017c3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400017ca  nop     dword ptr [rax+rax+00h]
0x1400017cf  call    cs:__imp_KeLeaveCriticalRegion
0x1400017d6  nop     dword ptr [rax+rax+00h]
0x1400017db  mov     dl, 2; PriorityBoost
0x1400017dd  mov     dword ptr [rdi+30h], 0C0000120h
0x1400017e4  mov     rcx, rdi; Irp
0x1400017e7  call    cs:__imp_IofCompleteRequest
0x1400017ee  nop     dword ptr [rax+rax+00h]
0x1400017f3  mov     rbx, [rsp+28h+arg_0]
0x1400017f8  add     rsp, 20h
0x1400017fc  pop     rdi
0x1400017fd  retn
0x1400017ff  mov     ecx, 3
0x140001804  int     29h; Win8: RtlFailFast(ecx)
```
