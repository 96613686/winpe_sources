# _guard_dispatch_icall_nop

- ea: `0x140006f50`
- end: `0x140006f52`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001410`
- `0x1400019dc`
- `0x140006f80`
- `0x140007010`

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
0x140006f50  jmp     rax
```
