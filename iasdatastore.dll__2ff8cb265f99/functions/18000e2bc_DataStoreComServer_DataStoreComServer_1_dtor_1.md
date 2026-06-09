# _DataStoreComServer::DataStoreComServer_::_1_::dtor$1

- ea: `0x18000e2bc`
- end: `0x18000e2cc`
- name: `_DataStoreComServer::DataStoreComServer_::_1_::dtor$1`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006af4`

## pseudocode

```c
void __fastcall DataStoreComServer::DataStoreComServer_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  IASTraceInitializer::~IASTraceInitializer((IASTraceInitializer *)(*(_QWORD *)(a2 + 48) + 65LL));
}

```

## disassembly

```asm
0x18000e2bc  mov     rcx, [rdx+30h]
0x18000e2c3  add     rcx, 41h ; 'A'; this
0x18000e2c7  jmp     ??1IASTraceInitializer@@QEAA@XZ; IASTraceInitializer::~IASTraceInitializer(void)
```
