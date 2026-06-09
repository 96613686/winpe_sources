# _guard_dispatch_icall

- ea: `0x14000bfe0`
- end: `0x14000bfe6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `112`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001508`
- `0x140001828`
- `0x140001fa0`
- `0x1400022e4`
- `0x1400023b0`
- `0x1400028d0`
- `0x140002a40`
- `0x140002b78`
- `0x140002d08`
- `0x1400036d0`
- `0x140003cec`
- `0x140003ee8`
- `0x140004354`
- `0x1400045c0`
- `0x140004f2c`
- `0x140005280`
- `0x1400056e0`
- `0x1400059b8`
- `0x140005d74`
- `0x140006000`
- `0x140006290`
- `0x140006500`
- `0x1400065fc`
- `0x14000695c`
- `0x140006be0`
- `0x140006de8`
- `0x140006f90`
- `0x140007160`
- `0x1400074a4`
- `0x1400076d0`
- `0x140007794`
- `0x140007b00`
- `0x1400085c8`
- `0x140008860`
- `0x140008c0c`
- `0x140008e7c`
- `0x140009060`
- `0x1400093e0`
- `0x14000a8b0`
- `0x14000ab50`
- `0x14000abf0`
- `0x14000ac30`
- `0x14000ad20`
- `0x14000ad90`
- `0x14000add0`
- `0x14000af30`
- `0x14000b2a0`
- `0x14000b390`
- `0x14000b5f0`
- `0x14000d010`

## callees

- `0x14000c010`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x14000bfe0  jmp     cs:__guard_dispatch_icall_fptr
```
