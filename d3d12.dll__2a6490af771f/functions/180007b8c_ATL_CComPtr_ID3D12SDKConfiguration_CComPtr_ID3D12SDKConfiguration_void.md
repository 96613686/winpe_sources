# ATL::CComPtr<ID3D12SDKConfiguration>::~CComPtr<ID3D12SDKConfiguration>(void)

- ea: `0x180007b8c`
- end: `0x180007b91`
- name: `??1?$CComPtr@UID3D12SDKConfiguration@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013d11`
- `0x180013f3c`

## callees

- `0x180002988`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<ID3D12SDKConfiguration>::~CComPtr<ID3D12SDKConfiguration>(__int64 *a1)
{
  return ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(a1);
}

```

## disassembly

```asm
0x180007b8c  jmp     ??1?$CComPtrBase@UID3D12CoreModule@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(void)
```
