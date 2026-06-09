# _guard_dispatch_icall

- ea: `0x140001450`
- end: `0x140001456`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002060`
- `0x140008e08`
- `0x140009018`
- `0x140009b60`
- `0x14000cbf8`
- `0x14000d7d0`
- `0x14000f158`
- `0x14000fdc4`

## callees

- `0x1400013f0`

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
0x140001450  jmp     cs:__guard_dispatch_icall_fptr
```
