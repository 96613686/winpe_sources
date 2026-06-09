# ATL::CComObjectCached<DataStoreComServer>::~CComObjectCached<DataStoreComServer>(void)

- ea: `0x1800021b4`
- end: `0x1800021ca`
- name: `??1?$CComObjectCached@VDataStoreComServer@@@ATL@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003ad0`

## callees

- `0x1800068dc`

## pseudocode

```c
void __fastcall ATL::CComObjectCached<DataStoreComServer>::~CComObjectCached<DataStoreComServer>(
        DataStoreComServer *a1)
{
  *((_DWORD *)a1 + 2) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObjectCached<DataStoreComServer>::`vftable';
  DataStoreComServer::~DataStoreComServer(a1);
}

```

## disassembly

```asm
0x1800021b4  lea     rax, ??_7?$CComObjectCached@VDataStoreComServer@@@ATL@@6B@; const ATL::CComObjectCached<DataStoreComServer>::`vftable'
0x1800021bb  mov     dword ptr [rcx+8], 0C0000001h
0x1800021c2  mov     [rcx], rax
0x1800021c5  jmp     ??1DataStoreComServer@@QEAA@XZ; DataStoreComServer::~DataStoreComServer(void)
```
