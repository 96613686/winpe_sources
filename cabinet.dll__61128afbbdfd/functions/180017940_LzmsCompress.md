# LzmsCompress

- ea: `0x180017940`
- end: `0x18001799b`
- name: `LzmsCompress`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180017940`
- `0x1800190e8`

## pseudocode

```c
__int64 __fastcall LzmsCompress(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int64 *a6)
{
  unsigned __int64 v6; // r10
  unsigned int v7; // r8d

  v6 = *(unsigned int *)(a1 + 24);
  if ( a3 <= v6 )
  {
    v7 = LzmsEncoderEncode(a1, a2);
    *a6 = 0;
  }
  else
  {
    v7 = 111;
    *a6 = v6;
  }
  return v7;
}

```

## disassembly

```asm
0x180017940  sub     rsp, 38h
0x180017944  mov     r10d, [rcx+18h]
0x180017948  mov     [rsp+38h+arg_0], 0
0x180017950  cmp     r8, r10
0x180017953  jbe     short loc_180017965
0x180017955  mov     rax, [rsp+38h+arg_28]
0x18001795a  mov     r8d, 6Fh ; 'o'
0x180017960  mov     [rax], r10
0x180017963  jmp     short loc_180017993
0x180017965  mov     rax, [rsp+38h+arg_20]
0x18001796a  lea     r10, [rsp+38h+arg_0]
0x18001796f  cmp     rax, r8
0x180017972  mov     [rsp+38h+var_10], r10
0x180017977  cmovnb  eax, r8d
0x18001797b  mov     [rsp+38h+var_18], eax
0x18001797f  call    LzmsEncoderEncode
0x180017984  mov     rcx, [rsp+38h+arg_28]
0x180017989  mov     r8d, eax
0x18001798c  mov     edx, [rsp+38h+arg_0]
0x180017990  mov     [rcx], rdx
0x180017993  mov     eax, r8d
0x180017996  add     rsp, 38h
0x18001799a  retn
```
