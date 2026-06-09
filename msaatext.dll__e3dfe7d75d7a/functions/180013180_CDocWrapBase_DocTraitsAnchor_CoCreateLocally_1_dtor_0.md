# _CDocWrapBase_DocTraitsAnchor_::CoCreateLocally_::_1_::dtor$0

- ea: `0x180013180`
- end: `0x18001318c`
- name: `_CDocWrapBase_DocTraitsAnchor_::CoCreateLocally_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000243c`

## pseudocode

```c
void __fastcall CDocWrapBase_DocTraitsAnchor_::CoCreateLocally_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  TSTR::~TSTR((TSTR *)(a2 + 136));
}

```

## disassembly

```asm
0x180013180  lea     rcx, [rdx+88h]; this
0x180013187  jmp     ??1TSTR@@QEAA@XZ; TSTR::~TSTR(void)
```
