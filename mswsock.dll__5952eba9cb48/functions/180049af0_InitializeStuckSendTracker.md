# InitializeStuckSendTracker

- ea: `0x180049af0`
- end: `0x180049b26`
- name: `InitializeStuckSendTracker`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003b760`
- `0x18003ff84`
- `0x18004b1d0`

## callees

- `0x180023b04`
- `0x180049af0`

## import_xrefs

- `ntdll!NtAlertThread` at `0x180049b0d`
- `ntdll!NtAlertThread` at `0x180049b0d`

## pseudocode

```c
__int64 __fastcall InitializeStuckSendTracker(__int64 a1)
{
  if ( _InterlockedExchange(&CheckForStuckLargeSendsThreadIdleCount, 0) >= 10 )
    NtAlertThread(ConnectThreadHandle);
  return AllocateStuckSendTracker(a1);
}

```

## disassembly

```asm
0x180049af0  push    rbx
0x180049af2  sub     rsp, 20h
0x180049af6  xor     eax, eax
0x180049af8  mov     rbx, rcx
0x180049afb  xchg    eax, cs:CheckForStuckLargeSendsThreadIdleCount
0x180049b01  cmp     eax, 0Ah
0x180049b04  jl      short loc_180049B19
0x180049b06  mov     rcx, cs:ConnectThreadHandle; ThreadHandle
0x180049b0d  call    cs:__imp_NtAlertThread
0x180049b14  nop     dword ptr [rax+rax+00h]
0x180049b19  mov     rcx, rbx
0x180049b1c  add     rsp, 20h
0x180049b20  pop     rbx
0x180049b21  jmp     AllocateStuckSendTracker
```
