# _guard_dispatch_icall

- ea: `0x140003580`
- end: `0x140003586`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140005010`
- `0x14000e858`
- `0x14000ef5c`
- `0x140014300`

## callees

- `0x1400035b0`

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
0x140003580  jmp     cs:__guard_dispatch_icall_fptr
```
