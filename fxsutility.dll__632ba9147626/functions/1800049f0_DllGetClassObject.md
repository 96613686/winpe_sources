# DllGetClassObject

- ea: `0x1800049f0`
- end: `0x180004a6b`
- name: `DllGetClassObject`
- size: `123`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002890`
- `0x1800049f0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180004a55`
- `RPCRT4!NdrDllGetClassObject` at `0x180004a55`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  const PCInterfaceStubVtblList *pStubVtblList; // r9
  const CLSID *pclsid; // rcx

  result = ATL::AtlModuleGetClassObject((struct ATL::_ATL_MODULE *)rclsid, rclsid, riid, ppv);
  if ( result < 0 )
  {
    pStubVtblList = aProxyFileList->pStubVtblList;
    if ( *pStubVtblList )
      pclsid = **(const CLSID ***)pStubVtblList;
    else
      pclsid = 0;
    return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  }
  return result;
}

```

## disassembly

```asm
0x1800049f0  mov     [rsp+arg_0], rbx
0x1800049f5  mov     [rsp+arg_8], rsi
0x1800049fa  push    rdi
0x1800049fb  sub     rsp, 30h
0x1800049ff  mov     rbx, r8
0x180004a02  mov     r9, r8; void **
0x180004a05  mov     r8, rdx; struct _GUID *
0x180004a08  mov     rdi, rdx
0x180004a0b  mov     rdx, rcx; struct _GUID *
0x180004a0e  mov     rsi, rcx
0x180004a11  call    ?AtlModuleGetClassObject@ATL@@YAJPEAU_ATL_MODULE@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlModuleGetClassObject(ATL::_ATL_MODULE *,_GUID const &,_GUID const &,void * *)
0x180004a16  test    eax, eax
0x180004a18  jns     short loc_180004A5B
0x180004a1a  mov     rax, cs:aProxyFileList
0x180004a21  mov     r9, [rax+8]
0x180004a25  mov     rax, [r9]
0x180004a28  test    rax, rax
0x180004a2b  jz      short loc_180004A32
0x180004a2d  mov     rcx, [rax]
0x180004a30  jmp     short loc_180004A34
0x180004a32  xor     ecx, ecx
0x180004a34  lea     rax, gPFactory
0x180004a3b  mov     r8, rbx; ppv
0x180004a3e  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180004a43  lea     r9, aProxyFileList; pProxyFileList
0x180004a4a  mov     [rsp+38h+pclsid], rcx; pclsid
0x180004a4f  mov     rdx, rdi; riid
0x180004a52  mov     rcx, rsi; rclsid
0x180004a55  call    cs:__imp_NdrDllGetClassObject
0x180004a5b  mov     rbx, [rsp+38h+arg_0]
0x180004a60  mov     rsi, [rsp+38h+arg_8]
0x180004a65  add     rsp, 30h
0x180004a69  pop     rdi
0x180004a6a  retn
```
