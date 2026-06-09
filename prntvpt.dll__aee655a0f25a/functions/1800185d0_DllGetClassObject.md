# DllGetClassObject

- ea: `0x1800185d0`
- end: `0x18001865d`
- name: `DllGetClassObject`
- size: `141`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b844`
- `0x1800185d0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180018647`
- `RPCRT4!NdrDllGetClassObject` at `0x180018647`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  struct ATL::_ATL_COM_MODULE70 *v7; // rcx
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx

  result = ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, rclsid, riid, ppv);
  if ( result )
  {
    result = ATL::AtlComModuleGetClassObject(v7, rclsid, riid, ppv);
    if ( result )
    {
      pStubVtblList = aProxyFileList->pStubVtblList;
      if ( *pStubVtblList )
        pclsid = **(const CLSID ***)pStubVtblList;
      else
        pclsid = 0;
      return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800185d0  mov     [rsp+arg_0], rbx
0x1800185d5  mov     [rsp+arg_8], rsi
0x1800185da  push    rdi
0x1800185db  sub     rsp, 30h
0x1800185df  mov     rbx, r8
0x1800185e2  mov     r9, r8; void **
0x1800185e5  mov     r8, rdx; struct _GUID *
0x1800185e8  mov     rdi, rdx
0x1800185eb  mov     rdx, rcx; struct _GUID *
0x1800185ee  mov     rsi, rcx
0x1800185f1  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800185f6  test    eax, eax
0x1800185f8  jz      short loc_18001864D
0x1800185fa  mov     r9, rbx; void **
0x1800185fd  mov     r8, rdi; struct _GUID *
0x180018600  mov     rdx, rsi; struct _GUID *
0x180018603  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180018608  test    eax, eax
0x18001860a  jz      short loc_18001864D
0x18001860c  mov     rax, cs:aProxyFileList
0x180018613  mov     rcx, [rax+8]
0x180018617  mov     rax, [rcx]
0x18001861a  test    rax, rax
0x18001861d  jz      short loc_180018624
0x18001861f  mov     rcx, [rax]
0x180018622  jmp     short loc_180018626
0x180018624  xor     ecx, ecx
0x180018626  lea     rax, gPFactory
0x18001862d  mov     r8, rbx; ppv
0x180018630  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180018635  lea     r9, aProxyFileList; pProxyFileList
0x18001863c  mov     [rsp+38h+pclsid], rcx; pclsid
0x180018641  mov     rdx, rdi; riid
0x180018644  mov     rcx, rsi; rclsid
0x180018647  call    cs:__imp_NdrDllGetClassObject
0x18001864d  mov     rbx, [rsp+38h+arg_0]
0x180018652  mov     rsi, [rsp+38h+arg_8]
0x180018657  add     rsp, 30h
0x18001865b  pop     rdi
0x18001865c  retn
```
