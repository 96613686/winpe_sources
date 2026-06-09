# _CDpSearchProtocol::CreateAccessorEx_::_1_::dtor$0

- ea: `0x18000b01e`
- end: `0x18000b02a`
- name: `_CDpSearchProtocol::CreateAccessorEx_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007cc4`

## pseudocode

```c
void __fastcall CDpSearchProtocol::CreateAccessorEx_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  DpSearch::~DpSearch((void **)(a2 + 128));
}

```

## disassembly

```asm
0x18000b01e  lea     rcx, [rdx+80h]; this
0x18000b025  jmp     ??1DpSearch@@QEAA@XZ; DpSearch::~DpSearch(void)
```
