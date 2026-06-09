# std::_Func_impl_std::_Callable_obj__lambda_5c27c0eae074924f85ec2cc9e10190c7__0__std::allocator_std::_Func_class_void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move

- ea: `0x140006230`
- end: `0x140006270`
- name: `std::_Func_impl_std::_Callable_obj__lambda_5c27c0eae074924f85ec2cc9e10190c7__0__std::allocator_std::_Func_class_void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001864`
- `0x140006230`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000624e`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000624e`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_std::_Callable_obj__lambda_5c27c0eae074924f85ec2cc9e10190c7__0__std::allocator_std::_Func_class_void_CommandSet_const___Command_const___unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const___Command_const___unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move(
        __int64 a1,
        _QWORD *a2)
{
  if ( !a2 )
  {
    a2 = operator new(0x18u);
    if ( !a2 )
    {
      std::_Xbad_alloc();
      __debugbreak();
    }
  }
  *a2 = off_14000C158;
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x140006230  push    rbx
0x140006232  sub     rsp, 20h
0x140006236  mov     rbx, rcx
0x140006239  test    rdx, rdx
0x14000623c  jnz     short loc_140006255
0x14000623e  lea     ecx, [rdx+18h]; Size
0x140006241  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006246  mov     rdx, rax
0x140006249  test    rax, rax
0x14000624c  jnz     short loc_140006255
0x14000624e  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140006254  int     3; Trap to Debugger
0x140006255  lea     rax, off_14000C158
0x14000625c  mov     [rdx], rax
0x14000625f  mov     rax, [rbx+8]
0x140006263  mov     [rdx+8], rax
0x140006267  mov     rax, rdx
0x14000626a  add     rsp, 20h
0x14000626e  pop     rbx
0x14000626f  retn
```
