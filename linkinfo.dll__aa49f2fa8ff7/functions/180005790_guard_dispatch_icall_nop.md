# _guard_dispatch_icall_nop

- ea: `0x180005790`
- end: `0x180005792`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180003760`
- `0x1800039d4`
- `0x1800057c0`

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
0x180005790  jmp     rax
```
