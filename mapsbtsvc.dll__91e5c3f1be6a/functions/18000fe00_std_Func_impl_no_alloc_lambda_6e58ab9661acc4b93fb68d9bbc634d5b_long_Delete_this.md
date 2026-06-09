# std::_Func_impl_no_alloc__lambda_6e58ab9661acc4b93fb68d9bbc634d5b__long_::_Delete_this

- ea: `0x18000fe00`
- end: `0x18000fe17`
- name: `std::_Func_impl_no_alloc__lambda_6e58ab9661acc4b93fb68d9bbc634d5b__long_::_Delete_this`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003c34`
- `0x18000fe00`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_6e58ab9661acc4b93fb68d9bbc634d5b__long_::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    std::_Deallocate<16>(a1, 0x30u);
}

```

## disassembly

```asm
0x18000fe00  sub     rsp, 28h
0x18000fe04  test    dl, dl
0x18000fe06  jz      short loc_18000FE12
0x18000fe08  mov     edx, 30h ; '0'
0x18000fe0d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000fe12  add     rsp, 28h
0x18000fe16  retn
```
