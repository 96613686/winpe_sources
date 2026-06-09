# _guard_dispatch_icall_nop

- ea: `0x1400c7b20`
- end: `0x1400c7b22`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `158`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400013f0`
- `0x140001970`
- `0x1400020a0`
- `0x140002684`
- `0x140006e90`
- `0x140006fe0`
- `0x1400075e0`
- `0x140007864`
- `0x1400085e8`
- `0x1400086dc`
- `0x140009d2c`
- `0x14000a06c`
- `0x14000a9d0`
- `0x14000ad40`
- `0x14000ad90`
- `0x14000ae50`
- `0x14000b220`
- `0x14000c99c`
- `0x14000cba4`
- `0x14000d7f0`
- `0x14000da40`
- `0x14000e5c0`
- `0x14000e610`
- `0x14000e6c0`
- `0x14000e7f4`
- `0x14000f374`
- `0x14000f814`
- `0x14000fb30`
- `0x14000fbf0`
- `0x14000fc40`
- `0x14000ffc0`
- `0x1400101fc`
- `0x14001025c`
- `0x1400104b0`
- `0x14001134c`
- `0x1400114cc`
- `0x140011510`
- `0x1400115a0`
- `0x140012a98`
- `0x140012b48`
- `0x140012e48`
- `0x140012ecc`
- `0x140013030`
- `0x140013070`
- `0x140014a7c`
- `0x140014bd4`
- `0x140014c80`
- `0x140014cd0`
- `0x140014d90`
- `0x1400150b8`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x1400c7b20  jmp     rax
```
