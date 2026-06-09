# ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(void)

- ea: `0x18000f520`
- end: `0x18000f525`
- name: `??1?$CComPtr@UIXMLDOMNamedNodeMap@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001acbe`
- `0x18001ad40`
- `0x18001ad52`
- `0x18001aec5`
- `0x18001af43`
- `0x18001af55`
- `0x18001af67`

## callees

- `0x180008924`

## pseudocode

```c
// attributes: thunk
__int64 ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>()
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>();
}

```

## disassembly

```asm
0x18000f520  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
