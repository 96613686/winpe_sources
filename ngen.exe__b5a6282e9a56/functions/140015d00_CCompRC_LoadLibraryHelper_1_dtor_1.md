# _CCompRC::LoadLibraryHelper_::_1_::dtor$1

- ea: `0x140015d00`
- end: `0x140015d0c`
- name: `_CCompRC::LoadLibraryHelper_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000e304`

## pseudocode

```c
void __fastcall CCompRC::LoadLibraryHelper_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  DelegatingException::~DelegatingException((DelegatingException *)(a2 + 168));
}

```

## disassembly

```asm
0x140015d00  lea     rcx, [rdx+0A8h]; this
0x140015d07  jmp     ??1DelegatingException@@UEAA@XZ; DelegatingException::~DelegatingException(void)
```
