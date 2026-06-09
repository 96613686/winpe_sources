# DllRegisterServer

- ea: `0x1800052b0`
- end: `0x1800053cc`
- name: `DllRegisterServer`
- size: `284`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005100`

## callees

- `0x180003284`
- `0x180004d04`
- `0x1800052b0`
- `0x180011010`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x1800052c6`
- `KERNEL32!SetThreadLocale` at `0x180005386`
- `KERNEL32!SetThreadLocale` at `0x1800052c6`
- `KERNEL32!SetThreadLocale` at `0x180005386`
- `KERNEL32!GetThreadLocale` at `0x1800052b9`
- `KERNEL32!GetThreadLocale` at `0x1800052b9`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800053bd`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800053bd`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  ATL::CAtlModule *v1; // rcx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rdi
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  PCInterfaceStubVtblList v8; // rax
  const CLSID *piid; // r8
  _QWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v11; // [rsp+30h] [rbp-38h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v10[0] = L"APPID";
  v10[1] = L"{37B73D7B-A976-43AE-97E4-BD4977B241F2}";
  v11 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v1, 0x12Eu, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v10);
  if ( updated >= 0 )
  {
    updated = 0;
    v3 = off_1800190E0;
    v4 = (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800190E8;
    while ( v3 < v4 )
    {
      v5 = *v3;
      if ( *v3 )
      {
        updated = (*((__int64 (__fastcall **)(__int64))v5 + 1))(1);
        if ( updated < 0 )
          break;
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v5 + 7))();
        updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 1);
        if ( updated < 0 )
          break;
        v4 = (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800190E8;
      }
      ++v3;
    }
    if ( updated >= 0 && ATL::_pPerfRegFunc )
      updated = ATL::_pPerfRegFunc(hInstance);
  }
  SetThreadLocale(ThreadLocale);
  if ( updated < 0 )
    return updated;
  v8 = *aProxyFileList->pStubVtblList;
  if ( v8 )
    piid = v8->header.piid;
  else
    piid = 0;
  return NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x1800052b0  push    rbx
0x1800052b2  push    rbp
0x1800052b3  push    rsi
0x1800052b4  push    rdi
0x1800052b5  sub     rsp, 48h
0x1800052b9  call    cs:__imp_GetThreadLocale
0x1800052bf  mov     ebp, eax
0x1800052c1  mov     ecx, 800h; Locale
0x1800052c6  call    cs:__imp_SetThreadLocale
0x1800052cc  lea     rax, aAppid; "APPID"
0x1800052d3  mov     [rsp+68h+var_48], rax
0x1800052d8  lea     rax, a37b73d7bA97643; "{37B73D7B-A976-43AE-97E4-BD4977B241F2}"
0x1800052df  mov     [rsp+68h+var_40], rax
0x1800052e4  xorps   xmm0, xmm0
0x1800052e7  movdqu  [rsp+68h+var_38], xmm0
0x1800052ed  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x1800052f2  mov     edx, 12Eh; unsigned int
0x1800052f7  mov     r8d, 1; int
0x1800052fd  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180005302  mov     ebx, eax
0x180005304  test    eax, eax
0x180005306  js      short loc_180005384
0x180005308  xor     ebx, ebx
0x18000530a  mov     rdi, cs:off_1800190E0
0x180005311  mov     rax, cs:off_1800190E8
0x180005318  jmp     short loc_180005361
0x18000531a  mov     rsi, [rdi]
0x18000531d  test    rsi, rsi
0x180005320  jz      short loc_18000535D
0x180005322  mov     ecx, 1
0x180005327  mov     rax, [rsi+8]
0x18000532b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005330  mov     ebx, eax
0x180005332  test    eax, eax
0x180005334  js      short loc_180005366
0x180005336  mov     rax, [rsi+38h]
0x18000533a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000533f  mov     r8d, 1; int
0x180005345  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005348  mov     rcx, [rsi]; rguid
0x18000534b  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005350  mov     ebx, eax
0x180005352  test    eax, eax
0x180005354  js      short loc_180005366
0x180005356  mov     rax, cs:off_1800190E8
0x18000535d  add     rdi, 8
0x180005361  cmp     rdi, rax
0x180005364  jb      short loc_18000531A
0x180005366  test    ebx, ebx
0x180005368  js      short loc_180005384
0x18000536a  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180005371  test    rax, rax
0x180005374  jz      short loc_180005384
0x180005376  mov     rcx, cs:hInstance
0x18000537d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005382  mov     ebx, eax
0x180005384  mov     ecx, ebp; Locale
0x180005386  call    cs:__imp_SetThreadLocale
0x18000538c  test    ebx, ebx
0x18000538e  jns     short loc_180005394
0x180005390  mov     eax, ebx
0x180005392  jmp     short loc_1800053C3
0x180005394  mov     rax, cs:aProxyFileList
0x18000539b  mov     rcx, [rax+8]
0x18000539f  mov     rax, [rcx]
0x1800053a2  test    rax, rax
0x1800053a5  jz      short loc_1800053AC
0x1800053a7  mov     r8, [rax]
0x1800053aa  jmp     short loc_1800053AF
0x1800053ac  xor     r8d, r8d; pclsid
0x1800053af  lea     rdx, aProxyFileList; pProxyFileList
0x1800053b6  mov     rcx, cs:hProxyDll; hDll
0x1800053bd  call    cs:__imp_NdrDllRegisterProxy
0x1800053c3  add     rsp, 48h
0x1800053c7  pop     rdi
0x1800053c8  pop     rsi
0x1800053c9  pop     rbp
0x1800053ca  pop     rbx
0x1800053cb  retn
```
