# NbtFreeIrp

- ea: `0x140006878`
- end: `0x1400068f3`
- name: `NbtFreeIrp`
- size: `123`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x14000178c`
- `0x140004cb0`
- `0x1400067e0`
- `0x140009150`
- `0x14000d070`
- `0x14001962c`
- `0x140021610`
- `0x1400226d0`
- `0x140023800`
- `0x140023e40`
- `0x140024350`
- `0x1400253e0`
- `0x14002efd0`
- `0x14002f230`
- `0x14002fbc0`

## callees

- `0x140006878`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400068d4`
- `ntoskrnl!IoFreeIrp` at `0x1400068d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000688c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000688c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068be`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068be`

## pseudocode

```c
void __fastcall NbtFreeIrp(PIRP Irp)
{
  KIRQL v2; // al
  LIST_ENTRY *p_ThreadListEntry; // rbx
  struct _LIST_ENTRY *Flink; // r8
  struct _LIST_ENTRY *Blink; // rdx

  v2 = KeAcquireSpinLockRaiseToDpc(&Lock);
  p_ThreadListEntry = &Irp->ThreadListEntry;
  Flink = Irp->ThreadListEntry.Flink;
  if ( Flink->Blink != &Irp->ThreadListEntry || (Blink = Irp->ThreadListEntry.Blink, Blink->Flink != p_ThreadListEntry) )
    __fastfail(3u);
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  KeReleaseSpinLock(&Lock, v2);
  Irp->ThreadListEntry.Blink = &Irp->ThreadListEntry;
  p_ThreadListEntry->Flink = p_ThreadListEntry;
  IoFreeIrp(Irp);
}

```

## disassembly

```asm
0x140006878  mov     [rsp+arg_0], rbx
0x14000687d  push    rdi
0x14000687e  sub     rsp, 20h
0x140006882  mov     rdi, rcx
0x140006885  lea     rcx, Lock; SpinLock
0x14000688c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006893  nop     dword ptr [rax+rax+00h]
0x140006898  lea     rbx, [rdi+20h]
0x14000689c  mov     r8, [rbx]
0x14000689f  cmp     [r8+8], rbx
0x1400068a3  jnz     short loc_1400068EC
0x1400068a5  mov     rdx, [rbx+8]
0x1400068a9  cmp     [rdx], rbx
0x1400068ac  jnz     short loc_1400068EC
0x1400068ae  mov     [rdx], r8
0x1400068b1  lea     rcx, Lock; SpinLock
0x1400068b8  mov     [r8+8], rdx
0x1400068bc  mov     dl, al; NewIrql
0x1400068be  call    cs:__imp_KeReleaseSpinLock
0x1400068c5  nop     dword ptr [rax+rax+00h]
0x1400068ca  mov     rcx, rdi; Irp
0x1400068cd  mov     [rbx+8], rbx
0x1400068d1  mov     [rbx], rbx
0x1400068d4  call    cs:__imp_IoFreeIrp
0x1400068db  nop     dword ptr [rax+rax+00h]
0x1400068e0  mov     rbx, [rsp+28h+arg_0]
0x1400068e5  add     rsp, 20h
0x1400068e9  pop     rdi
0x1400068ea  retn
0x1400068ec  mov     ecx, 3
0x1400068f1  int     29h; Win8: RtlFailFast(ecx)
```
