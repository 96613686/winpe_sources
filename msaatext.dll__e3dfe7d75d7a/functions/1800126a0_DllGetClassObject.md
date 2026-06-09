# DllGetClassObject

- ea: `0x1800126a0`
- end: `0x180012711`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ea10`
- `0x1800126a0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800126e9`
- `RPCRT4!NdrDllGetClassObject` at `0x1800126e9`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  struct ATL::_ATL_MODULE *v8; // rcx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result )
    return ATL::AtlModuleGetClassObject(v8, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x1800126a0  mov     [rsp+arg_0], rbx
0x1800126a5  mov     [rsp+arg_8], rsi
0x1800126aa  push    rdi
0x1800126ab  sub     rsp, 30h
0x1800126af  mov     rax, cs:aProxyFileList
0x1800126b6  mov     rbx, r8
0x1800126b9  mov     rdi, rdx
0x1800126bc  mov     rsi, rcx
0x1800126bf  mov     r9, [rax+8]
0x1800126c3  mov     rax, [r9]
0x1800126c6  test    rax, rax
0x1800126c9  jz      short loc_1800126CE
0x1800126cb  mov     rax, [rax]
0x1800126ce  lea     rcx, gPFactory
0x1800126d5  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x1800126da  lea     r9, aProxyFileList; pProxyFileList
0x1800126e1  mov     rcx, rsi; rclsid
0x1800126e4  mov     [rsp+38h+pclsid], rax; pclsid
0x1800126e9  call    cs:__imp_NdrDllGetClassObject
0x1800126ef  test    eax, eax
0x1800126f1  jz      short loc_180012701
0x1800126f3  mov     r9, rbx; void **
0x1800126f6  mov     r8, rdi; struct _GUID *
0x1800126f9  mov     rdx, rsi; struct _GUID *
0x1800126fc  call    ?AtlModuleGetClassObject@ATL@@YAJPEAU_ATL_MODULE@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlModuleGetClassObject(ATL::_ATL_MODULE *,_GUID const &,_GUID const &,void * *)
0x180012701  mov     rbx, [rsp+38h+arg_0]
0x180012706  mov     rsi, [rsp+38h+arg_8]
0x18001270b  add     rsp, 30h
0x18001270f  pop     rdi
0x180012710  retn
```
