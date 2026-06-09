# _ATL::CRegKey::RecurseDeleteKey_::_1_::dtor$0

- ea: `0x180013a0b`
- end: `0x180013a17`
- name: `_ATL::CRegKey::RecurseDeleteKey_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000e160`

## pseudocode

```c
void __fastcall ATL::CRegKey::RecurseDeleteKey_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 72));
}

```

## disassembly

```asm
0x180013a0b  lea     rcx, [rdx+48h]; this
0x180013a12  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
