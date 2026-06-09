# INTERNAL_ERROR_ACTION(long)

- ea: `0x14000731c`
- end: `0x14000732c`
- name: `?INTERNAL_ERROR_ACTION@@YAXJ@Z`
- size: `16`
- prototype: `void __fastcall __noreturn()`
- caller_count: `16`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14000eab4`
- `0x140012f84`
- `0x140013288`
- `0x140016ba8`
- `0x140024604`
- `0x140024aa0`
- `0x140024b14`
- `0x140024c94`
- `0x140024fe0`
- `0x140025740`
- `0x140025b30`
- `0x140025fb0`
- `0x140026784`
- `0x1400272fc`
- `0x140027a20`
- `0x140027b78`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x140007325`
- `ntdll!RtlRaiseStatus` at `0x140007325`

## pseudocode

```c
void __fastcall __noreturn INTERNAL_ERROR_ACTION()
{
  RtlRaiseStatus(-1073741595);
}

```

## disassembly

```asm
0x14000731c  sub     rsp, 28h
0x140007320  mov     ecx, 0C00000E5h; Status
0x140007325  call    cs:__imp_RtlRaiseStatus
```
