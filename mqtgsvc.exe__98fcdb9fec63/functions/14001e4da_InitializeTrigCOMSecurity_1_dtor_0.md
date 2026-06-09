# _InitializeTrigCOMSecurity_::_1_::dtor$0

- ea: `0x14001e4da`
- end: `0x14001e4e6`
- name: `_InitializeTrigCOMSecurity_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005e20`

## pseudocode

```c
void __fastcall InitializeTrigCOMSecurity_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CHandle::~CHandle((void **)(a2 + 232));
}

```

## disassembly

```asm
0x14001e4da  lea     rcx, [rdx+0E8h]; this
0x14001e4e1  jmp     ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
```
