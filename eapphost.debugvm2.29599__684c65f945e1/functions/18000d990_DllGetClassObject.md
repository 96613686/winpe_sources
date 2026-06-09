# DllGetClassObject

- ea: `0x18000d990`
- end: `0x18000d9ec`
- name: `DllGetClassObject`
- size: `92`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000d990`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000d9ca`
- `RPCRT4!NdrDllGetClassObject` at `0x18000d9ca`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result < 0 && ppv )
  {
    if ( *ppv )
      *ppv = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000d990  push    rbx
0x18000d992  sub     rsp, 30h
0x18000d996  mov     rax, cs:aProxyFileList
0x18000d99d  mov     rbx, r8
0x18000d9a0  mov     r9, [rax+8]
0x18000d9a4  mov     rax, [r9]
0x18000d9a7  test    rax, rax
0x18000d9aa  jz      short loc_18000D9AF
0x18000d9ac  mov     rax, [rax]
0x18000d9af  lea     r8, gPFactory
0x18000d9b6  mov     [rsp+38h+pPSFactoryBuffer], r8; pPSFactoryBuffer
0x18000d9bb  lea     r9, aProxyFileList; pProxyFileList
0x18000d9c2  mov     r8, rbx; ppv
0x18000d9c5  mov     [rsp+38h+pclsid], rax; pclsid
0x18000d9ca  call    cs:__imp_NdrDllGetClassObject
0x18000d9d0  test    eax, eax
0x18000d9d2  jns     short loc_18000D9E6
0x18000d9d4  test    rbx, rbx
0x18000d9d7  jz      short loc_18000D9E6
0x18000d9d9  cmp     qword ptr [rbx], 0
0x18000d9dd  jz      short loc_18000D9E6
0x18000d9df  mov     qword ptr [rbx], 0
0x18000d9e6  add     rsp, 30h
0x18000d9ea  pop     rbx
0x18000d9eb  retn
```
