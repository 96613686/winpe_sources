# CharIsSlash(ushort)

- ea: `0x1800023d0`
- end: `0x1800023e6`
- name: `?CharIsSlash@@YAHG@Z`
- size: `22`
- prototype: `_BOOL8 __fastcall(__int16)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800018c0`
- `0x180001bd0`
- `0x180001d90`
- `0x180001de0`
- `0x180001f10`
- `0x180002500`

## callees

- `0x1800023d0`

## pseudocode

```c
_BOOL8 __fastcall CharIsSlash(__int16 a1)
{
  return a1 == 92 || a1 == 47;
}

```

## disassembly

```asm
0x1800023d0  cmp     cx, 5Ch ; '\'
0x1800023d4  jz      short loc_1800023E0
0x1800023d6  cmp     cx, 2Fh ; '/'
0x1800023da  jz      short loc_1800023E0
0x1800023dc  xor     eax, eax
0x1800023de  retn
0x1800023e0  mov     eax, 1
0x1800023e5  retn
```
