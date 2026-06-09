# _guard_dispatch_icall

- ea: `0x1400138a0`
- end: `0x1400138a6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002350`
- `0x140004ae0`
- `0x140004b68`
- `0x140004c48`
- `0x140010460`
- `0x1400104b0`
- `0x140015010`
- `0x14001e740`

## callees

- `0x1400138d0`

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
0x1400138a0  jmp     cs:__guard_dispatch_icall_fptr
```
