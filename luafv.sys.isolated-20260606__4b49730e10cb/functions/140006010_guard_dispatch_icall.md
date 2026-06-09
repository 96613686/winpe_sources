# _guard_dispatch_icall

- ea: `0x140006010`
- end: `0x140006016`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002a70`
- `0x140002af8`
- `0x140002bd8`
- `0x140007050`
- `0x14001fe20`
- `0x140026270`

## callees

- `0x140005fb0`

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
0x140006010  jmp     cs:__guard_dispatch_icall_fptr
```
