# HidpFdoSetIoStateToFailAndFlushSentIo

- ea: `0x18001320c`
- end: `0x1800132b8`
- name: `HidpFdoSetIoStateToFailAndFlushSentIo`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800131f0`

## callees

- `0x180003f40`
- `0x18001320c`
- `0x18001337c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180013279`
- `ntoskrnl!IofCompleteRequest` at `0x180013279`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001325f`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001325f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180013228`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180013228`

## pseudocode

```c
__int64 __fastcall HidpFdoSetIoStateToFailAndFlushSentIo(__int64 a1)
{
  KSPIN_LOCK *v1; // rsi
  KIRQL v3; // al
  bool v4; // zf
  unsigned int v5; // edi
  IRP *v6; // rax

  v1 = (KSPIN_LOCK *)(a1 + 384);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 384));
  v4 = *(_DWORD *)(a1 + 1860) == 0;
  *(_DWORD *)(a1 + 1720) = 0;
  if ( v4 )
  {
    v5 = 2013;
  }
  else
  {
    v5 = 2009;
    *(_BYTE *)(a1 + 1724) = 1;
  }
  KeReleaseSpinLock(v1, v3);
  while ( 1 )
  {
    v6 = (IRP *)DequeuePowerDelayedIrp(a1);
    if ( !v6 )
      break;
    v6->IoStatus.Status = -1073741810;
    IofCompleteRequest(v6, 0);
    HidpFdoReleasePoFxPowerReferenceWithTag(a1, 8);
  }
  return v5;
}

```

## disassembly

```asm
0x18001320c  mov     [rsp+arg_0], rbx
0x180013211  mov     [rsp+arg_8], rsi
0x180013216  push    rdi
0x180013217  sub     rsp, 20h
0x18001321b  lea     rsi, [rcx+180h]
0x180013222  mov     rbx, rcx
0x180013225  mov     rcx, rsi; SpinLock
0x180013228  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18001322f  nop     dword ptr [rax+rax+00h]
0x180013234  cmp     dword ptr [rbx+744h], 0
0x18001323b  mov     dword ptr [rbx+6B8h], 0
0x180013245  jnz     short loc_18001324E
0x180013247  mov     edi, 7DDh
0x18001324c  jmp     short loc_18001325A
0x18001324e  mov     edi, 7D9h
0x180013253  mov     byte ptr [rbx+6BCh], 1
0x18001325a  mov     dl, al; NewIrql
0x18001325c  mov     rcx, rsi; SpinLock
0x18001325f  call    cs:__imp_KeReleaseSpinLock
0x180013266  nop     dword ptr [rax+rax+00h]
0x18001326b  jmp     short loc_180013295
0x18001326d  xor     edx, edx; PriorityBoost
0x18001326f  mov     dword ptr [rsi+30h], 0C000000Eh
0x180013276  mov     rcx, rsi; Irp
0x180013279  call    cs:__imp_IofCompleteRequest
0x180013280  nop     dword ptr [rax+rax+00h]
0x180013285  mov     r8, rsi
0x180013288  mov     edx, 8
0x18001328d  mov     rcx, rbx
0x180013290  call    HidpFdoReleasePoFxPowerReferenceWithTag
0x180013295  mov     rcx, rbx
0x180013298  call    DequeuePowerDelayedIrp
0x18001329d  mov     rsi, rax
0x1800132a0  test    rax, rax
0x1800132a3  jnz     short loc_18001326D
0x1800132a5  mov     rbx, [rsp+28h+arg_0]
0x1800132aa  mov     eax, edi
0x1800132ac  mov     rsi, [rsp+28h+arg_8]
0x1800132b1  add     rsp, 20h
0x1800132b5  pop     rdi
0x1800132b6  retn
```
