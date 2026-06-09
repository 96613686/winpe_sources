# DllGetClassObject

- ea: `0x180006b70`
- end: `0x180006be7`
- name: `DllGetClassObject`
- size: `119`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006b70`
- `0x180006bf0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180006bb9`
- `RPCRT4!NdrDllGetClassObject` at `0x180006bb9`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  struct ATL::_ATL_COM_MODULE70 *v7; // rcx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  if ( NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory) )
    return ATL::AtlComModuleGetClassObject(v7, rclsid, riid, ppv);
  else
    return 0;
}

```

## disassembly

```asm
0x180006b70  mov     [rsp+arg_0], rbx
0x180006b75  mov     [rsp+arg_8], rsi
0x180006b7a  push    rdi
0x180006b7b  sub     rsp, 30h
0x180006b7f  mov     rax, cs:aProxyFileList
0x180006b86  mov     rbx, r8
0x180006b89  mov     rdi, rdx
0x180006b8c  mov     rsi, rcx
0x180006b8f  mov     r9, [rax+8]
0x180006b93  mov     rax, [r9]
0x180006b96  test    rax, rax
0x180006b99  jz      short loc_180006BE5
0x180006b9b  mov     rax, [rax]
0x180006b9e  lea     rcx, gPFactory
0x180006ba5  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180006baa  lea     r9, aProxyFileList; pProxyFileList
0x180006bb1  mov     rcx, rsi; rclsid
0x180006bb4  mov     [rsp+38h+pclsid], rax; pclsid
0x180006bb9  call    cs:__imp_NdrDllGetClassObject
0x180006bbf  test    eax, eax
0x180006bc1  jz      short loc_180006BE1
0x180006bc3  mov     r9, rbx; void **
0x180006bc6  mov     r8, rdi; struct _GUID *
0x180006bc9  mov     rdx, rsi; struct _GUID *
0x180006bcc  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180006bd1  mov     rbx, [rsp+38h+arg_0]
0x180006bd6  mov     rsi, [rsp+38h+arg_8]
0x180006bdb  add     rsp, 30h
0x180006bdf  pop     rdi
0x180006be0  retn
0x180006be1  xor     eax, eax
0x180006be3  jmp     short loc_180006BD1
0x180006be5  jmp     short loc_180006B9E
```
