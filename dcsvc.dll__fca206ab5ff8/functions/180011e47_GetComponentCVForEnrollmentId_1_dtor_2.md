# _GetComponentCVForEnrollmentId_::_1_::dtor$2

- ea: `0x180011e47`
- end: `0x180011e53`
- name: `_GetComponentCVForEnrollmentId_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000eb6c`

## pseudocode

```c
void __fastcall GetComponentCVForEnrollmentId_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(a2 + 72);
}

```

## disassembly

```asm
0x180011e47  lea     rcx, [rdx+48h]
0x180011e4e  jmp     ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
```
