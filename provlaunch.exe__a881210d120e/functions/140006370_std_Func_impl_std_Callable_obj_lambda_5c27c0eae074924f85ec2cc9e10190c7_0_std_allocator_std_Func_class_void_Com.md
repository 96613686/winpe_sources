# std::_Func_impl_std::_Callable_obj__lambda_5c27c0eae074924f85ec2cc9e10190c7__0__std::allocator_std::_Func_class_void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this

- ea: `0x140006370`
- end: `0x1400063a5`
- name: `std::_Func_impl_std::_Callable_obj__lambda_5c27c0eae074924f85ec2cc9e10190c7__0__std::allocator_std::_Func_class_void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const_&_Command_const_&_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140006370`
- `0x14000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140006394`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006394`

## pseudocode

```c
void __fastcall std::_Func_impl_std::_Callable_obj__lambda_5c27c0eae074924f85ec2cc9e10190c7__0__std::allocator_std::_Func_class_void_CommandSet_const___Command_const___unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const___Command_const___unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this(
        void *a1,
        char a2)
{
  (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0);
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x140006370  mov     [rsp+arg_0], rbx
0x140006375  push    rdi
0x140006376  sub     rsp, 20h
0x14000637a  mov     rax, [rcx]
0x14000637d  mov     bl, dl
0x14000637f  xor     edx, edx
0x140006381  mov     rdi, rcx
0x140006384  mov     rax, [rax+28h]
0x140006388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000638d  test    bl, bl
0x14000638f  jz      short loc_14000639A
0x140006391  mov     rcx, rdi
0x140006394  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000639a  mov     rbx, [rsp+28h+arg_0]
0x14000639f  add     rsp, 20h
0x1400063a3  pop     rdi
0x1400063a4  retn
```
