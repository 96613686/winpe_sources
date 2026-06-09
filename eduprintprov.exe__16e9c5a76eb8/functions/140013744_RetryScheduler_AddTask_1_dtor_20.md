# _RetryScheduler::AddTask_::_1_::dtor$20

- ea: `0x140013744`
- end: `0x140013750`
- name: `_RetryScheduler::AddTask_::_1_::dtor$20`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140010300`

## pseudocode

```c
void __fastcall RetryScheduler::AddTask_::_1_::dtor_20(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 104));
}

```

## disassembly

```asm
0x140013744  lea     rcx, [rdx+68h]; this
0x14001374b  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
