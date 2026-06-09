# _guard_dispatch_icall_nop

- ea: `0x18000fb90`
- end: `0x18000fb92`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001110`
- `0x180001384`
- `0x180001598`
- `0x18000fbc0`
- `0x18000fc50`

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
0x18000fb90  jmp     rax
```
