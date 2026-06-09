# DllUnregisterServer

- ea: `0x180005f70`
- end: `0x180006008`
- name: `DllUnregisterServer`
- size: `152`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005824`
- `0x18000596c`
- `0x180005f70`
- `0x18000f010`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x180005f8d`
- `KERNEL32!SetThreadLocale` at `0x180005fee`
- `KERNEL32!SetThreadLocale` at `0x180005f8d`
- `KERNEL32!SetThreadLocale` at `0x180005fee`
- `KERNEL32!GetThreadLocale` at `0x180005f7a`
- `KERNEL32!GetThreadLocale` at `0x180005f7a`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  const unsigned __int16 *v1; // rdx
  GUID *v2; // rcx
  struct ITypeLib *v3; // r8
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
    v6[1] = L"{6f3282b6-2b50-42b7-af7a-aae69d14a6ca}";
    v7 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(
                (ATL::CAtlModule *)v2,
                (__int64)v1,
                0,
                (struct ATL::_ATL_REGMAP_ENTRY *)v6);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180005f70  mov     [rsp+arg_0], rbx
0x180005f75  push    rdi
0x180005f76  sub     rsp, 40h
0x180005f7a  call    cs:__imp_GetThreadLocale
0x180005f81  nop     dword ptr [rax+rax+00h]
0x180005f86  mov     edi, eax
0x180005f88  mov     ecx, 800h; Locale
0x180005f8d  call    cs:__imp_SetThreadLocale
0x180005f94  nop     dword ptr [rax+rax+00h]
0x180005f99  nop
0x180005f9a  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180005fa1  test    rax, rax
0x180005fa4  jz      short loc_180005FB1
0x180005fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fab  mov     ebx, eax
0x180005fad  test    eax, eax
0x180005faf  js      short loc_180005FB8
0x180005fb1  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x180005fb6  mov     ebx, eax
0x180005fb8  test    ebx, ebx
0x180005fba  js      short loc_180005FEC
0x180005fbc  lea     rax, aAppid_0; "APPID"
0x180005fc3  mov     [rsp+48h+var_28], rax
0x180005fc8  lea     rax, a6f3282b62b5042; "{6f3282b6-2b50-42b7-af7a-aae69d14a6ca}"
0x180005fcf  mov     [rsp+48h+var_20], rax
0x180005fd4  xorps   xmm0, xmm0
0x180005fd7  movdqu  [rsp+48h+var_18], xmm0
0x180005fdd  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x180005fe2  xor     r8d, r8d; int
0x180005fe5  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180005fea  mov     ebx, eax
0x180005fec  mov     ecx, edi; Locale
0x180005fee  call    cs:__imp_SetThreadLocale
0x180005ff5  nop     dword ptr [rax+rax+00h]
0x180005ffa  mov     eax, ebx
0x180005ffc  mov     rbx, [rsp+48h+arg_0]
0x180006001  add     rsp, 40h
0x180006005  pop     rdi
0x180006006  retn
```
