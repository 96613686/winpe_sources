# _guard_dispatch_icall_nop

- ea: `0x180006c20`
- end: `0x180006c22`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180006c00`
- `0x180006c40`

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
0x180006c20  jmp     rax
```
