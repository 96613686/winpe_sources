# _guard_dispatch_icall

- ea: `0x180002c80`
- end: `0x180002c86`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180003010`

## callees

- `0x180002c20`

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
0x180002c80  jmp     cs:__guard_dispatch_icall_fptr
```
