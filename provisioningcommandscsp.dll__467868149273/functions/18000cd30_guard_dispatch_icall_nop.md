# _guard_dispatch_icall_nop

- ea: `0x18000cd30`
- end: `0x18000cd32`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001730`
- `0x1800019a4`
- `0x180001c90`
- `0x18000cd00`
- `0x18000cd60`

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
0x18000cd30  jmp     rax
```
