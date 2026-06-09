# _ATL::CComCreator2_ATL::CComCreator_ATL::CComObject_CAccStore____ATL::CComCreator_ATL::CComAggObject_CAccStore_____::CreateInstance_::_1_::dtor$3

- ea: `0x1800139bd`
- end: `0x1800139cb`
- name: `_ATL::CComCreator2_ATL::CComCreator_ATL::CComObject_CAccStore____ATL::CComCreator_ATL::CComAggObject_CAccStore_____::CreateInstance_::_1_::dtor$3`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800139c4`

## pseudocode

```c
void __fastcall ATL::CComCreator2_ATL::CComCreator_ATL::CComObject_CAccStore____ATL::CComCreator_ATL::CComAggObject_CAccStore_____::CreateInstance_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x1800139bd  mov     rcx, [rdx+50h]
0x1800139c4  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
