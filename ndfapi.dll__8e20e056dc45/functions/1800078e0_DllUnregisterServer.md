# DllUnregisterServer

- ea: `0x1800078e0`
- end: `0x180007969`
- name: `DllUnregisterServer`
- size: `137`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180006b24`
- `0x180006c60`
- `0x1800078e0`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x1800078ea`
- `KERNEL32!GetThreadLocale` at `0x1800078ea`
- `KERNEL32!SetThreadLocale` at `0x1800078f7`
- `KERNEL32!SetThreadLocale` at `0x180007956`
- `KERNEL32!SetThreadLocale` at `0x1800078f7`
- `KERNEL32!SetThreadLocale` at `0x180007956`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  int v1; // edx
  ATL::CAtlComModule *v2; // rcx
  const struct _GUID *v3; // r8
  HRESULT updated; // ebx
  _QWORD v6[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (updated = ATL::_pPerfUnRegFunc(), updated >= 0) )
    updated = ATL::CAtlComModule::UnregisterServer(v2, v1, v3);
  if ( updated >= 0 )
  {
    v6[0] = L"APPID";
    v6[1] = L"{F3D3AA8D-EF96-4470-848E-BD70B803047A}";
    v7 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, 0x64u, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v6);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x1800078e0  mov     [rsp+arg_0], rbx
0x1800078e5  push    rdi
0x1800078e6  sub     rsp, 40h
0x1800078ea  call    cs:__imp_GetThreadLocale
0x1800078f0  mov     edi, eax
0x1800078f2  mov     ecx, 800h; Locale
0x1800078f7  call    cs:__imp_SetThreadLocale
0x1800078fd  nop
0x1800078fe  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180007905  test    rax, rax
0x180007908  jz      short loc_180007915
0x18000790a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000790f  mov     ebx, eax
0x180007911  test    eax, eax
0x180007913  js      short loc_18000791C
0x180007915  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x18000791a  mov     ebx, eax
0x18000791c  test    ebx, ebx
0x18000791e  js      short loc_180007954
0x180007920  lea     rax, aAppid_0; "APPID"
0x180007927  mov     [rsp+48h+var_28], rax
0x18000792c  lea     rax, aF3d3aa8dEf9644; "{F3D3AA8D-EF96-4470-848E-BD70B803047A}"
0x180007933  mov     [rsp+48h+var_20], rax
0x180007938  xorps   xmm0, xmm0
0x18000793b  movdqu  [rsp+48h+var_18], xmm0
0x180007941  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x180007946  xor     r8d, r8d; int
0x180007949  lea     edx, [r8+64h]; unsigned int
0x18000794d  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180007952  mov     ebx, eax
0x180007954  mov     ecx, edi; Locale
0x180007956  call    cs:__imp_SetThreadLocale
0x18000795c  mov     eax, ebx
0x18000795e  mov     rbx, [rsp+48h+arg_0]
0x180007963  add     rsp, 40h
0x180007967  pop     rdi
0x180007968  retn
```
