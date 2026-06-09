# _ATL::CComCreator_ATL::CComObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor$0

- ea: `0x180009ed8`
- end: `0x180009ee6`
- name: `_ATL::CComCreator_ATL::CComObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009edf`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 104));
}

```

## disassembly

```asm
0x180009ed8  mov     rcx, [rdx+68h]
0x180009edf  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
