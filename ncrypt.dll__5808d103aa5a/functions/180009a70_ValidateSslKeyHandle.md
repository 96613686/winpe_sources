# ValidateSslKeyHandle

- ea: `0x180009a70`
- end: `0x180009a8b`
- name: `ValidateSslKeyHandle`
- size: `27`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180009830`
- `0x180009aa0`
- `0x1800116b0`
- `0x180012a70`
- `0x180015cd0`
- `0x180019be0`
- `0x18001a8e0`
- `0x18001aa60`
- `0x18001aef0`
- `0x18001b050`
- `0x18001b500`
- `0x18001b5c0`
- `0x18001b680`

## callees

- `0x180009a70`

## pseudocode

```c
_DWORD *__fastcall ValidateSslKeyHandle(_DWORD *a1)
{
  _DWORD *result; // rax

  if ( !a1 || *a1 < 0x20u )
    return 0;
  result = 0;
  if ( a1[1] == 1145324610 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x180009a70  test    rcx, rcx
0x180009a73  jz      short loc_180009A88
0x180009a75  cmp     dword ptr [rcx], 20h ; ' '
0x180009a78  jb      short loc_180009A88
0x180009a7a  xor     eax, eax
0x180009a7c  cmp     dword ptr [rcx+4], 44444442h
0x180009a83  cmovz   rax, rcx
0x180009a87  retn
0x180009a88  xor     eax, eax
0x180009a8a  retn
```
