# DllGetClassObject

- ea: `0x180004400`
- end: `0x180004471`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800041d4`
- `0x180004400`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180004449`
- `RPCRT4!NdrDllGetClassObject` at `0x180004449`

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
  if ( result < 0 )
    return ATL::CAtlDllModuleT<CATLdtshModule>::DllGetClassObject(v8, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x180004400  mov     [rsp+arg_0], rbx
0x180004405  mov     [rsp+arg_8], rsi
0x18000440a  push    rdi
0x18000440b  sub     rsp, 30h
0x18000440f  mov     rax, cs:aProxyFileList
0x180004416  mov     rbx, r8
0x180004419  mov     rdi, rdx
0x18000441c  mov     rsi, rcx
0x18000441f  mov     r9, [rax+8]
0x180004423  mov     rax, [r9]
0x180004426  test    rax, rax
0x180004429  jz      short loc_18000442E
0x18000442b  mov     rax, [rax]
0x18000442e  lea     rcx, gPFactory
0x180004435  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x18000443a  lea     r9, aProxyFileList; pProxyFileList
0x180004441  mov     rcx, rsi; rclsid
0x180004444  mov     [rsp+38h+pclsid], rax; pclsid
0x180004449  call    cs:__imp_NdrDllGetClassObject
0x18000444f  test    eax, eax
0x180004451  jns     short loc_180004461
0x180004453  mov     r9, rbx
0x180004456  mov     r8, rdi
0x180004459  mov     rdx, rsi
0x18000445c  call    ?DllGetClassObject@?$CAtlDllModuleT@VCATLdtshModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CAtlDllModuleT<CATLdtshModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x180004461  mov     rbx, [rsp+38h+arg_0]
0x180004466  mov     rsi, [rsp+38h+arg_8]
0x18000446b  add     rsp, 30h
0x18000446f  pop     rdi
0x180004470  retn
```
