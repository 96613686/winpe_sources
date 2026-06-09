# DllGetClassObject

- ea: `0x180007490`
- end: `0x180007501`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006a30`
- `0x180007490`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800074d9`
- `RPCRT4!NdrDllGetClassObject` at `0x1800074d9`

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
0x180007490  mov     [rsp+arg_0], rbx
0x180007495  mov     [rsp+arg_8], rsi
0x18000749a  push    rdi
0x18000749b  sub     rsp, 30h
0x18000749f  mov     rax, cs:aProxyFileList
0x1800074a6  mov     rbx, r8
0x1800074a9  mov     rdi, rdx
0x1800074ac  mov     rsi, rcx
0x1800074af  mov     r9, [rax+8]
0x1800074b3  mov     rax, [r9]
0x1800074b6  test    rax, rax
0x1800074b9  jz      short loc_1800074BE
0x1800074bb  mov     rax, [rax]
0x1800074be  lea     rcx, gPFactory
0x1800074c5  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x1800074ca  lea     r9, aProxyFileList; pProxyFileList
0x1800074d1  mov     rcx, rsi; rclsid
0x1800074d4  mov     [rsp+38h+pclsid], rax; pclsid
0x1800074d9  call    cs:__imp_NdrDllGetClassObject
0x1800074df  test    eax, eax
0x1800074e1  jz      short loc_1800074F1
0x1800074e3  mov     r9, rbx; void **
0x1800074e6  mov     r8, rdi; struct _GUID *
0x1800074e9  mov     rdx, rsi; struct _GUID *
0x1800074ec  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800074f1  mov     rbx, [rsp+38h+arg_0]
0x1800074f6  mov     rsi, [rsp+38h+arg_8]
0x1800074fb  add     rsp, 30h
0x1800074ff  pop     rdi
0x180007500  retn
```
