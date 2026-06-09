# DrRemoveOpenHandle(_FILE_OBJECT *)

- ea: `0x14002ac20`
- end: `0x14002acb2`
- name: `?DrRemoveOpenHandle@@YAXPEAU_FILE_OBJECT@@@Z`
- size: `146`
- prototype: `void __fastcall(struct _FILE_OBJECT *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140024180`
- `0x1400254c0`
- `0x140027190`

## callees

- `0x140001c50`
- `0x140001ef0`
- `0x140002564`
- `0x140006560`
- `0x140017cac`
- `0x14002ac20`

## pseudocode

```c
void __fastcall DrRemoveOpenHandle(struct _FILE_OBJECT *a1)
{
  struct ListEntry *i; // rax
  DoubleList *v3; // rcx
  DoubleList *v4; // r9
  DrSessionManager *v5; // rcx
  struct _LIST_ENTRY *v6; // rcx

  ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Blink[2].Flink[1].Blink)(&WPP_MAIN_CB.Queue.ListEntry.Blink[2]);
  for ( i = DoubleList::First((DoubleList *)WPP_MAIN_CB.Queue.ListEntry.Blink); ; i = DoubleList::Next(v4, i) )
  {
    if ( !i )
    {
      v6 = (struct _LIST_ENTRY *)((char *)v4 + 32);
      goto LABEL_9;
    }
    if ( *((struct _FILE_OBJECT **)i + 2) == a1 )
      break;
  }
  DoubleList::RemoveEntry(v3, (struct ListEntry ***)i);
  if ( !--DrReferenceCount )
  {
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Blink[2].Flink[2].Flink)(&WPP_MAIN_CB.Queue.ListEntry.Blink[2]);
    DrUninitialize(v5);
    return;
  }
  v6 = WPP_MAIN_CB.Queue.ListEntry.Blink + 2;
LABEL_9:
  ((void (__fastcall *)(struct _LIST_ENTRY *))v6->Flink[2].Flink)(v6);
}

```

## disassembly

```asm
0x14002ac20  push    rbx
0x14002ac22  sub     rsp, 20h
0x14002ac26  mov     rbx, rcx
0x14002ac29  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14002ac30  add     rcx, 20h ; ' '
0x14002ac34  mov     rax, [rcx]
0x14002ac37  mov     rax, [rax+18h]
0x14002ac3b  call    _guard_dispatch_icall
0x14002ac40  mov     r9, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14002ac47  mov     rcx, r9; this
0x14002ac4a  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x14002ac4f  nop
0x14002ac50  test    rax, rax
0x14002ac53  jz      short loc_14002AC9B
0x14002ac55  mov     rdx, rax; struct ListEntry *
0x14002ac58  cmp     [rax+10h], rbx
0x14002ac5c  jz      short loc_14002AC68
0x14002ac5e  mov     rcx, r9; this
0x14002ac61  call    ?Next@DoubleList@@QEAAPEAVListEntry@@PEAV2@@Z; DoubleList::Next(ListEntry *)
0x14002ac66  jmp     short loc_14002AC50
0x14002ac68  call    ?RemoveEntry@DoubleList@@QEAAXPEAVListEntry@@@Z; DoubleList::RemoveEntry(ListEntry *)
0x14002ac6d  sub     cs:?DrReferenceCount@@3HA, 1; int DrReferenceCount
0x14002ac74  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14002ac7b  jnz     short loc_14002AC95
0x14002ac7d  mov     rax, [rcx+20h]
0x14002ac81  add     rcx, 20h ; ' '
0x14002ac85  mov     rax, [rax+20h]
0x14002ac89  call    _guard_dispatch_icall
0x14002ac8e  call    DrUninitialize
0x14002ac93  jmp     short loc_14002ACAB
0x14002ac95  add     rcx, 20h ; ' '
0x14002ac99  jmp     short loc_14002AC9F
0x14002ac9b  lea     rcx, [r9+20h]
0x14002ac9f  mov     rax, [rcx]
0x14002aca2  mov     rax, [rax+20h]
0x14002aca6  call    _guard_dispatch_icall
0x14002acab  add     rsp, 20h
0x14002acaf  pop     rbx
0x14002acb0  retn
```
