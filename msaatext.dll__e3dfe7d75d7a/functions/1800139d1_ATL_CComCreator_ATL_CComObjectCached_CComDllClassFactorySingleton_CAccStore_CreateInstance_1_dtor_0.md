# _ATL::CComCreator_ATL::CComObjectCached_CComDllClassFactorySingleton_CAccStore_____::CreateInstance_::_1_::dtor$0

- ea: `0x1800139d1`
- end: `0x1800139df`
- name: `_ATL::CComCreator_ATL::CComObjectCached_CComDllClassFactorySingleton_CAccStore_____::CreateInstance_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, loader_planting, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800139d8`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObjectCached_CComDllClassFactorySingleton_CAccStore_____::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 96));
}

```

## disassembly

```asm
0x1800139d1  mov     rcx, [rdx+60h]
0x1800139d8  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
