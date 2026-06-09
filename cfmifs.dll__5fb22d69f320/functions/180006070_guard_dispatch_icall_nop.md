# _guard_dispatch_icall_nop

- ea: `0x180006070`
- end: `0x180006072`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001150`
- `0x1800013c4`
- `0x18000195c`
- `0x1800060a0`
- `0x180006130`

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
0x180006070  jmp     rax
```
