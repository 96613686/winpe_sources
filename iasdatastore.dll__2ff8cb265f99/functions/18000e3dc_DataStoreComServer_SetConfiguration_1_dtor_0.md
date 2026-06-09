# _DataStoreComServer::SetConfiguration_::_1_::dtor$0

- ea: `0x18000e3dc`
- end: `0x18000e3e8`
- name: `_DataStoreComServer::SetConfiguration_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800068c8`

## pseudocode

```c
void __fastcall DataStoreComServer::SetConfiguration_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CDataStoreLock::~CDataStoreLock((CDataStoreLock *)(a2 + 80));
}

```

## disassembly

```asm
0x18000e3dc  lea     rcx, [rdx+50h]; this
0x18000e3e3  jmp     ??1CDataStoreLock@@QEAA@XZ; CDataStoreLock::~CDataStoreLock(void)
```
