# DllGetClassObject

- ea: `0x180009f30`
- end: `0x180009fa1`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000652c`
- `0x180009f30`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180009f79`
- `RPCRT4!NdrDllGetClassObject` at `0x180009f79`

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
0x180009f30  mov     [rsp+arg_0], rbx
0x180009f35  mov     [rsp+arg_8], rsi
0x180009f3a  push    rdi
0x180009f3b  sub     rsp, 30h
0x180009f3f  mov     rax, cs:aProxyFileList
0x180009f46  mov     rbx, r8
0x180009f49  mov     rdi, rdx
0x180009f4c  mov     rsi, rcx
0x180009f4f  mov     r9, [rax+8]
0x180009f53  mov     rax, [r9]
0x180009f56  test    rax, rax
0x180009f59  jz      short loc_180009F5E
0x180009f5b  mov     rax, [rax]
0x180009f5e  lea     rcx, gPFactory
0x180009f65  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180009f6a  lea     r9, aProxyFileList; pProxyFileList
0x180009f71  mov     rcx, rsi; rclsid
0x180009f74  mov     [rsp+38h+pclsid], rax; pclsid
0x180009f79  call    cs:__imp_NdrDllGetClassObject
0x180009f7f  test    eax, eax
0x180009f81  jns     short loc_180009F91
0x180009f83  mov     r9, rbx; void **
0x180009f86  mov     r8, rdi; struct _GUID *
0x180009f89  mov     rdx, rsi; struct _GUID *
0x180009f8c  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x180009f91  mov     rbx, [rsp+38h+arg_0]
0x180009f96  mov     rsi, [rsp+38h+arg_8]
0x180009f9b  add     rsp, 30h
0x180009f9f  pop     rdi
0x180009fa0  retn
```
