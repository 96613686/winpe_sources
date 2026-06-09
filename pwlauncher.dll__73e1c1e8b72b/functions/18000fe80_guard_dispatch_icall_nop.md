# _guard_dispatch_icall_nop

- ea: `0x18000fe80`
- end: `0x18000fe82`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800017c0`
- `0x180001a34`
- `0x180001fec`
- `0x18000fe50`
- `0x18000feb0`

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
0x18000fe80  jmp     rax
```
