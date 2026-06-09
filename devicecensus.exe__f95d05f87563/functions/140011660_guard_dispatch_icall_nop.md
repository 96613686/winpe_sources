# _guard_dispatch_icall_nop

- ea: `0x140011660`
- end: `0x140011662`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400018d0`
- `0x140001ea0`
- `0x140011630`
- `0x140011690`

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
0x140011660  jmp     rax
```
