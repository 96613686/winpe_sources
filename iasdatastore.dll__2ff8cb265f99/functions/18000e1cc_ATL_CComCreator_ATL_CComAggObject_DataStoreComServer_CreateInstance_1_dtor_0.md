# _ATL::CComCreator_ATL::CComAggObject_DataStoreComServer___::CreateInstance_::_1_::dtor$0

- ea: `0x18000e1cc`
- end: `0x18000e1d8`
- name: `_ATL::CComCreator_ATL::CComAggObject_DataStoreComServer___::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002360`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComAggObject_DataStoreComServer___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x18000e1cc  mov     rcx, [rdx+28h]; Block
0x18000e1d3  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
