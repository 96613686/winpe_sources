# _guard_dispatch_icall

- ea: `0x140002db0`
- end: `0x140002db6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400010f0`
- `0x140001960`
- `0x140001ae0`
- `0x140001b30`
- `0x1400021c8`
- `0x140002260`
- `0x140002354`
- `0x140002400`
- `0x140002490`
- `0x140002520`
- `0x1400025d8`
- `0x14000263c`
- `0x140002924`
- `0x140002988`
- `0x1400029f8`
- `0x140004010`
- `0x14000a6c0`
- `0x1400100a4`
- `0x140010128`
- `0x1400101c0`

## callees

- `0x140002de0`

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
0x140002db0  jmp     cs:__guard_dispatch_icall_fptr
```
