# _ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$15

- ea: `0x18001f513`
- end: `0x18001f51f`
- name: `_ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$15`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000ab84`

## pseudocode

```c
void __fastcall ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 152), (const struct std::nothrow_t *)a2);
}

```

## disassembly

```asm
0x18001f513  lea     rcx, [rdx+98h]; this
0x18001f51a  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
