# _GetComponentCVForEnrollmentId_::_1_::dtor$1

- ea: `0x180011e35`
- end: `0x180011e41`
- name: `_GetComponentCVForEnrollmentId_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ebcc`

## pseudocode

```c
void __fastcall GetComponentCVForEnrollmentId_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  wistd::unique_ptr<char,wil::process_heap_deleter>::~unique_ptr<char,wil::process_heap_deleter>((void **)(a2 + 56));
}

```

## disassembly

```asm
0x180011e35  lea     rcx, [rdx+38h]
0x180011e3c  jmp     ??1?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<char,wil::process_heap_deleter>::~unique_ptr<char,wil::process_heap_deleter>(void)
```
