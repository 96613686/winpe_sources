# _guard_dispatch_icall

- ea: `0x140003550`
- end: `0x140003556`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400010b0`
- `0x140002110`
- `0x140005010`
- `0x14000bce4`
- `0x14000c990`
- `0x14000e2f0`

## callees

- `0x140003580`

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
0x140003550  jmp     cs:__guard_dispatch_icall_fptr
```
