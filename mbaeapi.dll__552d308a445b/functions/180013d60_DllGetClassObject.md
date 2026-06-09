# DllGetClassObject

- ea: `0x180013d60`
- end: `0x180013df4`
- name: `DllGetClassObject`
- size: `148`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000fbb4`
- `0x180013d60`
- `0x180014410`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180013da9`
- `RPCRT4!NdrDllGetClassObject` at `0x180013da9`

## string_xrefs

- `0x180013dcf`: `DllGetClassObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  __int64 v8; // rcx
  unsigned int ClassObject; // eax
  __int64 v10; // rcx
  HRESULT v11; // ebx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result )
  {
    ClassObject = ATL::CAtlDllModuleT<CMbaeApiModule>::DllGetClassObject(v8, rclsid, riid, ppv);
    v11 = ClassObject;
    if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
      McTemplateU0sd_EventWriteTransfer(v10, mbaeapi_cpp132, "DllGetClassObject", ClassObject);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180013d60  mov     [rsp+arg_0], rbx
0x180013d65  mov     [rsp+arg_8], rsi
0x180013d6a  push    rdi
0x180013d6b  sub     rsp, 30h
0x180013d6f  mov     rax, cs:aProxyFileList
0x180013d76  mov     rbx, r8
0x180013d79  mov     rdi, rdx
0x180013d7c  mov     rsi, rcx
0x180013d7f  mov     r9, [rax+8]
0x180013d83  mov     rax, [r9]
0x180013d86  test    rax, rax
0x180013d89  jz      short loc_180013D8E
0x180013d8b  mov     rax, [rax]
0x180013d8e  lea     rcx, gPFactory
0x180013d95  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180013d9a  lea     r9, aProxyFileList; pProxyFileList
0x180013da1  mov     rcx, rsi; rclsid
0x180013da4  mov     [rsp+38h+pclsid], rax; pclsid
0x180013da9  call    cs:__imp_NdrDllGetClassObject
0x180013daf  test    eax, eax
0x180013db1  jz      short loc_180013DE4
0x180013db3  mov     r9, rbx
0x180013db6  mov     r8, rdi
0x180013db9  mov     rdx, rsi
0x180013dbc  call    ?DllGetClassObject@?$CAtlDllModuleT@VCMbaeApiModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CAtlDllModuleT<CMbaeApiModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x180013dc1  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x180013dc8  mov     ebx, eax
0x180013dca  jz      short loc_180013DE2
0x180013dcc  mov     r9d, eax
0x180013dcf  lea     r8, aDllgetclassobj_0; "DllGetClassObject"
0x180013dd6  lea     rdx, mbaeapi_cpp132
0x180013ddd  call    McTemplateU0sd_EventWriteTransfer
0x180013de2  mov     eax, ebx
0x180013de4  mov     rbx, [rsp+38h+arg_0]
0x180013de9  mov     rsi, [rsp+38h+arg_8]
0x180013dee  add     rsp, 30h
0x180013df2  pop     rdi
0x180013df3  retn
```
