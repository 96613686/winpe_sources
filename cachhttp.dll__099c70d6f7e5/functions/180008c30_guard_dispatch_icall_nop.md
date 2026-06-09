# _guard_dispatch_icall_nop

- ea: `0x180008c30`
- end: `0x180008c32`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180005aa0`
- `0x180005d14`
- `0x180008c60`
- `0x180008c90`

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
0x180008c30  jmp     rax
```
