# DllGetClassObject

- ea: `0x180001e50`
- end: `0x180001e8d`
- name: `DllGetClassObject`
- size: `61`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001e50`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180001e82`
- `RPCRT4!NdrDllGetClassObject` at `0x180001e82`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
}

```

## disassembly

```asm
0x180001e50  sub     rsp, 38h
0x180001e54  mov     rax, cs:aProxyFileList
0x180001e5b  mov     r9, [rax+8]
0x180001e5f  mov     rax, [r9]
0x180001e62  test    rax, rax
0x180001e65  jz      short loc_180001E6A
0x180001e67  mov     rax, [rax]
0x180001e6a  lea     r9, gPFactory
0x180001e71  mov     [rsp+38h+pPSFactoryBuffer], r9; pPSFactoryBuffer
0x180001e76  lea     r9, aProxyFileList; pProxyFileList
0x180001e7d  mov     [rsp+38h+pclsid], rax; pclsid
0x180001e82  call    cs:__imp_NdrDllGetClassObject
0x180001e88  add     rsp, 38h
0x180001e8c  retn
```
