# ATL::CComPtr<IXMLDOMElement>::~CComPtr<IXMLDOMElement>(void)

- ea: `0x18000d0dc`
- end: `0x18000d0e1`
- name: `??1?$CComPtr@UIXMLDOMElement@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `18`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030392`
- `0x1800304b4`
- `0x1800305b5`
- `0x18003156e`
- `0x180031580`
- `0x180031592`
- `0x1800315a4`
- `0x180031606`
- `0x18003163c`
- `0x1800318df`
- `0x1800318f1`
- `0x18003196c`
- `0x18003197e`
- `0x180031e43`
- `0x180031e79`
- `0x180031f96`
- `0x180031fba`
- `0x180031ff0`

## callees

- `0x18000d0e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IXMLDOMElement>::~CComPtr<IXMLDOMElement>(__int64 a1)
{
  return ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(a1);
}

```

## disassembly

```asm
0x18000d0dc  jmp     ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
```
