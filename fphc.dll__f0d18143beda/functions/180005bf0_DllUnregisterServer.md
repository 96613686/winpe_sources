# DllUnregisterServer

- ea: `0x180005bf0`
- end: `0x180005c75`
- name: `DllUnregisterServer`
- size: `133`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800054e4`
- `0x180005620`
- `0x180005bf0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180005bfa`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180005bfa`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180005c07`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180005c62`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180005c07`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180005c62`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  unsigned int v1; // edx
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
    v6[1] = L"{33AD1F2B-0DE9-429e-8529-F1FC7CAE52D0}";
    v7 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v6);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180005bf0  mov     [rsp+arg_0], rbx
0x180005bf5  push    rdi
0x180005bf6  sub     rsp, 40h
0x180005bfa  call    cs:__imp_GetThreadLocale
0x180005c00  mov     edi, eax
0x180005c02  mov     ecx, 800h; Locale
0x180005c07  call    cs:__imp_SetThreadLocale
0x180005c0d  nop
0x180005c0e  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180005c15  test    rax, rax
0x180005c18  jz      short loc_180005C25
0x180005c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c1f  mov     ebx, eax
0x180005c21  test    eax, eax
0x180005c23  js      short loc_180005C2C
0x180005c25  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x180005c2a  mov     ebx, eax
0x180005c2c  test    ebx, ebx
0x180005c2e  js      short loc_180005C60
0x180005c30  lea     rax, aAppid_0; "APPID"
0x180005c37  mov     [rsp+48h+var_28], rax
0x180005c3c  lea     rax, a33ad1f2b0de942; "{33AD1F2B-0DE9-429e-8529-F1FC7CAE52D0}"
0x180005c43  mov     [rsp+48h+var_20], rax
0x180005c48  xorps   xmm0, xmm0
0x180005c4b  movdqu  [rsp+48h+var_18], xmm0
0x180005c51  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x180005c56  xor     r8d, r8d; int
0x180005c59  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180005c5e  mov     ebx, eax
0x180005c60  mov     ecx, edi; Locale
0x180005c62  call    cs:__imp_SetThreadLocale
0x180005c68  mov     eax, ebx
0x180005c6a  mov     rbx, [rsp+48h+arg_0]
0x180005c6f  add     rsp, 40h
0x180005c73  pop     rdi
0x180005c74  retn
```
