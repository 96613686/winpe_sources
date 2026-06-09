# _guard_dispatch_icall_nop

- ea: `0x140009860`
- end: `0x140009862`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140002f58`
- `0x1400034d4`
- `0x140009890`
- `0x140009920`

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
0x140009860  jmp     rax
```
