# _guard_dispatch_icall

- ea: `0x1400015b0`
- end: `0x1400015b6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002070`
- `0x1400082f0`
- `0x14000dae0`
- `0x14000db90`
- `0x14000dc70`
- `0x14000dd10`
- `0x14000ddb0`
- `0x14000de50`
- `0x14000dee0`
- `0x14000e240`
- `0x14000e3a0`

## callees

- `0x140001550`

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
0x1400015b0  jmp     cs:__guard_dispatch_icall_fptr
```
