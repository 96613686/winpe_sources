# std::_Func_impl_std::_Callable_obj__lambda_5c27c0eae074924f85ec2cc9e10190c7__0__std::allocator_std::_Func_class_void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call

- ea: `0x140006440`
- end: `0x14000646c`
- name: `std::_Func_impl_std::_Callable_obj__lambda_5c27c0eae074924f85ec2cc9e10190c7__0__std::allocator_std::_Func_class_void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003bd4`
- `0x140006440`

## pseudocode

```c
void __fastcall std::_Func_impl_std::_Callable_obj__lambda_5c27c0eae074924f85ec2cc9e10190c7__0__std::allocator_std::_Func_class_void_CommandSet_const___Command_const___unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const___Command_const___unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        _DWORD *a4)
{
  unsigned __int8 v4; // r9
  const WCHAR *v5; // rdx

  v4 = *a4 != 0;
  if ( *((_QWORD *)a3 + 3) >= 8u )
    a3 = *(const WCHAR **)a3;
  v5 = (const WCHAR *)(a2 + 24);
  if ( *((_QWORD *)v5 + 3) >= 8u )
    v5 = *(const WCHAR **)v5;
  Add(**(LPCWSTR **)(a1 + 8), v5, a3, v4);
}

```

## disassembly

```asm
0x140006440  cmp     dword ptr [r9], 0
0x140006444  setnz   r9b; bool
0x140006448  cmp     qword ptr [r8+18h], 8
0x14000644d  jb      short loc_140006452
0x14000644f  mov     r8, [r8]; LPCWSTR
0x140006452  add     rdx, 18h
0x140006456  cmp     qword ptr [rdx+18h], 8
0x14000645b  jb      short loc_140006460
0x14000645d  mov     rdx, [rdx]; LPCWSTR
0x140006460  mov     rcx, [rcx+8]
0x140006464  mov     rcx, [rcx]; lpSubKey
0x140006467  jmp     ?Add@@YAXPEBG00_N@Z; Add(ushort const *,ushort const *,ushort const *,bool)
```
