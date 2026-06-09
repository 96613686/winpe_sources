# _guard_dispatch_icall_nop

- ea: `0x180027410`
- end: `0x180027412`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180015670`
- `0x1800158e4`
- `0x180027440`
- `0x180027470`

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
0x180027410  jmp     rax
```
