# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180001f30`
- end: `0x180001f59`
- name: `?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z`
- size: `41`
- prototype: `unsigned __int64 __fastcall(__int64, unsigned __int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015e0`
- `0x1800016c0`
- `0x1800019a0`
- `0x180003700`

## callees

- `0x180001f30`

## pseudocode

```c
unsigned __int64 __fastcall std::wstring::_Calculate_growth(__int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 result; // rax

  v3 = a1 | 7;
  if ( v3 > a3 || a2 > a3 - (a2 >> 1) )
    return a3;
  result = a2 + (a2 >> 1);
  if ( v3 >= result )
    return v3;
  return result;
}

```

## disassembly

```asm
0x180001f30  or      rcx, 7
0x180001f34  cmp     rcx, r8
0x180001f37  ja      short loc_180001F55
0x180001f39  mov     rax, rdx
0x180001f3c  mov     r9, r8
0x180001f3f  shr     rax, 1
0x180001f42  sub     r9, rax
0x180001f45  cmp     rdx, r9
0x180001f48  ja      short loc_180001F55
0x180001f4a  add     rax, rdx
0x180001f4d  cmp     rcx, rax
0x180001f50  cmovnb  rax, rcx
0x180001f54  retn
0x180001f55  mov     rax, r8
0x180001f58  retn
```
