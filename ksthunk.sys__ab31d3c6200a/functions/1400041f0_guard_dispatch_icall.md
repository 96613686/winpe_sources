# _guard_dispatch_icall

- ea: `0x1400041f0`
- end: `0x1400041f6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `30`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001370`
- `0x1400013d0`
- `0x140001440`
- `0x140001700`
- `0x140001760`
- `0x140001ba0`
- `0x1400021e0`
- `0x140002600`
- `0x14000272c`
- `0x14000280c`
- `0x140002d30`
- `0x140002db0`
- `0x140003650`
- `0x140003680`
- `0x140003e50`
- `0x140003ea0`
- `0x140003ef0`
- `0x140003f10`
- `0x140005040`
- `0x14000b0b0`
- `0x14000b1c0`
- `0x14000b3c0`
- `0x14000b400`
- `0x14000b570`
- `0x14000b770`
- `0x14000bc60`
- `0x14000bd80`
- `0x14000bea4`
- `0x14000bfc4`
- `0x14000e078`

## callees

- `0x140004190`

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
0x1400041f0  jmp     cs:__guard_dispatch_icall_fptr
```
