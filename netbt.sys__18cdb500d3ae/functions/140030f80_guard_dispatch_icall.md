# _guard_dispatch_icall

- ea: `0x140030f80`
- end: `0x140030f86`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `57`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400010f0`
- `0x14000178c`
- `0x1400031bc`
- `0x140003d04`
- `0x140004038`
- `0x14000508c`
- `0x140005de0`
- `0x140005e60`
- `0x140005fb0`
- `0x140006080`
- `0x1400067e0`
- `0x140007354`
- `0x140007c4c`
- `0x14000a7b0`
- `0x14000b540`
- `0x14000d070`
- `0x14000e408`
- `0x14000ebe0`
- `0x140010680`
- `0x140010c90`
- `0x1400133c0`
- `0x140015818`
- `0x14001962c`
- `0x140019db4`
- `0x14001a0e0`
- `0x14001a2b8`
- `0x14001c134`
- `0x14001c600`
- `0x14001d580`
- `0x14001e168`
- `0x14001e8f4`
- `0x14001f6dc`
- `0x140020900`
- `0x140021ff8`
- `0x1400226d0`
- `0x140022ed0`
- `0x1400232bc`
- `0x140023800`
- `0x140023b30`
- `0x1400247f8`
- `0x140025260`
- `0x1400253e0`
- `0x14002571c`
- `0x140027d80`
- `0x14002b4b8`
- `0x14002b540`
- `0x14002b620`
- `0x14002c018`
- `0x14002c240`
- `0x14002c360`

## callees

- `0x140030fb0`

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
0x140030f80  jmp     cs:__guard_dispatch_icall_fptr
```
