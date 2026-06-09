# _guard_dispatch_icall_nop

- ea: `0x140019680`
- end: `0x140019682`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140002440`
- `0x140002640`
- `0x140019650`
- `0x1400196b0`

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
0x140019680  jmp     rax
```
