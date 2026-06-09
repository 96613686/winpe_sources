# _CDocWrapBase_DocTraitsAnchor_::CoCreateLocally_::_1_::dtor$1

- ea: `0x180013192`
- end: `0x18001319e`
- name: `_CDocWrapBase_DocTraitsAnchor_::CoCreateLocally_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000243c`

## pseudocode

```c
void __fastcall CDocWrapBase_DocTraitsAnchor_::CoCreateLocally_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  TSTR::~TSTR((TSTR *)(a2 + 176));
}

```

## disassembly

```asm
0x180013192  lea     rcx, [rdx+0B0h]; this
0x180013199  jmp     ??1TSTR@@QEAA@XZ; TSTR::~TSTR(void)
```
