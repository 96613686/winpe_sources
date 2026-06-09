# _guard_dispatch_icall

- ea: `0x140007710`
- end: `0x140007716`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `90`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001a70`
- `0x1400027d0`
- `0x140003e08`
- `0x140003e38`
- `0x140003e7c`
- `0x140003fa4`
- `0x140004008`
- `0x140004064`
- `0x1400040c8`
- `0x140004138`
- `0x140004204`
- `0x140004248`
- `0x14000429c`
- `0x140004308`
- `0x140004374`
- `0x1400043e0`
- `0x140004468`
- `0x140004508`
- `0x140004588`
- `0x140004634`
- `0x1400046e4`
- `0x140004a08`
- `0x140004a9c`
- `0x140004b3c`
- `0x140004b98`
- `0x140004c64`
- `0x140004cf0`
- `0x140004db8`
- `0x140004e5c`
- `0x140004efc`
- `0x140004fc4`
- `0x1400050a4`
- `0x140005190`
- `0x140005558`
- `0x140006c80`
- `0x140006cf8`
- `0x140006db0`
- `0x140008010`
- `0x14000f0d8`
- `0x140011838`
- `0x140011c00`
- `0x140011d04`
- `0x1400122b0`
- `0x140012798`
- `0x140012ac0`
- `0x140012cf4`
- `0x140012f60`
- `0x1400133d0`
- `0x140013954`
- `0x140014c30`

## callees

- `0x140007740`

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
0x140007710  jmp     cs:__guard_dispatch_icall_fptr
```
