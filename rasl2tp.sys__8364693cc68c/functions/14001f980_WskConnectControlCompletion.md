# WskConnectControlCompletion

- ea: `0x14001f980`
- end: `0x14001fa1b`
- name: `WskConnectControlCompletion`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004830`
- `0x14001f980`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001f9ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f9ba`
- `ntoskrnl!IoFreeIrp` at `0x14001fa00`
- `ntoskrnl!IoFreeIrp` at `0x14001fa00`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f99c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f99c`

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
0x14001f980  push    rbx
0x14001f982  push    rbp
0x14001f983  push    rsi
0x14001f984  push    rdi
0x14001f985  sub     rsp, 28h
0x14001f989  mov     ebp, [rdx+30h]
0x14001f98c  lea     rbx, [r8+1C8h]
0x14001f993  mov     rcx, rbx; SpinLock
0x14001f996  mov     rdi, r8
0x14001f999  mov     rsi, rdx
0x14001f99c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001f9a3  nop     dword ptr [rax+rax+00h]
0x14001f9a8  or      dword ptr [rdi+188h], 20h
0x14001f9af  mov     rcx, rbx; SpinLock
0x14001f9b2  mov     dl, al; NewIrql
0x14001f9b4  mov     [rdi+1D0h], al
0x14001f9ba  call    cs:__imp_KeReleaseSpinLock
0x14001f9c1  nop     dword ptr [rax+rax+00h]
0x14001f9c6  mov     rax, [rdi+28h]
0x14001f9ca  test    rax, rax
0x14001f9cd  jz      short loc_14001F9DE
0x14001f9cf  mov     rcx, [rdi+8]
0x14001f9d3  mov     r8d, ebp
0x14001f9d6  mov     rdx, rdi
0x14001f9d9  call    _guard_dispatch_icall
0x14001f9de  or      eax, 0FFFFFFFFh
0x14001f9e1  lock xadd [rdi+200h], eax
0x14001f9e9  cmp     eax, 1
0x14001f9ec  jnz     short loc_14001F9FD
0x14001f9ee  mov     rax, [rdi+208h]
0x14001f9f5  mov     rcx, rdi
0x14001f9f8  call    _guard_dispatch_icall
0x14001f9fd  mov     rcx, rsi; Irp
0x14001fa00  call    cs:__imp_IoFreeIrp
0x14001fa07  nop     dword ptr [rax+rax+00h]
0x14001fa0c  mov     eax, 0C0000016h
0x14001fa11  add     rsp, 28h
0x14001fa15  pop     rdi
0x14001fa16  pop     rsi
0x14001fa17  pop     rbp
0x14001fa18  pop     rbx
0x14001fa19  retn
```
