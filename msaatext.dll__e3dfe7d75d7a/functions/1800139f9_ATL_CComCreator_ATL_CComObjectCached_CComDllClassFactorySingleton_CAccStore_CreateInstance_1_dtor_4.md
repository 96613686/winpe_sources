# _ATL::CComCreator_ATL::CComObjectCached_CComDllClassFactorySingleton_CAccStore_____::CreateInstance_::_1_::dtor$4

- ea: `0x1800139f9`
- end: `0x180013a05`
- name: `_ATL::CComCreator_ATL::CComObjectCached_CComDllClassFactorySingleton_CAccStore_____::CreateInstance_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e13c`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObjectCached_CComDllClassFactorySingleton_CAccStore_____::CreateInstance_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  ATL::CComClassFactory::~CComClassFactory(*(ATL::CComClassFactory **)(a2 + 96));
}

```

## disassembly

```asm
0x1800139f9  mov     rcx, [rdx+60h]; this
0x180013a00  jmp     ??1CComClassFactory@ATL@@QEAA@XZ; ATL::CComClassFactory::~CComClassFactory(void)
```
