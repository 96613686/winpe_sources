# SelfReg(ushort const *,ushort const *)

- ea: `0x140007550`
- end: `0x14000755f`
- name: `?SelfReg@@YAHPEBG0@Z`
- size: `15`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400011e4`

## callees

- `0x140007568`

## string_xrefs

- `0x140007553`: `DllRegisterServer`

## pseudocode

```c
__int64 __fastcall SelfReg(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  return SelfRegOrUnreg(a2, "DllRegisterServer");
}

```

## disassembly

```asm
0x140007550  mov     rcx, rdx; unsigned __int16 *
0x140007553  lea     rdx, aDllregisterser; "DllRegisterServer"
0x14000755a  jmp     ?SelfRegOrUnreg@@YAHPEBGPEBD@Z; SelfRegOrUnreg(ushort const *,char const *)
```
