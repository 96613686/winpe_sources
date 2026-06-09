# DllGetClassObject

- ea: `0x180028350`
- end: `0x1800283c1`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180026378`
- `0x180028350`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180028399`
- `RPCRT4!NdrDllGetClassObject` at `0x180028399`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  struct ATL::_ATL_COM_MODULE70 *v8; // rcx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result )
    return ATL::AtlComModuleGetClassObject(v8, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x180028350  mov     [rsp+arg_0], rbx
0x180028355  mov     [rsp+arg_8], rsi
0x18002835a  push    rdi
0x18002835b  sub     rsp, 30h
0x18002835f  mov     rax, cs:aProxyFileList
0x180028366  mov     rbx, r8
0x180028369  mov     rdi, rdx
0x18002836c  mov     rsi, rcx
0x18002836f  mov     r9, [rax+8]
0x180028373  mov     rax, [r9]
0x180028376  test    rax, rax
0x180028379  jz      short loc_18002837E
0x18002837b  mov     rax, [rax]
0x18002837e  lea     rcx, gPFactory
0x180028385  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x18002838a  lea     r9, aProxyFileList; pProxyFileList
0x180028391  mov     rcx, rsi; rclsid
0x180028394  mov     [rsp+38h+pclsid], rax; pclsid
0x180028399  call    cs:__imp_NdrDllGetClassObject
0x18002839f  test    eax, eax
0x1800283a1  jz      short loc_1800283B1
0x1800283a3  mov     r9, rbx; void **
0x1800283a6  mov     r8, rdi; struct _GUID *
0x1800283a9  mov     rdx, rsi; struct _GUID *
0x1800283ac  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800283b1  mov     rbx, [rsp+38h+arg_0]
0x1800283b6  mov     rsi, [rsp+38h+arg_8]
0x1800283bb  add     rsp, 30h
0x1800283bf  pop     rdi
0x1800283c0  retn
```
