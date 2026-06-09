# _guard_dispatch_icall_nop

- ea: `0x18000a1e0`
- end: `0x18000a1e2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800010a0`
- `0x180001314`
- `0x18000a210`
- `0x18000a2a0`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x18000a1e0  jmp     rax
```
