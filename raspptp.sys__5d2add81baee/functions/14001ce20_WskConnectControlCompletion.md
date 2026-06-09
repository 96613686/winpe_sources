# WskConnectControlCompletion

- ea: `0x14001ce20`
- end: `0x14001cebb`
- name: `WskConnectControlCompletion`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007710`
- `0x14001ce20`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001cea0`
- `ntoskrnl!IoFreeIrp` at `0x14001cea0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ce5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ce5a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ce3c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ce3c`

## pseudocode

```c
__int64 __fastcall WskConnectControlCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  unsigned int Status; // ebp
  KSPIN_LOCK *v4; // rbx
  KIRQL v7; // al
  void (__fastcall *v8)(_QWORD, __int64, _QWORD); // rax

  Status = a2->IoStatus.Status;
  v4 = (KSPIN_LOCK *)(a3 + 456);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 456));
  *(_DWORD *)(a3 + 392) |= 0x20u;
  *(_BYTE *)(a3 + 464) = v7;
  KeReleaseSpinLock(v4, v7);
  v8 = *(void (__fastcall **)(_QWORD, __int64, _QWORD))(a3 + 40);
  if ( v8 )
    v8(*(_QWORD *)(a3 + 8), a3, Status);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 512), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64))(a3 + 520))(a3);
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001ce20  push    rbx
0x14001ce22  push    rbp
0x14001ce23  push    rsi
0x14001ce24  push    rdi
0x14001ce25  sub     rsp, 28h
0x14001ce29  mov     ebp, [rdx+30h]
0x14001ce2c  lea     rbx, [r8+1C8h]
0x14001ce33  mov     rcx, rbx; SpinLock
0x14001ce36  mov     rdi, r8
0x14001ce39  mov     rsi, rdx
0x14001ce3c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ce43  nop     dword ptr [rax+rax+00h]
0x14001ce48  or      dword ptr [rdi+188h], 20h
0x14001ce4f  mov     rcx, rbx; SpinLock
0x14001ce52  mov     dl, al; NewIrql
0x14001ce54  mov     [rdi+1D0h], al
0x14001ce5a  call    cs:__imp_KeReleaseSpinLock
0x14001ce61  nop     dword ptr [rax+rax+00h]
0x14001ce66  mov     rax, [rdi+28h]
0x14001ce6a  test    rax, rax
0x14001ce6d  jz      short loc_14001CE7E
0x14001ce6f  mov     rcx, [rdi+8]
0x14001ce73  mov     r8d, ebp
0x14001ce76  mov     rdx, rdi
0x14001ce79  call    _guard_dispatch_icall
0x14001ce7e  or      eax, 0FFFFFFFFh
0x14001ce81  lock xadd [rdi+200h], eax
0x14001ce89  cmp     eax, 1
0x14001ce8c  jnz     short loc_14001CE9D
0x14001ce8e  mov     rax, [rdi+208h]
0x14001ce95  mov     rcx, rdi
0x14001ce98  call    _guard_dispatch_icall
0x14001ce9d  mov     rcx, rsi; Irp
0x14001cea0  call    cs:__imp_IoFreeIrp
0x14001cea7  nop     dword ptr [rax+rax+00h]
0x14001ceac  mov     eax, 0C0000016h
0x14001ceb1  add     rsp, 28h
0x14001ceb5  pop     rdi
0x14001ceb6  pop     rsi
0x14001ceb7  pop     rbp
0x14001ceb8  pop     rbx
0x14001ceb9  retn
```
