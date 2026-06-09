# _guard_dispatch_icall_nop

- ea: `0x1800083e0`
- end: `0x1800083e2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001a00`
- `0x180001c74`
- `0x180001ebc`
- `0x1800083b0`
- `0x180008410`

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
0x1800083e0  jmp     rax
```
