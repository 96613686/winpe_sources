# RtlpCheckBounds

- ea: `0x140008080`
- end: `0x1400080b4`
- name: `RtlpCheckBounds`
- size: `52`
- prototype: `_BOOL8 __fastcall(unsigned __int64, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140007aec`
- `0x1400080bc`
- `0x1400081d0`
- `0x140008424`
- `0x1400084b4`

## callees

- `0x140008080`

## pseudocode

```c
_BOOL8 __fastcall RtlpCheckBounds(unsigned __int64 a1, unsigned __int64 a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // r10
  _BOOL8 result; // rax

  result = 0;
  if ( a1 >= a3 )
  {
    v4 = a3 + a4;
    if ( a1 <= a3 + a4 )
    {
      v5 = a1 + a2;
      if ( a1 + a2 >= a3 && v5 <= v4 && a3 <= v4 && a1 <= v5 && a2 <= a4 )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008080  cmp     rcx, r8
0x140008083  jb      short loc_1400080B1
0x140008085  lea     rax, [r8+r9]
0x140008089  cmp     rcx, rax
0x14000808c  ja      short loc_1400080B1
0x14000808e  lea     r10, [rcx+rdx]
0x140008092  cmp     r10, r8
0x140008095  jb      short loc_1400080B1
0x140008097  cmp     r10, rax
0x14000809a  ja      short loc_1400080B1
0x14000809c  cmp     r8, rax
0x14000809f  ja      short loc_1400080B1
0x1400080a1  cmp     rcx, r10
0x1400080a4  ja      short loc_1400080B1
0x1400080a6  cmp     rdx, r9
0x1400080a9  ja      short loc_1400080B1
0x1400080ab  mov     eax, 1
0x1400080b0  retn
0x1400080b1  xor     eax, eax
0x1400080b3  retn
```
