# ATL::CComPtr<ATL::CComObject<MapsBackgroundTransferClassFactory>>::~CComPtr<ATL::CComObject<MapsBackgroundTransferClassFactory>>(void)

- ea: `0x1800033c8`
- end: `0x1800033cd`
- name: `??1?$CComPtr@V?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013bc6`

## callees

- `0x1800033f8`

## pseudocode

```c
// attributes: thunk
__int64 ATL::CComPtr<ATL::CComObject<MapsBackgroundTransferClassFactory>>::~CComPtr<ATL::CComObject<MapsBackgroundTransferClassFactory>>()
{
  return ATL::CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>::~CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>();
}

```

## disassembly

```asm
0x1800033c8  jmp     ??1?$CComPtrBase@V?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>::~CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>(void)
```
