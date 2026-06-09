# _guard_dispatch_icall

- ea: `0x140003770`
- end: `0x140003776`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `27`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001370`
- `0x1400013d0`
- `0x140001440`
- `0x140001700`
- `0x140001760`
- `0x140001ba0`
- `0x140002160`
- `0x140002430`
- `0x1400024b0`
- `0x140002cf0`
- `0x140002d20`
- `0x1400033d0`
- `0x140003420`
- `0x140003470`
- `0x140003490`
- `0x140004040`
- `0x14000a0b0`
- `0x14000a1c0`
- `0x14000a3c0`
- `0x14000a400`
- `0x14000a570`
- `0x14000a770`
- `0x14000ad00`
- `0x14000ae20`
- `0x14000af44`
- `0x14000b064`
- `0x14000d078`

## callees

- `0x140003710`

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
0x140003770  jmp     cs:__guard_dispatch_icall_fptr
```
