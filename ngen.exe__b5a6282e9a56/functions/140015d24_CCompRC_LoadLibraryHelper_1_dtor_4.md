# _CCompRC::LoadLibraryHelper_::_1_::dtor$4

- ea: `0x140015d24`
- end: `0x140015d30`
- name: `_CCompRC::LoadLibraryHelper_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c700`

## pseudocode

```c
void __fastcall CCompRC::LoadLibraryHelper_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  Exception::~Exception((Exception *)(a2 + 168));
}

```

## disassembly

```asm
0x140015d24  lea     rcx, [rdx+0A8h]; this
0x140015d2b  jmp     ??1Exception@@UEAA@XZ; Exception::~Exception(void)
```
