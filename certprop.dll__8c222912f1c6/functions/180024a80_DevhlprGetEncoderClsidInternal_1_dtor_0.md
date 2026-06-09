# _DevhlprGetEncoderClsidInternal_::_1_::dtor$0

- ea: `0x180024a80`
- end: `0x180024a8c`
- name: `_DevhlprGetEncoderClsidInternal_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800066d8`

## pseudocode

```c
void __fastcall DevhlprGetEncoderClsidInternal_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(a2 + 48, a2);
}

```

## disassembly

```asm
0x180024a80  lea     rcx, [rdx+30h]
0x180024a87  jmp     ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
```
