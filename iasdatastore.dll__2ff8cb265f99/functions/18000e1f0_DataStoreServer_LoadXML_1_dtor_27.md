# _DataStoreServer::LoadXML_::_1_::dtor$27

- ea: `0x18000e1f0`
- end: `0x18000e1fc`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$27`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x180002360`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_27(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 104));
}

```

## disassembly

```asm
0x18000e1f0  mov     rcx, [rdx+68h]; Block
0x18000e1f7  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
