# SelfUnreg(ushort const *,ushort const *)

- ea: `0x140007760`
- end: `0x14000776f`
- name: `?SelfUnreg@@YAHPEBG0@Z`
- size: `15`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400011e4`

## callees

- `0x140007568`

## string_xrefs

- `0x140007763`: `DllUnregisterServer`

## pseudocode

```c
__int64 __fastcall SelfUnreg(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  return SelfRegOrUnreg(a2, "DllUnregisterServer");
}

```

## disassembly

```asm
0x140007760  mov     rcx, rdx; unsigned __int16 *
0x140007763  lea     rdx, aDllunregisters; "DllUnregisterServer"
0x14000776a  jmp     ?SelfRegOrUnreg@@YAHPEBGPEBD@Z; SelfRegOrUnreg(ushort const *,char const *)
```
