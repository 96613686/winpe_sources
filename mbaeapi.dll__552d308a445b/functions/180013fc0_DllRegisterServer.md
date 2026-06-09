# DllRegisterServer

- ea: `0x180013fc0`
- end: `0x1800140d5`
- name: `DllRegisterServer`
- size: `277`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000e5a0`
- `0x18000ea68`
- `0x180013fc0`
- `0x180014410`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180013fc9`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180013fc9`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180013fd6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180014070`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180013fd6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180014070`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800140a3`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800140a3`

## string_xrefs

- `0x1800140b7`: `DllRegisterServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  const unsigned __int16 *v1; // rdx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rdi
  __int64 *i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rsi
  HRESULT v5; // ebx
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  PCInterfaceStubVtblList v7; // rax
  const CLSID *piid; // r8
  unsigned int v9; // eax
  __int64 v10; // rcx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v2 = off_180084400;
  for ( i = off_180084408; v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v2 )
  {
    v4 = *v2;
    if ( *v2 )
    {
      v5 = (*((__int64 (__fastcall **)(__int64))v4 + 1))(1);
      if ( v5 < 0 )
        goto LABEL_8;
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v4 + 7))();
      v5 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v6, 1);
      if ( v5 < 0 )
        goto LABEL_8;
      i = off_180084408;
    }
  }
  v5 = ATL::AtlRegisterTypeLib(off_1800843F8, v1);
LABEL_8:
  if ( v5 >= 0 && ATL::_pPerfRegFunc )
    v5 = ATL::_pPerfRegFunc(hModule);
  SetThreadLocale(ThreadLocale);
  if ( v5 >= 0 )
  {
    v7 = *aProxyFileList->pStubVtblList;
    if ( v7 )
      piid = v7->header.piid;
    else
      piid = 0;
    v9 = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
    v5 = v9;
    if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
      McTemplateU0sd_EventWriteTransfer(v10, mbaeapi_cpp149, "DllRegisterServer", v9);
  }
  return v5;
}

```

## disassembly

```asm
0x180013fc0  push    rbx
0x180013fc2  push    rbp
0x180013fc3  push    rsi
0x180013fc4  push    rdi
0x180013fc5  sub     rsp, 28h
0x180013fc9  call    cs:__imp_GetThreadLocale
0x180013fcf  mov     ebp, eax
0x180013fd1  mov     ecx, 800h; Locale
0x180013fd6  call    cs:__imp_SetThreadLocale
0x180013fdc  nop
0x180013fdd  xor     ebx, ebx
0x180013fdf  mov     rdi, cs:off_180084400
0x180013fe6  mov     rcx, cs:off_180084408
0x180013fed  cmp     rdi, rcx
0x180013ff0  jnb     short loc_180014042
0x180013ff2  mov     rsi, [rdi]
0x180013ff5  test    rsi, rsi
0x180013ff8  jz      short loc_180014035
0x180013ffa  mov     ecx, 1
0x180013fff  mov     rax, [rsi+8]
0x180014003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014008  mov     ebx, eax
0x18001400a  test    eax, eax
0x18001400c  js      short loc_180014050
0x18001400e  mov     rax, [rsi+38h]
0x180014012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014017  mov     r8d, 1; int
0x18001401d  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180014020  mov     rcx, [rsi]; rguid
0x180014023  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180014028  mov     ebx, eax
0x18001402a  test    eax, eax
0x18001402c  js      short loc_180014050
0x18001402e  mov     rcx, cs:off_180084408
0x180014035  add     rdi, 8
0x180014039  cmp     rdi, rcx
0x18001403c  jb      short loc_180013FF2
0x18001403e  test    ebx, ebx
0x180014040  js      short loc_18001406E
0x180014042  mov     rcx, cs:off_1800843F8; HINSTANCE
0x180014049  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x18001404e  mov     ebx, eax
0x180014050  test    ebx, ebx
0x180014052  js      short loc_18001406E
0x180014054  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18001405b  test    rax, rax
0x18001405e  jz      short loc_18001406E
0x180014060  mov     rcx, cs:hModule
0x180014067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001406c  mov     ebx, eax
0x18001406e  mov     ecx, ebp; Locale
0x180014070  call    cs:__imp_SetThreadLocale
0x180014076  test    ebx, ebx
0x180014078  js      short loc_1800140CA
0x18001407a  mov     rax, cs:aProxyFileList
0x180014081  mov     rcx, [rax+8]
0x180014085  mov     rax, [rcx]
0x180014088  test    rax, rax
0x18001408b  jz      short loc_180014092
0x18001408d  mov     r8, [rax]
0x180014090  jmp     short loc_180014095
0x180014092  xor     r8d, r8d; pclsid
0x180014095  lea     rdx, aProxyFileList; pProxyFileList
0x18001409c  mov     rcx, cs:hProxyDll; hDll
0x1800140a3  call    cs:__imp_NdrDllRegisterProxy
0x1800140a9  mov     ebx, eax
0x1800140ab  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x1800140b2  jz      short loc_1800140CA
0x1800140b4  mov     r9d, eax
0x1800140b7  lea     r8, aDllregisterser_0; "DllRegisterServer"
0x1800140be  lea     rdx, mbaeapi_cpp149
0x1800140c5  call    McTemplateU0sd_EventWriteTransfer
0x1800140ca  mov     eax, ebx
0x1800140cc  add     rsp, 28h
0x1800140d0  pop     rdi
0x1800140d1  pop     rsi
0x1800140d2  pop     rbp
0x1800140d3  pop     rbx
0x1800140d4  retn
```
