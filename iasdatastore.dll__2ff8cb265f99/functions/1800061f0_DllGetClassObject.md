# DllGetClassObject

- ea: `0x1800061f0`
- end: `0x180006261`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800041ac`
- `0x1800061f0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180006239`
- `RPCRT4!NdrDllGetClassObject` at `0x180006239`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  ATL::CComModule *v8; // rcx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result < 0 )
    return ATL::CComModule::GetClassObject(v8, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x1800061f0  mov     [rsp+arg_0], rbx
0x1800061f5  mov     [rsp+arg_8], rsi
0x1800061fa  push    rdi
0x1800061fb  sub     rsp, 30h
0x1800061ff  mov     rax, cs:aProxyFileList
0x180006206  mov     rbx, r8
0x180006209  mov     rdi, rdx
0x18000620c  mov     rsi, rcx
0x18000620f  mov     r9, [rax+8]
0x180006213  mov     rax, [r9]
0x180006216  test    rax, rax
0x180006219  jz      short loc_18000621E
0x18000621b  mov     rax, [rax]
0x18000621e  lea     rcx, gPFactory
0x180006225  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x18000622a  lea     r9, aProxyFileList; pProxyFileList
0x180006231  mov     rcx, rsi; rclsid
0x180006234  mov     [rsp+38h+pclsid], rax; pclsid
0x180006239  call    cs:__imp_NdrDllGetClassObject
0x18000623f  test    eax, eax
0x180006241  jns     short loc_180006251
0x180006243  mov     r9, rbx; void **
0x180006246  mov     r8, rdi; struct _GUID *
0x180006249  mov     rdx, rsi; struct _GUID *
0x18000624c  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x180006251  mov     rbx, [rsp+38h+arg_0]
0x180006256  mov     rsi, [rsp+38h+arg_8]
0x18000625b  add     rsp, 30h
0x18000625f  pop     rdi
0x180006260  retn
```
