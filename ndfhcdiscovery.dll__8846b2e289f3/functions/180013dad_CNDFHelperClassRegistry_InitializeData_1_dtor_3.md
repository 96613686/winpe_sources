# _CNDFHelperClassRegistry::InitializeData_::_1_::dtor$3

- ea: `0x180013dad`
- end: `0x180013db9`
- name: `_CNDFHelperClassRegistry::InitializeData_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180005884`

## pseudocode

```c
void __fastcall CNDFHelperClassRegistry::InitializeData_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 96));
}

```

## disassembly

```asm
0x180013dad  lea     rcx, [rdx+60h]; this
0x180013db4  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
