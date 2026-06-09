# _Cabinet::CreateCabSelected_::_1_::dtor$1

- ea: `0x180014090`
- end: `0x18001409c`
- name: `_Cabinet::CreateCabSelected_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800083c8`

## pseudocode

```c
void __fastcall Cabinet::CreateCabSelected_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CabContext::~CabContext((CabContext *)(a2 + 448));
}

```

## disassembly

```asm
0x180014090  lea     rcx, [rdx+1C0h]; this
0x180014097  jmp     ??1CabContext@@UEAA@XZ; CabContext::~CabContext(void)
```
