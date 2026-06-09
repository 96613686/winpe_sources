# DllGetClassObject

- ea: `0x180005080`
- end: `0x1800050f1`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003930`
- `0x180005080`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800050c9`
- `RPCRT4!NdrDllGetClassObject` at `0x1800050c9`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  __int64 v8; // rcx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result )
    return ATL::CAtlDllModuleT<CPortableWorkspaceLauncherModule>::DllGetClassObject(v8, rclsid, (__int64)riid, ppv);
  return result;
}

```

## disassembly

```asm
0x180005080  mov     [rsp+arg_0], rbx
0x180005085  mov     [rsp+arg_8], rsi
0x18000508a  push    rdi
0x18000508b  sub     rsp, 30h
0x18000508f  mov     rax, cs:aProxyFileList
0x180005096  mov     rbx, r8
0x180005099  mov     rdi, rdx
0x18000509c  mov     rsi, rcx
0x18000509f  mov     r9, [rax+8]
0x1800050a3  mov     rax, [r9]
0x1800050a6  test    rax, rax
0x1800050a9  jz      short loc_1800050AE
0x1800050ab  mov     rax, [rax]
0x1800050ae  lea     rcx, gPFactory
0x1800050b5  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x1800050ba  lea     r9, aProxyFileList; pProxyFileList
0x1800050c1  mov     rcx, rsi; rclsid
0x1800050c4  mov     [rsp+38h+pclsid], rax; pclsid
0x1800050c9  call    cs:__imp_NdrDllGetClassObject
0x1800050cf  test    eax, eax
0x1800050d1  jz      short loc_1800050E1
0x1800050d3  mov     r9, rbx
0x1800050d6  mov     r8, rdi
0x1800050d9  mov     rdx, rsi
0x1800050dc  call    ?DllGetClassObject@?$CAtlDllModuleT@VCPortableWorkspaceLauncherModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CAtlDllModuleT<CPortableWorkspaceLauncherModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x1800050e1  mov     rbx, [rsp+38h+arg_0]
0x1800050e6  mov     rsi, [rsp+38h+arg_8]
0x1800050eb  add     rsp, 30h
0x1800050ef  pop     rdi
0x1800050f0  retn
```
