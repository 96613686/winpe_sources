# _copysignf

- ea: `0x18006ccf0`
- end: `0x18006cd17`
- name: `_copysignf`
- size: `39`
- prototype: `float __cdecl(float Number, float Sign)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18006ccf0`

## pseudocode

```c
float __cdecl copysignf(float Number, float Sign)
{
  if ( (LODWORD(Number) ^ LODWORD(Sign)) < 0 )
    LODWORD(Number) ^= 0x80000000;
  return Number;
}

```

## disassembly

```asm
0x18006ccf0  movss   [rsp+arg_0], xmm0
0x18006ccf6  mov     ecx, [rsp+arg_0]
0x18006ccfa  movss   [rsp+arg_0], xmm1
0x18006cd00  mov     eax, [rsp+arg_0]
0x18006cd04  xor     eax, ecx
0x18006cd06  jge     short locret_18006CD16
0x18006cd08  btc     ecx, 1Fh
0x18006cd0c  mov     [rsp+arg_0], ecx
0x18006cd10  movss   xmm0, [rsp+arg_0]
0x18006cd16  retn
```
