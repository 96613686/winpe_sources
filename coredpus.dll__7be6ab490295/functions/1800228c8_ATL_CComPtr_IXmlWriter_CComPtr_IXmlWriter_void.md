# ATL::CComPtr<IXmlWriter>::~CComPtr<IXmlWriter>(void)

- ea: `0x1800228c8`
- end: `0x1800228cd`
- name: `??1?$CComPtr@UIXmlWriter@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `28`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e615`
- `0x18002e627`
- `0x18002e65d`
- `0x18002e66f`
- `0x18002f148`
- `0x18002f16c`
- `0x18002f17e`
- `0x18002f1b4`
- `0x18002f2ed`
- `0x18002f33c`
- `0x18002f34e`
- `0x18002f408`
- `0x18002f445`
- `0x18002f4b8`
- `0x18002f4ce`
- `0x18002f4e4`
- `0x18002f4fa`
- `0x18002f538`
- `0x18002f5bd`
- `0x18002f5cf`
- `0x18002f719`
- `0x18002f72b`
- `0x18002f952`
- `0x18002f964`
- `0x18002f976`
- `0x18002fa7a`
- `0x18002fb66`
- `0x18002fb8a`

## callees

- `0x1800110bc`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IXmlWriter>::~CComPtr<IXmlWriter>(__int64 *a1)
{
  return wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a1);
}

```

## disassembly

```asm
0x1800228c8  jmp     ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
```
