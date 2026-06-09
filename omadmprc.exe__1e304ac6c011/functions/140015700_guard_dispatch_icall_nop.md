# _guard_dispatch_icall_nop

- ea: `0x140015700`
- end: `0x140015702`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140002008`
- `0x1400022e4`
- `0x1400156d0`
- `0x140015730`

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
0x140015700  jmp     rax
```
