# _CDpSearchProtocol::Init_::_1_::dtor$0

- ea: `0x18000b125`
- end: `0x18000b131`
- name: `_CDpSearchProtocol::Init_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007cc4`

## pseudocode

```c
void __fastcall CDpSearchProtocol::Init_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  DpSearch::~DpSearch((void **)(a2 + 48));
}

```

## disassembly

```asm
0x18000b125  lea     rcx, [rdx+30h]; this
0x18000b12c  jmp     ??1DpSearch@@QEAA@XZ; DpSearch::~DpSearch(void)
```
