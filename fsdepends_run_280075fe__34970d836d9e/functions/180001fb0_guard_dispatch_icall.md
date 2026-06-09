# _guard_dispatch_icall

- ea: `0x180001fb0`
- end: `0x180001fb6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001020`
- `0x180001064`
- `0x1800010b8`
- `0x1800010fc`
- `0x180001150`
- `0x180001430`
- `0x180001460`
- `0x180001544`
- `0x1800015a8`
- `0x180001a08`
- `0x180001ad0`
- `0x180001b30`
- `0x180001ba4`
- `0x180001c34`
- `0x180001d10`
- `0x180001d68`
- `0x180003010`
- `0x18000a120`
- `0x18000a3fc`
- `0x18000a490`
- `0x18000a5e0`

## callees

- `0x180001fe0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x180001fb0  jmp     cs:__guard_dispatch_icall_fptr
```
