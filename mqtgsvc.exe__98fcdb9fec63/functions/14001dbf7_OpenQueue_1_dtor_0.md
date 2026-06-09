# _OpenQueue_::_1_::dtor$0

- ea: `0x14001dbf7`
- end: `0x14001dc03`
- name: `_OpenQueue_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003194`

## pseudocode

```c
void __fastcall OpenQueue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t(*(_bstr_t **)(a2 + 88));
}

```

## disassembly

```asm
0x14001dbf7  mov     rcx, [rdx+58h]; this
0x14001dbfe  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
