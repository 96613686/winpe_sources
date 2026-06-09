# _guard_dispatch_icall

- ea: `0x140004e10`
- end: `0x140004e16`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001464`
- `0x140001524`
- `0x14000163c`
- `0x14000171c`
- `0x140001808`
- `0x1400026d0`
- `0x140002780`
- `0x140002830`
- `0x14000292c`
- `0x140002a08`
- `0x140002af0`
- `0x140002c2c`
- `0x140002d28`
- `0x140002e68`
- `0x140002ff0`
- `0x140003b4c`
- `0x140003bfc`
- `0x140003cf8`
- `0x1400048c0`
- `0x140004a0c`
- `0x140004b34`
- `0x140006010`
- `0x14000b044`
- `0x14000b0f8`
- `0x14000b1c0`
- `0x14000b310`

## callees

- `0x140004e40`

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
0x140004e10  jmp     cs:__guard_dispatch_icall_fptr
```
