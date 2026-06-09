# _guard_dispatch_icall_nop

- ea: `0x140006630`
- end: `0x140006632`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001380`
- `0x1400019cc`
- `0x140006660`
- `0x1400066f0`

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
0x140006630  jmp     rax
```
