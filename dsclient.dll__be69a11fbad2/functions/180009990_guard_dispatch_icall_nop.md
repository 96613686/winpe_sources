# _guard_dispatch_icall_nop

- ea: `0x180009990`
- end: `0x180009992`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800027d0`
- `0x180002a44`
- `0x180002e4c`
- `0x1800099c0`
- `0x180009a50`

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
0x180009990  jmp     rax
```
