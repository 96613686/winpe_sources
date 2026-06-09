# _guard_dispatch_icall_nop

- ea: `0x180006b40`
- end: `0x180006b42`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180005010`
- `0x180005284`
- `0x180006b70`

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
0x180006b40  jmp     rax
```
