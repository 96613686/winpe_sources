# DllRegisterServer

- ea: `0x180012d20`
- end: `0x180012e35`
- name: `DllRegisterServer`
- size: `277`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180009c78`
- `0x180012560`
- `0x180012d20`
- `0x180015010`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x180012d3c`
- `KERNEL32!SetThreadLocale` at `0x180012e04`
- `KERNEL32!SetThreadLocale` at `0x180012d3c`
- `KERNEL32!SetThreadLocale` at `0x180012e04`
- `KERNEL32!GetThreadLocale` at `0x180012d29`
- `KERNEL32!GetThreadLocale` at `0x180012d29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  unsigned int v1; // edx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v3; // rdi
  __int64 *v4; // rax
  __int64 v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  unsigned int v7; // edx
  _QWORD v9[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v10; // [rsp+30h] [rbp-38h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v9[0] = L"APPID";
  v9[1] = L"{51AF64B1-E07B-4e5c-AB58-D08A9F58E33B}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(ATL::_pAtlModule, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    updated = 0;
    v3 = off_18001D150;
    v4 = (__int64 *)off_18001D158;
    while ( v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v4 )
    {
      v5 = *(_QWORD *)v3;
      if ( *(_QWORD *)v3 )
      {
        updated = (*(__int64 (__fastcall **)(__int64))(v5 + 8))(1);
        if ( updated < 0 )
          break;
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
        updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 1);
        if ( updated < 0 )
          break;
        v4 = (__int64 *)off_18001D158;
      }
      v3 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v3 + 8);
    }
    if ( updated >= 0 && ATL::_pPerfRegFunc )
      updated = ATL::_pPerfRegFunc(hInstance);
  }
  SetThreadLocale(ThreadLocale);
  if ( updated >= 0 )
    return ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_AtlModule, v7, 1, 0);
  return updated;
}

```

## disassembly

```asm
0x180012d20  push    rbx
0x180012d22  push    rbp
0x180012d23  push    rsi
0x180012d24  push    rdi
0x180012d25  sub     rsp, 48h
0x180012d29  call    cs:__imp_GetThreadLocale
0x180012d30  nop     dword ptr [rax+rax+00h]
0x180012d35  mov     ebp, eax
0x180012d37  mov     ecx, 800h; Locale
0x180012d3c  call    cs:__imp_SetThreadLocale
0x180012d43  nop     dword ptr [rax+rax+00h]
0x180012d48  lea     rax, aAppid; "APPID"
0x180012d4f  mov     [rsp+68h+var_48], rax
0x180012d54  lea     rax, a51af64b1E07b4e; "{51AF64B1-E07B-4e5c-AB58-D08A9F58E33B}"
0x180012d5b  mov     [rsp+68h+var_40], rax
0x180012d60  xorps   xmm0, xmm0
0x180012d63  movdqu  [rsp+68h+var_38], xmm0
0x180012d69  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180012d6e  mov     r8d, 1; int
0x180012d74  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; this
0x180012d7b  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180012d80  mov     ebx, eax
0x180012d82  test    eax, eax
0x180012d84  js      short loc_180012E02
0x180012d86  xor     ebx, ebx
0x180012d88  mov     rdi, cs:off_18001D150
0x180012d8f  mov     rax, cs:off_18001D158
0x180012d96  jmp     short loc_180012DDF
0x180012d98  mov     rsi, [rdi]
0x180012d9b  test    rsi, rsi
0x180012d9e  jz      short loc_180012DDB
0x180012da0  mov     ecx, 1
0x180012da5  mov     rax, [rsi+8]
0x180012da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dae  mov     ebx, eax
0x180012db0  test    eax, eax
0x180012db2  js      short loc_180012DE4
0x180012db4  mov     rax, [rsi+38h]
0x180012db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dbd  mov     r8d, 1; int
0x180012dc3  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180012dc6  mov     rcx, [rsi]; rguid
0x180012dc9  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180012dce  mov     ebx, eax
0x180012dd0  test    eax, eax
0x180012dd2  js      short loc_180012DE4
0x180012dd4  mov     rax, cs:off_18001D158
0x180012ddb  add     rdi, 8
0x180012ddf  cmp     rdi, rax
0x180012de2  jb      short loc_180012D98
0x180012de4  test    ebx, ebx
0x180012de6  js      short loc_180012E02
0x180012de8  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180012def  test    rax, rax
0x180012df2  jz      short loc_180012E02
0x180012df4  mov     rcx, cs:hInstance
0x180012dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e00  mov     ebx, eax
0x180012e02  mov     ecx, ebp; Locale
0x180012e04  call    cs:__imp_SetThreadLocale
0x180012e0b  nop     dword ptr [rax+rax+00h]
0x180012e10  test    ebx, ebx
0x180012e12  js      short loc_180012E29
0x180012e14  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180012e17  lea     r8d, [r9+1]; int
0x180012e1b  lea     rcx, ?_AtlModule@@3VNDFHCDiscModule@@A; this
0x180012e22  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180012e27  mov     ebx, eax
0x180012e29  mov     eax, ebx
0x180012e2b  add     rsp, 48h
0x180012e2f  pop     rdi
0x180012e30  pop     rsi
0x180012e31  pop     rbp
0x180012e32  pop     rbx
0x180012e33  retn
```
