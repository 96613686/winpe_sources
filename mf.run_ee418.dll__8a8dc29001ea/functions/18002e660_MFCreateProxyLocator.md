# MFCreateProxyLocator

- ea: `0x18002e660`
- end: `0x18002e667`
- name: `MFCreateProxyLocator`
- size: `7`
- prototype: `HRESULT __stdcall(LPCWSTR pszProtocol, IPropertyStore *pProxyConfig, IMFNetProxyLocator **ppProxyLocator)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `mfnetcore!MFCreateProxyLocator` at `0x18002e660`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall MFCreateProxyLocator(
        LPCWSTR pszProtocol,
        IPropertyStore *pProxyConfig,
        IMFNetProxyLocator **ppProxyLocator)
{
  return MFCreateProxyLocator_0(pszProtocol, pProxyConfig, ppProxyLocator);
}

```

## disassembly

```asm
0x18002e660  jmp     cs:MFCreateProxyLocator_0
```
