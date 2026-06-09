# DllRegisterServer

- ea: `0x180005e50`
- end: `0x180005f5e`
- name: `DllRegisterServer`
- size: `270`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180003a50`
- `0x180003f80`
- `0x18000596c`
- `0x180005e50`
- `0x18000f010`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x180005e6c`
- `KERNEL32!SetThreadLocale` at `0x180005f46`
- `KERNEL32!SetThreadLocale` at `0x180005e6c`
- `KERNEL32!SetThreadLocale` at `0x180005f46`
- `KERNEL32!GetThreadLocale` at `0x180005e59`
- `KERNEL32!GetThreadLocale` at `0x180005e59`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  unsigned int v1; // edx
  ATL::CAtlModule *v2; // rcx
  const unsigned __int16 *v3; // rdx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rdi
  __int64 *v6; // rax
  __int64 v7; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v8; // rax
  _QWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v11; // [rsp+30h] [rbp-38h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v10[0] = L"APPID";
  v10[1] = L"{6f3282b6-2b50-42b7-af7a-aae69d14a6ca}";
  v11 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v10);
  if ( updated >= 0 )
  {
    v5 = off_180017350;
    v6 = (__int64 *)off_180017358;
    if ( off_180017350 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_180017358 )
    {
      do
      {
        v7 = *(_QWORD *)v5;
        if ( *(_QWORD *)v5 )
        {
          updated = (*(__int64 (__fastcall **)(__int64))(v7 + 8))(1);
          if ( updated < 0 )
            goto LABEL_9;
          v8 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v7 + 56))();
          updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v7, v8, 1);
          if ( updated < 0 )
            goto LABEL_9;
          v6 = (__int64 *)off_180017358;
        }
        v5 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v5 + 8);
      }
      while ( v5 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v6 );
    }
    updated = ATL::AtlRegisterTypeLib(off_180017348, v3);
LABEL_9:
    if ( updated >= 0 && ATL::_pPerfRegFunc )
      updated = ATL::_pPerfRegFunc(hModule);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180005e50  push    rbx
0x180005e52  push    rbp
0x180005e53  push    rsi
0x180005e54  push    rdi
0x180005e55  sub     rsp, 48h
0x180005e59  call    cs:__imp_GetThreadLocale
0x180005e60  nop     dword ptr [rax+rax+00h]
0x180005e65  mov     ebp, eax
0x180005e67  mov     ecx, 800h; Locale
0x180005e6c  call    cs:__imp_SetThreadLocale
0x180005e73  nop     dword ptr [rax+rax+00h]
0x180005e78  lea     rax, aAppid_0; "APPID"
0x180005e7f  mov     [rsp+68h+var_48], rax
0x180005e84  lea     rax, a6f3282b62b5042; "{6f3282b6-2b50-42b7-af7a-aae69d14a6ca}"
0x180005e8b  mov     [rsp+68h+var_40], rax
0x180005e90  xorps   xmm0, xmm0
0x180005e93  movdqu  [rsp+68h+var_38], xmm0
0x180005e99  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180005e9e  mov     r8d, 1; int
0x180005ea4  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180005ea9  mov     ebx, eax
0x180005eab  test    eax, eax
0x180005ead  js      loc_180005F44
0x180005eb3  xor     ebx, ebx
0x180005eb5  mov     rdi, cs:off_180017350
0x180005ebc  mov     rax, cs:off_180017358
0x180005ec3  cmp     rdi, rax
0x180005ec6  jnb     short loc_180005F18
0x180005ec8  mov     rsi, [rdi]
0x180005ecb  test    rsi, rsi
0x180005ece  jz      short loc_180005F0B
0x180005ed0  mov     ecx, 1
0x180005ed5  mov     rax, [rsi+8]
0x180005ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ede  mov     ebx, eax
0x180005ee0  test    eax, eax
0x180005ee2  js      short loc_180005F26
0x180005ee4  mov     rax, [rsi+38h]
0x180005ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eed  mov     r8d, 1; int
0x180005ef3  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005ef6  mov     rcx, [rsi]; rguid
0x180005ef9  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005efe  mov     ebx, eax
0x180005f00  test    eax, eax
0x180005f02  js      short loc_180005F26
0x180005f04  mov     rax, cs:off_180017358
0x180005f0b  add     rdi, 8
0x180005f0f  cmp     rdi, rax
0x180005f12  jb      short loc_180005EC8
0x180005f14  test    ebx, ebx
0x180005f16  js      short loc_180005F44
0x180005f18  mov     rcx, cs:off_180017348; HINSTANCE
0x180005f1f  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180005f24  mov     ebx, eax
0x180005f26  test    ebx, ebx
0x180005f28  js      short loc_180005F44
0x180005f2a  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180005f31  test    rax, rax
0x180005f34  jz      short loc_180005F44
0x180005f36  mov     rcx, cs:hModule
0x180005f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f42  mov     ebx, eax
0x180005f44  mov     ecx, ebp; Locale
0x180005f46  call    cs:__imp_SetThreadLocale
0x180005f4d  nop     dword ptr [rax+rax+00h]
0x180005f52  mov     eax, ebx
0x180005f54  add     rsp, 48h
0x180005f58  pop     rdi
0x180005f59  pop     rsi
0x180005f5a  pop     rbp
0x180005f5b  pop     rbx
0x180005f5c  retn
```
