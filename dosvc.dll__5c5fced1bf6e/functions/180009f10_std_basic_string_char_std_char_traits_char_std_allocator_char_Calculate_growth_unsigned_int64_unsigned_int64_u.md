# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180009f10`
- end: `0x180009f3a`
- name: `?_Calculate_growth@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@CA_K_K00@Z`
- size: `42`
- prototype: `unsigned __int64 __fastcall(__int64, unsigned __int64, unsigned __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ce4`
- `0x180008d84`
- `0x180008ecc`
- `0x1800090b0`
- `0x1800091a0`
- `0x180009340`

## callees

- `0x180009f10`

## pseudocode

```c
unsigned __int64 __fastcall std::string::_Calculate_growth(__int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // r9
  unsigned __int64 result; // rax

  v3 = a1 | 0xF;
  if ( v3 > a3 )
    return a3;
  v4 = a2 >> 1;
  if ( a2 > a3 - (a2 >> 1) )
    return a3;
  result = v4 + a2;
  if ( v3 >= v4 + a2 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x180009f10  or      rcx, 0Fh
0x180009f14  cmp     rcx, r8
0x180009f17  ja      short loc_180009F36
0x180009f19  mov     r9, rdx
0x180009f1c  mov     rax, r8
0x180009f1f  shr     r9, 1
0x180009f22  sub     rax, r9
0x180009f25  cmp     rdx, rax
0x180009f28  ja      short loc_180009F36
0x180009f2a  lea     rax, [r9+rdx]
0x180009f2e  cmp     rcx, rax
0x180009f31  cmovnb  rax, rcx
0x180009f35  retn
0x180009f36  mov     rax, r8
0x180009f39  retn
```
