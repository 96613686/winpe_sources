# _GetUserSIDString_::_1_::dtor$1

- ea: `0x18000b400`
- end: `0x18000b40c`
- name: `_GetUserSIDString_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180007c40`

## pseudocode

```c
__int64 __fastcall GetUserSIDString_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::_Tidy(a2 + 56);
}

```

## disassembly

```asm
0x18000b400  lea     rcx, [rdx+38h]
0x18000b407  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
```
