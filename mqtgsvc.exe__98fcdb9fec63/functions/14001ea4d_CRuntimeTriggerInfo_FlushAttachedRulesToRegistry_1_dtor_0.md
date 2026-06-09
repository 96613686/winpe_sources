# _CRuntimeTriggerInfo::FlushAttachedRulesToRegistry_::_1_::dtor$0

- ea: `0x14001ea4d`
- end: `0x14001ea59`
- name: `_CRuntimeTriggerInfo::FlushAttachedRulesToRegistry_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ce94`

## pseudocode

```c
void __fastcall CRuntimeTriggerInfo::FlushAttachedRulesToRegistry_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CRegHandle::~CRegHandle((HKEY *)(a2 + 144));
}

```

## disassembly

```asm
0x14001ea4d  lea     rcx, [rdx+90h]; this
0x14001ea54  jmp     ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
```
