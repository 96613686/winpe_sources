# _guard_xfg_dispatch_icall_nop

- ea: `0x180003190`
- end: `0x180003196`
- name: `_guard_xfg_dispatch_icall_nop`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180003160`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_xfg_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x180003190  jmp     cs:__guard_dispatch_icall_fptr
```
