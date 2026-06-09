# DllRegisterServer

- ea: `0x1800077d0`
- end: `0x1800078ce`
- name: `DllRegisterServer`
- size: `254`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180004fdc`
- `0x1800054a4`
- `0x180006c60`
- `0x1800077d0`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x1800077d9`
- `KERNEL32!GetThreadLocale` at `0x1800077d9`
- `KERNEL32!SetThreadLocale` at `0x1800077e6`
- `KERNEL32!SetThreadLocale` at `0x1800078bd`
- `KERNEL32!SetThreadLocale` at `0x1800077e6`
- `KERNEL32!SetThreadLocale` at `0x1800078bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  ATL::CAtlModule *v1; // rcx
  const unsigned __int16 *v2; // rdx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rdi
  __int64 *i; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v6; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax
  _QWORD v9[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v10; // [rsp+30h] [rbp-38h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v9[0] = L"APPID";
  v9[1] = L"{F3D3AA8D-EF96-4470-848E-BD70B803047A}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v1, 0x64u, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    v4 = off_18002F450;
    for ( i = off_18002F458; v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v4 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        updated = (*((__int64 (__fastcall **)(__int64))v6 + 1))(1);
        if ( updated < 0 )
          goto LABEL_9;
        v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v6 + 7))();
        updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 1);
        if ( updated < 0 )
          goto LABEL_9;
        i = off_18002F458;
      }
    }
    updated = ATL::AtlRegisterTypeLib(off_18002F448, v2);
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
0x1800077d0  push    rbx
0x1800077d2  push    rbp
0x1800077d3  push    rsi
0x1800077d4  push    rdi
0x1800077d5  sub     rsp, 48h
0x1800077d9  call    cs:__imp_GetThreadLocale
0x1800077df  mov     ebp, eax
0x1800077e1  mov     ecx, 800h; Locale
0x1800077e6  call    cs:__imp_SetThreadLocale
0x1800077ec  lea     rax, aAppid_0; "APPID"
0x1800077f3  mov     [rsp+68h+var_48], rax
0x1800077f8  lea     rax, aF3d3aa8dEf9644; "{F3D3AA8D-EF96-4470-848E-BD70B803047A}"
0x1800077ff  mov     [rsp+68h+var_40], rax
0x180007804  xorps   xmm0, xmm0
0x180007807  movdqu  [rsp+68h+var_38], xmm0
0x18000780d  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180007812  mov     edx, 64h ; 'd'; unsigned int
0x180007817  lea     r8d, [rdx-63h]; int
0x18000781b  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180007820  mov     ebx, eax
0x180007822  test    eax, eax
0x180007824  js      loc_1800078BB
0x18000782a  xor     ebx, ebx
0x18000782c  mov     rdi, cs:off_18002F450
0x180007833  mov     rax, cs:off_18002F458
0x18000783a  cmp     rdi, rax
0x18000783d  jnb     short loc_18000788F
0x18000783f  mov     rsi, [rdi]
0x180007842  test    rsi, rsi
0x180007845  jz      short loc_180007882
0x180007847  mov     ecx, 1
0x18000784c  mov     rax, [rsi+8]
0x180007850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007855  mov     ebx, eax
0x180007857  test    eax, eax
0x180007859  js      short loc_18000789D
0x18000785b  mov     rax, [rsi+38h]
0x18000785f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007864  mov     r8d, 1; int
0x18000786a  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000786d  mov     rcx, [rsi]; rguid
0x180007870  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180007875  mov     ebx, eax
0x180007877  test    eax, eax
0x180007879  js      short loc_18000789D
0x18000787b  mov     rax, cs:off_18002F458
0x180007882  add     rdi, 8
0x180007886  cmp     rdi, rax
0x180007889  jb      short loc_18000783F
0x18000788b  test    ebx, ebx
0x18000788d  js      short loc_1800078BB
0x18000788f  mov     rcx, cs:off_18002F448; HINSTANCE
0x180007896  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x18000789b  mov     ebx, eax
0x18000789d  test    ebx, ebx
0x18000789f  js      short loc_1800078BB
0x1800078a1  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x1800078a8  test    rax, rax
0x1800078ab  jz      short loc_1800078BB
0x1800078ad  mov     rcx, cs:hModule
0x1800078b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078b9  mov     ebx, eax
0x1800078bb  mov     ecx, ebp; Locale
0x1800078bd  call    cs:__imp_SetThreadLocale
0x1800078c3  mov     eax, ebx
0x1800078c5  add     rsp, 48h
0x1800078c9  pop     rdi
0x1800078ca  pop     rsi
0x1800078cb  pop     rbp
0x1800078cc  pop     rbx
0x1800078cd  retn
```
