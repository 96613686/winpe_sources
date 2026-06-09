# _guard_dispatch_icall_nop

- ea: `0x180013480`
- end: `0x180013482`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800016d0`
- `0x180001944`
- `0x180001b88`
- `0x180013450`
- `0x1800134b0`

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
0x180013480  jmp     rax
```
