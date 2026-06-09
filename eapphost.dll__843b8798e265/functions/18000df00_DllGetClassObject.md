# DllGetClassObject

- ea: `0x18000df00`
- end: `0x18000df63`
- name: `DllGetClassObject`
- size: `99`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000df00`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000df3a`
- `RPCRT4!NdrDllGetClassObject` at `0x18000df3a`

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
0x18000df00  push    rbx
0x18000df02  sub     rsp, 30h
0x18000df06  mov     rax, cs:aProxyFileList
0x18000df0d  mov     rbx, r8
0x18000df10  mov     r9, [rax+8]
0x18000df14  mov     rax, [r9]
0x18000df17  test    rax, rax
0x18000df1a  jz      short loc_18000DF1F
0x18000df1c  mov     rax, [rax]
0x18000df1f  lea     r8, gPFactory
0x18000df26  mov     [rsp+38h+pPSFactoryBuffer], r8; pPSFactoryBuffer
0x18000df2b  lea     r9, aProxyFileList; pProxyFileList
0x18000df32  mov     r8, rbx; ppv
0x18000df35  mov     [rsp+38h+pclsid], rax; pclsid
0x18000df3a  call    cs:__imp_NdrDllGetClassObject
0x18000df41  nop     dword ptr [rax+rax+00h]
0x18000df46  test    eax, eax
0x18000df48  jns     short loc_18000DF5C
0x18000df4a  test    rbx, rbx
0x18000df4d  jz      short loc_18000DF5C
0x18000df4f  cmp     qword ptr [rbx], 0
0x18000df53  jz      short loc_18000DF5C
0x18000df55  mov     qword ptr [rbx], 0
0x18000df5c  add     rsp, 30h
0x18000df60  pop     rbx
0x18000df61  retn
```
