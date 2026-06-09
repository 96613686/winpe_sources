# _guard_dispatch_icall_nop

- ea: `0x18000abd0`
- end: `0x18000abd2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001350`
- `0x1800015c4`
- `0x180001818`
- `0x18000aba0`
- `0x18000ac00`

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
0x18000abd0  jmp     rax
```
