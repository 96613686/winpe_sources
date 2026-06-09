# DllUnregisterServer

- ea: `0x180012e40`
- end: `0x180012f40`
- name: `DllUnregisterServer`
- size: `256`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180009c78`
- `0x180012560`
- `0x180012e40`
- `0x180015010`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x180012e62`
- `KERNEL32!SetThreadLocale` at `0x180012f13`
- `KERNEL32!SetThreadLocale` at `0x180012e62`
- `KERNEL32!SetThreadLocale` at `0x180012f13`
- `KERNEL32!GetThreadLocale` at `0x180012e4f`
- `KERNEL32!GetThreadLocale` at `0x180012e4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // esi
  unsigned int v1; // edx
  int v2; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v3; // rbx
  __int64 *v4; // rcx
  __int64 v5; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  unsigned int v7; // edx
  _QWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v10; // [rsp+30h] [rbp-18h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (v2 = ATL::_pPerfUnRegFunc(), v2 >= 0) )
  {
    v2 = 0;
    v3 = off_18001D150;
    v4 = (__int64 *)off_18001D158;
    while ( v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v4 )
    {
      v5 = *(_QWORD *)v3;
      if ( *(_QWORD *)v3 )
      {
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
        v2 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
        if ( v2 < 0 )
          break;
        v2 = (*(__int64 (__fastcall **)(_QWORD))(v5 + 8))(0);
        if ( v2 < 0 )
          break;
        v4 = (__int64 *)off_18001D158;
      }
      v3 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v3 + 8);
    }
  }
  if ( v2 >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{51AF64B1-E07B-4e5c-AB58-D08A9F58E33B}";
    v10 = 0;
    ATL::CAtlModule::UpdateRegistryFromResourceS(ATL::_pAtlModule, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_AtlModule, v7, 0, 0);
}

```

## disassembly

```asm
0x180012e40  mov     [rsp+arg_0], rbx
0x180012e45  mov     [rsp+arg_8], rsi
0x180012e4a  push    rdi
0x180012e4b  sub     rsp, 40h
0x180012e4f  call    cs:__imp_GetThreadLocale
0x180012e56  nop     dword ptr [rax+rax+00h]
0x180012e5b  mov     esi, eax
0x180012e5d  mov     ecx, 800h; Locale
0x180012e62  call    cs:__imp_SetThreadLocale
0x180012e69  nop     dword ptr [rax+rax+00h]
0x180012e6e  nop
0x180012e6f  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180012e76  test    rax, rax
0x180012e79  jz      short loc_180012E84
0x180012e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e80  test    eax, eax
0x180012e82  js      short loc_180012ED8
0x180012e84  xor     eax, eax
0x180012e86  mov     rbx, cs:off_18001D150
0x180012e8d  mov     rcx, cs:off_18001D158
0x180012e94  jmp     short loc_180012ED3
0x180012e96  mov     rdi, [rbx]
0x180012e99  test    rdi, rdi
0x180012e9c  jz      short loc_180012ECF
0x180012e9e  mov     rax, [rdi+38h]
0x180012ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ea7  xor     r8d, r8d; int
0x180012eaa  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180012ead  mov     rcx, [rdi]; rguid
0x180012eb0  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180012eb5  test    eax, eax
0x180012eb7  js      short loc_180012ED8
0x180012eb9  xor     ecx, ecx
0x180012ebb  mov     rax, [rdi+8]
0x180012ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ec4  test    eax, eax
0x180012ec6  js      short loc_180012ED8
0x180012ec8  mov     rcx, cs:off_18001D158
0x180012ecf  add     rbx, 8
0x180012ed3  cmp     rbx, rcx
0x180012ed6  jb      short loc_180012E96
0x180012ed8  test    eax, eax
0x180012eda  js      short loc_180012F11
0x180012edc  lea     rax, aAppid; "APPID"
0x180012ee3  mov     [rsp+48h+var_28], rax
0x180012ee8  lea     rax, a51af64b1E07b4e; "{51AF64B1-E07B-4e5c-AB58-D08A9F58E33B}"
0x180012eef  mov     [rsp+48h+var_20], rax
0x180012ef4  xorps   xmm0, xmm0
0x180012ef7  movdqu  [rsp+48h+var_18], xmm0
0x180012efd  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x180012f02  xor     r8d, r8d; int
0x180012f05  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; this
0x180012f0c  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180012f11  mov     ecx, esi; Locale
0x180012f13  call    cs:__imp_SetThreadLocale
0x180012f1a  nop     dword ptr [rax+rax+00h]
0x180012f1f  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180012f22  xor     r8d, r8d; int
0x180012f25  lea     rcx, ?_AtlModule@@3VNDFHCDiscModule@@A; this
0x180012f2c  mov     rbx, [rsp+48h+arg_0]
0x180012f31  mov     rsi, [rsp+48h+arg_8]
0x180012f36  add     rsp, 40h
0x180012f3a  pop     rdi
0x180012f3b  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
