# _guard_dispatch_icall_nop

- ea: `0x18000df80`
- end: `0x18000df82`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001b80`
- `0x180001df4`
- `0x1800024c4`
- `0x18000df50`
- `0x18000dfb0`

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
0x18000df80  jmp     rax
```
