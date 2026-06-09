# _IsNewCommandLine_::_1_::dtor$8

- ea: `0x140014ba3`
- end: `0x140014bb6`
- name: `_IsNewCommandLine_::_1_::dtor$8`
- size: `19`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400016d0`

## pseudocode

```c
void __fastcall IsNewCommandLine_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  NGenPrivateAttributesClass::~NGenPrivateAttributesClass((NGenPrivateAttributesClass *)(a2 + 192));
}

```

## disassembly

```asm
0x140014ba3  lea     rcx, [rdx+40h]
0x140014baa  add     rcx, 80h; this
0x140014bb1  jmp     ??1NGenPrivateAttributesClass@@QEAA@XZ; NGenPrivateAttributesClass::~NGenPrivateAttributesClass(void)
```
