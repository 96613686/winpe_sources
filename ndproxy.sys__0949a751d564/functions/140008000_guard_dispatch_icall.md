# _guard_dispatch_icall

- ea: `0x140008000`
- end: `0x140008006`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `43`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001b54`
- `0x140001b84`
- `0x140001bc8`
- `0x140001c0c`
- `0x140001c60`
- `0x140001cd0`
- `0x140001d54`
- `0x140001da8`
- `0x140004554`
- `0x140004628`
- `0x140004690`
- `0x140004704`
- `0x140004ad0`
- `0x140005718`
- `0x14000576c`
- `0x1400057c4`
- `0x140005820`
- `0x140007308`
- `0x140007354`
- `0x1400073bc`
- `0x140007424`
- `0x140007488`
- `0x1400074f4`
- `0x14000757c`
- `0x1400075d8`
- `0x140007670`
- `0x140007720`
- `0x140007788`
- `0x1400077f4`
- `0x14000785c`
- `0x140007cb0`
- `0x140007d0c`
- `0x140007d84`
- `0x140009010`
- `0x14000f830`
- `0x140013bc0`
- `0x140014ca0`
- `0x1400171d0`
- `0x140017254`
- `0x1400172e8`
- `0x140017430`
- `0x1400176c4`
- `0x140018214`

## callees

- `0x140008030`

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
0x140008000  jmp     cs:__guard_dispatch_icall_fptr
```
