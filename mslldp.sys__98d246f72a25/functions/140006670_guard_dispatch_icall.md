# _guard_dispatch_icall

- ea: `0x140006670`
- end: `0x140006676`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `32`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400041fc`
- `0x14000458c`
- `0x140004a60`
- `0x140004b00`
- `0x140005144`
- `0x1400052c0`
- `0x1400052f4`
- `0x140005454`
- `0x140005550`
- `0x14000561c`
- `0x1400056ac`
- `0x14000574c`
- `0x1400057c0`
- `0x140005a6c`
- `0x140005ac0`
- `0x140005b20`
- `0x140005d20`
- `0x140005f74`
- `0x1400060e0`
- `0x140006460`
- `0x140008010`
- `0x14000e008`
- `0x14000e420`
- `0x14000e580`
- `0x14000e670`
- `0x14000f51c`
- `0x14000f5a0`
- `0x14000fcf0`
- `0x14000fdd0`
- `0x140010ca0`
- `0x140013180`
- `0x1400133dc`

## callees

- `0x1400066a0`

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
0x140006670  jmp     cs:__guard_dispatch_icall_fptr
```
