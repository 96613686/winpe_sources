# _CCompRC::LoadLibraryHelper_::_1_::dtor$3

- ea: `0x140015d18`
- end: `0x140015d24`
- name: `_CCompRC::LoadLibraryHelper_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001209c`

## pseudocode

```c
void __fastcall CCompRC::LoadLibraryHelper_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ArrayList::~ArrayList((ArrayList *)(a2 + 208));
}

```

## disassembly

```asm
0x140015d18  lea     rcx, [rdx+0D0h]; this
0x140015d1f  jmp     ??1ArrayList@@QEAA@XZ; ArrayList::~ArrayList(void)
```
