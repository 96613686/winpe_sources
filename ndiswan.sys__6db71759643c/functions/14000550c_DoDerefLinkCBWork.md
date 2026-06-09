# DoDerefLinkCBWork

- ea: `0x14000550c`
- end: `0x140005560`
- name: `DoDerefLinkCBWork`
- size: `84`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `33`
- callee_count: `3`
- tags: ``

## callers

- `0x140002e40`
- `0x140003620`
- `0x140004be0`
- `0x140007560`
- `0x140007710`
- `0x140007a00`
- `0x140007bf0`
- `0x140007dd0`
- `0x140007fb0`
- `0x140008c80`
- `0x140011320`
- `0x140011540`
- `0x140024008`
- `0x140025070`
- `0x1400267f4`
- `0x140026970`
- `0x1400274e0`
- `0x140027da0`
- `0x140027fe0`
- `0x1400288a0`
- `0x140028f60`
- `0x1400296d0`
- `0x140029850`
- `0x14002aa40`
- `0x14002b270`
- `0x14002bab0`
- `0x14002bd20`
- `0x14002dd7c`
- `0x14002e540`
- `0x14002fe1c`
- `0x1400312a0`
- `0x1400318c0`
- `0x140031b80`

## callees

- `0x140005880`
- `0x140005930`
- `0x1400059d4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000552a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000552a`

## pseudocode

```c
void __fastcall DoDerefLinkCBWork(_QWORD *Entry)
{
  void *v1; // rbx

  v1 = (void *)Entry[10];
  KeReleaseSpinLock(Entry + 92, *((_BYTE *)Entry + 744));
  RemoveLinkFromBundle(v1);
  RemoveLinkFromConnectionTable((__int64)Entry);
  NdisWanFreeLinkCB(Entry);
}

```

## disassembly

```asm
0x14000550c  mov     [rsp+arg_0], rbx
0x140005511  push    rdi
0x140005512  sub     rsp, 20h
0x140005516  mov     rbx, [rcx+50h]
0x14000551a  mov     rdi, rcx
0x14000551d  add     rcx, 2E0h; SpinLock
0x140005524  mov     dl, [rdi+2E8h]; NewIrql
0x14000552a  call    cs:__imp_KeReleaseSpinLock
0x140005531  nop     dword ptr [rax+rax+00h]
0x140005536  xor     r8d, r8d
0x140005539  mov     rdx, rdi
0x14000553c  mov     rcx, rbx; Entry
0x14000553f  call    RemoveLinkFromBundle
0x140005544  mov     rcx, rdi
0x140005547  call    RemoveLinkFromConnectionTable
0x14000554c  mov     rcx, rdi; Entry
0x14000554f  call    NdisWanFreeLinkCB
0x140005554  mov     rbx, [rsp+28h+arg_0]
0x140005559  add     rsp, 20h
0x14000555d  pop     rdi
0x14000555e  retn
```
