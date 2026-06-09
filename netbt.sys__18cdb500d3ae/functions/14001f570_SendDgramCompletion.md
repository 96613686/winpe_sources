# SendDgramCompletion

- ea: `0x14001f570`
- end: `0x14001f5f8`
- name: `SendDgramCompletion`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006a60`

## callees

- `0x14000699c`
- `0x14001f570`
- `0x14001f600`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f58b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f58b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f5b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f5e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f5b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f5e0`

## pseudocode

```c
void __fastcall SendDgramCompletion(__int64 a1, unsigned int a2)
{
  KIRQL v4; // al
  __int64 v5; // rdx
  __int64 v6; // r8
  KIRQL v7; // di

  v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v7 = v4;
  if ( *(_WORD *)(a1 + 144) )
  {
    KeReleaseSpinLock(&SpinLock, v4);
    SendNextDgramToGroup(a1, a2);
  }
  else
  {
    LOBYTE(v6) = 1;
    DgramSendCleanupTracker(a1, v5, v6);
    KeReleaseSpinLock(&SpinLock, v7);
  }
}

```

## disassembly

```asm
0x14001f570  mov     [rsp+arg_0], rbx
0x14001f575  mov     [rsp+arg_8], rsi
0x14001f57a  push    rdi
0x14001f57b  sub     rsp, 20h
0x14001f57f  mov     rbx, rcx
0x14001f582  mov     esi, edx
0x14001f584  lea     rcx, SpinLock; SpinLock
0x14001f58b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001f592  nop     dword ptr [rax+rax+00h]
0x14001f597  cmp     word ptr [rbx+90h], 0
0x14001f59f  mov     dil, al
0x14001f5a2  jnz     short loc_14001F5D6
0x14001f5a4  mov     r8b, 1
0x14001f5a7  mov     rcx, rbx
0x14001f5aa  call    DgramSendCleanupTracker
0x14001f5af  mov     dl, dil; NewIrql
0x14001f5b2  lea     rcx, SpinLock; SpinLock
0x14001f5b9  call    cs:__imp_KeReleaseSpinLock
0x14001f5c0  nop     dword ptr [rax+rax+00h]
0x14001f5c5  mov     rbx, [rsp+28h+arg_0]
0x14001f5ca  mov     rsi, [rsp+28h+arg_8]
0x14001f5cf  add     rsp, 20h
0x14001f5d3  pop     rdi
0x14001f5d4  retn
0x14001f5d6  mov     dl, dil; NewIrql
0x14001f5d9  lea     rcx, SpinLock; SpinLock
0x14001f5e0  call    cs:__imp_KeReleaseSpinLock
0x14001f5e7  nop     dword ptr [rax+rax+00h]
0x14001f5ec  mov     edx, esi
0x14001f5ee  mov     rcx, rbx
0x14001f5f1  call    SendNextDgramToGroup
0x14001f5f6  jmp     short loc_14001F5C5
```
