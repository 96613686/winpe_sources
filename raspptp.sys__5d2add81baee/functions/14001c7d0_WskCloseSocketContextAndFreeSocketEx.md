# WskCloseSocketContextAndFreeSocketEx

- ea: `0x14001c7d0`
- end: `0x14001c849`
- name: `WskCloseSocketContextAndFreeSocketEx`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400047b0`
- `0x14001c4f0`
- `0x14001c7b4`
- `0x14001cd00`

## callees

- `0x140007710`
- `0x14001c65c`
- `0x14001c7d0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001c812`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c812`

## pseudocode

```c
__int64 __fastcall WskCloseSocketContextAndFreeSocketEx(__int64 a1, char a2, __int64 a3)
{
  unsigned int v6; // ebp

  (*(void (__fastcall **)(const char *))(a1 + 48))("WskCloseSocketContextAndFreeSocketEx..Enter");
  v6 = WskCloseSocketContext(a1);
  if ( a2 )
    *(_QWORD *)(a1 + 8) = 0;
  if ( a3 )
    KeReleaseSpinLock((PKSPIN_LOCK)a3, *(_BYTE *)(a3 + 8));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 512), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64))(a1 + 520))(a1);
  return v6;
}

```

## disassembly

```asm
0x14001c7d0  push    rbx
0x14001c7d2  push    rbp
0x14001c7d3  push    rsi
0x14001c7d4  push    rdi
0x14001c7d5  sub     rsp, 28h
0x14001c7d9  mov     rax, [rcx+30h]
0x14001c7dd  mov     rdi, rcx
0x14001c7e0  lea     rcx, aWskclosesocket; "WskCloseSocketContextAndFreeSocketEx..E"...
0x14001c7e7  mov     rsi, r8
0x14001c7ea  mov     bl, dl
0x14001c7ec  call    _guard_dispatch_icall
0x14001c7f1  mov     rcx, rdi
0x14001c7f4  call    WskCloseSocketContext
0x14001c7f9  mov     ebp, eax
0x14001c7fb  test    bl, bl
0x14001c7fd  jz      short loc_14001C807
0x14001c7ff  mov     qword ptr [rdi+8], 0
0x14001c807  test    rsi, rsi
0x14001c80a  jz      short loc_14001C81E
0x14001c80c  mov     dl, [rsi+8]; NewIrql
0x14001c80f  mov     rcx, rsi; SpinLock
0x14001c812  call    cs:__imp_KeReleaseSpinLock
0x14001c819  nop     dword ptr [rax+rax+00h]
0x14001c81e  or      eax, 0FFFFFFFFh
0x14001c821  lock xadd [rdi+200h], eax
0x14001c829  cmp     eax, 1
0x14001c82c  jnz     short loc_14001C83D
0x14001c82e  mov     rax, [rdi+208h]
0x14001c835  mov     rcx, rdi
0x14001c838  call    _guard_dispatch_icall
0x14001c83d  mov     eax, ebp
0x14001c83f  add     rsp, 28h
0x14001c843  pop     rdi
0x14001c844  pop     rsi
0x14001c845  pop     rbp
0x14001c846  pop     rbx
0x14001c847  retn
```
