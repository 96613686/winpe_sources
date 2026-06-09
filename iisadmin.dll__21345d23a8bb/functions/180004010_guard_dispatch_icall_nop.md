# _guard_dispatch_icall_nop

- ea: `0x180004010`
- end: `0x180004012`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800010a0`
- `0x180001314`
- `0x180004040`
- `0x180004070`

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
0x180004010  jmp     rax
```
