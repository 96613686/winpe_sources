# _AutoThreadpool::QueueThreadpoolWork_::_1_::dtor$2

- ea: `0x140015cd9`
- end: `0x140015ce5`
- name: `_AutoThreadpool::QueueThreadpoolWork_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000da5c`

## pseudocode

```c
void __fastcall AutoThreadpool::QueueThreadpoolWork_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>((void **)(a2 + 32));
}

```

## disassembly

```asm
0x140015cd9  lea     rcx, [rdx+20h]
0x140015ce0  jmp     ??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)
```
