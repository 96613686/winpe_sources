# ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)

- ea: `0x180007b28`
- end: `0x180007b2d`
- name: `??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `16`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024b2f`
- `0x180024b41`
- `0x180024cc7`
- `0x180024cd9`
- `0x180024ceb`
- `0x180024cfd`
- `0x180024d0f`
- `0x180024d21`
- `0x180024d33`
- `0x180024d45`
- `0x180024d57`
- `0x180024d69`
- `0x180024d7b`
- `0x180024d8d`
- `0x180025592`
- `0x1800255a4`

## callees

- `0x180007b34`

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
0x180007b28  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
