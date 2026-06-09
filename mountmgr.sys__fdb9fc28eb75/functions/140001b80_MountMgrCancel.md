# MountMgrCancel

- ea: `0x140001b80`
- end: `0x140001be6`
- name: `MountMgrCancel`
- size: `102`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001010`

## callees

- `0x140001b80`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001bcc`
- `ntoskrnl!IofCompleteRequest` at `0x140001bcc`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001bac`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001bac`

## pseudocode

```c
void __fastcall MountMgrCancel(__int64 a1, IRP *a2)
{
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rax
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY *Blink; // rcx

  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Flink->Blink != p_ListEntry
    || (Blink = p_ListEntry->ListEntry.Blink,
        (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink != p_ListEntry) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  a2->IoStatus.Status = -1073741536;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x140001b80  push    rbx
0x140001b82  sub     rsp, 20h
0x140001b86  lea     rax, [rdx+0A8h]
0x140001b8d  mov     rbx, rdx
0x140001b90  mov     rdx, [rax]
0x140001b93  cmp     [rdx+8], rax
0x140001b97  jnz     short loc_140001BDF
0x140001b99  mov     rcx, [rax+8]
0x140001b9d  cmp     [rcx], rax
0x140001ba0  jnz     short loc_140001BDF
0x140001ba2  mov     [rcx], rdx
0x140001ba5  mov     [rdx+8], rcx
0x140001ba9  mov     cl, [rbx+45h]; Irql
0x140001bac  call    cs:__imp_IoReleaseCancelSpinLock
0x140001bb3  nop     dword ptr [rax+rax+00h]
0x140001bb8  xor     edx, edx; PriorityBoost
0x140001bba  mov     dword ptr [rbx+30h], 0C0000120h
0x140001bc1  mov     rcx, rbx; Irp
0x140001bc4  mov     qword ptr [rbx+38h], 0
0x140001bcc  call    cs:__imp_IofCompleteRequest
0x140001bd3  nop     dword ptr [rax+rax+00h]
0x140001bd8  add     rsp, 20h
0x140001bdc  pop     rbx
0x140001bdd  retn
0x140001bdf  mov     ecx, 3
0x140001be4  int     29h; Win8: RtlFailFast(ecx)
```
