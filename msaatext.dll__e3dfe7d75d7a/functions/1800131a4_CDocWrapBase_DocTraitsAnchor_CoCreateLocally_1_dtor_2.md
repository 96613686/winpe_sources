# _CDocWrapBase_DocTraitsAnchor_::CoCreateLocally_::_1_::dtor$2

- ea: `0x1800131a4`
- end: `0x1800131b0`
- name: `_CDocWrapBase_DocTraitsAnchor_::CoCreateLocally_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000243c`

## pseudocode

```c
void __fastcall CDocWrapBase_DocTraitsAnchor_::CoCreateLocally_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  TSTR::~TSTR((TSTR *)(a2 + 224));
}

```

## disassembly

```asm
0x1800131a4  lea     rcx, [rdx+0E0h]; this
0x1800131ab  jmp     ??1TSTR@@QEAA@XZ; TSTR::~TSTR(void)
```
