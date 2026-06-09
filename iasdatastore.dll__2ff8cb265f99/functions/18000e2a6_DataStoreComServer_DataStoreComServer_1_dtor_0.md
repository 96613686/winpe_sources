# _DataStoreComServer::DataStoreComServer_::_1_::dtor$0

- ea: `0x18000e2a6`
- end: `0x18000e2b6`
- name: `_DataStoreComServer::DataStoreComServer_::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800021d0`

## pseudocode

```c
void __fastcall DataStoreComServer::DataStoreComServer_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(*(_QWORD *)(a2 + 48) + 8LL);
}

```

## disassembly

```asm
0x18000e2a6  mov     rcx, [rdx+30h]
0x18000e2ad  add     rcx, 8
0x18000e2b1  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
