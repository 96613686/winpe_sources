# DllGetClassObject

- ea: `0x180017990`
- end: `0x180017a0b`
- name: `DllGetClassObject`
- size: `123`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800152bc`
- `0x180017990`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800179f5`
- `RPCRT4!NdrDllGetClassObject` at `0x1800179f5`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  const PCInterfaceStubVtblList *pStubVtblList; // r9
  const CLSID *pclsid; // rcx

  result = ATL::CComModule::GetClassObject((ATL::CComModule *)rclsid, rclsid, riid, ppv);
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
0x180017990  mov     [rsp+arg_0], rbx
0x180017995  mov     [rsp+arg_8], rsi
0x18001799a  push    rdi
0x18001799b  sub     rsp, 30h
0x18001799f  mov     rbx, r8
0x1800179a2  mov     r9, r8; void **
0x1800179a5  mov     r8, rdx; struct _GUID *
0x1800179a8  mov     rdi, rdx
0x1800179ab  mov     rdx, rcx; struct _GUID *
0x1800179ae  mov     rsi, rcx
0x1800179b1  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x1800179b6  test    eax, eax
0x1800179b8  jns     short loc_1800179FB
0x1800179ba  mov     rax, cs:aProxyFileList
0x1800179c1  mov     r9, [rax+8]
0x1800179c5  mov     rax, [r9]
0x1800179c8  test    rax, rax
0x1800179cb  jz      short loc_1800179D2
0x1800179cd  mov     rcx, [rax]
0x1800179d0  jmp     short loc_1800179D4
0x1800179d2  xor     ecx, ecx
0x1800179d4  lea     rax, gPFactory
0x1800179db  mov     r8, rbx; ppv
0x1800179de  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800179e3  lea     r9, aProxyFileList; pProxyFileList
0x1800179ea  mov     [rsp+38h+pclsid], rcx; pclsid
0x1800179ef  mov     rdx, rdi; riid
0x1800179f2  mov     rcx, rsi; rclsid
0x1800179f5  call    cs:__imp_NdrDllGetClassObject
0x1800179fb  mov     rbx, [rsp+38h+arg_0]
0x180017a00  mov     rsi, [rsp+38h+arg_8]
0x180017a05  add     rsp, 30h
0x180017a09  pop     rdi
0x180017a0a  retn
```
