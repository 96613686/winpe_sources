# _guard_dispatch_icall

- ea: `0x180004070`
- end: `0x180004076`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180005010`

## callees

- `0x180004010`

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
0x180004070  jmp     cs:__guard_dispatch_icall_fptr
```
