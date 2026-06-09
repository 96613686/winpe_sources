# StopTimer

- ea: `0x14001f6dc`
- end: `0x14001f7ca`
- name: `StopTimer`
- size: `238`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x1400010f0`
- `0x1400031bc`
- `0x140004038`
- `0x140007354`
- `0x14000d310`
- `0x140010c90`
- `0x140013d98`
- `0x14001e8f4`
- `0x140021ff8`
- `0x1400232bc`
- `0x140024920`
- `0x140025260`
- `0x14002571c`
- `0x140029108`
- `0x14002919c`
- `0x14002a75c`
- `0x14002cda0`
- `0x14002e1d0`

## callees

- `0x140005fb0`
- `0x14001f6dc`
- `0x140030f80`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14001f718`
- `ntoskrnl!KeCancelTimer` at `0x14001f718`

## pseudocode

```c
__int64 __fastcall StopTimer(struct _KTIMER *Entry, struct _LIST_ENTRY **a2, _QWORD *a3)
{
  char Blink_high; // al
  bool v5; // zf
  struct _LIST_ENTRY *Blink; // rax
  __int64 v8; // rdx
  struct _KDPC *Dpc; // rcx
  struct _LIST_ENTRY *Flink; // rax
  _BYTE *v11; // rdx

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  Blink_high = HIBYTE(Entry->Header.WaitListHead.Blink);
  if ( Blink_high == 1 )
  {
    if ( a2 )
      *a2 = Entry[1].Header.WaitListHead.Flink;
    if ( a3 )
      *a3 = *(_QWORD *)&Entry[1].Header.Lock;
    v5 = (Entry[4].Header.Type & 8) == 0;
    Entry[1].Header.WaitListHead.Flink = 0;
    if ( v5 && !KeCancelTimer(Entry + 3) )
    {
      Blink = Entry->TimerListEntry.Blink;
      if ( Blink )
      {
        v8 = *(_QWORD *)&Entry->Processor;
        Dpc = Entry->Dpc;
        Entry->TimerListEntry.Blink = 0;
        ((void (__fastcall *)(struct _KDPC *, __int64, _QWORD))Blink)(Dpc, v8, 0);
      }
      HIBYTE(Entry->Header.WaitListHead.Blink) = 2;
      return 0;
    }
    else
    {
      return CleanupCTETimer(Entry);
    }
  }
  else
  {
    if ( Blink_high == 2 )
    {
      Flink = Entry[1].Header.WaitListHead.Flink;
      if ( Flink )
      {
        if ( a2 )
          *a2 = Flink;
        v11 = (char *)&Entry->Header.WaitListHead.Blink + 7;
        if ( a3 )
          *a3 = *(_QWORD *)&Entry[1].Header.Lock;
        Entry[1].Header.WaitListHead.Flink = 0;
      }
      else
      {
        v11 = (char *)&Entry->Header.WaitListHead.Blink + 7;
      }
      HIBYTE(Entry->Header.WaitListHead.Blink) = *v11 + 1;
    }
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x14001f6dc  push    rbx
0x14001f6de  sub     rsp, 20h
0x14001f6e2  mov     rbx, rcx
0x14001f6e5  test    rdx, rdx
0x14001f6e8  jnz     short loc_14001F742
0x14001f6ea  test    r8, r8
0x14001f6ed  jnz     short loc_14001F74B
0x14001f6ef  mov     al, [rcx+17h]
0x14001f6f2  cmp     al, 1
0x14001f6f4  jnz     short loc_14001F737
0x14001f6f6  test    rdx, rdx
0x14001f6f9  jnz     short loc_14001F754
0x14001f6fb  test    r8, r8
0x14001f6fe  jnz     short loc_14001F75D
0x14001f700  test    byte ptr [rcx+100h], 8
0x14001f707  mov     qword ptr [rcx+48h], 0
0x14001f70f  jnz     short loc_14001F728
0x14001f711  add     rcx, 0C0h; PKTIMER
0x14001f718  call    cs:__imp_KeCancelTimer
0x14001f71f  nop     dword ptr [rax+rax+00h]
0x14001f724  test    al, al
0x14001f726  jz      short loc_14001F766
0x14001f728  mov     rcx, rbx; Entry
0x14001f72b  call    CleanupCTETimer
0x14001f730  add     rsp, 20h
0x14001f734  pop     rbx
0x14001f735  retn
0x14001f737  cmp     al, 2
0x14001f739  jz      short loc_14001F78F
0x14001f73b  mov     eax, 0C0000001h
0x14001f740  jmp     short loc_14001F730
0x14001f742  mov     qword ptr [rdx], 0
0x14001f749  jmp     short loc_14001F6EA
0x14001f74b  mov     qword ptr [r8], 0
0x14001f752  jmp     short loc_14001F6EF
0x14001f754  mov     rax, [rcx+48h]
0x14001f758  mov     [rdx], rax
0x14001f75b  jmp     short loc_14001F6FB
0x14001f75d  mov     rax, [rcx+40h]
0x14001f761  mov     [r8], rax
0x14001f764  jmp     short loc_14001F700
0x14001f766  mov     rax, [rbx+28h]
0x14001f76a  test    rax, rax
0x14001f76d  jz      short loc_14001F787
0x14001f76f  mov     rdx, [rbx+38h]
0x14001f773  xor     r8d, r8d
0x14001f776  mov     rcx, [rbx+30h]
0x14001f77a  mov     qword ptr [rbx+28h], 0
0x14001f782  call    _guard_dispatch_icall
0x14001f787  mov     byte ptr [rbx+17h], 2
0x14001f78b  xor     eax, eax
0x14001f78d  jmp     short loc_14001F730
0x14001f78f  mov     rax, [rcx+48h]
0x14001f793  test    rax, rax
0x14001f796  jz      short loc_14001F7BA
0x14001f798  test    rdx, rdx
0x14001f79b  jz      short loc_14001F7A0
0x14001f79d  mov     [rdx], rax
0x14001f7a0  lea     rdx, [rcx+17h]
0x14001f7a4  test    r8, r8
0x14001f7a7  jz      short loc_14001F7B0
0x14001f7a9  mov     rax, [rcx+40h]
0x14001f7ad  mov     [r8], rax
0x14001f7b0  mov     qword ptr [rcx+48h], 0
0x14001f7b8  jmp     short loc_14001F7BE
0x14001f7ba  lea     rdx, [rcx+17h]
0x14001f7be  mov     al, [rdx]
0x14001f7c0  inc     al
0x14001f7c2  mov     [rcx+17h], al
0x14001f7c5  jmp     loc_14001F73B
```
