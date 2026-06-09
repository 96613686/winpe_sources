# _CThread::CThread_::_1_::dtor$2

- ea: `0x14001d64d`
- end: `0x14001d65d`
- name: `_CThread::CThread_::_1_::dtor$2`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003194`

## pseudocode

```c
void __fastcall CThread::CThread_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(*(_QWORD *)(a2 + 80) + 40LL));
}

```

## disassembly

```asm
0x14001d64d  mov     rcx, [rdx+50h]
0x14001d654  add     rcx, 28h ; '('; this
0x14001d658  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
