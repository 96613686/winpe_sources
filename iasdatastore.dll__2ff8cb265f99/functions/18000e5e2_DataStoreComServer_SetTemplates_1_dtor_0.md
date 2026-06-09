# _DataStoreComServer::SetTemplates_::_1_::dtor$0

- ea: `0x18000e5e2`
- end: `0x18000e5ee`
- name: `_DataStoreComServer::SetTemplates_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800068c8`

## pseudocode

```c
void __fastcall DataStoreComServer::SetTemplates_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CDataStoreLock::~CDataStoreLock((CDataStoreLock *)(a2 + 112));
}

```

## disassembly

```asm
0x18000e5e2  lea     rcx, [rdx+70h]; this
0x18000e5e9  jmp     ??1CDataStoreLock@@QEAA@XZ; CDataStoreLock::~CDataStoreLock(void)
```
