# _guard_dispatch_icall_nop

- ea: `0x180003cb0`
- end: `0x180003cb2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180002970`
- `0x180002be4`
- `0x180003ce0`
- `0x180003d10`

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
0x180003cb0  jmp     rax
```
