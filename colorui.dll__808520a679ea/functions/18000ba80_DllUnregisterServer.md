# DllUnregisterServer

- ea: `0x18000ba80`
- end: `0x18000bab0`
- name: `DllUnregisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ba80`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18000baa9`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  return NdrDllUnregisterProxy((HMODULE)hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x18000ba80  mov     rax, cs:aProxyFileList
0x18000ba87  mov     rcx, [rax+8]
0x18000ba8b  mov     rax, [rcx]
0x18000ba8e  test    rax, rax
0x18000ba91  jz      short loc_18000BA98
0x18000ba93  mov     r8, [rax]
0x18000ba96  jmp     short loc_18000BA9B
0x18000ba98  xor     r8d, r8d
0x18000ba9b  mov     rcx, cs:hProxyDll
0x18000baa2  lea     rdx, aProxyFileList
0x18000baa9  jmp     cs:__imp_NdrDllUnregisterProxy
```
