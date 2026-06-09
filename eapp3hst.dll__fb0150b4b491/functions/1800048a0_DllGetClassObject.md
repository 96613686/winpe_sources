# DllGetClassObject

- ea: `0x1800048a0`
- end: `0x180004927`
- name: `DllGetClassObject`
- size: `135`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800048a0`
- `0x18000f960`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800048e9`
- `RPCRT4!NdrDllGetClassObject` at `0x1800048e9`

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
  if ( result < 0 )
  {
    result = ATL::AtlComModuleGetClassObject(v8, rclsid, riid, ppv);
    if ( result < 0 )
    {
      if ( ppv )
      {
        if ( *ppv )
          *ppv = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800048a0  mov     [rsp+arg_0], rbx
0x1800048a5  mov     [rsp+arg_8], rsi
0x1800048aa  push    rdi
0x1800048ab  sub     rsp, 30h
0x1800048af  mov     rax, cs:aProxyFileList
0x1800048b6  mov     rbx, r8
0x1800048b9  mov     rdi, rdx
0x1800048bc  mov     rsi, rcx
0x1800048bf  mov     r9, [rax+8]
0x1800048c3  mov     rax, [r9]
0x1800048c6  test    rax, rax
0x1800048c9  jz      short loc_1800048CE
0x1800048cb  mov     rax, [rax]
0x1800048ce  lea     rcx, gPFactory
0x1800048d5  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x1800048da  lea     r9, aProxyFileList; pProxyFileList
0x1800048e1  mov     rcx, rsi; rclsid
0x1800048e4  mov     [rsp+38h+pclsid], rax; pclsid
0x1800048e9  call    cs:__imp_NdrDllGetClassObject
0x1800048ef  test    eax, eax
0x1800048f1  jns     short loc_180004917
0x1800048f3  mov     r9, rbx; void **
0x1800048f6  mov     r8, rdi; struct _GUID *
0x1800048f9  mov     rdx, rsi; struct _GUID *
0x1800048fc  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180004901  test    eax, eax
0x180004903  jns     short loc_180004917
0x180004905  test    rbx, rbx
0x180004908  jz      short loc_180004917
0x18000490a  cmp     qword ptr [rbx], 0
0x18000490e  jz      short loc_180004917
0x180004910  mov     qword ptr [rbx], 0
0x180004917  mov     rbx, [rsp+38h+arg_0]
0x18000491c  mov     rsi, [rsp+38h+arg_8]
0x180004921  add     rsp, 30h
0x180004925  pop     rdi
0x180004926  retn
```
