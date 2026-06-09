# DllUnregisterServer

- ea: `0x1800053e0`
- end: `0x180005520`
- name: `DllUnregisterServer`
- size: `320`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005100`

## callees

- `0x180003284`
- `0x180004d04`
- `0x1800053e0`
- `0x180011010`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x1800053f6`
- `KERNEL32!SetThreadLocale` at `0x1800054a7`
- `KERNEL32!SetThreadLocale` at `0x1800053f6`
- `KERNEL32!SetThreadLocale` at `0x1800054a7`
- `KERNEL32!GetThreadLocale` at `0x1800053e9`
- `KERNEL32!GetThreadLocale` at `0x1800053e9`
- `RPCRT4!NdrDllUnregisterProxy` at `0x180005511`
- `RPCRT4!NdrDllUnregisterProxy` at `0x180005511`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800054de`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800054de`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // ebp
  ATL::CAtlModule *v1; // rcx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rdi
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  HRESULT result; // eax
  PCInterfaceStubVtblList v8; // rax
  const CLSID *piid; // r8
  PCInterfaceStubVtblList v10; // rax
  const CLSID *v11; // r8
  _QWORD v12[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v13; // [rsp+30h] [rbp-38h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (updated = ATL::_pPerfUnRegFunc(), updated >= 0) )
  {
    updated = 0;
    v3 = off_1800190E0;
    v4 = (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800190E8;
    while ( v3 < v4 )
    {
      v5 = *v3;
      if ( *v3 )
      {
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v5 + 7))();
        updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
        if ( updated < 0 )
          break;
        updated = (*((__int64 (__fastcall **)(_QWORD))v5 + 1))(0);
        if ( updated < 0 )
          break;
        v4 = (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800190E8;
      }
      ++v3;
    }
  }
  if ( updated >= 0 )
  {
    v12[0] = L"APPID";
    v12[1] = L"{37B73D7B-A976-43AE-97E4-BD4977B241F2}";
    v13 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v1, 0x12Eu, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v12);
  }
  SetThreadLocale(ThreadLocale);
  if ( updated < 0 )
    return updated;
  v8 = *aProxyFileList->pStubVtblList;
  if ( v8 )
    piid = v8->header.piid;
  else
    piid = 0;
  result = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  if ( result >= 0 )
  {
    v10 = *aProxyFileList->pStubVtblList;
    if ( v10 )
      v11 = v10->header.piid;
    else
      v11 = 0;
    return NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800053e0  push    rbx
0x1800053e2  push    rbp
0x1800053e3  push    rsi
0x1800053e4  push    rdi
0x1800053e5  sub     rsp, 48h
0x1800053e9  call    cs:__imp_GetThreadLocale
0x1800053ef  mov     ebp, eax
0x1800053f1  mov     ecx, 800h; Locale
0x1800053f6  call    cs:__imp_SetThreadLocale
0x1800053fc  nop
0x1800053fd  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180005404  test    rax, rax
0x180005407  jz      short loc_180005414
0x180005409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000540e  mov     ebx, eax
0x180005410  test    eax, eax
0x180005412  js      short loc_18000546C
0x180005414  xor     ebx, ebx
0x180005416  mov     rdi, cs:off_1800190E0
0x18000541d  mov     rax, cs:off_1800190E8
0x180005424  jmp     short loc_180005467
0x180005426  mov     rsi, [rdi]
0x180005429  test    rsi, rsi
0x18000542c  jz      short loc_180005463
0x18000542e  mov     rax, [rsi+38h]
0x180005432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005437  xor     r8d, r8d; int
0x18000543a  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000543d  mov     rcx, [rsi]; rguid
0x180005440  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005445  mov     ebx, eax
0x180005447  test    eax, eax
0x180005449  js      short loc_18000546C
0x18000544b  xor     ecx, ecx
0x18000544d  mov     rax, [rsi+8]
0x180005451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005456  mov     ebx, eax
0x180005458  test    eax, eax
0x18000545a  js      short loc_18000546C
0x18000545c  mov     rax, cs:off_1800190E8
0x180005463  add     rdi, 8
0x180005467  cmp     rdi, rax
0x18000546a  jb      short loc_180005426
0x18000546c  test    ebx, ebx
0x18000546e  js      short loc_1800054A5
0x180005470  lea     rax, aAppid; "APPID"
0x180005477  mov     [rsp+68h+var_48], rax
0x18000547c  lea     rax, a37b73d7bA97643; "{37B73D7B-A976-43AE-97E4-BD4977B241F2}"
0x180005483  mov     [rsp+68h+var_40], rax
0x180005488  xorps   xmm0, xmm0
0x18000548b  movdqu  [rsp+68h+var_38], xmm0
0x180005491  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180005496  xor     r8d, r8d; int
0x180005499  mov     edx, 12Eh; unsigned int
0x18000549e  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x1800054a3  mov     ebx, eax
0x1800054a5  mov     ecx, ebp; Locale
0x1800054a7  call    cs:__imp_SetThreadLocale
0x1800054ad  test    ebx, ebx
0x1800054af  jns     short loc_1800054B5
0x1800054b1  mov     eax, ebx
0x1800054b3  jmp     short loc_180005517
0x1800054b5  mov     rax, cs:aProxyFileList
0x1800054bc  mov     rcx, [rax+8]
0x1800054c0  mov     rax, [rcx]
0x1800054c3  test    rax, rax
0x1800054c6  jz      short loc_1800054CD
0x1800054c8  mov     r8, [rax]
0x1800054cb  jmp     short loc_1800054D0
0x1800054cd  xor     r8d, r8d; pclsid
0x1800054d0  lea     rdx, aProxyFileList; pProxyFileList
0x1800054d7  mov     rcx, cs:hProxyDll; hDll
0x1800054de  call    cs:__imp_NdrDllRegisterProxy
0x1800054e4  test    eax, eax
0x1800054e6  js      short loc_180005517
0x1800054e8  mov     rax, cs:aProxyFileList
0x1800054ef  mov     rcx, [rax+8]
0x1800054f3  mov     rax, [rcx]
0x1800054f6  test    rax, rax
0x1800054f9  jz      short loc_180005500
0x1800054fb  mov     r8, [rax]
0x1800054fe  jmp     short loc_180005503
0x180005500  xor     r8d, r8d; pclsid
0x180005503  lea     rdx, aProxyFileList; pProxyFileList
0x18000550a  mov     rcx, cs:hProxyDll; hDll
0x180005511  call    cs:__imp_NdrDllUnregisterProxy
0x180005517  add     rsp, 48h
0x18000551b  pop     rdi
0x18000551c  pop     rsi
0x18000551d  pop     rbp
0x18000551e  pop     rbx
0x18000551f  retn
```
