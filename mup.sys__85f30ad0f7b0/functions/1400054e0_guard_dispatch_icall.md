# _guard_dispatch_icall

- ea: `0x1400054e0`
- end: `0x1400054e6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `53`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002614`
- `0x140002700`
- `0x140002754`
- `0x14000290c`
- `0x1400029b0`
- `0x140002a14`
- `0x140002a44`
- `0x140002b18`
- `0x140002b90`
- `0x140002c28`
- `0x140002ccc`
- `0x140002dcc`
- `0x140002e74`
- `0x140002eb8`
- `0x140002f2c`
- `0x140002f94`
- `0x140003564`
- `0x140003608`
- `0x1400036c8`
- `0x140003e44`
- `0x140003edc`
- `0x140003f80`
- `0x140004040`
- `0x1400040fc`
- `0x140004ad4`
- `0x140006010`
- `0x14000f104`
- `0x14000f188`
- `0x14000f6e0`
- `0x14000f7b0`
- `0x14000f830`
- `0x14000f8a0`
- `0x14000f930`
- `0x14000f9b0`
- `0x14000fa80`
- `0x14000fb50`
- `0x14000fbc0`
- `0x14000fc30`
- `0x140011a20`
- `0x1400172c0`
- `0x140017a98`
- `0x14001c0f0`
- `0x14001e740`
- `0x14001e7f0`
- `0x14001e880`
- `0x14001eb80`
- `0x14001ebf0`
- `0x14001ec90`
- `0x14001ee00`
- `0x14001eec0`

## callees

- `0x140005510`

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
0x1400054e0  jmp     cs:__guard_dispatch_icall_fptr
```
