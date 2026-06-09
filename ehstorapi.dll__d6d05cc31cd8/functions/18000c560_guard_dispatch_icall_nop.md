# _guard_dispatch_icall_nop

- ea: `0x18000c560`
- end: `0x18000c562`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800012f0`
- `0x180001564`
- `0x180001b84`
- `0x18000c530`
- `0x18000c590`

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
0x18000c560  jmp     rax
```
