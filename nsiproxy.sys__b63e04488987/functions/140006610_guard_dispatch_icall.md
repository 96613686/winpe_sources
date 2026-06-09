# _guard_dispatch_icall

- ea: `0x140006610`
- end: `0x140006616`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140007050`
- `0x14000d010`
- `0x14000dca4`

## callees

- `0x1400065b0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x140006610  jmp     cs:__guard_dispatch_icall_fptr
```
