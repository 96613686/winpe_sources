# WskSocketDisconnectCompletion

- ea: `0x14001dda0`
- end: `0x14001ddf3`
- name: `WskSocketDisconnectCompletion`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007710`
- `0x14001dda0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001ddac`
- `ntoskrnl!IoFreeIrp` at `0x14001ddac`

## string_xrefs

- `0x14001ddbc`: `WskSocketDisconnectCompletion..Deref for DISC Pending`

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
0x14001dda0  push    rbx
0x14001dda2  sub     rsp, 20h
0x14001dda6  mov     rcx, rdx; Irp
0x14001dda9  mov     rbx, r8
0x14001ddac  call    cs:__imp_IoFreeIrp
0x14001ddb3  nop     dword ptr [rax+rax+00h]
0x14001ddb8  mov     rax, [rbx+30h]
0x14001ddbc  lea     rcx, aWsksocketdisco; "WskSocketDisconnectCompletion..Deref fo"...
0x14001ddc3  call    _guard_dispatch_icall
0x14001ddc8  or      eax, 0FFFFFFFFh
0x14001ddcb  lock xadd [rbx+210h], eax
0x14001ddd3  cmp     eax, 1
0x14001ddd6  jnz     short loc_14001DDE7
0x14001ddd8  mov     rax, [rbx+218h]
0x14001dddf  mov     rcx, rbx
0x14001dde2  call    _guard_dispatch_icall
0x14001dde7  mov     eax, 0C0000016h
0x14001ddec  add     rsp, 20h
0x14001ddf0  pop     rbx
0x14001ddf1  retn
```
