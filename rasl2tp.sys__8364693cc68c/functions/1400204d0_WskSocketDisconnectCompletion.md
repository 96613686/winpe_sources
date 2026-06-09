# WskSocketDisconnectCompletion

- ea: `0x1400204d0`
- end: `0x140020523`
- name: `WskSocketDisconnectCompletion`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004830`
- `0x1400204d0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400204dc`
- `ntoskrnl!IoFreeIrp` at `0x1400204dc`

## string_xrefs

- `0x1400204ec`: `WskSocketDisconnectCompletion..Deref for DISC Pending`

## pseudocode

```c
__int64 __fastcall WskSocketDisconnectCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  IoFreeIrp(a2);
  (*(void (__fastcall **)(const char *))(a3 + 48))("WskSocketDisconnectCompletion..Deref for DISC Pending");
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 528), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64))(a3 + 536))(a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400204d0  push    rbx
0x1400204d2  sub     rsp, 20h
0x1400204d6  mov     rcx, rdx; Irp
0x1400204d9  mov     rbx, r8
0x1400204dc  call    cs:__imp_IoFreeIrp
0x1400204e3  nop     dword ptr [rax+rax+00h]
0x1400204e8  mov     rax, [rbx+30h]
0x1400204ec  lea     rcx, aWsksocketdisco; "WskSocketDisconnectCompletion..Deref fo"...
0x1400204f3  call    _guard_dispatch_icall
0x1400204f8  or      eax, 0FFFFFFFFh
0x1400204fb  lock xadd [rbx+210h], eax
0x140020503  cmp     eax, 1
0x140020506  jnz     short loc_140020517
0x140020508  mov     rax, [rbx+218h]
0x14002050f  mov     rcx, rbx
0x140020512  call    _guard_dispatch_icall
0x140020517  mov     eax, 0C0000016h
0x14002051c  add     rsp, 20h
0x140020520  pop     rbx
0x140020521  retn
```
