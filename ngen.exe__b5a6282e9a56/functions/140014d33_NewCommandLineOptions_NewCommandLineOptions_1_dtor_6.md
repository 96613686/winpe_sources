# _NewCommandLineOptions::_NewCommandLineOptions_::_1_::dtor$6

- ea: `0x140014d33`
- end: `0x140014d46`
- name: `_NewCommandLineOptions::_NewCommandLineOptions_::_1_::dtor$6`
- size: `19`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400016d0`

## pseudocode

```c
void __fastcall NewCommandLineOptions::_NewCommandLineOptions_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  NGenPrivateAttributesClass::~NGenPrivateAttributesClass((NGenPrivateAttributesClass *)(*(_QWORD *)(a2 + 48) + 128LL));
}

```

## disassembly

```asm
0x140014d33  mov     rcx, [rdx+30h]
0x140014d3a  add     rcx, 80h; this
0x140014d41  jmp     ??1NGenPrivateAttributesClass@@QEAA@XZ; NGenPrivateAttributesClass::~NGenPrivateAttributesClass(void)
```
