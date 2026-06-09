# _guard_dispatch_icall_nop

- ea: `0x180012500`
- end: `0x180012502`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800010b0`
- `0x180001324`
- `0x180012530`
- `0x180012560`

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
0x180012500  jmp     rax
```
