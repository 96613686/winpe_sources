# _ThreadpoolManager::QueueThreadpoolWork_::_1_::dtor$0

- ea: `0x140015fff`
- end: `0x14001600b`
- name: `_ThreadpoolManager::QueueThreadpoolWork_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000da5c`

## pseudocode

```c
void __fastcall ThreadpoolManager::QueueThreadpoolWork_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>((void **)(a2 + 96));
}

```

## disassembly

```asm
0x140015fff  lea     rcx, [rdx+60h]
0x140016006  jmp     ??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)
```
