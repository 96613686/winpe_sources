# _invalid_parameter_noinfo

- ea: `0x180014f34`
- end: `0x180014f55`
- name: `_invalid_parameter_noinfo`
- size: `33`
- prototype: `void __cdecl()`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180014660`
- `0x180015934`
- `0x180016490`
- `0x180017ab0`
- `0x1800180b0`
- `0x180018170`
- `0x180018400`
- `0x1800188c0`
- `0x18001b0f0`
- `0x18001b710`
- `0x18001bd80`
- `0x18001bef4`
- `0x18001c1d0`

## callees

- `0x180014d98`

## pseudocode

```c
void __cdecl invalid_parameter_noinfo()
{
  invalid_parameter(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x180014f34  sub     rsp, 38h
0x180014f38  xor     r9d, r9d; int
0x180014f3b  mov     [rsp+38h+var_18], 0; uintptr_t
0x180014f44  xor     r8d, r8d; int
0x180014f47  xor     edx, edx; int
0x180014f49  xor     ecx, ecx; int
0x180014f4b  call    _invalid_parameter
0x180014f50  add     rsp, 38h
0x180014f54  retn
```
