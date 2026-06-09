# _guard_dispatch_icall_nop

- ea: `0x14000a3b0`
- end: `0x14000a3b2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400019d0`
- `0x140001ba8`
- `0x14000a3e0`
- `0x14000a410`

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
0x14000a3b0  jmp     rax
```
