# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Calculate_growth(unsigned __int64)

- ea: `0x180002340`
- end: `0x180002374`
- name: `?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBA_K_K@Z`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e20`
- `0x180008fb8`
- `0x18000926c`
- `0x1800093fc`

## callees

- `0x180002340`

## pseudocode

```c
__int64 __fastcall std::wstring::_Calculate_growth(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // rdx
  __int64 result; // rax
  unsigned __int64 v4; // r9
  unsigned __int64 v5; // r8

  v2 = a2 | 7;
  result = 0x7FFFFFFFFFFFFFFELL;
  if ( v2 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = *(_QWORD *)(a1 + 24);
    v5 = v4 >> 1;
    if ( v4 <= 0x7FFFFFFFFFFFFFFELL - (v4 >> 1) )
    {
      result = v5 + v4;
      if ( v2 >= v5 + v4 )
        return v2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002340  or      rdx, 7
0x180002344  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000234e  cmp     rdx, rax
0x180002351  ja      short locret_180002373
0x180002353  mov     r9, [rcx+18h]
0x180002357  mov     rcx, rax
0x18000235a  mov     r8, r9
0x18000235d  shr     r8, 1
0x180002360  sub     rcx, r8
0x180002363  cmp     r9, rcx
0x180002366  ja      short locret_180002373
0x180002368  lea     rax, [r8+r9]
0x18000236c  cmp     rdx, rax
0x18000236f  cmovnb  rax, rdx
0x180002373  retn
```
