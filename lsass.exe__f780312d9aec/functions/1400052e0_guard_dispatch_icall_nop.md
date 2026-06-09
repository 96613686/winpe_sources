# _guard_dispatch_icall_nop

- ea: `0x1400052e0`
- end: `0x1400052e2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400052c0`
- `0x140005300`

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
0x1400052e0  jmp     rax
```
