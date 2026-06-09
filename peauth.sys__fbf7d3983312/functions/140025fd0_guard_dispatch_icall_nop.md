# _guard_dispatch_icall_nop

- ea: `0x140025fd0`
- end: `0x140025fd2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `26`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001010`
- `0x1400019e0`
- `0x140001a18`
- `0x140001d30`
- `0x140002058`
- `0x14000236c`
- `0x140002690`
- `0x1400029a8`
- `0x140002ccc`
- `0x140002fe0`
- `0x1400032fc`
- `0x140003620`
- `0x1400054f0`
- `0x1400055f0`
- `0x140005664`
- `0x14000704c`
- `0x14000a2bc`
- `0x14000a46c`
- `0x14000a5e8`
- `0x14000a748`
- `0x140026000`
- `0x140044008`
- `0x140044d30`
- `0x1400a7658`
- `0x1400c9008`
- `0x1400c96b0`

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
0x140025fd0  jmp     rax
```
