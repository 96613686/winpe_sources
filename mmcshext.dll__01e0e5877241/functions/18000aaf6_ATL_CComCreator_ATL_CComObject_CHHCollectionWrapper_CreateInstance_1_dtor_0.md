# _ATL::CComCreator_ATL::CComObject_CHHCollectionWrapper___::CreateInstance_::_1_::dtor$0

- ea: `0x18000aaf6`
- end: `0x18000ab04`
- name: `_ATL::CComCreator_ATL::CComObject_CHHCollectionWrapper___::CreateInstance_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000aafd`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_CHHCollectionWrapper___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x18000aaf6  mov     rcx, [rdx+40h]
0x18000aafd  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
