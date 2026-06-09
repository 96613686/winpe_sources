# DrAddOpenHandle(_FILE_OBJECT *)

- ea: `0x14002be3c`
- end: `0x14002be8f`
- name: `?DrAddOpenHandle@@YAXPEAU_FILE_OBJECT@@@Z`
- size: `83`
- prototype: `void __fastcall(struct _FILE_OBJECT *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140024180`
- `0x140027190`

## callees

- `0x140002284`
- `0x140006560`

## pseudocode

```c
void __fastcall DrAddOpenHandle(struct _FILE_OBJECT *a1)
{
  ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Blink[2].Flink[1].Blink)(&WPP_MAIN_CB.Queue.ListEntry.Blink[2]);
  DoubleList::CreateEntry((DoubleList *)WPP_MAIN_CB.Queue.ListEntry.Blink, a1);
  ++DrReferenceCount;
  ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Blink[2].Flink[2].Flink)(&WPP_MAIN_CB.Queue.ListEntry.Blink[2]);
}

```

## disassembly

```asm
0x14002be3c  push    rbx
0x14002be3e  sub     rsp, 20h
0x14002be42  mov     rbx, rcx
0x14002be45  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14002be4c  add     rcx, 20h ; ' '
0x14002be50  mov     rax, [rcx]
0x14002be53  mov     rax, [rax+18h]
0x14002be57  call    _guard_dispatch_icall
0x14002be5c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8; this
0x14002be63  mov     rdx, rbx; void *
0x14002be66  call    ?CreateEntry@DoubleList@@QEAAHPEAX@Z; DoubleList::CreateEntry(void *)
0x14002be6b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14002be72  inc     cs:?DrReferenceCount@@3HA; int DrReferenceCount
0x14002be78  add     rcx, 20h ; ' '
0x14002be7c  mov     rax, [rcx]
0x14002be7f  mov     rax, [rax+20h]
0x14002be83  call    _guard_dispatch_icall
0x14002be88  add     rsp, 20h
0x14002be8c  pop     rbx
0x14002be8d  retn
```
