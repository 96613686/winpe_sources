# _guard_dispatch_icall_nop

- ea: `0x18000c400`
- end: `0x18000c402`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800018e0`
- `0x180001b54`
- `0x180001f8c`
- `0x18000c430`
- `0x18000c4c0`

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
0x18000c400  jmp     rax
```
