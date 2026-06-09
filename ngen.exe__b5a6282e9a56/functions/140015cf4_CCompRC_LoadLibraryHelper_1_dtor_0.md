# _CCompRC::LoadLibraryHelper_::_1_::dtor$0

- ea: `0x140015cf4`
- end: `0x140015d00`
- name: `_CCompRC::LoadLibraryHelper_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400121ec`

## pseudocode

```c
void __fastcall CCompRC::LoadLibraryHelper_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  StringArrayList::~StringArrayList((StringArrayList *)(a2 + 208));
}

```

## disassembly

```asm
0x140015cf4  lea     rcx, [rdx+0D0h]; this
0x140015cfb  jmp     ??1StringArrayList@@QEAA@XZ; StringArrayList::~StringArrayList(void)
```
