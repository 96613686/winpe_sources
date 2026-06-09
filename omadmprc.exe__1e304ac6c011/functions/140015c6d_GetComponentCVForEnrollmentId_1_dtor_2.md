# _GetComponentCVForEnrollmentId_::_1_::dtor$2

- ea: `0x140015c6d`
- end: `0x140015c79`
- name: `_GetComponentCVForEnrollmentId_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000d9a8`

## pseudocode

```c
void __fastcall GetComponentCVForEnrollmentId_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(a2 + 72);
}

```

## disassembly

```asm
0x140015c6d  lea     rcx, [rdx+48h]
0x140015c74  jmp     ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
```
