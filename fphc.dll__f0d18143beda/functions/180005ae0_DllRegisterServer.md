# DllRegisterServer

- ea: `0x180005ae0`
- end: `0x180005bdb`
- name: `DllRegisterServer`
- size: `251`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000399c`
- `0x180003e64`
- `0x180005620`
- `0x180005ae0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180005ae9`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180005ae9`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180005af6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180005bca`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180005af6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180005bca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  unsigned int v1; // edx
  ATL::CAtlModule *v2; // rcx
  const unsigned __int16 *v3; // rdx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v5; // rdi
  __int64 *i; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v7; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v8; // rax
  _QWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v11; // [rsp+30h] [rbp-38h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v10[0] = L"APPID";
  v10[1] = L"{33AD1F2B-0DE9-429e-8529-F1FC7CAE52D0}";
  v11 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v10);
  if ( updated >= 0 )
  {
    v5 = off_18001C710;
    for ( i = off_18001C718; v5 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v5 )
    {
      v7 = *v5;
      if ( *v5 )
      {
        updated = (*((__int64 (__fastcall **)(__int64))v7 + 1))(1);
        if ( updated < 0 )
          goto LABEL_9;
        v8 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v7 + 7))();
        updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v7, v8, 1);
        if ( updated < 0 )
          goto LABEL_9;
        i = off_18001C718;
      }
    }
    updated = ATL::AtlRegisterTypeLib(off_18001C708, v3);
LABEL_9:
    if ( updated >= 0 && ATL::_pPerfRegFunc )
      updated = ATL::_pPerfRegFunc(hInstance);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180005ae0  push    rbx
0x180005ae2  push    rbp
0x180005ae3  push    rsi
0x180005ae4  push    rdi
0x180005ae5  sub     rsp, 48h
0x180005ae9  call    cs:__imp_GetThreadLocale
0x180005aef  mov     ebp, eax
0x180005af1  mov     ecx, 800h; Locale
0x180005af6  call    cs:__imp_SetThreadLocale
0x180005afc  lea     rax, aAppid_0; "APPID"
0x180005b03  mov     [rsp+68h+var_48], rax
0x180005b08  lea     rax, a33ad1f2b0de942; "{33AD1F2B-0DE9-429e-8529-F1FC7CAE52D0}"
0x180005b0f  mov     [rsp+68h+var_40], rax
0x180005b14  xorps   xmm0, xmm0
0x180005b17  movdqu  [rsp+68h+var_38], xmm0
0x180005b1d  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180005b22  mov     r8d, 1; int
0x180005b28  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180005b2d  mov     ebx, eax
0x180005b2f  test    eax, eax
0x180005b31  js      loc_180005BC8
0x180005b37  xor     ebx, ebx
0x180005b39  mov     rdi, cs:off_18001C710
0x180005b40  mov     rax, cs:off_18001C718
0x180005b47  cmp     rdi, rax
0x180005b4a  jnb     short loc_180005B9C
0x180005b4c  mov     rsi, [rdi]
0x180005b4f  test    rsi, rsi
0x180005b52  jz      short loc_180005B8F
0x180005b54  mov     ecx, 1
0x180005b59  mov     rax, [rsi+8]
0x180005b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b62  mov     ebx, eax
0x180005b64  test    eax, eax
0x180005b66  js      short loc_180005BAA
0x180005b68  mov     rax, [rsi+38h]
0x180005b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b71  mov     r8d, 1; int
0x180005b77  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005b7a  mov     rcx, [rsi]; rguid
0x180005b7d  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005b82  mov     ebx, eax
0x180005b84  test    eax, eax
0x180005b86  js      short loc_180005BAA
0x180005b88  mov     rax, cs:off_18001C718
0x180005b8f  add     rdi, 8
0x180005b93  cmp     rdi, rax
0x180005b96  jb      short loc_180005B4C
0x180005b98  test    ebx, ebx
0x180005b9a  js      short loc_180005BC8
0x180005b9c  mov     rcx, cs:off_18001C708; HINSTANCE
0x180005ba3  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180005ba8  mov     ebx, eax
0x180005baa  test    ebx, ebx
0x180005bac  js      short loc_180005BC8
0x180005bae  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180005bb5  test    rax, rax
0x180005bb8  jz      short loc_180005BC8
0x180005bba  mov     rcx, cs:hInstance
0x180005bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc6  mov     ebx, eax
0x180005bc8  mov     ecx, ebp; Locale
0x180005bca  call    cs:__imp_SetThreadLocale
0x180005bd0  mov     eax, ebx
0x180005bd2  add     rsp, 48h
0x180005bd6  pop     rdi
0x180005bd7  pop     rsi
0x180005bd8  pop     rbp
0x180005bd9  pop     rbx
0x180005bda  retn
```
