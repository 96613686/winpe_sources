# _ATL::CComCreator2_ATL::CComCreator_ATL::CComObject_CHHCollectionWrapper____ATL::CComCreator_ATL::CComAggObject_CHHCollectionWrapper_____::CreateInstance_::_1_::dtor$0

- ea: `0x18000aae2`
- end: `0x18000aaf0`
- name: `_ATL::CComCreator2_ATL::CComCreator_ATL::CComObject_CHHCollectionWrapper____ATL::CComCreator_ATL::CComAggObject_CHHCollectionWrapper_____::CreateInstance_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000aae9`

## pseudocode

```c
void __fastcall ATL::CComCreator2_ATL::CComCreator_ATL::CComObject_CHHCollectionWrapper____ATL::CComCreator_ATL::CComAggObject_CHHCollectionWrapper_____::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 96));
}

```

## disassembly

```asm
0x18000aae2  mov     rcx, [rdx+60h]
0x18000aae9  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
