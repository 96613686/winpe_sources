# DllRegisterServer

- ea: `0x1800283d0`
- end: `0x18002845f`
- name: `DllRegisterServer`
- size: `143`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800063b8`
- `0x180025864`
- `0x180027758`
- `0x18002800c`
- `0x1800283d0`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x1800283da`
- `KERNEL32!GetThreadLocale` at `0x1800283da`
- `KERNEL32!SetThreadLocale` at `0x1800283e7`
- `KERNEL32!SetThreadLocale` at `0x180028406`
- `KERNEL32!SetThreadLocale` at `0x1800283e7`
- `KERNEL32!SetThreadLocale` at `0x180028406`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // edi
  int updated; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  updated = CFileSystemImagingModule::UpdateRegistryAppId(1);
  if ( updated >= 0 )
    updated = ATL::CAtlModuleT<CFileSystemImagingModule>::RegisterServer();
  SetThreadLocale(ThreadLocale);
  if ( (updated < 0 || (int)PrxDllRegisterServer() < 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_3f8da94856503e18e8b1748b7bc6ee3e_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1800283d0  mov     [rsp+arg_0], rbx
0x1800283d5  push    rdi
0x1800283d6  sub     rsp, 20h
0x1800283da  call    cs:__imp_GetThreadLocale
0x1800283e0  mov     ecx, 800h; Locale
0x1800283e5  mov     edi, eax
0x1800283e7  call    cs:__imp_SetThreadLocale
0x1800283ed  mov     ecx, 1; int
0x1800283f2  call    ?UpdateRegistryAppId@CFileSystemImagingModule@@SAJH@Z; CFileSystemImagingModule::UpdateRegistryAppId(int)
0x1800283f7  mov     ebx, eax
0x1800283f9  test    eax, eax
0x1800283fb  js      short loc_180028404
0x1800283fd  call    ?RegisterServer@?$CAtlModuleT@VCFileSystemImagingModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CFileSystemImagingModule>::RegisterServer(int,_GUID const *)
0x180028402  mov     ebx, eax
0x180028404  mov     ecx, edi; Locale
0x180028406  call    cs:__imp_SetThreadLocale
0x18002840c  test    ebx, ebx
0x18002840e  js      short loc_18002841B
0x180028410  call    PrxDllRegisterServer
0x180028415  mov     ebx, eax
0x180028417  test    eax, eax
0x180028419  jns     short loc_180028452
0x18002841b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028422  lea     rax, WPP_GLOBAL_Control
0x180028429  cmp     rcx, rax
0x18002842c  jz      short loc_180028452
0x18002842e  test    byte ptr [rcx+44h], 4
0x180028432  jz      short loc_180028452
0x180028434  cmp     byte ptr [rcx+41h], 3
0x180028438  jb      short loc_180028452
0x18002843a  mov     rcx, [rcx+38h]
0x18002843e  lea     r8, WPP_3f8da94856503e18e8b1748b7bc6ee3e_Traceguids
0x180028445  mov     edx, 0Dh
0x18002844a  mov     r9d, ebx
0x18002844d  call    WPP_SF_d
0x180028452  mov     rbx, [rsp+28h+arg_0]
0x180028457  xor     eax, eax
0x180028459  add     rsp, 20h
0x18002845d  pop     rdi
0x18002845e  retn
```
