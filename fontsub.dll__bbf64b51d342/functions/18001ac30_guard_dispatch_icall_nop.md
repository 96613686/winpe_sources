# _guard_dispatch_icall_nop

- ea: `0x18001ac30`
- end: `0x18001ac32`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800020f0`
- `0x180002364`
- `0x180002784`
- `0x18001ac60`
- `0x18001ad30`

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
0x18001ac30  jmp     rax
```
