# _DataStoreComServer::GetTemplates_::_1_::dtor$0

- ea: `0x18000e2d2`
- end: `0x18000e2de`
- name: `_DataStoreComServer::GetTemplates_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800068c8`

## pseudocode

```c
void __fastcall DataStoreComServer::GetTemplates_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CDataStoreLock::~CDataStoreLock((CDataStoreLock *)(a2 + 96));
}

```

## disassembly

```asm
0x18000e2d2  lea     rcx, [rdx+60h]; this
0x18000e2d9  jmp     ??1CDataStoreLock@@QEAA@XZ; CDataStoreLock::~CDataStoreLock(void)
```
