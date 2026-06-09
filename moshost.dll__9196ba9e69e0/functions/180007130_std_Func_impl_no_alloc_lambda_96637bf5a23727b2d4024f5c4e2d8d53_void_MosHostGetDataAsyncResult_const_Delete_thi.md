# std::_Func_impl_no_alloc__lambda_96637bf5a23727b2d4024f5c4e2d8d53__void_MosHostGetDataAsyncResult_const_&_::_Delete_this

- ea: `0x180007130`
- end: `0x180007147`
- name: `std::_Func_impl_no_alloc__lambda_96637bf5a23727b2d4024f5c4e2d8d53__void_MosHostGetDataAsyncResult_const_&_::_Delete_this`
- size: `23`
- prototype: `void __fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001d24`
- `0x180007130`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_96637bf5a23727b2d4024f5c4e2d8d53__void_MosHostGetDataAsyncResult_const___::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x180007130  sub     rsp, 28h
0x180007134  test    dl, dl
0x180007136  jz      short loc_180007142
0x180007138  mov     edx, 48h ; 'H'
0x18000713d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007142  add     rsp, 28h
0x180007146  retn
```
