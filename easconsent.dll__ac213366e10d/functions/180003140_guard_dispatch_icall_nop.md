# _guard_dispatch_icall_nop

- ea: `0x180003140`
- end: `0x180003142`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800010c0`
- `0x180001334`
- `0x18000157c`
- `0x180003170`
- `0x1800031a0`

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
0x180003140  jmp     rax
```
