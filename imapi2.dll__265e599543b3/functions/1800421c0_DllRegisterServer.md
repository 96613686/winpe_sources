# DllRegisterServer

- ea: `0x1800421c0`
- end: `0x18004224f`
- name: `DllRegisterServer`
- size: `143`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180010ef0`
- `0x1800140f4`
- `0x18004203c`
- `0x18004217c`
- `0x1800421c0`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x1800421d7`
- `KERNEL32!SetThreadLocale` at `0x1800421f6`
- `KERNEL32!SetThreadLocale` at `0x1800421d7`
- `KERNEL32!SetThreadLocale` at `0x1800421f6`
- `KERNEL32!GetThreadLocale` at `0x1800421ca`
- `KERNEL32!GetThreadLocale` at `0x1800421ca`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // edi
  int updated; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  updated = CImapi2Module::UpdateRegistryAppId(1);
  if ( updated >= 0 )
    updated = ATL::CAtlModuleT<CImapi2Module>::RegisterServer();
  SetThreadLocale(ThreadLocale);
  if ( updated < 0 || (updated = PrxDllRegisterServer(), updated < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        12,
        WPP_4ee8c0ccf5b13ef7721a296dee7fcadd_Traceguids,
        (unsigned int)updated);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800421c0  mov     [rsp+arg_0], rbx
0x1800421c5  push    rdi
0x1800421c6  sub     rsp, 20h
0x1800421ca  call    cs:__imp_GetThreadLocale
0x1800421d0  mov     ecx, 800h; Locale
0x1800421d5  mov     edi, eax
0x1800421d7  call    cs:__imp_SetThreadLocale
0x1800421dd  mov     ecx, 1; int
0x1800421e2  call    ?UpdateRegistryAppId@CImapi2Module@@SAJH@Z; CImapi2Module::UpdateRegistryAppId(int)
0x1800421e7  mov     ebx, eax
0x1800421e9  test    eax, eax
0x1800421eb  js      short loc_1800421F4
0x1800421ed  call    ?RegisterServer@?$CAtlModuleT@VCImapi2Module@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CImapi2Module>::RegisterServer(int,_GUID const *)
0x1800421f2  mov     ebx, eax
0x1800421f4  mov     ecx, edi; Locale
0x1800421f6  call    cs:__imp_SetThreadLocale
0x1800421fc  test    ebx, ebx
0x1800421fe  js      short loc_18004220B
0x180042200  call    PrxDllRegisterServer
0x180042205  mov     ebx, eax
0x180042207  test    eax, eax
0x180042209  jns     short loc_180042242
0x18004220b  mov     rcx, cs:WPP_GLOBAL_Control
0x180042212  lea     rax, WPP_GLOBAL_Control
0x180042219  cmp     rcx, rax
0x18004221c  jz      short loc_180042242
0x18004221e  test    byte ptr [rcx+44h], 1
0x180042222  jz      short loc_180042242
0x180042224  cmp     byte ptr [rcx+41h], 3
0x180042228  jb      short loc_180042242
0x18004222a  mov     rcx, [rcx+38h]
0x18004222e  lea     r8, WPP_4ee8c0ccf5b13ef7721a296dee7fcadd_Traceguids
0x180042235  mov     edx, 0Ch
0x18004223a  mov     r9d, ebx
0x18004223d  call    WPP_SF_d
0x180042242  mov     rbx, [rsp+28h+arg_0]
0x180042247  xor     eax, eax
0x180042249  add     rsp, 20h
0x18004224d  pop     rdi
0x18004224e  retn
```
