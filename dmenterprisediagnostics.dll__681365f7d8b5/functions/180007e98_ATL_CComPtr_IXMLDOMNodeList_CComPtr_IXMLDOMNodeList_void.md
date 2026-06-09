# ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)

- ea: `0x180007e98`
- end: `0x180007e9d`
- name: `??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800259ef`
- `0x180025a01`
- `0x180025b89`
- `0x180025b9b`
- `0x180025bad`
- `0x180025bbf`
- `0x180025bd1`
- `0x180025be3`
- `0x180025bf5`
- `0x180025c07`
- `0x180025c19`
- `0x180025c2b`
- `0x180025c3d`
- `0x180025c4f`
- `0x18002644b`
- `0x18002645d`

## callees

- `0x180007ea4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(__int64 a1)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1);
}

```

## disassembly

```asm
0x180007e98  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
