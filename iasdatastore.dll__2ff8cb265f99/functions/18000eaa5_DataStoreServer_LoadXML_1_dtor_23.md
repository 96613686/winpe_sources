# _DataStoreServer::LoadXML_::_1_::dtor$23

- ea: `0x18000eaa5`
- end: `0x18000eab1`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$23`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x180002360`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_23(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 112));
}

```

## disassembly

```asm
0x18000eaa5  mov     rcx, [rdx+70h]; Block
0x18000eaac  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
