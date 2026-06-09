# _guard_dispatch_icall_nop

- ea: `0x180018540`
- end: `0x180018542`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800013e0`
- `0x180001654`
- `0x180001bec`
- `0x180018570`
- `0x180018600`

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
0x180018540  jmp     rax
```
