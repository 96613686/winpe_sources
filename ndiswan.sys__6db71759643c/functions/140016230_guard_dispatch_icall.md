# _guard_dispatch_icall

- ea: `0x140016230`
- end: `0x140016236`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `58`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001800`
- `0x1400035f0`
- `0x140003970`
- `0x140004be0`
- `0x140007710`
- `0x14000a23c`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000a5f4`
- `0x14000a648`
- `0x14000a68c`
- `0x14000a6e0`
- `0x14000a744`
- `0x14000ab68`
- `0x14000abf0`
- `0x14000acd0`
- `0x14000aff4`
- `0x14000b04c`
- `0x14000b0c4`
- `0x14000b1fc`
- `0x14000b25c`
- `0x14000bd50`
- `0x14000cac8`
- `0x14000cb38`
- `0x14000cbc8`
- `0x14000ed38`
- `0x14000ed9c`
- `0x140010150`
- `0x14001043c`
- `0x1400104a4`
- `0x140010518`
- `0x140010580`
- `0x1400105d4`
- `0x1400107dc`
- `0x14001090c`
- `0x140010ff8`
- `0x140011bd4`
- `0x140011c4c`
- `0x140012570`
- `0x140012ddc`
- `0x140013080`
- `0x140013570`
- `0x140017010`
- `0x140025070`
- `0x140026970`
- `0x14002c7c0`
- `0x14002f620`
- `0x140030940`
- `0x140030e70`
- `0x140031b80`

## callees

- `0x140016260`

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
0x140016230  jmp     cs:__guard_dispatch_icall_fptr
```
