# _guard_dispatch_icall

- ea: `0x140002b20`
- end: `0x140002b26`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140004010`
- `0x140014060`

## callees

- `0x140002b50`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x140002b20  jmp     cs:__guard_dispatch_icall_fptr
```
