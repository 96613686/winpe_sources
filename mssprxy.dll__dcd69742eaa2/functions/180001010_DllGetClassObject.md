# DllGetClassObject

- ea: `0x180001010`
- end: `0x180001052`
- name: `DllGetClassObject`
- size: `66`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180001042`
- `RPCRT4!NdrDllGetClassObject` at `0x180001042`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  PCInterfaceStubVtblList v3; // rax
  const CLSID *pclsid; // r9

  v3 = *aProxyFileList->pStubVtblList;
  if ( v3 )
    pclsid = v3->header.piid;
  else
    pclsid = 0;
  return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 38h
0x180001014  mov     rax, cs:aProxyFileList
0x18000101b  mov     rax, [rax+8]
0x18000101f  mov     rax, [rax]
0x180001022  test    rax, rax
0x180001025  jz      short loc_18000104D
0x180001027  mov     r9, [rax]
0x18000102a  lea     rax, gPFactory
0x180001031  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180001036  mov     [rsp+38h+pclsid], r9; pclsid
0x18000103b  lea     r9, aProxyFileList; pProxyFileList
0x180001042  call    cs:__imp_NdrDllGetClassObject
0x180001048  add     rsp, 38h
0x18000104c  retn
0x18000104d  xor     r9d, r9d
0x180001050  jmp     short loc_18000102A
```
