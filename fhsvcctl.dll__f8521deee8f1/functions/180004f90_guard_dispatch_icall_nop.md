# _guard_dispatch_icall_nop

- ea: `0x180004f90`
- end: `0x180004f92`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001640`
- `0x1800018b4`
- `0x180004f60`
- `0x180004fc0`

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
0x180004f90  jmp     rax
```
