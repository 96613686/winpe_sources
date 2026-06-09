# __SetSecurityOnTree_::_1_::dtor$0

- ea: `0x1800172c0`
- end: `0x1800172cc`
- name: `__SetSecurityOnTree_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, wil::details **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ccc4`

## pseudocode

```c
void __fastcall _SetSecurityOnTree_::_1_::dtor_0(__int64 a1, wil::details **a2)
{
  wistd::unique_ptr<_WIN32_FIND_DATAW,wil::process_heap_deleter>::~unique_ptr<_WIN32_FIND_DATAW,wil::process_heap_deleter>(
    a2 + 4,
    a2);
}

```

## disassembly

```asm
0x1800172c0  lea     rcx, [rdx+20h]
0x1800172c7  jmp     ??1?$unique_ptr@U_WIN32_FIND_DATAW@@Uprocess_heap_deleter@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_WIN32_FIND_DATAW,wil::process_heap_deleter>::~unique_ptr<_WIN32_FIND_DATAW,wil::process_heap_deleter>(void)
```
