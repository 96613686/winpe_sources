# _guard_dispatch_icall_nop

- ea: `0x180007c00`
- end: `0x180007c02`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800058f0`
- `0x180005b64`
- `0x180007c30`
- `0x180007c60`

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
0x180007c00  jmp     rax
```
