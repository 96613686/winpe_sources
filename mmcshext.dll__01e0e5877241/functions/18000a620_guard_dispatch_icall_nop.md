# _guard_dispatch_icall_nop

- ea: `0x18000a620`
- end: `0x18000a622`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001410`
- `0x180001684`
- `0x180001908`
- `0x18000a5f0`
- `0x18000a650`

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
0x18000a620  jmp     rax
```
