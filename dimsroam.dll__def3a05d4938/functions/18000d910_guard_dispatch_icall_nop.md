# _guard_dispatch_icall_nop

- ea: `0x18000d910`
- end: `0x18000d912`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001220`
- `0x180001494`
- `0x1800018a0`
- `0x18000d940`
- `0x18000d9d0`

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
0x18000d910  jmp     rax
```
