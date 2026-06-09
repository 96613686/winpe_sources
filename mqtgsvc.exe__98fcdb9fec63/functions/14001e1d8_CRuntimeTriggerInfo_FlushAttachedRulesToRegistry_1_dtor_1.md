# _CRuntimeTriggerInfo::FlushAttachedRulesToRegistry_::_1_::dtor$1

- ea: `0x14001e1d8`
- end: `0x14001e1e4`
- name: `_CRuntimeTriggerInfo::FlushAttachedRulesToRegistry_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ce94`

## pseudocode

```c
void __fastcall CRuntimeTriggerInfo::FlushAttachedRulesToRegistry_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CRegHandle::~CRegHandle((HKEY *)(a2 + 136));
}

```

## disassembly

```asm
0x14001e1d8  lea     rcx, [rdx+88h]; this
0x14001e1df  jmp     ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
```
