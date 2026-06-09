# DllUnregisterServer

- ea: `0x180004b90`
- end: `0x180004be0`
- name: `DllUnregisterServer`
- size: `80`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004b90`

## import_xrefs

- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180004bab`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180004bab`
- `RPCRT4!NdrDllUnregisterProxy` at `0x180004bd9`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  const CLSID *v0; // r8

  UnRegisterTypeLib(&LIBID_FaxUtilityCOMLib, 1u, 0, 0, SYS_WIN32);
  v0 = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( v0 )
    v0 = *(const CLSID **)&v0->Data1;
  return NdrDllUnregisterProxy((HMODULE)hProxyDll, (const ProxyFileInfo **)&aProxyFileList, v0);
}

```

## disassembly

```asm
0x180004b90  sub     rsp, 38h
0x180004b94  xor     r8d, r8d; wVerMinor
0x180004b97  lea     rcx, LIBID_FaxUtilityCOMLib; libID
0x180004b9e  xor     r9d, r9d; lcid
0x180004ba1  lea     eax, [r8+1]
0x180004ba5  mov     edx, eax; wVerMajor
0x180004ba7  mov     [rsp+38h+syskind], eax; syskind
0x180004bab  call    cs:__imp_UnRegisterTypeLib
0x180004bb1  mov     rax, cs:aProxyFileList
0x180004bb8  mov     rcx, [rax+8]
0x180004bbc  mov     r8, [rcx]
0x180004bbf  test    r8, r8
0x180004bc2  jz      short loc_180004BC7
0x180004bc4  mov     r8, [r8]
0x180004bc7  mov     rcx, cs:hProxyDll
0x180004bce  lea     rdx, aProxyFileList
0x180004bd5  add     rsp, 38h
0x180004bd9  jmp     cs:__imp_NdrDllUnregisterProxy
```
