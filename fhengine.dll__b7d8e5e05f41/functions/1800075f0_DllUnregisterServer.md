# DllUnregisterServer

- ea: `0x1800075f0`
- end: `0x180007678`
- name: `DllUnregisterServer`
- size: `136`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007510`

## callees

- `0x180006934`
- `0x1800070c4`
- `0x1800075f0`
- `0x180007818`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18000766c`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18000766c`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT v0; // ebx
  HRESULT result; // eax
  PCInterfaceStubVtblList v2; // rax
  const CLSID *piid; // r8

  v0 = ATL::CAtlDllModuleT<CEngineModule>::DllUnregisterServer();
  if ( v0 >= 0 )
  {
    result = PrxDllRegisterServer();
    if ( result >= 0 )
    {
      v2 = *aProxyFileList->pStubVtblList;
      if ( v2 )
        piid = v2->header.piid;
      else
        piid = 0;
      return NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_96e2a10888f0373d27c6534814b7f9a0_Traceguids,
        (unsigned int)v0);
    return v0;
  }
  return result;
}

```

## disassembly

```asm
0x1800075f0  push    rbx
0x1800075f2  sub     rsp, 20h
0x1800075f6  call    ?DllUnregisterServer@?$CAtlDllModuleT@VCEngineModule@@@ATL@@QEAAJH@Z; ATL::CAtlDllModuleT<CEngineModule>::DllUnregisterServer(int)
0x1800075fb  mov     ebx, eax
0x1800075fd  test    eax, eax
0x1800075ff  jns     short loc_18000763A
0x180007601  mov     rcx, cs:WPP_GLOBAL_Control
0x180007608  lea     rax, WPP_GLOBAL_Control
0x18000760f  cmp     rcx, rax
0x180007612  jz      short loc_180007632
0x180007614  test    byte ptr [rcx+1Ch], 2
0x180007618  jz      short loc_180007632
0x18000761a  mov     rcx, [rcx+10h]
0x18000761e  lea     r8, WPP_96e2a10888f0373d27c6534814b7f9a0_Traceguids
0x180007625  mov     edx, 0Dh
0x18000762a  mov     r9d, ebx
0x18000762d  call    WPP_SF_d
0x180007632  mov     eax, ebx
0x180007634  add     rsp, 20h
0x180007638  pop     rbx
0x180007639  retn
0x18000763a  call    PrxDllRegisterServer
0x18000763f  test    eax, eax
0x180007641  js      short loc_180007672
0x180007643  mov     rax, cs:aProxyFileList
0x18000764a  mov     rcx, [rax+8]
0x18000764e  mov     rax, [rcx]
0x180007651  test    rax, rax
0x180007654  jz      short loc_18000765B
0x180007656  mov     r8, [rax]
0x180007659  jmp     short loc_18000765E
0x18000765b  xor     r8d, r8d; pclsid
0x18000765e  mov     rcx, cs:hProxyDll; hDll
0x180007665  lea     rdx, aProxyFileList; pProxyFileList
0x18000766c  call    cs:__imp_NdrDllUnregisterProxy
0x180007672  add     rsp, 20h
0x180007676  pop     rbx
0x180007677  retn
```
