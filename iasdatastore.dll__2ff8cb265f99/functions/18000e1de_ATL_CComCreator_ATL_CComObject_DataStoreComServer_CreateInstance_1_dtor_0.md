# _ATL::CComCreator_ATL::CComObject_DataStoreComServer___::CreateInstance_::_1_::dtor$0

- ea: `0x18000e1de`
- end: `0x18000e1ea`
- name: `_ATL::CComCreator_ATL::CComObject_DataStoreComServer___::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002360`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_DataStoreComServer___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x18000e1de  mov     rcx, [rdx+20h]; Block
0x18000e1e5  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
