# _ATL::CComCreator_ATL::CComObject_CNDFHelperClassRegistry___::CreateInstance_::_1_::dtor$0

- ea: `0x180013d26`
- end: `0x180013d34`
- name: `_ATL::CComCreator_ATL::CComObject_CNDFHelperClassRegistry___::CreateInstance_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013d2d`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_CNDFHelperClassRegistry___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x180013d26  mov     rcx, [rdx+20h]
0x180013d2d  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
