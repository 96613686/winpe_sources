# std::_Func_impl_no_alloc__lambda_229fa764f073e20c52ca67eb391bb4d8__long_unsigned_long_unsigned___int64___unsigned___int64___::_Delete_this

- ea: `0x180005bd0`
- end: `0x180005be7`
- name: `std::_Func_impl_no_alloc__lambda_229fa764f073e20c52ca67eb391bb4d8__long_unsigned_long_unsigned___int64___unsigned___int64___::_Delete_this`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003c34`
- `0x180005bd0`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_229fa764f073e20c52ca67eb391bb4d8__long_unsigned_long_unsigned___int64___unsigned___int64___::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    std::_Deallocate<16>(a1, 0x10u);
}

```

## disassembly

```asm
0x180005bd0  sub     rsp, 28h
0x180005bd4  test    dl, dl
0x180005bd6  jz      short loc_180005BE2
0x180005bd8  mov     edx, 10h
0x180005bdd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180005be2  add     rsp, 28h
0x180005be6  retn
```
